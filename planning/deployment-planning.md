# Planning for the Apprenda Platform
Because the Apprenda Platform fills such a well-defined and abstracted role in a complete PaaS solution, you have many options for the infrastructure configuration on which it will run.  In some ways, you should approach this planning process as you would a standard hosting or cloud solution rollout.  Take into account the things about your operations that are most important to you.  Disaster recovery?  Scalability and/or high availability? Ease of access?  Before you read through this reference architecture, take a few minutes to identify the aspects of your cloud strategy that will be most important to you, or your customers, or your internal development teams.

## Public Cloud, Private Datacenter, and Hybrid
Your intended use of the Apprenda Platform will play into how you apply the information included in this reference architecture.  Take into account the types of applications your organization produces - are most applications monoliths?  Are they microservices?  Will you be migrating existing applications into the platform environment or using it only for greenfield development?  How you interpret this reference architecture and formulate an implementation should be informed by your intended use case(s), cloud computing goals, and primary Platform constituents.

Apprenda has no strict dependency on a particular cloud provider or type of infrastructure.  The software leverages the operating system and networking primarily, along with tangential configuration, which allows it function in a variety of configurations on machines running virtually anywhere.  You can install Apprenda on a public cloud provider like AWS, Azue, Google Cloud, or IBM Bluemix.  You can also install it on your own machines inside your private datacenter(s).  You can even install a single instance of Apprenda across public and private machines.

## Optional Infrastructure
The Apprenda Platform per se consists of a series of Windows Services, an Apprenda Core DB deployed on an instance of MS SQL Server, and a number of WCF services and .NET UIs.  This means that a single Windows server with IIS and SQL Server is capable of hosting an Apprenda Platform installation—as well as three-tiered .NET guest applications—but it also means that Windows-based infrastructure is required for core Platform functionality.  Conversely, while additional infrastructure can be configured for the Platform in order to support Java components and Oracle-based storage for guest applications, such additions are superfluous to core Platform functionality.  While hardware/software recommendations have been made for supporting non-essential Platform infrastructure, they are noted as “optional” in this reference architecture.

## A Note About Infrastructure Sizing
The Apprenda Platform is architecturally interesting in that it was designed to manage as little as one server or scale to manage thousands: from your laptop to a datacenter with thousands of CPUs and terabytes of RAM.  The Platform’s job is to maintain a comprehensive view of the infrastructure under its control and usher guest application components around to suitable host servers.  Because applications are first-class citizens to the Apprenda Platform, sizing relies quite heavily on the requirements of guest apps.  The Platform’s resource allocation and utilization tracking engine exists to help operators “slice” the infrastructure into trackable units, which is a great aid in analyzing true app resource usage vs allocation and thus infrastructure sizing and capacity planning. This reference architecture is a starting point.