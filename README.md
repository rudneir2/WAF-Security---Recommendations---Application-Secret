# WAF20 - Application Secret

**NOTE:** 
This content below is supposed to be part of the WAF 20 document, to be embedded in the chapter "WAF > Recommendations > SE:09 Application Secret".

[https://review.learn.microsoft.com/en-us/azure/well-architected/security/segmentation?branch=release-waf-2-0-1](https://review.learn.microsoft.com/en-us/azure/well-architected/security/application-secrets?branch=release-waf-2-0-1)

in this scenario, we have an IT architecture with some examples which we may apply several recommendations described in this section. The diagram below will help you understand when to consider some of the best practices for Azure Security regarding keys, secrets, and encryption and how to apply them.

![image](https://github.com/rudneir2/WAF-Security---Recommendations---Application-Secret/assets/97529152/ed121a2e-3366-42a5-b1f7-da41fc3d9e1c)

Let's consider the following in the image above:

1. Through encryption services we may add encryption to Azure VM disk and control these encryption keys with Azure Key Vault services, protecting data residing in Virtual Machine disks from being compromised by the bad actors.

2. Different services may be accessed from external personas, like customer's clients accessing Web Apps that are exposed to the internet. Those Web apps usually contains some types of data that are stored in object storage repositories, also running on the cloud.

3. Application and Data administrators may have direct access to those Storage repositories, such as object storage or file servers, running on Azure. Azure security services deliver security services to protect your data on Storage running in the Azure cloud, such as Storage encryption, SAS (Shared Access Signature), which provide users, temporary access, and others.

key vault may hold keys, secrets, and certificates for multiple Azure solutions, including also Storage keys. Key vault service contains different tiers of service, including a dedicated HSM and features like Security key rotation.

4. Any service running on Azure will require authentication through Entra ID (formerly known as Azure AD). Entra ID security services may add great protection to your environment and users, avoiding many types of attacks involving users' accounts, such as lateral movement or privileges escalation. Just to mention some of them, through RBAC, Managed Identities, and Service Principals, you may add protection to your resources by setting the right level of permission for them. MFA (Multiple Factors of Authentication), Conditional Access, and Password protection are other important security services available to protect your identities.

5. Through Azure policies you may automate some implementations on Azure and provide security boundaries for your Azure resources. That includes, as an example, the installation of Azure Monitoring Agent in an automated way, allowing different resources, such as Virtual Machines, Operating Systems, Network services, storage, and Identity send logs to Log Analytics and Sentinel.

6. Log Analytics and Sentinel will help you to detect potential attacks on your environment, through different logs and metrics sent to them. Sentinel still allow you to automate responses to the incidents identified through the analytics queries that run on top of the logs ingested on it.

7. Microsoft Defender for Cloud may be integrated to Log Analytics and Sentinel, providing Recommendations and Security Alerts for infrastructure services such as Virtual Machines and Storage, but also to services such as key Vault.

**NOTE:**
If you'd like to understand more about any solution described in the diagram, including acronyms, please refer to this table of contents, from the **Baseline chapter**.
(table to be built)

**This content above is intended to be embedded with current WAF 20 draft content, at the time of this writing (Nov 2023), still in development**

### DISCLAIMER
**This is only a draft with a recommendation to have WAF 2.0 Security doc based on a common IT environment context and explanation about Security recommendations on top of some architecture diagrams for a better understanding. It is not a final version. Diagrams, its colors, text information are all draft and suggestions, that may be changed and refined.**



