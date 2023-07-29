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

In these Requirements, the CA is responsible for all tasks performed by Delegated Third Parties and Trusted Roles, and the CA SHALL define, document, and disclose to its auditors:

a. the tasks assigned to Delegated Third Parties or Trusted Roles;
b. the arrangements made with Delegated Third parties to ensure compliance with these Requirements; and
c. the relevant practices implemented by Delegated Third Parties.

**Guiding Principle and Goal**:

CAs are expected to maintain a very high level of security for their infrastructure and systems because the certificates they issue play a vital role in the security of the internet, email, and software distribution. 

**Desired Outcomes**:

As a document which outlines requirements some CAs must meet, it can help to understand the outcomes which are expected to be achieved by CAs complying with this document. Following are outcomes which this document seeks to achieve:
* CAs seeking compliance with the NCSSRs are able to clearly understand the minimum security requirements of the NCSSRs and successfully adapt/implement these requirements to their own infrastructure and architecture.
* Audit and assessment bodies are able to accurately map the general requirements of the NCSSRs to the specific implementations observed during audit engagements, and judge compliance against these requirements.
* CA organizations, operations, infrastructure, and the private keys of their CA and signing certificates are not compromised.
* The NCSSRs are a best in class representation of modern security requirements.
* Controls are implemented that protect against external and internal threats, including mistakes.
* CA personnel are limited in their ability to negatively impact the CA’s operations (through a combination of credentialing, role management, and training) whether intentional or unintentional.
* Systems provide sufficient artifacts to enable traceability of all events and identification and investigation of anomalous events.
* Continuous monitoring and testing are conducted to identify any vulnerabilities or weaknesses that need to be addressed promptly and to ensure the effectiveness of implemented security controls.
* CA Infrastructure is maintained, including timely patching of software and firmware, and hardware is kept sufficiently up-to-date to support underlying dependencies.
* A framework is provided for assessment of infrastructure or systems not owned/controlled by the CA against the NCSSRs.
* The use of infrastructure or systems not owned/controlled by the CA is possible, if it has been determined such use and systems do align with the NCSSRs and any other applicable standards, policies, or requirements.


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

**CA Infrastructure**: Collectively the infrastructure used by the CA or Delegated Third Party which qualifies as a:
   * Certificate Management System;
   * Certificate System;
   * Front End / Internal Support System; 
   * Issuing System;
   * Root CA System (Air-Gapped and otherwise); or
   * Security Support System. <!-- should be removable  after checklist with definition is done -->

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

**Multi-Factor Authentication**: An authentication mechanism consisting of two or more of the following independent categories of credentials (i.e. factors) to verify the user’s identity for a login or other transaction: 
   1. something the user knows (knowledge factor);
   2. something the user has (possession factor); and 
   3. something the user is (inherence factor). 
Each factor is independent of the other(s). 
Authentication based on the possession of a certificate can be used as part of Multi-factor Authentication only if the associated Private Key is stored in a Secure Key Storage Device.
<!-- This definition could use some further enhancement. -->

**Multi-Party Control**: An access control mechanism which requires two or more separate, authorized users to successfully authenticate with their own unique credentials prior to access being granted.

**National Vulnerability Database (NVD)**: A database that includes the Common Vulnerability Scoring System (CVSS) scores of security-related software flaws, misconfigurations, and vulnerabilities associated with systems (see <http://nvd.nist.gov/>).

**Network Equipment**: Hardware devices and components that facilitate communication and data transfer within the CA Infrastructure.

**OWASP Top Ten**: A list of application vulnerabilities published by the Open Web Application Security Project (see <https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project>).

**Penetration Test**: A process that identifies and attempts to exploit openings and vulnerabilities on systems through the active use of known attack techniques, including the combination of different types of exploits, with a goal of breaking through layers of defenses and reporting on unpatched vulnerabilities and system weaknesses.

**Physically Secure Environment**:  A controlled and protected physical space consisting minimally of a physical environment which is:
1. protected by security controls which address the topics outlined in [section 4.5.1 of RFC 3647](https://datatracker.ietf.org/doc/html/rfc3647#section-4.5.1); and
2. designed, built, and maintained in accordance with Risk Assessments conducted by the CA.

<!-- 
* This should address access control, perimeter security, video surveillance, security personnel, alarms and intrusion detection, secure storage, redundancy and resiliency, etc.
* Much of this may belong in more dedicated sections of the NCSSRs rather than the definition, with a reference from the definition.
* The 2nd bullet point intimates a requirement that the CA be responsible for first conducting a Risk Assessment and second designing, building, and maintaining the Physically Secure Environment (which could be directly or more likely the CA "signing off" on those processes). Is that the right expectation for _all_ CA Infrastructure? I think it would be better to separate this into two environments: 1 for Root CA Systems and 1 for everything else. Criteria for Root CA Systems should be prescriptive while criteria for everything else should be less rigid and likely move away from specifying the CA's need to be involved _before_ the environment can be built (i.e. no reason they can't assess existing environments as meeting the criteria and their risk assessment).
-->

**Principle of Least Privilege**: The principle that users, devices, and software should only have the minimum necessary access and privileges to complete their functions.

**Private Key**: The cryptographic key of an asymmetric Key Pair that is kept secret by the holder of the Key Pair. It may be used to create digital signatures and/or to decrypt data that were encrypted by the corresponding Public Key.

**Public Key**: The cryptographic key of an asymmetric Key Pair that can be made public without compromising the security of the Key Pair. It may be used to verify digital signatures and/or to encrypt data that can be decrypted by the corresponding Private Key.

**Risk Assessment**: A formal process that:
1. Identifies and documents foreseeable internal and external threats to the CA Infrastucture that could result in:
   + unauthorized access to the CA Infrastructure;
   + disclosure of data stored in the CA Infrastructure;
   + misuse of the CA Infractructure; or
   + unapproved alteration or destruction of any part of the CA Infrastructure;
2. Assesses and documents the likelihood and potential damage of each identified threat, taking into consideration minimally the sensitivity and criticality of the CA Infrastructure; and
3. Assesses and documents the sufficiency of the policies, procedures, controls, information systems, technology, and other arrangements that the CA has in place to counter each identified threat.

**Root CA Certificate**:  A self-signed and self-issued certificate where:
   1. the issuer and subject of the certificate are the same; and
   2. the digital signature of the certificate is: 
      * generated using the Private Key of a Key Pair whose corresponding Public Key is bound to the certificate; and
      * verified using the Public Key contained in the certificate.

**Root CA Private Key**: The Private Key associated with a Root CA Certificate.

**Root CA System**: A system used to:
   1. generate a Key Pair whose Private Key is or will be a Root CA Private Key;
   2. store a Root CA Private Key;
   3. create digital signatures using a Root CA Private Key; or
   4. create a Root CA Certificate. <!-- potentially redundant -->

**SANS Top 25**: A list created with input from the SysAdmin, Audit, Network, and Security (SANS) Institute and the Common Weakness Enumeration (CWE) that identifies the Top 25 Most Dangerous Software Errors that lead to exploitable vulnerabilities (see <http://www.sans.org/top25-software-errors/>).

**Secure Key Storage Device**: A device certified as meeting at least:
   * FIPS 140-2 or 140-3, level 2 overall or level 3 physical; or
   * Common Criteria (EAL 4+).
<!-- Seems this could be updated e.g. for passkey storage or FIDO -->

**Security Support System**: A system or set of systems supporting the security of the CA Infrastructure., which minimally includes:
   1. authentication;
   2. network boundary control;
   3. audit logging;
   4. audit log reduction and analysis;
   5. vulnerability scanning;
   6. physical intrusion detection;
   7. host-based intrusion detection; and
   8. network-based intrusion detection.
<!-- This is another definition that seems better suited to be part of the core requirements. We should be able to obviate the need for it because of the presence of dedicated sections outlining these requirements:
   1. authentication; (2.3.5/6) <DONE>
   2. network boundary control; (1.1.1) <DONE>
   3. audit logging; (3)
   4. audit log reduction and analysis; (3)
   5. vulnerability scanning; (4)
   6. physical intrusion detection; (5)
   7. host-based intrusion detection; and (4)
   8. network-based intrusion detection. (4)
-->

<!-- With the update to Root CA Certificate, I think this becomes unnecessary in this document

**Self-Signed Certificate**: A certificate containing a Public Key and a digital signature created by the associated Private Key. The Public Key can be used to verify the digital signature of the certificate. -->

**System**: One or more pieces of equipment or software that stores, transforms, or communicates data.

**Trusted Role**: An employee or contractor of a CA or Delegated Third Party who has authorized access to any component of CA Infrastructure.

**Vulnerability Scan**: A process that uses manual or automated tools to probe internal and external systems to check and report on the status of operating systems, services, and devices exposed to the network and the presence of vulnerabilities listed in the NVD, OWASP Top Ten, or SANS Top 25.
<!-- NVD is really all we need here, probably -->

**Workstation**: A device, such as a phone, tablet, or desktop or laptop computer, which is:
   1. connected to the same network as CA Infrastructure and/or Network Equipment; and
   2. capable of accessing CA Infrastructure and/or Network Equipment.

## 1. CA Infrastructure and Network Equipment Configuration

### 1.1 Network Segmentation

CA Infrastructure MUST be segmented into separate networks based on the functional and/or logical relationships of CA Infrastructure components.

Network segmentation MUST be designed and implemented using appropriate and applicable Network Equipment, such as:
   a. firewalls
   b. network access controls
   c. virtual LANs (VLANs) and VLAN access control lists
   d. physically separate networks
   e. software-defined networking
   f. virtual private networks (VPNs)

Network segmentation MUST be designed and implemented in a manner that:
   1. minimizes attack surfaces;
   2. limits lateral movement within networks;
   3. restricts traffic flow between different network segments; and 
   4. protects all components of the CA Infrastructure from unauthorized access.

### 1.2 Security

#### 1.2.1
CA Infrastructure MUST be in a Physically Secure Environment.
<!-- This should change as described in my comment about the definition of Physically Secure Environment so it's clarified that the level of security expected of the Root CA System is greater than that of the rest of the CA Infrastructure; this and the current NSRs effectively require the same security for everything.-->

<!--
#### 1.1.2.2
Security Support System(s) SHALL be designed, implemented, and configured to:
   1. protect the CA Infrastructure; 
   2. secure connections and communications between components of the CA Infrastructure; and
   3. secure connections and communications between the CA Infrastructure and non-CA Infrastructure (including those with organizational business units that do not provide PKI-related services and those on public networks).
-->

#### 1.2.2
CA Infrastructure and Network Equipment MUST be implemented and configured to authenticate and encrypt connections:
   1. between CA Infrastructure components; and
   2. between CA Infrastructure and non-CA Infrastructure.
<!-- Something more could be added here to address further the existence and expected properties of connections between the CA Infra and external Infra.
A start might be something like: 

Connections between CA Infrastructure and non-CA Infrastructure MUST be secured within a demarkation zone and SHOULD be minimized.
-->

<!--
Combining this and 1.1.6 and 1.1.2.2 into a new 1.2.2

### 1.1.5 
CA Infrastructure by:
   1. removing and/or disabling all connections, applications, services, protocols, and ports that are not used in the CA’s or Delegated Third Party’s operations; and 
   2. allowing only those connections, applications, services, protocols, and ports that are identified as necessary by the CA under the Principle of Least Privilege and approved by the CA or Delegated Third Party.
-->
CA Infrastructure and Network Equipment MUST be implemented and configured in a manner that minimizes unnecessary active components and capabilities such that:
   1. all connections, communications, applications, services, protocols, and ports not used are removed and/or disabled; and 
   2. only connections, communications, applications, services, protocols, and ports necessary and approved under the Principle of Least Privilege are enabled.

#### 1.2.3
Equivalent security MUST be implemented on all Systems on the same network as any CA Infrastructure component.
<!--
### 1.1.6
The CA MUST ensure network segmentation systems or technologies are configured such that only the services, protocols, ports, and communications that the CA has identified as necessary to its operations under the Principle of Least Privilege; and
-->

### 1.3 Change Management

<!--
Rewriting and combining with 1.2.2

Ensure that the CA’s security policies are encompassed within a change management process, which MUST minimally include:
   1. comprehensive documentation; and
   2. review and approval procedures limited to individuals in roles commensurate with the responsibility; and
   
### 1.2.2 
Ensure that all changes to CA Infrastructure follow the change management process required by Section 1.2.1. -->

The CA MUST establish and maintain a change management process which is minimally:
   1. documented comprehensively;
   1. authoritative for all personnel in Trusted Roles, Network Equipment, and the CA Infrastructure;   
   1. reviewed annually; 
   1. updated as needed; and
   1. approved:
      * with each update;
      * prior to going into effect; and
      * by personnel in associated Trusted Roles.

The CA MUST ensure the change management process:
   1. enables identification, documentation, and remediation of risks associated with introducing, modifying, or removing:
      * Trusted Role definitions;
      * personnel in Trusted Roles;
      * Network Equipment; or
      * CA Infrastructure;
   2. addresses managing exceptions and responding to emergencies; and
   3. incorporates procedures for change reversal where applicable.

The CA MUST ensure that all changes to Trusted Role definitions, Trusted Role appointments, CA Infrastructure, and Network Equipment are completed in accordance with this change management process.

## 2. Access Control

### 2.1 Trusted roles

The CA MUST define Trusted Roles necessary, as applicable, to design, build, implement, operate, and maintain its CA Infrastructure and Network Equipment.

Each Trusted Role MUST have its responsibilities, privileges, and access documented. Such documentation MUST be kept up-to-date.

Each Trusted Role MUST be assigned responsibilities, privileges, and access in a manner consistent with:
   1. the Principle of Least Privilege;
   2. requirements of Multi-Party Control; and 
   3. accountability.

#### 2.1.2
The CA MUST ensure personnel act only within the scope of their Trusted Role(s).

<!-- Should no longer be required separately from 1.3
### 2.1.2 
Follow a documented procedure for managing authorized individuals appointed to Trusted Roles, to minimally include:
   1. initial appointment of an individual to a Trusted Role;
   2. modifying an individual's Trusted Role; and
   3. removing an individual from a Trusted Role;
-->

### 2.2 Access Management
<!--
Combining, reordering, and rewriting

#### 2.1.2.1
When an individual's authorization to access a CA System is changed or revoked (for example, by removing a Trusted Role, modifying an individual's Trusted Role, or modifying the defined access associated with a Trusted Role) authentication keys and passwords MUST also be changed or revoked;

### 2.1.3 
Ensure that only personnel assigned to Trusted Roles have access to CA Infrastructure;

### 2.1.5 
Require employees and contractors to observe the Principle of Least Privilege when accessing, or when configuring access privileges on, CA Infrastructure;

### 2.1.6 
Require that each individual in a Trusted Role use a unique credential created by or assigned to that person in order to authenticate to CA Infrastructure;

#### 2.1.6.1 
Group accounts and shared role credentials SHALL NOT be used;
-->
#### 2.2.1
The CA MUST ensure access to CA Infrastructure and/or Network Equipment is limited to personnel assigned to applicable Trusted Roles and based on the Principle of Least Privilege.

##### 2.2.1.1
The CA MUST ensure personnel assigned to Trusted Roles authorized to access or authenticate to CA Infrastructure and/or Network Equipment use unique authentication credentials created by or assigned to the authorized individual.

##### 2.2.1.2
The CA MUST NOT allow group accounts or shared role credentials to access or authenticate to CA Infrastructure and/or Network Equipment. 

##### 2.2.1.3
The CA MUST ensure authentication credentials are changed or revoked when associated authorizations are changed or revoked.

<!--
Slight rewrite and moving up to Trusted roles under 2.1, but also this seems very difficult to actually implement and audit...
### 2.1.4

Implement processes such that an individual only acts within the scope of their Trusted Role;
-->

<!--
The next 3 sections seem rather out of place and difficult to "fix", i.e. restate in a way that addresses their intended function (making sure employee laptops/desktops aren't totally insecure) without referencing somewhat archaic modes of operation for many companies. 

It's also unclear to me whether the intended scope (is it for all company laptop, desktop, phone, tablet... TV? devices, or just stuff like BMCs and devices actually hosting CA Infrastructure). I assume it's the former, but if so I think a lot of devices (and device types) aren't clearly indicated to be in-scope and it's questionable whether and how they should be.

The third section/bullet in particular seems very problematic as it effectively negates any value in the other requirements.

That said, here's my attempt to introduce a definition and reorder/rewrite the requirements to be a bit more generic while maintaining the same level of expected security

### 2.1.7
Require Trusted Roles to log out of or lock workstations when not in active use;

#### 2.1.7.1
CAs and Delegated Third Parties SHALL configure workstations with inactivity time‐outs that automatically log the user off or lock the workstation after a set time of inactivity without input from the user

#### 2.1.7.2
The CA or Delegated Third Party MAY allow a workstation to remain active and unattended if the workstation is otherwise secured and running administrative tasks that would be interrupted by an inactivity time‐out or system lock;

-->
#### 2.2.2 
The CA SHOULD ensure Workstations are configured in a manner that prevents continued access to the Workstation after a set period of inactivity, for example by automatically logging off active users. The allowed and configured duration of inactivity MUST be selected based on the CA's assessment of associated risks.

The CA MAY allow a Workstation to remain active and unattended if the Workstation is otherwise secured and running administrative tasks that would be interrupted by an inactivity time‐out or system lock.

The CA MUST ensure personnel assigned to Trusted Roles log out of or lock Workstations when not in active use.

<!--
FINISHED HERE 7/28/2023
-->
## 2.2 Password-based Authentication

If an authentication control used by a Trusted Role is a username and password, then each CA or Delegated Third Party SHALL implement the following controls:
   1. For accounts that are accessible only within Secure Zones or High Security Zones, require that passwords have at least twelve (12) characters;
   2. For authentications which cross a zone boundary into a Secure Zone or High Security Zone, require Multi‐Factor Authentication. For accounts accessible from outside a Secure Zone or High Security Zone require passwords that have at least eight (8) characters and are not be one of the user’s previous four (4) passwords; and implement account lockout for failed access attempts in accordance with subsection k;
   3. When developing password policies, CAs SHOULD take into account the password guidance in NIST 800‐63B Appendix A.
   4. If the CA has any policy that requires periodic password changes, that period SHALL NOT be less than two years.

## 2.3 CA Infrastructure Access

Each CA or Delegated Third Party SHALL:
### 2.3.1 
Ensure that System access and System account permissions are restricted:
   1. to persons assigned a Trusted Role associated with such access and permissions; and
   2. in accordance with the Principle of Least Privilege;

### 2.3.2
Review all System accounts at least every three (3) months and deactivate any accounts that are no longer necessary for operations;

### 2.3.3 
Lockout account access to CA Infrastructure after no more than five (5) failed access attempts, provided that this security measure:
   1. Is supported by the System;
   2. Cannot be leveraged for a denial of service attack; and
   3. Does not weaken the security of this authentication control;

### 2.3.4
Implement a process that disables all access by an individual to CA Infrastructure within twenty-four (24) hours upon termination of the individual’s employment or contracting relationship with the CA or Delegated Third Party;

<!--### 2.3.5
Enforce Multi‐Factor Authentication for all accounts on CA Infrastructure;

### 2.3.6
Enforce Multi-Factor Authentication and/or multi‐party authentication for all access to CA Infrastructure;-->
The CA MUST enforce Multi-Factor Authentication for all accounts on and access to CA Infrastructure.

The CA MUST enforce Multi‐party Control for all access to physical CA Infrastructure assets.

### 2.3.7
Restrict remote administration of and/or access to CA Infrastructure except when:
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
Implement, as part of a Security Support System, continuous monitoring of CA Infrastructure for modifications not authorized through the change management process outlined in Section 1.2;

### 3.1.2
Identify CA Infrastructure capable of monitoring and logging System activity and enable those capabilities to create audit-compliant logs (for example, to meet the requirements in Section 5.4.1 (3) of the Baseline Requirements for the Issuance and Management of Publicly‐Trusted Certificates);

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
   2. unauthorized changes to CA Infrastructure (as identified by 3.1.1);

### 3.2.3
Require Trusted Role personnel to respond to alerts within twenty-four (24) hours.

Once the responder(s) has confirmed the legitimacy of the alert, the further response MUST include:
   1. identifying the potential impact and severity of the event;
   2. initiating relevant containment actions (such as isolating a System from the network, disabling accounts, or other mitigation measures); and
   3. developing and initiating an appropriate risk-based plan of action to fully remediate the Critical Security Event.

# 4. Vulnerability Detection and Patch Management

CSA CCM stuff goes here(?)