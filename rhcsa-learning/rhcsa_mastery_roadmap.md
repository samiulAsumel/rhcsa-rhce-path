# RHCSA Mastery Roadmap: Complete Learning Path for Red Hat Certified System Administrator

## 🎯 Overview

This comprehensive 90-day roadmap covers both RHCSA-124 and RHCSA-134 exam objectives, designed to take you from Linux fundamentals to advanced system administration mastery. The path is structured in progressive stages with hands-on labs and real-world scenarios.

## 📋 Course Structure

### **RHCSA-124: Foundation (Days 1-45)**

- Linux fundamentals and command line mastery
- File system management and permissions
- User administration and security basics
- Process management and networking
- System services and troubleshooting

### **RHCSA-134: Advanced (Days 46-90)**

- Advanced scripting and automation
- Storage management and LVM
- Security hardening with SELinux
- Container management
- Performance tuning and optimization

---

## 🗓️ 90-Day Learning Schedule

### **Phase 1: Linux Foundation (Days 1-15)**

#### **Week 1: Getting Started with RHEL (Days 1-7)**

**📚 Topics Covered:**

- Linux fundamentals and RHEL architecture
- Command line access and basic navigation
- Bash shell essentials and command execution

**🎯 Daily Goals:**

- **Day 1:** Linux fundamentals and RHEL introduction
  - Understand Linux vs Unix vs Windows
  - RHEL features and enterprise benefits
  - Open source concepts and GPL
  - Practice: Install RHEL in virtual environment

- **Day 2:** Command line access methods
  - Local terminal access (GNOME Terminal, Konsole)
  - SSH remote access configuration
  - TTY switching (Ctrl+Alt+F1-F6)
  - Practice: Switch between virtual terminals

- **Day 3:** Basic bash commands
  - Navigation: pwd, cd, ls, tree
  - File operations: touch, cp, mv, rm
  - Directory operations: mkdir, rmdir
  - Practice: Create directory structure for projects

- **Day 4:** Command line productivity
  - Command history and shortcuts
  - Tab completion and wildcards
  - Command chaining with ; and &&
  - Practice: Navigate complex directory trees efficiently

- **Day 5:** Getting help and documentation
  - man pages navigation
    --help option usage
  - info pages and whatis command
  - Practice: Explore documentation for key commands

- **Day 6:** Text file operations
  - Viewing files: cat, less, more, head, tail
  - Creating files: echo, printf, cat > file
  - Practice: Create and manipulate configuration files

- **Day 7:** Weekly review and lab
  - Comprehensive command line exercises
  - File system navigation challenges
  - Practice Lab: Complete command line mastery exercises

#### **Week 2: File System Management (Days 8-14)**

**📚 Topics Covered:**

- Linux file system hierarchy
- File operations and permissions
- Links and shell expansions
- Text editing and redirection

**🎯 Daily Goals:**

- **Day 8:** File system hierarchy
  - FHS standard directories (/bin, /etc, /var, /home)
  - System vs user data locations
  - Temporary files and logging directories
  - Practice: Map out complete file system structure

- **Day 9:** Advanced file operations
  - Wildcards and pattern matching
  - Recursive operations with find
  - File metadata and timestamps
  - Practice: Organize files by date and type

- **Day 10:** File permissions and ownership
  - Permission bits (rwx) and octal notation
  - Changing permissions with chmod
  - Ownership management with chown/chgrp
  - Practice: Set up secure file sharing scenarios

- **Day 11:** Hard and symbolic links
  - Understanding inode concepts
  - Creating hard links vs symbolic links
  - Link limitations and use cases
  - Practice: Create linked file structures

- **Day 12:** Shell expansions and globbing
  - Brace expansion {a,b,c}
  - Tilde expansion ~ and ~user
  - Parameter and command substitution
  - Practice: Use expansions for batch operations

- **Day 13:** Text editing with vi/vim
  - Vi modes: command, insert, visual
  - Essential vi commands
  - Search and replace operations
  - Practice: Edit configuration files in vi

- **Day 14:** I/O redirection and pipes
  - Standard streams (stdin, stdout, stderr)
  - Redirection operators >, >>, <, 2>
  - Pipe operations and command chaining
  - Practice Lab: Complete file management challenges

#### **Week 3: Users and Security Basics (Days 15-21)**

**📚 Topics Covered:**

- User and group management
- Superuser access and sudo
- Permission control and security
- Process monitoring and management

**🎯 Daily Goals:**

- **Day 15:** User and group concepts
  - User account types (system, regular, service)
  - Primary vs secondary groups
  - UID/GID numbering schemes
  - Practice: Create user hierarchy for organization

- **Day 16:** User account management
  - Creating users: useradd, adduser
  - Modifying users: usermod
  - Deleting users: userdel
  - Practice: Manage user lifecycle scenarios

- **Day 17:** Group management
  - Creating and managing groups
  - Group membership management
  - Effective groups vs primary groups
  - Practice: Set up project-based group structure

- **Day 18:** Superuser access
  - Direct root login vs sudo
  - Sudo configuration and policies
  - Privilege escalation best practices
  - Practice: Configure sudo for admin tasks

- **Day 19:** Advanced permissions
  - Special permissions (SUID, SGID, sticky bit)
  - Access Control Lists (ACLs)
  - Default permissions with umask
  - Practice: Implement complex permission scenarios

- **Day 20:** Process management basics
  - Process states and lifecycle
  - Listing processes: ps, top, htop
  - Controlling processes: kill, killall
  - Practice: Monitor and manage system processes

- **Day 21:** Job control
  - Foreground/background processes
  - Job control commands (jobs, bg, fg, &)
  - Terminal session management
  - Practice Lab: Complete user management and security exercises

---

### **Phase 2: System Administration (Days 22-45)**

#### **Week 4: System Services and Networking (Days 22-28)**

**📚 Topics Covered:**

- System services and daemons
- Network configuration and management
- SSH configuration and security
- Log analysis and system monitoring

**🎯 Daily Goals:**

- **Day 22:** System services management
  - systemd vs SysV init
  - Service control: systemctl start/stop/restart
  - Service status and logging
  - Practice: Manage essential system services

- **Day 23:** Service configuration
  - Enabling/disabling services
  - Service dependencies and targets
  - Custom service creation
  - Practice: Configure startup services

- **Day 24:** Network fundamentals
  - TCP/IP concepts and addressing
  - Network interfaces and configuration
  - Basic network troubleshooting
  - Practice: Configure network interfaces

- **Day 25:** Network configuration tools
  - nmcli for network management
  - Network configuration files
  - DNS and hostname configuration
  - Practice: Set up complete network configuration

- **Day 26:** SSH configuration
  - OpenSSH server configuration
  - SSH key-based authentication
  - SSH security hardening
  - Practice: Configure secure remote access

- **Day 27:** Log management
  - System logging architecture (rsyslog)
  - Log file locations and rotation
  - Journalctl for systemd logs
  - Practice: Analyze system logs for issues

- **Day 28:** Time synchronization
  - NTP and chrony configuration
  - Time zone management
  - Time synchronization troubleshooting
  - Practice Lab: Complete system services and networking setup

#### **Week 5: Software and Storage (Days 29-35)**

**📚 Topics Covered:**

- Package management with DNF/RPM
- File system management
- Storage devices and mounting
- File system troubleshooting

**🎯 Daily Goals:**

- **Day 29:** Package management basics
  - RPM package format and queries
  - DNF package manager usage
  - Repository configuration
  - Practice: Install and manage software packages

- **Day 30:** Advanced package management
  - Package updates and upgrades
  - Repository management
  - Package troubleshooting
  - Practice: Maintain system software

- **Day 31:** File system concepts
  - Partition types and formats
  - Mount points and fstab
  - File system attributes
  - Practice: Work with different file system types

- **Day 32:** Disk partitioning
  - MBR vs GPT partition schemes
  - fdisk and gdisk partitioning tools
  - Partition management strategies
  - Practice: Create and manage disk partitions

- **Day 33:** File system operations
  - Creating file systems: mkfs
  - Mounting and unmounting
  - Mount options and persistence
  - Practice: Set up complex file system layouts

- **Day 34:** File system maintenance
  - File system checking: fsck
  - Disk space analysis: df, du
  - File system monitoring
  - Practice: Maintain and troubleshoot file systems

- **Day 35:** File location and searching
  - locate command and updatedb
  - find command advanced usage
  - File content searching with grep
  - Practice Lab: Complete software and storage management

#### **Week 6: Advanced Topics and Review (Days 36-45)**

**📚 Topics Covered:**

- File archiving and transfer
- System analysis and troubleshooting
- Red Hat support and tools
- Comprehensive RHCSA-124 review

**🎯 Daily Goals:**

- **Day 36:** File archiving
  - tar command and compression
  - gzip, bzip2, xz compression
  - Archive creation and extraction
  - Practice: Create and manage file archives

- **Day 37:** File transfer
  - Secure copy with scp
  - Synchronized transfer with rsync
  - FTP/SFTP usage
  - Practice: Transfer files between systems

- **Day 38:** System analysis
  - System information gathering
  - Performance monitoring basics
  - Resource utilization analysis
  - Practice: Analyze system health and performance

- **Day 39:** Troubleshooting methodology
  - Systematic troubleshooting approach
  - Common issues and solutions
  - Log analysis techniques
  - Practice: Troubleshoot simulated system issues

- **Day 40:** Red Hat support tools
  - Red Hat Customer Portal usage
  - sosreport for system analysis
  - Red Hat Insights integration
  - Practice: Generate and analyze system reports

- **Day 41-44:** RHCSA-124 Comprehensive Review
  - Day 41: Command line and file systems review
  - Day 42: Users, permissions, and processes review
  - Day 43: Services, networking, and software review
  - Day 44: Storage, logs, and troubleshooting review

- **Day 45:** RHCSA-124 Practice Exam
  - Full practice exam simulation
  - Performance analysis and weak areas
  - Study plan for remaining topics
  - Practice: Complete RHCSA-124 mock exam

---

### **Phase 3: Advanced System Administration (Days 46-75)**

#### **Week 7: Advanced Scripting and Automation (Days 46-52)**

**📚 Topics Covered:**

- Advanced bash scripting
- Regular expressions and text processing
- Task scheduling with cron and at
- System automation techniques

**🎯 Daily Goals:**

- **Day 46:** Bash scripting fundamentals
  - Script structure and shebang
  - Variables and parameter expansion
  - Conditional statements and testing
  - Practice: Write system administration scripts

- **Day 47:** Advanced scripting concepts
  - Loops and arrays
  - Functions and modular scripting
  - Error handling and debugging
  - Practice: Create reusable script modules

- **Day 48:** Regular expressions
  - Regex fundamentals and metacharacters
  - grep advanced usage
  - sed for stream editing
  - Practice: Process text files with regex

- **Day 49:** Advanced text processing
  - awk programming fundamentals
  - Complex text manipulation
  - Data extraction and reporting
  - Practice: Generate system reports with awk

- **Day 50:** Task scheduling
  - at command for one-time tasks
  - crontab syntax and management
  - System cron directories
  - Practice: Schedule automated maintenance tasks

- **Day 51:** System automation
  - Automated backup scripts
  - Log rotation automation
  - System monitoring scripts
  - Practice: Build automation framework

- **Day 52:** Scripting project
  - Comprehensive system administration script
  - Integration with system services
  - Error handling and logging
  - Practice Lab: Complete automation project

#### **Week 8: Advanced Storage Management (Days 53-59)**

**📚 Topics Covered:**

- Logical Volume Management (LVM)
- Advanced file systems
- Network storage (NFS)
- Storage troubleshooting

**🎯 Daily Goals:**

- **Day 53:** LVM concepts
  - Physical volumes, volume groups, logical volumes
  - LVM advantages and use cases
  - LVM architecture and terminology
  - Practice: Plan LVM deployment strategy

- **Day 54:** LVM implementation
  - Creating physical volumes and volume groups
  - Logical volume creation and management
  - LVM monitoring and maintenance
  - Practice: Build complete LVM setup

- **Day 55:** Advanced LVM operations
  - Extending logical volumes
  - LVM snapshots and cloning
  - LVM migration and recovery
  - Practice: Perform advanced LVM operations

- **Day 56:** Swap space management
  - Swap partition and file creation
  - Swap space monitoring
  - Swap performance tuning
  - Practice: Optimize system swap configuration

- **Day 57:** Network File System
  - NFS concepts and architecture
  - NFS server configuration
  - NFS client mounting
  - Practice: Set up NFS file sharing

- **Day 58:** Advanced NFS features
  - NFS security and permissions
  - Automount configuration
  - NFS performance tuning
  - Practice: Configure secure NFS environment

- **Day 59:** Storage troubleshooting
  - LVM corruption recovery
  - File system repair techniques
  - Storage performance analysis
  - Practice Lab: Complete storage management challenges

#### **Week 9: Security Hardening (Days 60-66)**

**📚 Topics Covered:**

- SELinux fundamentals
- Firewall configuration
- System security hardening
- Security monitoring and auditing

**🎯 Daily Goals:**

- **Day 60:** SELinux concepts
  - SELinux architecture and modes
  - Security contexts and policies
  - SELinux vs traditional permissions
  - Practice: Understand SELinux in action

- **Day 61:** SELinux management
  - Changing SELinux modes
  - Managing SELinux contexts
  - SELinux boolean configuration
  - Practice: Configure SELinux for applications

- **Day 62:** SELinux troubleshooting
  - Analyzing SELinux denials
  - Creating custom policies
  - SELinux audit logging
  - Practice: Resolve SELinux policy issues

- **Day 63:** Firewall fundamentals
  - firewalld architecture and zones
  - Service and port management
  - Rich rules and direct rules
  - Practice: Configure basic firewall rules

- **Day 64:** Advanced firewall configuration
  - NAT and port forwarding
  - ICMP filtering
  - Firewall logging and monitoring
  - Practice: Implement complex firewall scenarios

- **Day 65:** System security hardening
  - Service hardening and disablement
  - Kernel parameter tuning
  - Access control refinement
  - Practice: Harden system against common threats

- **Day 66:** Security monitoring
  - Audit system configuration
  - Log monitoring for security events
  - Intrusion detection basics
  - Practice Lab: Complete security hardening project

---

### **Phase 4: Enterprise Features and Final Prep (Days 67-90)**

#### **Week 10: Performance and Boot Management (Days 67-73)**

**📚 Topics Covered:**

- System performance tuning
- Boot process management
- Kernel management
- System rescue and recovery

**🎯 Daily Goals:**

- **Day 67:** Performance monitoring
  - System performance metrics
  - Process priority management
  - CPU and memory optimization
  - Practice: Analyze and optimize system performance

- **Day 68:** Tuning profiles
  - tuned service configuration
  - Performance profile selection
  - Custom tuning profiles
  - Practice: Optimize system for specific workloads

- **Day 69:** Boot process management
  - systemd boot sequence
  - Boot targets and runlevels
  - Boot loader configuration
  - Practice: Manage system boot process

- **Day 70:** Boot troubleshooting
  - Emergency shell access
  - Root password recovery
  - Boot parameter modification
  - Practice: Recover from boot failures

- **Day 71:** Kernel management
  - Kernel version management
  - Kernel module operations
  - Kernel parameter tuning
  - Practice: Manage kernel and modules

- **Day 72:** System rescue
  - Rescue mode usage
  - System recovery techniques
  - Backup and restoration
  - Practice: Perform system recovery operations

- **Day 73:** Performance project
  - Complete performance analysis
  - Optimization implementation
  - Monitoring setup
  - Practice Lab: Complete performance tuning project

#### **Week 11: Containerization and Virtualization (Days 74-80)**

**📚 Topics Covered:**

- Container concepts and management
- Podman for container operations
- Container networking and storage
- Virtual machine management

**🎯 Daily Goals:**

- **Day 74:** Container fundamentals
  - Container vs virtual machine concepts
  - Container architecture and benefits
  - Container ecosystem overview
  - Practice: Understand container use cases

- **Day 75:** Podman basics
  - Podman installation and configuration
  - Running containers with Podman
  - Container image management
  - Practice: Deploy basic containers

- **Day 76:** Container management
  - Container lifecycle management
  - Container networking
  - Container storage and volumes
  - Practice: Manage containerized applications

- **Day 77:** Advanced container operations
  - Podman pods and multi-container apps
  - Container security
  - Container integration with systemd
  - Practice: Build multi-container applications

- **Day 78:** Container registries
  - Working with container images
  - Private registry setup
  - Image building and customization
  - Practice: Create and manage container images

- **Day 79:** Virtualization basics
  - KVM virtualization concepts
  - VM management with virt-manager
  - VM networking and storage
  - Practice: Deploy and manage virtual machines

- **Day 80:** Container project
  - Complete containerized application
  - Production-ready configuration
  - Monitoring and logging
  - Practice Lab: Complete containerization project

#### **Week 12: Final Review and Exam Preparation (Days 81-90)**

**📚 Topics Covered:**

- Comprehensive RHCSA review
- Practice exams and simulations
- Weak area focus
- Exam strategy and preparation

**🎯 Daily Goals:**

- **Day 81-82:** RHCSA-134 Comprehensive Review
  - Day 81: Scripting, storage, and SELinux review
  - Day 82: Performance, containers, and security review

- **Day 83-85:** Practice Exams
  - Day 83: Full RHCSA-124 practice exam
  - Day 84: Full RHCSA-134 practice exam
  - Day 85: Combined RHCSA practice exam

- **Day 86-87:** Weak Area Focus
  - Identify and strengthen weak topics
  - Additional practice on challenging areas
  - Hands-on lab reinforcement

- **Day 88:** Exam Strategy
  - Time management techniques
  - Question analysis methods
  - Exam environment preparation

- **Day 89:** Final Practice
  - Timed practice scenarios
  - Stress testing under exam conditions
  - Final knowledge validation

- **Day 90:** Rest and Preparation
  - Light review of key concepts
  - Exam day preparation
  - Confidence building and mental preparation

---

## 🎯 Key Learning Objectives

### **RHCSA-124 Core Competencies**

1. **Command Line Mastery**: Efficient navigation, file management, and text processing
2. **File System Operations**: Permissions, links, archiving, and system hierarchy
3. **User Administration**: Account management, group policies, and access control
4. **System Management**: Process control, service management, and basic networking
5. **Security Fundamentals**: Permission models, SSH configuration, and basic hardening

### **RHCSA-134 Advanced Competencies**

1. **Automation Skills**: Bash scripting, regular expressions, and task scheduling
2. **Storage Expertise**: LVM management, advanced file systems, and network storage
3. **Security Mastery**: SELinux configuration, firewall management, and system hardening
4. **Performance Tuning**: System optimization, resource management, and monitoring
5. **Container Operations**: Container deployment, management, and integration

---

## 🛠️ Recommended Study Resources

### **Primary Resources**

- **Red Hat Documentation**: Official RHEL documentation and guides
- **Lab Environment**: Virtual machines with RHEL 9.x
- **Practice Labs**: Hands-on exercises for each topic
- **Practice Exams**: RHCSA exam simulations

### **Supplementary Materials**

- **Linux Bible**: Comprehensive reference guide
- **Command Line Bible**: Quick reference for commands
- **System Administrator's Guide**: In-depth technical reference
- **Online Forums**: Red Hat community and discussion groups

---

## 📊 Assessment and Progress Tracking

### **Weekly Milestones**

- **Week 1-3**: Command line and file system mastery
- **Week 4-6**: System administration fundamentals
- **Week 7-9**: Advanced topics and automation
- **Week 10-12**: Enterprise features and exam preparation

### **Skill Validation**

- **Daily Practice**: Hands-on exercises for each topic
- **Weekly Quizzes**: Knowledge assessment and review
- **Monthly Projects**: Comprehensive practical applications
- **Practice Exams**: Full exam simulation and analysis

### **Success Metrics**

- **Command Proficiency**: Speed and accuracy in command line operations
- **Problem Solving**: Ability to troubleshoot and resolve issues
- **System Management**: Competence in administrative tasks
- **Exam Readiness**: Performance in practice exams and simulations

---

## 🎓 Certification Path

### **Prerequisites**

- Basic computer literacy and familiarity with operating systems
- Access to RHEL environment (physical or virtual)
- Commitment to 90-day study schedule

### **Exam Details**

- **RHCSA-124**: Foundation level certification
- **RHCSA-134**: Advanced level certification
- **Format**: Hands-on performance-based exam
- **Duration**: 2.5 hours per exam
- **Passing Score**: 70% or higher

### **Career Opportunities**

- Linux System Administrator
- DevOps Engineer
- Cloud Infrastructure Specialist
- Site Reliability Engineer
- Systems Architect

---

## 💡 Study Tips and Best Practices

### **Effective Learning Strategies**

1. **Hands-On Practice**: Spend 70% of study time in practical exercises
2. **Regular Review**: Weekly reinforcement of previously learned topics
3. **Real-World Scenarios**: Apply knowledge to practical situations
4. **Documentation Skills**: Learn to read and understand technical documentation

### **Time Management**

- **Daily Study**: 2-3 hours focused study sessions
- **Weekend Labs**: Extended hands-on practice sessions
- **Review Sessions**: Regular knowledge reinforcement
- **Practice Tests**: Timed exam simulations

### **Success Habits**

- **Consistent Schedule**: Maintain regular study routine
- **Note Taking**: Document commands and procedures
- **Community Engagement**: Participate in forums and study groups
- **Continuous Learning**: Stay updated with new features and best practices

---

## 🔧 Lab Environment Setup

### **Minimum Requirements**

- **CPU**: 2 virtual cores
- **Memory**: 4GB RAM
- **Storage**: 40GB disk space
- **Network**: Internet access for package installation

### **Recommended Setup**

- **Virtualization**: VirtualBox, VMware, or KVM
- **RHEL Version**: Latest RHEL 9.x
- **Additional Tools**: SSH client, text editor, web browser
- **Backup Strategy**: Regular snapshots for recovery

---

## 📈 Beyond RHCSA

### **Next Steps**

1. **RHCE Certification**: Red Hat Certified Engineer
2. **Specializations**: Cloud, containers, or security focus
3. **Advanced Topics**: Automation, orchestration, DevOps
4. **Community Involvement**: Contribute to open source projects

### **Continuous Learning**

- **Stay Current**: Regular updates with new RHEL releases
- **Expand Skills**: Learn complementary technologies
- **Professional Development**: Attend conferences and workshops
- **Knowledge Sharing**: Mentor others and contribute to community

---

_This roadmap provides a comprehensive path to RHCSA mastery. Adjust the pace and focus based on your current knowledge level and career goals. Consistent practice and hands-on experience are key to success in both the exams and real-world system administration._
