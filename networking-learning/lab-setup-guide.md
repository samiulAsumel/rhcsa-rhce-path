# Networking Lab Setup Guide

## Overview

This guide helps you set up a comprehensive networking lab environment for the 90-day Networking Mastery Learning Path. The lab environment will support all the hands-on exercises, from basic network configuration to advanced automation and security scenarios.

## Hardware Requirements

### Minimum Requirements

- **CPU**: 4 cores (8 cores recommended)
- **RAM**: 8GB (16GB recommended)
- **Storage**: 100GB free space (200GB recommended)
- **Network**: Ethernet connection for internet access

### Recommended Setup

- **CPU**: 8+ cores
- **RAM**: 32GB
- **Storage**: 500GB SSD
- **Multiple Network Interfaces**: For advanced networking scenarios

## Software Requirements

### Host System Options

1. **Linux** (Recommended): Ubuntu 20.04+, Fedora 35+, or Arch Linux
2. **Windows**: Windows 10/11 Pro with WSL2
3. **macOS**: macOS 11+ with Virtualization Framework

### Virtualization Software

- **VirtualBox** (Free): Good for beginners
- **VMware Workstation** (Paid): More features, better performance
- **KVM/QEMU** (Linux): Native virtualization, best performance
- **libvirt**: Management layer for KVM

## Lab Network Architecture

### Network Topology

```
Internet
    |
    v
[Host System] - NAT/Host-Only
    |
    v
[Management Network] - 192.168.56.0/24
    |
    +-- [RHEL Server 1] - 192.168.56.10
    +-- [RHEL Server 2] - 192.168.56.11
    +-- [RHEL Server 3] - 192.168.56.12
    +-- [Network Device VM] - 192.168.56.20
    |
    v
[Internal Network] - 10.0.0.0/24
    |
    +-- [Client VM 1] - 10.0.0.10
    +-- [Client VM 2] - 10.0.0.11
    +-- [Service VM] - 10.0.0.20
```

### Network Types

1. **NAT Network**: Internet access for all VMs
2. **Host-Only Network**: Management and communication
3. **Internal Network**: Isolated network for testing
4. **Bridged Network**: Direct physical network access (optional)

## Virtual Machine Setup

### Base RHEL System

- **OS**: RHEL 9.x or CentOS Stream 9
- **Resources**: 2GB RAM, 20GB disk, 2 CPU cores
- **Network**: 2 interfaces (management + internal)

### VM Templates

Create the following VM templates:

#### Server Template (3 VMs)

- **Purpose**: Main network servers
- **Specs**: 2GB RAM, 30GB disk, 2 CPU cores
- **Software**: RHEL 9, basic networking tools

#### Network Device Template (1 VM)

- **Purpose**: Router/firewall/switch simulation
- **Specs**: 1GB RAM, 20GB disk, 1 CPU core
- **Software**: RHEL 9, additional network packages

#### Client Template (2 VMs)

- **Purpose**: Client systems for testing
- **Specs**: 1GB RAM, 15GB disk, 1 CPU core
- **Software**: RHEL 9 or Fedora

## Installation Steps

### Step 1: Install Virtualization Software

#### For Linux (KVM/QEMU)

```bash
# Install required packages
sudo dnf install qemu-kvm libvirt virt-install bridge-utils
sudo dnf install virt-manager virt-viewer

# Start and enable services
sudo systemctl start libvirtd
sudo systemctl enable libvirtd

# Add user to libvirt group
sudo usermod -aG libvirt $(whoami)
```

#### For Windows/Mac (VirtualBox)

1. Download VirtualBox from <https://www.virtualbox.org>
2. Install with default settings
3. Install Extension Pack for additional features

### Step 2: Download RHEL/CentOS

#### Options

1. **RHEL**: Requires subscription (free for development)
2. **CentOS Stream**: Free, RHEL-compatible
3. **Rocky Linux**: Free, RHEL-compatible

#### Download Links

- CentOS Stream: <https://centos.org/download/>
- Rocky Linux: <https://rockylinux.org/download/>
- RHEL Developer: <https://developers.redhat.com/products/rhel/download>

### Step 3: Create Base VM Template

#### VirtualBox Setup

```bash
# Create VM (example commands)
VBoxManage createvm --name "RHEL-Base" --register
VBoxManage modifyvm "RHEL-Base" --memory 2048 --cpus 2
VBoxManage createhd --filename "RHEL-Base.vdi" --size 20000
VBoxManage storagectl "RHEL-Base" --name "SATA" --add sata
VBoxManage storageattach "RHEL-Base" --storagectl "SATA" --port 0 --device 0 --type hdd --medium "RHEL-Base.vdi"
VBoxManage storagectl "RHEL-Base" --name "IDE" --add ide
VBoxManage storageattach "RHEL-Base" --storagectl "IDE" --port 0 --device 0 --type dvddrive --medium "/path/to/rhel.iso"
```

#### KVM Setup

```bash
# Create VM with virt-install
virt-install \
  --name rhel-base \
  --memory 2048 \
  --vcpus 2 \
  --disk size=20 \
  --cdrom /path/to/rhel.iso \
  --network network=default \
  --graphics spice
```

### Step 4: Install RHEL

1. Boot from ISO
2. Follow installation wizard
3. Configure:
   - Language: English
   - Timezone: Your location
   - Root password: Set strong password
   - User: Create student user
   - Network: Enable DHCP for initial setup
4. Complete installation and reboot

### Step 5: Post-Installation Configuration

#### Basic System Setup

```bash
# Update system
sudo dnf update -y

# Install essential packages
sudo dnf install -y vim net-tools tcpdump wireshark-cli
sudo dnf install -y ansible git curl wget
sudo dnf install -y bind-utils traceroute mtr
sudo dnf install -y firewalld selinux-policy-targeted

# Enable services
sudo systemctl enable NetworkManager
sudo systemctl enable firewalld
sudo systemctl start NetworkManager
sudo systemctl start firewalld

# Configure sudo for user
echo "student ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/student
```

#### Network Configuration

```bash
# Configure static IP for management interface
sudo nmcli connection modify "Wired connection 1" \
  ipv4.addresses 192.168.56.10/24 \
  ipv4.gateway 192.168.56.1 \
  ipv4.dns "8.8.8.8,8.8.4.4" \
  ipv4.method manual

# Restart network
sudo nmcli connection down "Wired connection 1"
sudo nmcli connection up "Wired connection 1"
```

### Step 6: Clone VM Templates

#### Clone Commands

```bash
# VirtualBox cloning
VBoxManage clonevm "RHEL-Base" --name "RHEL-Server1" --register
VBoxManage clonevm "RHEL-Base" --name "RHEL-Server2" --register
VBoxManage clonevm "RHEL-Base" --name "RHEL-Server3" --register

# Modify IPs for each clone
# Server1: 192.168.56.10
# Server2: 192.168.56.11
# Server3: 192.168.56.12
```

## Network Configuration

### Management Network Setup

```bash
# On each VM, configure static IP
sudo nmcli connection modify "Wired connection 1" \
  ipv4.addresses 192.168.56.X/24 \
  ipv4.gateway 192.168.56.1 \
  ipv4.dns "192.168.56.1" \
  ipv4.method manual

# Verify connectivity
ping -c 3 192.168.56.1
ping -c 3 google.com
```

### Internal Network Setup

```bash
# Add second interface for internal network
sudo nmcli connection add type ethernet ifname eth1 con-name internal
sudo nmcli connection modify internal \
  ipv4.addresses 10.0.0.X/24 \
  ipv4.method manual

# Test internal connectivity
ping -c 3 10.0.0.1
```

## Lab Environment Verification

### Connectivity Tests

```bash
# Test basic networking
ping -c 3 127.0.0.1
ping -c 3 192.168.56.1
ping -c 3 google.com

# Test DNS resolution
nslookup google.com
dig redhat.com

# Test network tools
ip addr show
ip route show
ss -tulpn
```

### Service Verification

```bash
# Check NetworkManager
systemctl status NetworkManager

# Check firewall
systemctl status firewalld
sudo firewall-cmd --list-all

# Check SELinux
getenforce
sestatus
```

## Optional Enhancements

### Network Simulation Tools

```bash
# Install GNS3 for advanced network simulation
sudo dnf install -y python3-pip
pip3 install gns3-server gns3-gui

# Install EVE-NG (alternative)
# Follow official EVE-NG installation guide
```

### Container Support

```bash
# Install Docker/Podman for container networking
sudo dnf install -y podman docker-compose
sudo systemctl enable docker
sudo systemctl start docker
```

### Cloud Integration

```bash
# Install cloud CLI tools
sudo dnf install -y python3-pip
pip3 install awscli azure-cli gcloud-cli
```

## Troubleshooting

### Common Issues

#### Network Not Working

```bash
# Check NetworkManager status
sudo systemctl status NetworkManager

# Restart network services
sudo systemctl restart NetworkManager
sudo nmcli connection down "Wired connection 1"
sudo nmcli connection up "Wired connection 1"

# Check driver issues
lspci | grep -i network
dmesg | grep -i eth
```

#### Firewall Blocking Traffic

```bash
# Check firewall status
sudo firewall-cmd --state
sudo firewall-cmd --list-all

# Temporarily disable for testing
sudo systemctl stop firewalld

# Re-enable after testing
sudo systemctl start firewalld
```

#### SELinux Issues

```bash
# Check SELinux status
getenforce
sestatus

# Check for denials
sudo ausearch -m avc -ts recent
sudo grep AVC /var/log/audit/audit.log

# Set to permissive for testing
sudo setenforce 0
```

### Performance Issues

```bash
# Check VM resources
free -h
df -h
top

# Optimize VM settings
# - Increase RAM if needed
# - Enable virtualization extensions
# - Use SSD storage
# - Allocate more CPU cores
```

## Backup and Recovery

### VM Backup Strategy

```bash
# VirtualBox snapshots
VBoxManage snapshot "RHEL-Server1" take "Day1-Setup" --description "Initial lab setup"

# KVM/libvirt snapshots
virsh snapshot-create-as --domain rhel-server1 --name "initial-setup" --description "Initial lab setup"
```

### Configuration Backup

```bash
# Backup network configurations
sudo tar -czf network-config-backup.tar.gz /etc/sysconfig/network-scripts/
sudo tar -czf firewall-config-backup.tar.gz /etc/firewalld/

# Document current setup
ip addr show > network-state.txt
ip route show >> network-state.txt
sudo firewall-cmd --list-all >> network-state.txt
```

## Maintenance

### Regular Tasks

1. **Weekly**: Update systems, clean up temporary files
2. **Monthly**: Review configurations, update documentation
3. **Quarterly**: Backup configurations, test restore procedures

### System Updates

```bash
# Update all VMs
sudo dnf update -y

# Check for issues
sudo dnf check
sudo rpm -Va
```

---

## Getting Started Checklist

- [ ] Install virtualization software
- [ ] Download RHEL/CentOS ISO
- [ ] Create base VM template
- [ ] Install and configure base system
- [ ] Clone VMs for lab environment
- [ ] Configure network interfaces
- [ ] Verify connectivity and services
- [ ] Create initial backups
- [ ] Document your setup

Your networking lab is now ready for the 90-day learning journey!
