
## Case description and current state

Bell-Fin JSC Overview:

    Company Profile: Bell-Fin JSC is a midsize financial company based in the USA,
    with headquarters in Galloway, NJ, and another office in San Diego, CA.

IT Infrastructure & Transition:

    Pre-COVID-19: The entire IT infrastructure was on-premises with Windows being the dominant platform. 
    All devices were using Windows 10, maintaining the latest build minus one.
    During COVID-19: To accommodate remote work, the company adopted Office 365 and other SaaS solutions. 
    Employees accessed internal systems via VPN, which didn't meet the granularity and endpoint security assessment needs of the IT and Information Security teams.

Identity and Access Management:

    AD Forest Design: Bell-Fin JSC has been using a single Active Directory Forest design 15 years ago. 
    While the directory's infrastructure is up-to-date, its internal domain naming convention (bell-fin.local) doesn't follow best practices.
    SaaS Account Management: When integrating Microsoft SaaS services and other SaaS solutions, user accounts were manually provisioned as per requests in a single Azure AD tenant (bell-fin.onmicrosoft.com).

Challenges & Concerns:

    Identity Management: There's a need to centralize and consolidate account management using their internal Active Directory.
    Security: The company faced challenges related to MFA enforcement, monitoring of compromised accounts, and blocking unsafe passwords.
    Password Reset: There were incidents involving successful social engineering attacks targeting the Help Desk staff due to issues with the remote password reset process.
    Device Compliance: The company desires to conditionally grant access based on both user authentication and the compliance state of their device.
    Partner Collaboration: Bell-Fin JSC is expanding partnerships, like with Vasil Brokers. They aim to provide access to their business apps to partners without compromising security or overburdening their helpdesk.

In essence, Bell-Fin JSC, post COVID-19, is seeking to upgrade and integrate their identity management solutions, address security concerns, and enhance their collaboration capabilities with partners while ensuring the robustness of their IT infrastructure.


![current situation](currentsituation.jpg)



## Business drivers and goals

Business Drivers:

    Business Continuity and Resilience: The company had to quickly adapt its business processes to SaaS solutions and remote access during the COVID-19 lockdown, highlighting the need for a resilient IT infrastructure that can adapt to unforeseen events.

    Expansion and Collaboration: Bell-Fin JSC is expanding its partner operating model, as shown by its partnership agreement with Vasil Brokers. This suggests a need for scalable and secure collaboration solutions.

    Security Concerns: The company has faced security challenges, such as social engineering attacks against Help Desk personnel and potential vulnerabilities in remote password reset processes.

    Operational Efficiency: The manual provisioning of users in various SaaS solutions indicates inefficiencies in their current processes. Streamlining and automating these processes can improve operational efficiency.

Business Goals:

    Centralized Identity Management: As the business returns to regular operations, there's a clear goal to consolidate the management of its employees' accounts based on the internal Active Directory.

    Enhanced Security: Bell-Fin JSC aims to:
        Implement and enforce multi-factor authentication (MFA) across VPNs, line-of-business apps, and other informational systems.
        Address concerns related to compromised accounts and weak password usage.
        Establish secure methods for password resets, reducing human-related risks.
        Ensure device compliance and secure access for business-critical operations.

    Business Agility: Ensure the company's infrastructure allows for seamless work, regardless of potential cloud service outages or issues with internal systems. This will provide flexibility and ensure operations aren't interrupted by IT disruptions.

    Efficient Partner Collaboration: Implement secure and manageable collaboration methods with partners like Vasil Brokers, without compromising security or placing undue burdens on internal resources.

In summary, Bell-Fin JSC's primary objectives revolve around improving IT resilience, security, operational efficiency, and enhancing collaboration capabilities, all underpinned by a strong emphasis on modern identity and access management solutions.


# Scope

Given the detailed description of Bell-Fin JSC's current state and requirements, the scope of the solution to their problems can be outlined as follows:

1. Identity Management & Synchronization

   Implementing a centralized system to synchronize and manage identities across on-premises AD and Azure AD.
   Transitioning from manual provisioning of users to an automated, unified system for both on-premises and cloud applications.

2. Active Directory Modernization

   Addressing the current non-best-practice naming convention of their AD domain (bell-fin.local).
   Ensuring all domain controllers and schema adhere to the latest and secure configurations.

3. Security Enhancements

   Enforcing Multi-Factor Authentication (MFA) for accessing VPN, line-of-business apps, and other key systems.
   Setting up mechanisms to detect and block compromised account activities and prevent the setting of insecure passwords.
   Implementing Azure AD Identity Protection for continuous monitoring of risks and providing appropriate responses.

4. Remote Password Reset

   Transitioning away from the existing remote password reset process, which is vulnerable to social engineering.
   Introducing Azure AD Self-Service Password Reset (SSPR) with strong identity verification mechanisms.

5. Endpoint Security and Compliance

   Ensuring secure access based on both user authentication and the compliance state of the accessing device.
   Implementing solutions like Intune to monitor and manage device compliance.

6. Emergency Access & Monitoring

   Creating provisions for emergency access to Azure AD without depending on external factors.
   Setting up robust monitoring and auditing systems for critical and elevated activities.

7. Partner Collaboration & Integration

   Setting up a secure and efficient B2B collaboration mechanism with partners like Vasil Brokers.
   Using Azure AD B2B, enabling partner users to authenticate using their native organization's credentials while Bell-Fin JSC provides an additional authentication layer.

8. Resilience & Business Continuity

   Ensuring uninterrupted work capability irrespective of cloud service outages or issues with the internal infrastructure.
   Implementing a hybrid solution, where cloud and on-premises resources back each other up in case of service disruptions.

9. Audit & Review

   Continuous monitoring of all the implemented solutions for optimization and security enhancements.
   Regular auditing and reviews to ensure alignment with best practices and evolving business requirements.

In essence, the solution scope aims to provide Bell-Fin JSC with a modern, secure, and efficient identity and access management system, coupled with enhanced security measures, improved partner collaboration mechanisms, and better business continuity solutions.



# Assumptions

Given the details provided on Bell-Fin JSC's situation, the following assumptions have been made:
1. Infrastructure Readiness

   Assumption: Bell-Fin JSC's existing infrastructure (hardware, network, software) can support the proposed hybrid identity and security solutions.
   Rationale: Implementing Azure AD and other cloud-based solutions require certain infrastructure prerequisites.

2. Domain Modernization

   Assumption: The company is willing to undergo a domain renaming or trust configuration process to align with best practices.
   Rationale: The use of the .local domain naming isn't recommended and may affect certain cloud functionalities.

3. Budget and Licensing

   Assumption: Bell-Fin JSC is prepared to invest in necessary licensing for Azure AD Premium features, Intune, or any other suggested tools.
   Rationale: Features like Azure AD Identity Protection, B2B collaboration, and Intune require premium licenses.

4. Training & Change Management

   Assumption: The company is open to training its IT staff and end-users on new tools, processes, and security measures.
   Rationale: Successful adoption of new technologies often requires education and training.

5. Stakeholder Buy-in

   Assumption: Key stakeholders, including top management and the security department, are supportive of the changes and will cooperate in the implementation phase.
   Rationale: Significant IT transformations often require approval and cooperation from multiple departments.

6. Data & Privacy Compliance

   Assumption: Transitioning to a hybrid model and storing some identity data in the cloud adheres to Bell-Fin JSC's compliance and regulatory requirements.
   Rationale: Financial institutions often face strict regulations regarding data storage and privacy.

7. Endpoint Device Types

   Assumption: The majority, if not all, of the endpoint devices accessing the corporate resources are Windows-based, given the information about Windows 10 migration.
   Rationale: Different endpoint OS types may require varied management solutions.

8. Partner Collaboration Readiness

   Assumption: Partner companies, like Vasil Brokers, have the IT capability and willingness to participate in the Azure AD B2B collaboration method.
   Rationale: B2B collaboration requires actions on both ends for successful implementation.

9. Existing Security Solutions

   Assumption: Bell-Fin JSC doesn’t already have other security solutions in place that could conflict with the proposed measures.
   Rationale: It's crucial to ensure compatibility and prevent overlaps in security solutions.

10. Backup & Recovery

    Assumption: The company has effective backup and disaster recovery solutions in place for their on-premises systems.
    Rationale: Hybrid solutions rely on both on-premises and cloud resources. If one fails, the backup and recovery processes become vital.

In the process of developing a detailed solution and planning the implementation, it's essential to validate these assumptions with Bell-Fin JSC to ensure accuracy and reduce risks.


