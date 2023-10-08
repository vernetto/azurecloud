I need to design a Hybrid Identity Azure solution for Bell-Fin JSC company. Bell-Fin JSC is a midsize financial company based in the USA. It has HQ in Galloway, NJ and an office in San Diego, CA.

Before the COVID-19 the whole IT infrastructure was on premises of the organization with Windows as a dominant platform. 
All PCs and laptops were successfully migrated to Windows 10 sticking to the latest build minus one. 
During the lockdown, company had to recreate some of the business processes based on Office 365 and other SaaS solutions and allow users to access internal systems using VPN. 
IT and Information Security teams are not happy with the solution, as they were not able to provide granular access only to specific systems and do not provide information on connecting endpoint security posture.

Current state of Identity and Access Management system

Bell-fin JSC has implemented the “one Active Directory Forest” design 15 years ago. 
While all the DCs are regularly updated to the latest version of OS and directory schema is being updated to the latest version available, the implementation didn’t follow the best practices. 
For instance, they use bell-fin.local domain name internally. Multiple plans to migrate to a recommended public domain name were not acted upon, but public zone bell-fin.com is owned by the organization.

To speed up Microsoft SaaS services implementation users were provisioned manually per request in a single Entra ID (Azure AD) tenant bell-fin.onmicrosoft.com. 
The same approach was used for every other SaaS solution in use.

Customer requirements

As the business returns to regular operations, time has come to consolidate management of accounts of its employees based on internal Active Directory catalogue.

Security department insists on enforcing multi-factor authentication in VPN, line-of-business apps, and informational systems access.

It is strictly required to keep emergency access to Entra ID (Azure AD) without technical burden in case of global security services outages. 
Instead, the company requires strict audit and monitoring of any activities linked to these accounts.

Security department requires to implement monitoring of compromised accounts and block deliberately incorrect passwords from being set during password change.

Several successful social engineering attacks against Help Desk personal in the past have identified problems with the remote password reset process used. 
Company wants to exclude human actors from the process and ensure strict identity verification during the operation.

The customer asks to enable authorization in specific scenarios (access to business-critical data/apps, administrative tasks) based on a combination of user authentication and client endpoint compliance state. 
And only require access from domain joined devices for the most critical use cases.

The company is expanding its partner operating model and has already signed an extended partnership agreement with Vasil Brokers company. 
They plan to provide users of the partner organization with an access to a range of internal business apps using Windows Integrated Authentication. 
Security team is opposed to providing internal Active Directory accounts and passwords to partner employees, as it would lead to account compromise on the partner side and place a significant additional workload on the local Help Desk dealing with account lifecycle requests. 
An ideal solution would allow partner-side authentication using internal accounts, while bell-fin would only provide 2nd factor of authentication, to minimize account sharing, and partner group business lead should be able to evaluate partner user access on a regular basis.

The final solution should not affect the ability of bell-fin users to work inside the organization in case of cloud service outages, but at the same time provide the ability to work in cloud services if the internal infrastructure is unavailable

