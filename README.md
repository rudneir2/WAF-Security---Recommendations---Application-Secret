# WAF Security
## Recommendations - Application-Secret

in this scenario we have an IT architecture with a workload which we may apply several recommendations described in this section (Application Secret). The diagrams below will help you understand when to consider some of the best practices for Azure Security regarding keys, secrets and encryption and how to apply it.

This is what we have in the architcture below:

A hybrid environment with on-premises, Azure and Office 365 services, that serves a web solution running on Azure, that store data on Azure Storage and communicate with some VMs that holds application code.

![image](https://github.com/rudneir2/WAF-Security---Recommendations---Application-Secret/assets/97529152/7a137bc5-58e6-4883-acd9-9cd31bbfbbd5)

The main component in this scenario are:

1. the Azure Web App that contains the web front end with customer main web site, accessed by the company's end users (A) and also by External Developers that maintin the website (B).
2. the Azure Storage Account with blob service to store web site objects, also accessed by External Developers (B).
3. some Azure VMs that holds the business application code that interact with Web App. These VMs are managed by Local and Remote Admins (C).
4. These Azure VMs is part of an Azure VNET.
5. These Azure VMs have Azure VM disks that holds many important data.
6. All Applications, including Azure Web apps, Azure Storage are authenticated through Azure AD. Azure AD is syncronized with local ADDS (Kerberos based).

## Adding Security Recommendations

Now that we understand our scenario, let's check it out what WAF Security recommends to you regarding "Application Secret". Following we have an architecture with some of the Azure Security services highlighted (blue box) and some of the Azure security services that may be considered to complement the solution. After the architecture diagram, you will have detailed information regarding every security solution described in the diagram.

<diagram>

in the diagram above we have some components that helps in the pre-breach and pos-breach phases of a cybersecurity attack.

1. through Encryption services we may add encryption to Azure VM disk and control this encryption keys with Azure Key Vault services.

2. key vault may hold keys, secrets and certificates for multiple Azure solution, including also Storage keys. Key vault service contains different tiers of service, and we are available to build your dedicated HSM, if your security needs requires for it. Security rotation is another feature available in the Key Vault.

3. Azure Storage account may be defined with different scopes, like File server, blob and others. It contains different types of encryption services, at rest or in transit. It also integrates very well with azure key vault.

4. storage SAS key offers an additional security so you may provide temporary access to your storage data to external people or users with no access to your storage account.

5. Azure AD security services, through RBAC, Managed Identities, Service Principals, adds an additional layer of security, integrating with all Azure services and Azure Key Vault.

6. There are still many powerfull security services available on Azure AD (now called Entra ID) that you may count with to improve your Security posture. Some of them will be described in details in other WAF security section.

7. Through Azure policies you may automate some implementations on Azure and stabilish some security boundaries for your Azure resources. That include, as an example, the installation of Azure Monitoring Agent in an automated way.

8/9. Log Analytics and Sentinel may be used to identify possible breaches and threats once you were not able to stop it with primary Azure security services. You may ingest logs from most of Azure resources including Azure security services.

10. Microsoft Defender for Cloud includes a module that helps you collect information from multiple Azure resources, including Azure Key Vault, and then receive Alerts and Recommendations to keep your environment secure.

From this point ... we should come with the current WAF Security content in the section "Application Secret".




