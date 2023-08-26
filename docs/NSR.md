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

**Critical Security Event**: An event, set of circumstances, or anomalous activity that could lead to a circumvention of CA Infrastructure security controls or compromise of CA Infrastructure integrity or operational continuity, including, but not limited to, excessive login attempts, attempts to access prohibited resources, DoS/DDoS attacks, attacker reconnaissance, excessive traffic at unusual hours, signs of unauthorized access, system intrusion, or physical compromise of component integrity.

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

**Requirements**: The Network and Certificate System Security Requirements found in this document.

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

<!-- Added FIPS 140-3 -->
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

# Requirements
## 1. CA Infrastructure and Network Equipment Configuration

### 1.1 Network Segmentation

#### 1.1.1
CA Infrastructure MUST be segmented into separate networks based on the functional and/or logical relationships of CA Infrastructure components.

##### 1.1.1.1
Network segmentation MUST be designed and implemented using appropriate and applicable Network Equipment, such as:
   * firewalls
   * network access controls
   * virtual LANs (VLANs) and VLAN access control lists
   * physically separate networks
   * software-defined networking
   * virtual private networks (VPNs)

###### 1.1.1.2
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
Rewriting and combining with 1.2.2; should ensure alignment with WTCA and ETSI

Ensure that the CA’s security policies are encompassed within a change management process, which MUST minimally include:
   1. comprehensive documentation; and
   2. review and approval procedures limited to individuals in roles commensurate with the responsibility; and
   
### 1.2.2 
Ensure that all changes to CA Infrastructure follow the change management process required by Section 1.2.1. -->

The CA MUST establish and maintain a change management process which is minimally:
   1. documented comprehensively;
   1. authoritative for:
      1. all personnel in Trusted Roles;
      2. management of Network Equipment; and
      3. management of CA Infrastructure;   
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

The CA MUST ensure that all changes are completed in accordance with this change management process for:
   1. Trusted Role definitions;
   2. Trusted Role appointments;
   3. CA Infrastructure; and
   4. Network Equipment.

## 2. Access Control

### 2.1 Trusted roles

The CA MUST define Trusted Roles necessary — as applicable — to design, build, implement, operate, and maintain its CA Infrastructure and Network Equipment.

Each Trusted Role MUST have its responsibilities, privileges, and access documented. Such documentation MUST be kept up-to-date. <!-- how up to date? -->

Each Trusted Role MUST be assigned responsibilities, privileges, and access in a manner consistent with:
   1. the Principle of Least Privilege; and
   2. requirements of Multi-Party Control.
   <!-- Removing:
   ; and 
   3. accountability.
   What does accountability mean here? -->

#### 2.1.1
<!--
Slight rewrite and moving up to Trusted roles under 2.1, but also this seems very difficult to actually implement and audit...

### 2.1.4 -> 2.1.1
Implement processes such that an individual only acts within the scope of their Trusted Role;
-->
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
Combining, reordering, and rewriting. Also bringing up some of the requirements from further down that are directly related to managing access to CA Infrastructure and Network Equipment.

### 2.1.3 -> 2.2.1
Ensure that only personnel assigned to Trusted Roles have access to CA Infrastructure;

### 2.1.5  -> 2.2.1
Require employees and contractors to observe the Principle of Least Privilege when accessing, or when configuring access privileges on, CA Infrastructure;

### 2.3.1  -> 2.2.1
Ensure that System access and System account permissions are restricted:
   1. to persons assigned a Trusted Role associated with such access and permissions; and
   2. in accordance with the Principle of Least Privilege;

### 2.1.6 -> 2.2.1.1
Require that each individual in a Trusted Role use a unique credential created by or assigned to that person in order to authenticate to CA Infrastructure;

#### 2.1.6.1 -> 2.2.1.2
Group accounts and shared role credentials SHALL NOT be used;

#### 2.1.2.1 -> 2.2.1.3
When an individual's authorization to access a CA System is changed or revoked (for example, by removing a Trusted Role, modifying an individual's Trusted Role, or modifying the defined access associated with a Trusted Role) authentication keys and passwords MUST also be changed or revoked;

### 2.3.4 -> 2.2.1.3
Implement a process that disables all access by an individual to CA Infrastructure within twenty-four (24) hours upon termination of the individual’s employment or contracting relationship with the CA or Delegated Third Party;

### 2.3.2 -> 2.2.1.4
Review all System accounts at least every three (3) months and deactivate any accounts that are no longer necessary for operations;

### 2.3.3 -> 2.2.1.5
Lockout account access to CA Infrastructure after no more than five (5) failed access attempts, provided that this security measure:
   1. Is supported by the System;
   2. Cannot be leveraged for a denial of service attack; and
   3. Does not weaken the security of this authentication control;
-->
#### 2.2.1
The CA MUST ensure access to CA Infrastructure and/or Network Equipment is:
   1. limited to personnel assigned to applicable Trusted Roles; and
   2. based on the Principle of Least Privilege.
##### 2.2.1.1
The CA MUST ensure personnel assigned to Trusted Roles authorized to access or authenticate to CA Infrastructure and/or Network Equipment use unique authentication credentials created by or assigned to the authorized individual.
##### 2.2.1.2
The CA MUST NOT allow group accounts or shared role credentials to authenticate to or access CA Infrastructure and/or Network Equipment. 
##### 2.2.1.3
The CA MUST ensure authentication credentials are changed or revoked when associated authorizations are changed or revoked.

The CA MUST ensure all access to CA Infrastructure and Network Equipment is disabled for personnel within twenty-four (24) hours of the termination of an individual's employment or contracting relationship.
<!--QUESTIONS:
1. Combine these last two? There could then be a timeline for when authentication credentials need to be changed or revoked generally that's the same or different from "when associated authorizations are changed or revoked due to the termination of an individual's employment or contracting relationship"
-->
##### 2.2.1.4
<!--Maybe expand on what the review is for? e.g.
This review MUST:
   1. ensure each account's necessity to the CA Infrastructure;
   2. ensure each account meets these Requirements;
   3. deactivate or remove any account which is not necessary; and
   4. update, deactivate, remove, or otherwise remediate any account which does not meet these Requirements.-->
The CA MUST ensure any account capable of authenticating to or accessing CA Infrastructure or Network Equipment is reviewed at a minimumum of every three (3) months.
<!-- Should Network Equipment be included here? -->
The CA MUST ensure any account that is not necessary for the operation of CA Infrastructure or Network Equipment is deactivated or removed such that the account is no longer capable of authenticating to or accessing CA Infrastructure nor Network Equipment.

##### 2.2.1.5
<!-- This whole requirement seems so neutered by the provisions allowing CAs to not enforce it that I'm not sure it's very useful or provides meaningful value to the NSRs. For example, I would posit that _by definition_ *any and every* automatic lockout function *can* be used to cause a denial of service, using the Oxford definition (since we don't have one) of "an interruption in an authorized user's access to a computer network"
Beyond that, there's no specification of how long the lockout is for or when the failed attempts need to occur (since it doesn't say it's temporary, is this being interpreted as requiring CAs to indefinitely lock out accounts after 5 failed access attempts? Do the attempts need to happen within a specific period of time?)
If that is indeed the interpretation, I would expect every CA to consider this as either being able to cause a denial of service or a weakening of the authentication control and, therefore, not really implement it? Or do so in some different way than that interpretation requires, which again circles back to this requirement not being meaningful in practice.
I'm also not sure I understand the, seemingly circular, logic of "lockout accounts as long as doing so doesn't weaken the security of locking out accounts"

All that said, here's my attempt at a rewrite/clarification to maintain what I believe to be the intent. I'm not particularly happy even with the rewrite, but for the sake of keeping the requirement unchanged I've included it anyway.

[Originating requirement]
k. Lockout account access to Certificate Systems after no more than five (5) failed access attempts, provided that this security measure;
    Is supported by the Certificate System,
    Cannot be leveraged for a denial of service attack, and
    Does not weaken the security of this authentication control;
-->
The CA MUST ensure security measures are implemented which minimize the susceptability of CA Infrastructure to unauthorized access through repeated attempts to authenticate to or access an account on or with access to CA Infrastructure. These measures SHOULD prevent brute-force attacks which systematically enumerate authentication credentials such as username and password combinations. These measures SHOULD be based on a Risk Assessment.
<!-- We could also consider listing examples of typical measures, like account lockout policies, rate limiting, and IP blocking. We could also tie the role of these measures more directly to the MFA requirements of 2.2.3, the Password Complexity requirements of 2.2.4, and the monitoring/logging requirements in section 3 (3.1 currently, but that'll probably change). -->

#### 2.2.2 
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

The CA SHOULD ensure Workstations are configured in a manner that prevents continued access to the Workstation after a set period of inactivity, for example by automatically logging off active users. The allowed and configured duration of inactivity MUST be selected based on the CA's assessment of associated risks.

The CA MAY allow a Workstation to remain active and unattended if the Workstation is otherwise secured and running administrative tasks that would be interrupted by an inactivity time‐out or system lock.

The CA MUST ensure personnel assigned to Trusted Roles log out of or lock their Workstation(s) when not in active use.
<!-- Does this mean Trusted Roles just wander around logging out of or locking workstations that no one's using? :thinking_face:
(I added "their" to try to prevent such an interpretation)-->

#### 2.2.3
<!--
Below is a consolidation of requirements for Multi-Factor Authentication or Multi-Party Control.

1.j. Implement Multi-Factor Authentication to each component of the Certificate System that supports Multi-Factor Authentication;

2.m. Enforce Multi-Factor Authentication OR multi-party authentication for administrator access to Issuing Systems and Certificate Management Systems;

2.n. Enforce Multi-Factor Authentication for all Trusted Role accounts on Certificate Systems (including those approving the issuance of a Certificate, which equally applies to Delegated Third Parties) that are accessible from outside a Secure Zone or High Security Zone

### 2.3.5
Enforce Multi‐Factor Authentication for all accounts on CA Infrastructure;

### 2.3.6
Enforce Multi-Factor Authentication and/or multi‐party authentication for all access to CA Infrastructure;-->
The CA MUST enforce the use of Multi-Factor Authentication for:
   1. accounts on CA Infrastructure; and 
   2. access to CA Infrastructure.

The CA MUST enforce the use of Multi-Party Control for access to any physical CA Infrastructure component.
#### 2.2.4 
<!--
Below is a rephrasing of 2.g to:
1. Remove prose not related to requirements
2. Reformat to align with document style
3. Consolidation or removal of duplicative requirements

2.g. If an authentication control used by a Trusted Role is a username and password, then, where technically feasible, implement the following controls:

    #. For accounts that are accessible only within Secure Zones or High Security Zones, require that passwords have at least twelve (12) characters;
    #. For authentications which cross a zone boundary into a Secure Zone or High Security Zone, require Multi-Factor Authentication. For accounts accessible from outside a Secure Zone or High Security Zone require passwords that have at least eight (8) characters and are not be one of the user's previous four (4) passwords; and implement account lockout for failed access attempts in accordance with subsection k;
    #. When developing password policies, CAs SHOULD take into account the password guidance in NIST 800-63B Appendix A.
    #. Frequent password changes have been shown to cause users to select less secure passwords. If the CA has any policy that specifies routine periodic password changes, that period SHOULD NOT be less than two years. Effective April 1, 2020, if the CA has any policy that requires routine periodic password changes, that period SHALL NOT be less than two years.

## 2.2 Password-based Authentication
If an authentication control used by a Trusted Role is a username and password, then each CA or Delegated Third Party SHALL implement the following controls:
   1. For accounts that are accessible only within Secure Zones or High Security Zones, require that passwords have at least twelve (12) characters;
   2. For authentications which cross a zone boundary into a Secure Zone or High Security Zone, require Multi‐Factor Authentication. For accounts accessible from outside a Secure Zone or High Security Zone require passwords that have at least eight (8) characters and are not be one of the user’s previous four (4) passwords; and implement account lockout for failed access attempts in accordance with subsection k;
   3. When developing password policies, CAs SHOULD take into account the password guidance in NIST 800‐63B Appendix A.
   4. If the CA has any policy that requires periodic password changes, that period SHALL NOT be less than two years.
-->
The CA SHOULD ensure passwords used as authenticatoin credentials for accounts on CA Infrastructure, Network Equipment, or Workstations are generated and managed in accordance with NIST 800-63B Appendix A.

The CA SHALL NOT require periodic password changes with a period less then two (2) years.

The CA MUST ensure passwords used as authentication credentials for accounts on CA Infrastructure have a minimum of twelve (12) characters.

The CA MUST ensure passwords used as authentication credentials for accounts on Network Equipment or Workstations have a minimum of eight (8) characters.
#### 2.2.5
<!-- 
Slight rephrasing the VPN requirements, also added a definition of "Requirements" since that's used even in prod NSRs, but isn't actually defined.

[Originating Requirements]
2.o. Restrict remote administration or access to an Issuing System, Certificate Management System, or Security Support System except when:

    the remote connection originates from a device owned or controlled by the CA or Delegated Third Party,

    the remote connection is through a temporary, non-persistent encrypted channel that is supported by Multi-Factor Authentication, and

    the remote connection is made to a designated intermediary device

    i. located within the CA’s network, ii. secured in accordance with these Requirements, and iii. that mediates the remote connection to the Issuing System.

### 2.3.7
Restrict remote administration of and/or access to CA Infrastructure except when:
   1. the remote connection originates from a device owned or controlled by the CA or Delegated Third Party;
   2. the remote connection is through a temporary, non‐persistent encrypted channel that is authenticated using Multi‐Factor Authentication; and
   3. the remote connection is made to a designated intermediary device which:
      * is located within the CA’s network;
      * is secured in accordance with these Requirements; and
      * mediates the remote connection to the CA System.
-->
The CA MUST ensure any remote connection which enables administration of and/or access to CA Infrastructure:
   1. originates from a Workstation owned and/or controlled by the CA;
   2. is made through a temporary, non‐persistent, and encrypted channel;
   3. is authenticated using Multi‐Factor Authentication; and
   4. is made to a Network Equipment asset which:
      * is located within the CA’s network;
      * is secured in accordance with these Requirements; and
      * mediates the remote connection to the CA Infrastructure.
<!-- I think there is still room for improvement on this one (e.g. "mediates" isn't super clear). Aside from that, it's not entirely clear that the limitations set here are balanced to be entirely appropriate/necessary for the security of the CA Infrastructure; I'm not sure what exactly, but it seems like something here could be removed with no decrease in security. -->

## 3 Logging, Monitoring, Auditing, and Incident Response
<!--
Certification Authorities and Delegated Third Parties SHALL:

a. Implement a System under the control of CA or Delegated Third Party Trusted Roles that continuously monitors, detects, and alerts personnel to any modification to Certificate Systems, Issuing Systems, Certificate Management Systems, Security Support Systems, and Front-End / Internal-Support Systems unless the modification has been authorized through a change management process. The CA or Delegated Third Party shall respond to the alert and initiate a plan of action within at most twenty-four (24) hours;

b. Identify those Certificate Systems under the control of CA or Delegated Third Party Trusted Roles capable of monitoring and logging system activity, and enable those systems to log and continuously monitor the events specified in Section 5.4.1 (3) of the Baseline Requirements for the Issuance and Management of Publicly-Trusted Certificates;

c. Implement automated mechanisms under the control of CA or Delegated Third Party Trusted Roles to process logged system activity and alert personnel, using notices provided to multiple destinations, of possible Critical Security Events;

d. Require Trusted Role personnel to follow up on alerts of possible Critical Security Events;

e. Monitor the integrity of the logging processes for application and system logs through continuous automated monitoring and alerting or through a human review to ensure that logging and log-integrity functions are effective. Alternatively, if a human review is utilized and the system is online, the process must be performed at least once every 31 days.

f. Monitor the archival and retention of logs to ensure that logs are retained for the appropriate amount of time in accordance with the disclosed business practices and applicable legislation.

g. If continuous automated monitoring and alerting is utilized to satisfy sections 1.h. or 3.e. of these Requirements, respond to the alert and initiate a plan of action within at most twenty-four (24) hours.
-->
### 3.1 Logging and Monitoring
<!-- 
Here I'm primarily rewording in an attempt to improve clarity and flow/readability of the requirements, adding some (imo) logical expectations as SHOULDs in a couple places.

[Originating Requirements]
3.a. Implement a System under the control of CA or Delegated Third Party Trusted Roles that continuously monitors, detects, and alerts personnel to any modification to Certificate Systems, Issuing Systems, Certificate Management Systems, Security Support Systems, and Front-End / Internal-Support Systems unless the modification has been authorized through a change management process. The CA or Delegated Third Party shall respond to the alert and initiate a plan of action within at most twenty-four (24) hours;
>> Just the first part, not the alerting/plan of action which is in 3.2

3.b. Identify those Certificate Systems under the control of CA or Delegated Third Party Trusted Roles capable of monitoring and logging system activity, and enable those systems to log and continuously monitor the events specified in Section 5.4.1 (3) of the Baseline Requirements for the Issuance and Management of Publicly-Trusted Certificates;

3.e. Monitor the integrity of the logging processes for application and system logs through continuous automated monitoring and alerting or through a human review to ensure that logging and log-integrity functions are effective. Alternatively, if a human review is utilized and the system is online, the process must be performed at least once every 31 days.

3.f. Monitor the archival and retention of logs to ensure that logs are retained for the appropriate amount of time in accordance with the disclosed business practices and applicable legislation.

### 3.1.1
Implement, as part of a Security Support System, continuous monitoring of CA Infrastructure for modifications not authorized through the change management process outlined in Section 1.2;

### 3.1.2
Identify CA Infrastructure capable of monitoring and logging System activity and enable those capabilities to create audit-compliant logs (for example, to meet the requirements in Section 5.4.1 (3) of the Baseline Requirements for the Issuance and Management of Publicly‐Trusted Certificates);

### 3.1.3
Monitor the integrity of System logging processes through:
    a Security Support System's continuous automated monitoring; or
    a review by personnel acting in a Trusted Role at least once every 31 days;

### 3.1.4
Monitor the archival and retention of logs to ensure that logs are retained for the appropriate amount of time in accordance with the disclosed business practices and applicable legislation.
-->
#### 3.1.1
The CA MUST identify and document the monitoring and logging capabilities of CA Infrastructure and Network Equipment.

The CA SHOULD establish, evaluate, and maintain policies and procedures for
   1. identifying and utilizing the monitoring and logging capabilities of CA Infrastructure and Network Equipment; and
   2. retaining, parsing, securing, and archiving the audit logs output by CA Infrastructure and Network Equipment.
<!-- This is intended to be helpful additional guidance that's almost certainly already done by most or all CAs. I think the first line is clearly part of 3.1.1, 3.1.1.1, and 3.1.1.2, but the second part is imo also strongly implied by 3.1.2.1, 3.2, etc.-->
The CA SHOULD review and update such policies and procedures at least annually.

##### 3.1.1.1
The CA MUST ensure the monitoring and logging capabilities of CA Infrastructure and Network Equipment are enabled to the extent and as necessary to meet
   1. these Requirements; and
   2. applicable obligations which depend on such audit logs (such as the requirements in Section 5.4.1 (3) of the Baseline Requirements for the Issuance and Management of Publicly‐Trusted Certificates).

##### 3.1.1.2
The CA MUST ensure audit logs produced by the monitoring and logging capabilities of CA Infrastructure and Network Equipment include activities and/or events that occur on CA Infrastructure
   1. necessary to detect possible:
      1. Critical Security Events; and
      2. modifications to CA Infrastructure not authorized through the change management process outlined in Section 1.3; and
   2. with sufficient detail to meet
      1. these Requirements; and
      2. applicable obligations which depend on such audit logs (such as the requirements in Section 5.4.1 (3) of the Baseline Requirements for the Issuance and Management of Publicly‐Trusted Certificates).

#### 3.1.2
<!--
3.e. Monitor the integrity of the logging processes for application and system logs through continuous automated monitoring and alerting or through a human review to ensure that logging and log-integrity functions are effective. Alternatively, if a human review is utilized and the system is online, the process must be performed at least once every 31 days.
>> alerting moved down to 3.2

### 3.1.3
Monitor the integrity of System logging processes through:
   1. a Security Support System's continuous automated monitoring; or
   2. a review by personnel acting in a Trusted Role at least once every 31 days;
-->
The CA MUST ensure the integrity of logging processes within CA Infrastructure is monitored through
   1. continuous automated monitoring operating within CA Infrastructure; or
   2. a review by personnel assigned to applicable Trusted Roles at least once every 31 days.
<!-- 
I'm intentionally not including the "system is online" requirement here based on the assumption(s) that:
   1. we'll be moving the Root CA System requirements to their own section or possibly even document (as, at that point, we're not really talking about a network — we're talking about a _lack_ of a network — and we're not really talking about a security system — we're talking very specifically about a much narrower scope, the Root CA System, which is far from anything resembling a general security system (Though I'll admit I also don't recall if separating it into its own document has already been discussed and rejected by majority consensus)); 
   2. that none of the other parts of CA Infrastructure are kept inherently, persistently, or in a default state of "offline", like a Root CA System;
   3. that the phrase in the current requirements "if a human review is utilized and the system is online" was/is intended to specifically (or at least primarily) refer to the Root CA System; and
   4. that, while I don't think it'd be the best idea to _mandate_ that a manual review be performed on (inherently, persistently, and in a default state of) offline Root CA Systems, it doesn't seem preternaturally *bad* to _allow_ the CA do monitor their logs in such a way — I don't think it's terribly uncommon for larger CAs with many service offerings to perform an offline key ceremony at least as frequently as monthly.
If any of these assumptions is incorrect, we should probably/possibly re-add the requirement that manual review can only occur for online systems.
-->

<!-- Comparing to similar requirements elsewhere, this should also probably have a detection+criteria (e.g. anomalous or compromised logs) here and then alerting somewhere, probably below like for 3.1.1.2. Not sure I really like how this reads, but I think it conveys the general expectation with the exception of the vagueness of "reasonably suspect".-->
The CA MUST ensure such integrity monitoring is configured and managed in a manner sufficiently effective to identify possible audit log compromise.

#### 3.1.2.1
<!--
There's a bit of somewhat subtle, potentially unnecessary, specificity here in that CAs must currently monitor archival/retention of logs in order to ensure they're retained correctly, but it's not imo true that monitoring is an absolute necessecity for the outcome of having audit logs archived/retained for the appropriate amount of time.
The phrasing "the disclosed business practices" is unclear w.r.t. what it's referencing (seemingly "the CA's disclosed business practices"?), but I think copying the language from 3.1.1.1 and 3.1.1.2 could work here as well to keep this concept consistently referenced.

There are also several very closely adjacent requirements not specified here, such as secure storage and access control. These could be inferred by the requirement that they be retained (which would imply they not be lost, damaged, or otherwise made unavailable in any form other than the form in which they were originally archived/retained), but perhaps highlighting these aspects would help lead to better outcomes.

[Originating Requirements]
### 3.1.4
Monitor the archival and retention of logs to ensure that logs are retained for the appropriate amount of time in accordance with the disclosed business practices and applicable legislation.

f. Monitor the archival and retention of logs to ensure that logs are retained for the appropriate amount of time in accordance with the disclosed business practices and applicable legislation.
-->
The CA MUST ensure audit logs are retained and/or archived for the amount of time necessary to meet
   1. these Requirements; and
   2. applicable obligations which depend on such audit logs (such as the requirements in Section 5.4.1 (3) of the Baseline Requirements for the Issuance and Management of Publicly‐Trusted Certificates).

The CA SHOULD ensure retained and/or archived audit logs are kept and managed in a manner sufficiently effective to prevent unapproved alteration or access.

### 3.2 Audit Log Processing and Alerting
<!-- 
I'm breaking things apart to improve clarity around the various components (processing, alerting, following up). I think there are also fairly substantial issues with 3.d ("follow up" is almost meaningless) and 3.g:
   1. it's not clear how continuous monitoring/alerting satisfy 1.h (a part of 1.h, sure, but all of the change management process certainly doesn't fit into monitoring/alerting)
   2. the requirements for responding and initiating a plan of action are weak/vague
   3. the presence of a timeline for automated monitoring/alerting highlights the stark lack of a timeline for non-automated monitoring/alerting
   4. 3.g requires responding to an alert within 24 hours, but only for 3.e and 1.h, somehow missing the "main" automated alerting requirement which is 3.c

3.c. Implement automated mechanisms under the control of CA or Delegated Third Party Trusted Roles to process logged system activity and alert personnel, using notices provided to multiple destinations, of possible Critical Security Events;

3.d. Require Trusted Role personnel to follow up on alerts of possible Critical Security Events;

3.g. If continuous automated monitoring and alerting is utilized to satisfy sections 1.h. or 3.e. of these Requirements, respond to the alert and initiate a plan of action within at most twenty-four (24) hours.

   1.h. Ensure that the CA’s security policies encompass a change management process, following the principles of documentation, approval and review, and to ensure that all changes to Certificate Systems, Issuing Systems, Certificate Management Systems, Security Support Systems, and Front-End / Internal-Support Systems follow said change management process;

   3.e. Monitor the integrity of the logging processes for application and system logs through continuous automated monitoring and alerting or through a human review to ensure that logging and log-integrity functions are effective. Alternatively, if a human review is utilized and the system is online, the process must be performed at least once every 31 days.

### 3.2.1
Implement automated mechanisms under the control of individuals the CA or Delegated Third Party Trusted Roles to process logged system activity and identify possible Critical Security Events;

### 3.2.2
Alert personnel in relevant Trusted Roles, using notices provided to multiple destinations, of:
    possible Critical Security Events; and
    unauthorized changes to CA Infrastructure (as identified by 3.1.1);

### 3.2.3
Require Trusted Role personnel to respond to alerts within twenty-four (24) hours.
Once the responder(s) has confirmed the legitimacy of the alert, the further response MUST include:
    identifying the potential impact and severity of the event;
    initiating relevant containment actions (such as isolating a System from the network, disabling accounts, or other mitigation measures); and
    developing and initiating an appropriate risk-based plan of action to fully remediate the Critical Security Event.
-->

#### 3.2.1
The CA MUST ensure audit logs are processed:
   1. through automated mechanisms under the control of personnel assigned to applicable Trusted Roles; and
   2. in a manner sufficiently effective to minimally identify possible:
      1. Critical Security Events; and
      2. unauthorized changes to CA Infrastructure.

#### 3.2.2
<!-- 
3.g's reference to 3.e makes it seem that alerts originating not from processing audit logs, but from ensuring audit log integrity should also be included in the same "pipeline" as the 2 classes of alerts that come from processing audit logs. Though there's a requirement to ensure audit log integrity, there's not really a requirement to do something which results in identifying when audit log integrity is compromised, so there's no origin for the "identification" (which, when it occurs, otherwise results in the "alert" which results in the "response" which results in the "plan of action")
So I added that to 3.1.2.
-->
The CA MUST ensure personnel assigned to applicable Trusted Roles are alerted via multiple mechanisms and/or communication channels of identified possible:
   1. audit log compromise;
   2. Critical Security Events; and
   3. unauthorized changes to CA Infrastructure.

#### 3.2.3
The CA MUST ensure personnel assigned to applicable Trusted Roles commence an initial response to alerts of Section 3.2.2 within twenty-four (24) hours of the alert being generated.
<!--
I'm keeping the requirement essentially (i.e. in essence) the same, but I do think it would be an improvement to also identify a requirement for when the initial response must conclude, e.g.
"The CA MUST ensure the initial response is completed within seven (7) days of commencing."
-->

##### 3.2.3.1
The CA MUST ensure the initial response confirms whether the alert identifies a legitimate
   1. audit log compromise;
   2. Critical Security Event; and/or
   3. unauthorized change to the CA Infrastructure.

The CA MUST ensure personnel assigned to applicable Trusted Roles create and follow an incident response plan for all legitimate alerts. 

##### 3.2.3.2
The CA SHOULD ensure incident response plans minimally include:
   1. identification of the potential impact, scope, and severity of the incident;
   2. containment of the incident to minimize further impact; and
   3. identification and mitigation or eradication of the incident root cause(s).

<!--FINISHED HERE 8/26/2023-->
# 4. Vulnerability Detection and Patch Management

CSA CCM stuff goes here(?)