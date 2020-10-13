# Introduction 
The Secure Research Workbench/Enclave/Environment (SRW) is a secure way for researchers to access both data and compute resources in [Microsoft Azure](https://azure.microsoft.com) for research projects. The idea behind the SRW is that researchers and research department administration staff can feel confident that their intellectual property can reside in a secure place that has stringent access control policies preventing exfiltration and unauthorized access to research data and compute. Being a secure implementation of Azure resources, the SRW also complies inherently with government regulatory compliance (GRC) regulations as well.

# Getting Started
## Assumptions
This SRW implementation assumes the following are in place before deploying any SRW Azure resources.
1.	A singular [Azure Active Directory Tenant](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-create-new-tenant) (AAD) and singular [Active Directory Domain Services](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview) (AD DS) are in place. 
2.	Networking in the SRW will follow the Hub-and-Spoke aka Transit Hub Azure networking topology.

    ![](images\hub-n-spoke2.png)

3.	Azure Management Groups are not part of this solution although Azure Blueprints will be. The scope of those blueprints will be evident in the documentation for each Blueprint
4.	Researcher groups will have independent Azure resource groups in the <b>same subscription</b> as the SRW management research group. 
5.  Each resource group will have access controls on the Azure resource level [(IAM)](https://docs.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). Networking and Azure resources connected to a network will use [Azure Network Security Groups](https://docs.microsoft.com/en-us/azure/virtual-network/security-overview) (NSGs) to control network access. 
    * If a deploy Azure platform service (i.e. Azure SQL) supports security <i>inside it's platform boundaries</i>, security will be enforced using that platform's (i.e. SQL Server security) capabilities in addition to the security listed above in point [5.](5.)

# SRW Services in Scope for Deployment
## Infrastructure & Management
* Windows Virtual Desktop
* Azure Monitor - Log Analytics
* Azure Blueprints
* Data Science Virtual Machines
* Azure Key Vault
* Azure CycleCloud (High-Performance Compute)
* Azure Machine Learning Service
* Virtual Networks
## Data Platform
* Azure SQL Server Serverless
## Governance & Regulatory Compliance (GRC)
* Azure Security Center 
    * Enable GRC for HIPAA/NIST
* Azure Sentinel
# Deployed Secure Research Workbench
## [Secure Research Workbench PDF](Visio_PDF.pdf)
![](images\overviewVisio.gif)

# Aspirational Additions to the Secure Research Workbench
* Azure Machine Learning Service - Compute Instances
* Azure DevOps Integration
* Azure Managed Relational Database Management System - PostgreSQL
* Azure API for FHIR
    * IoMT integration for Azure API for FHIR
* Azure Functions Serverless Code Execution Environment
* Azure Kubernetes for Scaled Inferencing

# Credits
This collaboration was originally devised by the US Microsoft Education National team. The members are:
* [Ana Del Campo Mendizabal](https://www.linkedin.com/in/ana-del-campo-mendizabal-96112113/) - del.ana@microsoft.com
* [John Brown](https://www.linkedin.com/in/johnstewartbrown/) - brown.john@microsoft.com
* [Clayton Barlow](https://www.linkedin.com/in/clayton-b-barlow/) - clayton.barlow@microsoft.com
* [Gustavo Lopez](https://www.linkedin.com/in/gustavo-a-lopez/) - gulopez@microsoft.com
* [David Ulloa](https://www.linkedin.com/in/davidulloa/) - daullo@microsoft.com
* [Charles Rice](https://www.linkedin.com/in/cricex/) - crice@microsoft.com
* [Sven Aelterman](https://www.linkedin.com/in/svenaelterman/) - Sven.Aelterman@microsoft.com
* [Paul Yu](https://www.linkedin.com/in/yupaul/) - yu.paul@microsoft.com
* [Marco Di Palma](https://www.linkedin.com/in/marcodipalma/) - mardi@microsoft.com
* [Bill Campman](https://www.linkedin.com/in/bill-campman-a84b8b5/) - billc@microsoft.com
* [Edgar Ferrer](https://www.linkedin.com/in/edgar-ferrer-92748657/) - eferrer@microsoft.com
* [Joey Brakefield](https://www.linkedin.com/in/joeybrakefield/) - joey.brakefield@microsoft.com

# Contribute
Contributions to the code base are MORE than welcome. Please submit your pull requests and we'll do our best to integrate the changes in just a few days!

