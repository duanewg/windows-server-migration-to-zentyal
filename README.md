<p align="center">
<img src="assets/zentyal-logo.png" alt="Zentyal Logo" />
</p>

# Windows Server 2016 Migration to Zentyal 7
The migration project involved transferring data from Active Directory in Windows Server 2016 to Zentyal 7, by establishing a new domain. The project seamlessly transitioned user accounts, groups, and organizational data to Zentyal, ensuring continuity of operations and enhanced management capabilities.

## Environments and Technologies Used

- Proxmox VE 7
- Zentyal 7
- AD Pro Toolkit
- User State Migration Tool (USMT)
- Power Shell

## Operating Systems Used

- Windows Server 2016
- Ubuntu Server 22.04 LTS
- Windows 10

## High-Level Deployment and Configuration Steps

- Zentyal Installation
    - Create a new VM in Promox
    - Mount Ubuntu Server image and install
    - Update Ubuntu
    - Download and run Zentyal installation script
    - Open Zentyal web interface and launch initial configuration wizard
    - Choose Controller and File Sharing from the Server Roles list to install all required software and dependencies
    - Configure the network interface(s) with a static IP(s)
    - Configure as a Standalone Server and set the domain name
- Active Directory OU, Group, and User migration
    - Install AD Pro Toolkit on a Windows client machine existing in the old domain
    - Use AD Pro Toolkit to export all OUs, users, and groups to csv
    - Join windows client machine to new domain
    - Use AD Pro Toolkit import all Ous, users, and groups from the csv
    - Verify user counts on all objects using a Power Shell 
- Desktop migration
    - Join all existing client machines to the new domain
    - Use USMT to migrate local user data from the old domain's user profile to the new domain's user profile
    

<h2>Architecture Diagram</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>