Azure Hybrid solution


<!-- TOC -->
* [Requirement: Consolidation of account management based on internal Active Directory.](#requirement-consolidation-of-account-management-based-on-internal-active-directory)
* [Requirement: Adherence to best practices for domain naming.](#requirement-adherence-to-best-practices-for-domain-naming)
* [Requirement: Security department's requirement for enforcing MFA in VPN and line-of-business apps.](#requirement-security-departments-requirement-for-enforcing-mfa-in-vpn-and-line-of-business-apps)
* [Requirement: Issues with the remote password reset process and reducing the help desk workload.](#requirement-issues-with-the-remote-password-reset-process-and-reducing-the-help-desk-workload)
* [Requirement: Requirement for emergency access to Azure AD and monitoring of related activities.](#requirement-requirement-for-emergency-access-to-azure-ad-and-monitoring-of-related-activities)
* [Requirement: Requirement to allow authorization based on user authentication and client endpoint compliance state.](#requirement-requirement-to-allow-authorization-based-on-user-authentication-and-client-endpoint-compliance-state)
* [Requirement: Requirement for secure and manageable collaboration with Vasil Brokers.](#requirement-requirement-for-secure-and-manageable-collaboration-with-vasil-brokers)
* [Requirement: Security department's requirement to block compromised and incorrect passwords.](#requirement-security-departments-requirement-to-block-compromised-and-incorrect-passwords)
* [Requirement: Requirement to maintain operational capability during cloud or internal infrastructure outages.](#requirement-requirement-to-maintain-operational-capability-during-cloud-or-internal-infrastructure-outages)
* [Requirement: Requirement for secure connectivity between on-premises and Azure environments.](#requirement-requirement-for-secure-connectivity-between-on-premises-and-azure-environments)
* [Requirement: Requirement for granular access control to Azure resources.](#requirement-requirement-for-granular-access-control-to-azure-resources)
<!-- TOC -->

# Requirement: Consolidation of account management based on internal Active Directory.

Solution: **Azure AD Connect** Implementation

Actions:

    - Synchronize On-Premise AD with Azure AD.
    - Configure Password Hash Synchronization and Single Sign-On (SSO).


# Requirement: Adherence to best practices for domain naming.

Solution: Rename AD Domain

Actions:
    
    Change the internal domain name to a public domain subdomain


# Requirement: Security department's requirement for enforcing MFA in VPN and line-of-business apps.

Solution: Multi-Factor Authentication (MFA)

Actions:

    Enforce MFA for all users accessing remotely and create Conditional Access Policies.


# Requirement: Issues with the remote password reset process and reducing the help desk workload.

Solution:  Self-Service Password Reset (SSPR)

Actions:

    Implement Azure AD Self-Service Password Reset and enable Azure AD Identity Protection.


# Requirement: Requirement for emergency access to Azure AD and monitoring of related activities.

Solution: Emergency Access & Auditing

Actions:

    Create emergency access accounts and enable Azure AD Sign-in and Audit logs.


# Requirement: Requirement to allow authorization based on user authentication and client endpoint compliance state.

Solution: Endpoint Compliance and Conditional Access

Actions:

    Use Intune for endpoint management and create Conditional Access Policies based on compliance state.


# Requirement: Requirement for secure and manageable collaboration with Vasil Brokers.

Solution: Business-to-Business (B2B) Collaboration

Actions:

    Utilize Azure AD B2B for collaboration and assign role-based access.

# Requirement: Security department's requirement to block compromised and incorrect passwords.

Solution: Password Policies & Monitoring

Actions:

    Implement Azure AD Password Protection and monitor for compromised accounts using Azure AD Identity Protection.

# Requirement: Requirement to maintain operational capability during cloud or internal infrastructure outages.

Solution: Hybrid Scenario Handling
 
Actions:

    Ensure availability of on-premise resources during cloud outages and vice versa.


# Requirement: Requirement for secure connectivity between on-premises and Azure environments.

Solution: Network Security and Connectivity

Actions:

    Implement secure and seamless connectivity solutions and enforce network security policies.


# Requirement: Requirement for granular access control to Azure resources.

Solution: Role-based Access Control (RBAC)

Actions:

    Implement RBAC for Azure resources.



#Actions
- Setup of Azure AD Connect, AD Domain Rename, MFA, and SSPR
- Setup of Endpoint Compliance, Conditional Access, and Intune for Device Management.
- B2B Collaboration Setup, Password Policies & Monitoring, and RBAC Setup.


Open Points

Pass Through Agent (PTA) is needed? 

Federation Proxy?


# References

https://www.youtube.com/watch?v=SS-5qDgPvJU  How to get started with hybrid identity in Azure Active Directory

https://learn.microsoft.com/en-us/azure/active-directory/hybrid/connect/choose-ad-authn





Microsoft Entra Connect features

    Password hash synchronization - A sign-in method that synchronizes a hash of a users on-premises AD password with Microsoft Entra ID.

    Pass-through authentication - A sign-in method that allows users to use the same password on-premises and in the cloud, but doesn't require the additional infrastructure of a federated environment.

    Federation integration - Federation is an optional part of Microsoft Entra Connect and can be used to configure a hybrid environment using an on-premises AD FS infrastructure. It also provides AD FS management capabilities such as certificate renewal and additional AD FS server deployments.

    Synchronization - Responsible for creating users, groups, and other objects. As well as, making sure identity information for your on-premises users and groups is matching the cloud. This synchronization also includes password hashes.

    Health Monitoring - Microsoft Entra Connect Health can provide robust monitoring and provide a central location in the Microsoft Entra admin center to view this activity.





