---
title: Network and Certificate System Security Requirements
subtitle: Version 1.7
author:
  - CA/Browser Forum
date: 5 April, 2021
copyright: |
  Copyright 2021 CA/Browser Forum

  This work is licensed under the Creative Commons Attribution 4.0 International license.
---

# Introduction

## Overview

**Scope and Applicability**:

These Network and Certificate System Security Requirements (Requirements) apply to all publicly trusted Certification Authorities (CAs) and are adopted with the intent that all such CAs and Delegated Third Parties be audited for conformity with these Requirements as soon as they have been incorporated as mandatory requirements (if not already mandatory requirements) in the root embedding program for any major Internet browsing client and that they be incorporated into the WebTrust Service Principles and Criteria for Certification Authorities, ETSI TS 101 456, ETSI TS 102 042 and ETSI EN 319 411-1 including revisions and implementations thereof, including any audit scheme that purports to determine conformity therewith.

In these Requirements, the CA is responsible for all tasks performed by Delegated Third Parties and Trusted Roles, and the CA SHALL define, document, and disclose to its auditors

a. the tasks assigned to Delegated Third Parties or Trusted Roles, and
b. the arrangements made with Delegated Third parties to ensure compliance with these Requirements, and
c. the relevant practices implemented by Delegated Third Parties.

**Guiding Principle and Goal**:

CAs are expected to maintain a very high level of security for their infrastructure and systems because the certificates they issue play a vital role in the security of the internet, email, and software distribution. 

**Desired Outcomes**:

As a document which outlines requirements some CAs must meet, it can help to understand the outcomes which are expected to be achieved by CAs complying with this document. Below are outcomes which this document seeks to achieve:
* All CAs seeking compliance with the NCSSRs are able to clearly understand the minimum security requirements of the NCSSRs and successfully adapt/implement these requirements to their own infrastructure and architecture.
* Audit and assessment bodies are able to accurately map the general requirements of the NCSSRs to the specific implementations observed during audit engagements, and judge compliance against these requirements.
* CA organizations, operations, infrastructure, and the private keys of their CA and signing certificates are not compromised.
* Desired Outcome: The NCSSRs are a best in class representation of modern security requirements.
* Controls are implemented that protect against external and internal threats, including mistakes.
* CA personnel are limited in their ability to negatively impact the CA’s operations (through a combination of credentialing, role management, and training) whether intentional or unintentional.
* Systems provide sufficient artifacts to enable traceability of all events and identification and investigation of anomalous events.
* Continuous monitoring and testing are conducted to identify any vulnerabilities or weaknesses that need to be addressed promptly and to ensure the effectiveness of implemented security controls.
* CA infrastructure is maintained, including timely patching of software and firmware, and hardware is kept sufficiently up-to-date to support underlying dependencies.
* Provides a framework for assessment of infrastructure or systems not owned/controlled by the CA against the NCSSRs.
* Enables the use of infrastructure or systems not owned/controlled by the CA, if it has been determined such use and systems do align with the NCSSRs.


## Document History

| **Ver.** | **Ballot** | **Description** | **Adopted** | **Effective\*** |
|-|-|-----|--|--|
| 1.0 | 83 | Original Version Adopted | 3‐Aug‐12 | 01‐Jan‐13 |
| 1.1 | 210 | Misc. Changes to NCSSRs | 31‐Aug‐17 | 09-Mar-18 |
| 1.2 | SC3 | Two-Factor Authentication and Password Improvements | 16‐Aug‐18 | 15-Sep-18 |
| 1.3 | SC21 | The Network and Certificate Systems Security Requirements Section 3 (Log Integrity Controls) | 26‐Sep‐19 | 4-Nov-2019 |
| 1.4 | SC29 | System Configuration Management | 7-May-20 | 8-Jun-2020 |
| 1.5 | SC28 | Logging and Log Retention | 10-Sep-2020 | 19-Sep-2020 |
| 1.6 | SC39 | Definition of Critical Vulnerability | 16-Feb-2021 | 30-Mar-2021 |
| 1.7 | SC41 | Reformatting the BRs, EVGs, and NCSSRs | 24-Feb-2021 | 5-Apr-2021 |

\* Effective Date based on completion of 30‐day IPR review without filing of any Exclusion Notices.

## Definitions

**Air-Gapped**:  Physically and logically separated, disconnected, and isolated from all other Systems.

**CA Systems**: Collectively the infrastructure which qualifies as a:
   * Certificate Management System;
   * Certificate System;
   * Front End / Internal Support System;
   * Issuing System;
   * Root CA System (Air-Gapped and otherwise); or
   * Security Support System.

**Certificate Management System**: A system used by a CA or Delegated Third Party to process, approve issuance of, or store certificates or certificate status information, including the database, database server, and storage.

**Certificate System**: A system used by a CA or Delegated Third Party to access, process, or manage data or provide services related to:
   1. identity validation;
   2. identity authentication;
   3. account registration;
   4. certificate application;
   5. certificate approval;
   6. certificate issuance;
   7. certificate revocation;
   8. certificate status; or
   9. certificate or key escrow.
   
**Common Vulnerability Scoring System (CVSS)**: A quantitative model used to measure the base level severity of a vulnerability (see <http://nvd.nist.gov/vuln-metrics/cvss>).

**Critical Security Event**: An event, set of circumstances, or anomalous activity that could lead to a circumvention of a CA System's security controls or compromise of a CA System’s integrity or operational continuity, including, but not limited to, excessive login attempts, attempts to access prohibited resources, DoS/DDoS attacks, attacker reconnaissance, excessive traffic at unusual hours, signs of unauthorized access, system intrusion, or physical compromise of component integrity.

**Critical Vulnerability**: A system vulnerability that has a CVSS v2.0 score of 7.0 or higher according to the NVD or an equivalent to such CVSS rating (see <https://nvd.nist.gov/vuln-metrics/cvss>), or as otherwise designated as a Critical Vulnerability by the CA or the CA/Browser Forum.

**Delegated Third Party**: A natural person or legal entity that is not the CA and that operates any part of a Certificate System.

**Delegated Third Party System**: Any part of a Certificate System used by a Delegated Third Party while performing the functions delegated to it by the CA.

**Front End / Internal Support System**: A system with a public IP address, including a web server, mail server, DNS server, jump host, or authentication server.

**Issuing System**: A system used to sign certificates or validity status information.

**Key Pair**: The Private Key and its associated Public Key.

**Multi-Factor Authentication**: An authentication mechanism consisting of two or more of the following independent categories of credentials (i.e. factors) to verify the user’s identity for a login or other transaction: something you know (knowledge factor), something you have (possession factor), and something you are (inherence factor). Each factor must be independent. Certificate-based authentication can be used as part of Multifactor Authentication only if the private key is stored in a Secure Key Storage Device.

**National Vulnerability Database (NVD)**: A database that includes the Common Vulnerability Scoring System (CVSS) scores of security-related software flaws, misconfigurations, and vulnerabilities associated with systems (see <http://nvd.nist.gov/>).

**OWASP Top Ten**: A list of application vulnerabilities published by the Open Web Application Security Project (see <https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project>).

**Penetration Test**: A process that identifies and attempts to exploit openings and vulnerabilities on systems through the active use of known attack techniques, including the combination of different types of exploits, with a goal of breaking through layers of defenses and reporting on unpatched vulnerabilities and system weaknesses.

**Physically Secure Environment**:  An environment protected by physical security controls according to section 4.5.1 of RFC 3647 and in accordance with a risk assessment conducted by the CA as required by the Baseline Requirements, etc., meeting section 5.1 below.

**Principle of Least Privilege**: The principle that users, devices, and software should only have the minimum necessary access and privileges to complete their functions.

**Private Key**: The cryptographic key of an asymmetric Key Pair that is kept secret by the holder of the Key Pair. It may be used to create digital signatures and/or to decrypt data that were encrypted by the corresponding Public Key.

**Public Key**: The cryptographic key of an asymmetric Key Pair that is made public. It may be used to verify digital signatures and/or to encrypt data that can be decrypted by the corresponding Private Key.

**Root CA Certificate**:  The Self-Signed Certificate issued by the Root CA to identify itself and to facilitate verification of Certificates issued to its Subordinate CAs. 

**Root CA Private Key**: The Private Key associated with a Root CA Certificate.

**Root CA System**: A system used to:
   1. generate a Key Pair whose Private Key is a Root CA Private Key;
   2. store a Root CA Private Key;
   3. sign with a Root CA Private Key; or
   4. create a Root CA Certificate.

**SANS Top 25**: A list created with input from the SANS Institute and the Common Weakness Enumeration (CWE) that identifies the Top 25 Most Dangerous Software Errors that lead to exploitable vulnerabilities (see <http://www.sans.org/top25-software-errors/>).

**Secure Key Storage Device**: A device certified as meeting at least FIPS 140-2 level 2 overall, level 3 physical, or Common Criteria (EAL 4+).

**Security Support System**: A system used to provide security support functions, which minimally includes:
   1. authentication;
   2. network boundary control;
   3. audit logging;
   4. audit log reduction and analysis;
   5. vulnerability scanning; and
   6. physical, host-based, and network-based intrusion detection.

**Self-Signed Certificate**: A certificate containing a Public Key and a digital signature created by the associated Private Key. The Public Key can be used to verify the digital signature of the certificate.

**System**: One or more pieces of equipment or software that stores, transforms, or communicates data.

**Trusted Role**: An employee or contractor of a CA or Delegated Third Party who has authorized access to a Certificate System.

**Vulnerability Scan**: A process that uses manual or automated tools to probe internal and external systems to check and report on the status of operating systems, services, and devices exposed to the network and the presence of vulnerabilities listed in the NVD, OWASP Top Ten, or SANS Top 25.

# 1. CA Systems

## 1.1 CA Systems and Network Configuration

Each CA or Delegated Third Party SHALL:
### 1.1.1 
Segment CA Systems into networks based on their functional or logical relationship, for example separate physical networks or VLANs;

### 1.1.2 
Apply equivalent security controls to all systems co-located in or on the same network as a CA System;

### 1.1.3 
Maintain and protect all CA Systems in a Physically Secure Environment;

### 1.1.4 
Implement and configure Security Support System(s) that:
   1. protect CA Systems; 
   2. secure connections and communications between CA Systems; and
   2. secure connections and communications between CA Systems and non-CA Systems (including those with organizational business units that do not provide PKI-related services and those on public networks); and

### 1.1.5 
Configure CA Systems by:
   1. removing and/or disabling all connections, applications, services, protocols, and ports that are not used in the CA’s or Delegated Third Party’s operations; and 
   2. allowing only those connections, applications, services, protocols, and ports that are identified as necessary by the CA under the Principle of Least Privilege and approved by the CA or Delegated Third Party.

### 1.1.6
Configure each network boundary control (firewall, switch, router, gateway, or other network control device or system) with rules that support only the services, protocols, ports, and communications that the CA has identified as necessary to its operations under the Principle of Least Privilege; and

## 1.2 Change Management

Each CA or Delegated Third Party SHALL:

### 1.2.1 
Ensure that the CA’s security policies are encompassed within a change management process, which MUST minimally include:
   1. comprehensive documentation; and
   2. review and approval procedures limited to individuals in roles commensurate with the responsibility; and
   
### 1.2.2 
Ensure that all changes to CA Systems follow the change management process required by Section 1.2.1.

# 2. Access Control

## 2.1 Trusted roles

Each CA or Delegated Third Party SHALL:

### 2.1.1 
Define and document a set of Trusted Roles necessary to operate all CA Systems;

#### 2.1.1.1
Each Trusted Role MUST have its responsibilities, privileges, and access documented.

#### 2.1.1.2
Each Trusted Role MUST be created in a manner consistent with:
   1. the Principle of Least Privilege;
   2. requirements of multi-party control; and 
   3. accountability;

### 2.1.2 
Follow a documented procedure for managing authorized individuals appointed to Trusted Roles, to minimally include:
   1. initial appointment of an individual to a Trusted Role;
   2. modifying an individual's Trusted Role; and
   3. removing an individual from a Trusted Role;

#### 2.1.2.1
When an individual's authorization to access a CA System is changed or revoked (for example, by removing a Trusted Role, modifying an individual's Trusted Role, or modifying the defined access associated with a Trusted Role) authentication keys and passwords MUST also be changed or revoked;

### 2.1.3 
Ensure that only personnel assigned to Trusted Roles have access to CA Systems;

### 2.1.4 
Implement processes such that an individual only acts within the scope of their Trusted Role;

### 2.1.5 
Require employees and contractors to observe the Principle of Least Privilege when accessing, or when configuring access privileges on, CA Systems;

### 2.1.6 
Require that each individual in a Trusted Role use a unique credential created by or assigned to that person in order to authenticate to CA Systems;

#### 2.1.6.1 
Group accounts and shared role credentials SHALL NOT be used; 

### 2.1.7 
Require Trusted Roles to log out of or lock workstations when not in active use;

#### 2.1.7.1
CAs and Delegated Third Parties SHALL configure workstations with inactivity time‐outs that automatically log the user off or lock the workstation after a set time of inactivity without input from the user 

#### 2.1.7.2
The CA or Delegated Third Party MAY allow a workstation to remain active and unattended if the workstation is otherwise secured and running administrative tasks that would be interrupted by an inactivity time‐out or system lock;

## 2.2 Password-based Authentication

If an authentication control used by a Trusted Role is a username and password, then each CA or Delegated Third Party SHALL implement the following controls:
   1. For accounts that are accessible only within Secure Zones or High Security Zones, require that passwords have at least twelve (12) characters;
   2. For authentications which cross a zone boundary into a Secure Zone or High Security Zone, require Multi‐Factor Authentication. For accounts accessible from outside a Secure Zone or High Security Zone require passwords that have at least eight (8) characters and are not be one of the user’s previous four (4) passwords; and implement account lockout for failed access attempts in accordance with subsection k;
   3. When developing password policies, CAs SHOULD take into account the password guidance in NIST 800‐63B Appendix A.
   4. If the CA has any policy that requires periodic password changes, that period SHALL NOT be less than two years.

## 2.3 CA Systems Access

Each CA or Delegated Third Party SHALL:
### 2.3.1 
Ensure that System access and System account permissions are restricted:
   1. to persons assigned a Trusted Role associated with such access and permissions; and
   2. in accordance with the Principle of Least Privilege;

### 2.3.2
Review all System accounts at least every three (3) months and deactivate any accounts that are no longer necessary for operations;

### 2.3.3 
Lockout account access to CA Systems after no more than five (5) failed access attempts, provided that this security measure:
   1. Is supported by the System;
   2. Cannot be leveraged for a denial of service attack; and
   3. Does not weaken the security of this authentication control;

### 2.3.4
Implement a process that disables all access by an individual to CA Systems within twenty-four (24) hours upon termination of the individual’s employment or contracting relationship with the CA or Delegated Third Party;

### 2.3.5
Enforce Multi‐Factor Authentication for all accounts on CA Systems;

### 2.3.6
Enforce Multi-Factor Authentication and/or multi‐party authentication for all access to CA Systems;

### 2.3.7
Restrict remote administration of and/or access to CA Systems except when:
   1. the remote connection originates from a device owned or controlled by the CA or Delegated Third Party;
   2. the remote connection is through a temporary, non‐persistent encrypted channel that is authenticated using Multi‐Factor Authentication; and
   3. the remote connection is made to a designated intermediary device which:
      * is located within the CA’s network;
      * is secured in accordance with these Requirements; and
      * mediates the remote connection to the CA System.

# 3. Incident Response and Reporting

## 3.1 Logging and Monitoring
Each CA or Delegated Third Party SHALL:

### 3.1.1
Implement, as part of a Security Support System, continuous monitoring of CA Systems for modifications not authorized through the change management process outlined in Section 1.2;

### 3.1.2
Identify CA Systems capable of monitoring and logging System activity and enable those capabilities to create audit-compliant logs (for example, to meet the requirements in Section 5.4.1 (3) of the Baseline Requirements for the Issuance and Management of Publicly‐Trusted Certificates);

### 3.1.3
Monitor the integrity of System logging processes through:
   1. a Security Support System's continuous automated monitoring; or
   2. a review by personnel acting in a Trusted Role at least once every 31 days;

### 3.1.4
Monitor the archival and retention of logs to ensure that logs are retained for the appropriate amount of time in accordance with the disclosed business practices and applicable legislation.

## 3.2 Log Processing and Alerting
Each CA or Delegated Third Party SHALL:

### 3.2.1
Implement automated mechanisms under the control of individuals the CA or Delegated Third Party Trusted Roles to process logged system activity and identify possible Critical Security Events;

### 3.2.2
Alert personnel in relevant Trusted Roles, using notices provided to multiple destinations, of:
   1. possible Critical Security Events; and
   2. unauthorized changes to CA Systems (as identified by 3.1.1);

### 3.2.3
Require Trusted Role personnel to respond to alerts within twenty-four (24) hours.

Once the responder(s) has confirmed the legitimacy of the alert, the further response MUST include:
   1. identifying the potential impact and severity of the event;
   2. initiating relevant containment actions (such as isolating a System from the network, disabling accounts, or other mitigation measures); and
   3. developing and initiating an appropriate risk-based plan of action to fully remediate the Critical Security Event.

# 4. Vulnerability Detection and Patch Management

CSA CCM stuff goes here(?)

# 5. Protections for Root CA Systems

This Section 5 separates requirements for Root CA Systems into three subsections--trusted roles, logical security, and physical security. 

## 5.1 Trusted Roles

Each CA and Delegated Third Parties SHALL:

### 5.1.1
Implement a process to document and approve all changes to  Air-Gapped CA Systems; 

### 5.1.2  
Define and document the responsibilities assigned to Trusted Roles, taking into account the principles of least-privilege and dual control;

### 5.1.3
Assign tasks to Trusted Roles and follow a documented procedure for appointing authorized individuals to those Trusted Roles; 

### 5.1.4  
Implement processes such that an individual only acts within the scope of their Trusted Role; and

### 5.1.5
Implement controls, which may be a combination of physical and logical access controls, such  that all access to systems and offline key material can be traced back to an individual in a Trusted Role (through a combination of recordkeeping, use of logical and physical credentials, authentication factors, video recording, etc.)/

## 5.2  Logical Security

Each CA and Delegated Third Parties SHALL:

### 5.2.1
Review logical access at least annually and deactivate any access  that is no longer necessary for operation of the Air-Gapped CA System; 

### 5.2.2
Implement Multi-Factor Authentication and/or  multi-party authentication for physical  access to the Air-Gapped CA System;

### 5.2.3
Identify those Air-Gapped CA Systems capable of logging system activity and enable those systems to continuously log system activity;

### 5.2.4
Back up logs to an external system each time the system is used or on a quarterly basis, whichever is less frequent; 

### 5.2.5
On a quarterly basis or each time the Air-Gapped CA System is used, whichever is less frequent, check the integrity of the activity logging processes and ensure that logging and log-integrity functions are effective;

### 5.2.6
On a quarterly basis or each time the Air-Gapped CA System is used, whichever is less frequent, confirm that the archival and retention of activity logs occurs  for the appropriate amount of time in accordance with the disclosed business practices and applicable legislation; and

### 5.2.7
Based on the logs, determine whether there were any unauthorized procedures and follow the appropriate run book to remediate issues.

## 5.3 Physical Security

Each CA and Delegated Third Party SHALL:

### 5.3.1
Maintain the Root CA Private Key in a hardware security module operating in FIPS 140-2 Level 3 or higher mode.

#### 5.3.1.1
All hardware security modules, devices, and software used with the Root CA Private key (i.e. associated key ceremony equipment) MUST be maintained in a Physically Secure Environment.

#### 5.3.1.2
The hardware security module MUST be stored in an offline state.  While powered on, all equipment MUST be Air‐Gapped from all other networks.

### 5.3.2
Grant physical access to Air-Gapped CA Systems only to persons acting in Trusted Roles and implement controls so that all physical access to Air-Gapped CA Systems can be traced back to accountable individuals; 

### 5.3.3
Ensure that only personnel assigned to Trusted Roles have physical access to Air-Gapped CA Systems and multi-person access controls are enforced at all times;

### 5.3.4
Implement a process that removes physical access of an individual to all Air-Gapped CA Systems when: (a) a person’s responsibility changes and their access is no longer necessary, or (b) within twenty-four (24) hours upon termination of an individual’s employment or contracting relationship with the CA or Delegated Third Party; 

### 5.3.5
Implement video monitoring, intrusion detection, and intrusion prevention controls to protect Air-Gapped CA Systems against unauthorized physical access attempts; 

### 5.3.6
Implement a Security Support System that monitors, detects, and alerts personnel to any physical access to Air-Gapped CA Systems; 

### 5.3.7
Implement a process that prevents physical access of an individual to an Air-Gapped CA within twenty-four (24) hours of removal from the relevant authorized Trusted Role, and review lists of holders of physical keys and combinations to doors and safes as well as logical accounts tied to physical access controls at least every three (3) months; 

### 5.3.8
On a quarterly basis or each time the Air-Gapped CA System is used, whichever is less frequent, monitor the archival and retention of the physical access logs to ensure that logs are retained for the appropriate amount of time in accordance with the disclosed business practices and applicable legislation; and

### 5.3.9
On a quarterly basis or each time the Air-Gapped CA System is used, whichever is less frequent, check the integrity of the physical access logging processes and ensure that logging and log-integrity functions are effective.