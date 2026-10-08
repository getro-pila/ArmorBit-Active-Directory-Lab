# 🛡️ ArmorBit | Enterprise Active Directory Infrastructure Lab

**Building, Managing, Securing & Troubleshooting a Windows Enterprise Environment**



\


## 📌 Project Overview

ArmorBit is a simulated enterprise IT environment designed to demonstrate practical skills in Windows Server administration, Active Directory Domain Services (AD DS), networking, system security, automation, and technical troubleshooting.

The project simulates an organization with **100 employees across five departments**, using Microsoft Hyper-V to build and manage a virtualized Windows infrastructure.

The goal is to develop hands-on experience with technologies and responsibilities commonly encountered in IT Support, Help Desk, System Administration, and Cybersecurity positions.

## 🎯 Project Objectives

- Deploy and configure Windows Server 2025.
- Install and manage Active Directory Domain Services.
- Configure DNS and centralized domain authentication.
- Create and organize 100 simulated employee accounts.
- Implement Organizational Units (OUs) and security groups.
- Join Windows 11 workstations to the domain.
- Configure Group Policy Objects (GPOs).
- Implement role-based file sharing and access permissions.
- Automate administrative tasks using PowerShell.
- Diagnose and resolve common enterprise IT issues.
- Document configuration procedures and validation results.

## 🏢 Enterprise Environment

**Organization:** ArmorBit

**Active Directory Domain:** `ad.armorbit.com`

**NetBIOS Domain:** `ARMORBIT`

### Department Structure

| Department             | Simulated Users |
| ---------------------- | --------------: |
| Information Technology |              20 |
| Human Resources        |              20 |
| Finance                |              20 |
| Sales                  |              20 |
| Operations             |              20 |
| **Total**              |         **100** |

## 🖥️ Lab Infrastructure

| Component          | Configuration           |
| ------------------ | ----------------------- |
| Hypervisor         | Microsoft Hyper-V       |
| Host Memory        | 16 GB RAM               |
| Domain Controller  | DC01                    |
| Server OS          | Windows Server 2025     |
| Client Workstation | CLIENT01                |
| Client OS          | Windows 11 Enterprise   |
| Active Directory   | AD DS                   |
| DNS                | Windows DNS Server      |
| Virtual Network    | Hyper-V Internal Switch |
| Automation         | PowerShell              |

### IP Addressing

| Device       | IP Address    | Role                      |
| ------------ | ------------- | ------------------------- |
| Hyper-V Host | 10.10.10.1    | Virtual network interface |
| DC01         | 10.10.10.10   | AD DS / DNS               |
| CLIENT01     | 10.10.10.101  | Domain workstation        |
| Subnet       | 10.10.10.0/24 | Isolated lab network      |

## 🏗️ Network Architecture

The initial environment consists of a Windows Server 2025 domain controller and a Windows 11 client connected through an isolated Hyper-V virtual switch.

```text
                  ARMORBIT ENTERPRISE LAB
                  Domain: ad.armorbit.com
                            |
                   Windows Hyper-V Host
                       16 GB RAM
                            |
                    NS-LabSwitch
                     10.10.10.0/24
                            |
                 +----------+----------+
                 |                     |
                DC01                CLIENT01
          Windows Server 2025     Windows 11
           10.10.10.10          10.10.10.101
                 |                     |
           Active Directory      Domain Client
           DNS Services          GPO Testing
           User Management       Authentication
           File Sharing          Troubleshooting
```

## 🔐 Active Directory Design

The directory will be organized using departmental Organizational Units.

```text
ad.armorbit.com
|
+-- ArmorBit
|   |
|   +-- IT
|   +-- HumanResources
|   +-- Finance
|   +-- Sales
|   +-- Operations
|   +-- Workstations
|   +-- Servers
|
+-- Domain Controllers
    |
    +-- DC01
```

The built-in Domain Controllers OU will retain the domain controller.

Departmental security groups will be used to implement role-based access controls.

## ⚙️ Planned Implementation Phases

### Phase 1 — Virtual Infrastructure

- [ ] Enable and configure Hyper-V
- [ ] Create isolated virtual networking
- [ ] Deploy Windows Server 2025
- [ ] Deploy Windows 11 Enterprise

### Phase 2 — Active Directory Deployment

- [ ] Configure server hostname and static IP address
- [ ] Install AD DS and DNS
- [ ] Create the `ad.armorbit.com` forest
- [ ] Validate domain controller health

### Phase 3 — Identity & Access Management

- [ ] Create departmental Organizational Units
- [ ] Provision 100 simulated user accounts
- [ ] Create and assign security groups
- [ ] Join Windows 11 to the domain

### Phase 4 — Group Policy & File Services

- [ ] Configure workstation security policies
- [ ] Implement screen locking and firewall settings
- [ ] Configure departmental shared folders
- [ ] Apply NTFS and SMB permissions
- [ ] Verify access restrictions

### Phase 5 — PowerShell Automation

- [ ] Automate user provisioning
- [ ] Automate security group assignment
- [ ] Export user and group audit reports

### Phase 6 — Troubleshooting & Validation

- [ ] Validate domain authentication
- [ ] Test DNS resolution
- [ ] Verify Group Policy application
- [ ] Troubleshoot simulated account and connectivity issues
- [ ] Document incident resolutions

## 🧪 Technical Validation

Validation will include commands such as:

- `dcdiag` — Domain controller diagnostics
- `Get-ADUser` — Active Directory user verification
- `Get-ADGroupMember` — Security group membership
- `nslookup` — DNS troubleshooting
- `gpresult /r` — Group Policy verification
- `whoami /groups` — User security context
- `Test-NetConnection` — Network connectivity
- `icacls` — NTFS permission inspection

Evidence and test results will be documented as the project progresses.

## 📂 Repository Structure

```text
ArmorBit-Active-Directory-Lab/
├── README.md
├── architecture/
│   └── network-diagram.png
├── documentation/
│   ├── hyper-v-setup.md
│   ├── active-directory-deployment.md
│   ├── user-management.md
│   ├── group-policy.md
│   └── troubleshooting.md
├── scripts/
│   ├── create-users.ps1
│   └── validate-ad.ps1
├── screenshots/
└── reports/
    └── validation-results.md
```

## 📚 Skills Demonstrated

**System Administration:** Windows Server, Active Directory, user and computer management, DNS, Group Policy.

**Networking:** TCP/IP, virtual switches, DNS troubleshooting, network connectivity testing.

**Security:** Role-based access control, least privilege, account administration, NTFS permissions.

**Automation:** PowerShell scripting, bulk user provisioning, administrative reporting.

**IT Support:** Domain authentication troubleshooting, workstation configuration, technical documentation.

## 🚀 Future Enhancements

- Add a secondary domain controller for redundancy.
- Implement DHCP services.
- Deploy a dedicated file server.
- Integrate centralized security monitoring.
- Implement advanced PowerShell automation.
- Test Active Directory backup and disaster recovery.

## 👨‍💻 About This Project

This project is part of my independent technical portfolio, where I apply practical IT administration, networking, and cybersecurity skills to realistic infrastructure challenges.

My objective is to build solutions, troubleshoot problems, document technical work, and continuously improve my understanding of enterprise technologies.

**Project Status:** In Progress

**Disclaimer:** ArmorBit is used as the name of this simulated lab environment. All employee accounts and business scenarios are fictional. No production systems are involved.
