___
**Topics:**
- [[#What is Cloud Computing?|What is Cloud Computing?]]
	- [[#What is Cloud Computing?#On-Premise|On-Premise]]
	- [[#What is Cloud Computing?#Cloud Providers|Cloud Providers]]
- [[#Evolution of Cloud Hosting|Evolution of Cloud Hosting]]
	- [[#Evolution of Cloud Hosting#Dedicated Server|Dedicated Server]]
	- [[#Evolution of Cloud Hosting#Virtual Private Servers (VPS)|Virtual Private Servers (VPS)]]
	- [[#Evolution of Cloud Hosting#Shared Hosting|Shared Hosting]]
- [[#What is a Cloud Service Provider (CSP)|What is a Cloud Service Provider (CSP)]]
	- [[#What is a Cloud Service Provider (CSP)#Landscape of CSPs|Landscape of CSPs]]
- [[#Gartner Magic Quadrant for Cloud|Gartner Magic Quadrant for Cloud]]
- [[#Common Cloud Services|Common Cloud Services]]
- [[#AWS Technology Overview|AWS Technology Overview]]
- [[#Types of Cloud Computing|Types of Cloud Computing]]
	- [[#Types of Cloud Computing#SaaS (Software as a Service)|SaaS (Software as a Service)]]
	- [[#Types of Cloud Computing#PaaS (Platform as a Service)|PaaS (Platform as a Service)]]
	- [[#Types of Cloud Computing#IaaS (Infrastructure as a Service)|IaaS (Infrastructure as a Service)]]
- [[#Cloud Computing Deployment Models|Cloud Computing Deployment Models]]
	- [[#Cloud Computing Deployment Models#Public Cloud|Public Cloud]]
	- [[#Cloud Computing Deployment Models#Private Cloud|Private Cloud]]
	- [[#Cloud Computing Deployment Models#Hybrid Cloud|Hybrid Cloud]]
	- [[#Cloud Computing Deployment Models#Cross-Cloud|Cross-Cloud]]
- [[#Deployment Model Use Cases|Deployment Model Use Cases]]
___

# What is Cloud Computing?

Cloud computing is on-demand access, via the internet, to computing resources—applications, servers (physical servers and virtual servers), data storage, development tools, networking capabilities, and more—hosted at a remote [data center](https://www.ibm.com/topics/data-centers) managed by a cloud services provider (or CSP). The CSP makes these resources available for a monthly subscription fee or bills them according to usage.[^1]

## On-Premise
- You own the servers
- You hire the IT people
- You pay or rent the real-estate
- You take all the risk

## Cloud Providers
- Someone else owns the servers
- Someone else hires the IT people
- Someone else pays or rents the real-estate
- You are responsible for your configuring cloud services and code, someone else takes care of the rest.

# Evolution of Cloud Hosting

## Dedicated Server

**One physical machine** dedicated **to a single business**. Runs a single web-app/site.
**(Very Expensive, High Maintenance, \*High Security)**

## Virtual Private Servers (VPS)

**One physical machine** dedicated **to a single business**. The physical machine is virtualized into sub-machines. Runs multiple web-apps/sites 
**(Better Utilization and Isolation of Resources)**

## Shared Hosting

**One physical machine**, shared by **hundred of businesses**
Relies on most tenants under-utilizing their resources.
**(Very Cheap, Limited functionality, Poor Isolation)**

# What is a Cloud Service Provider (CSP)

A **Cloud Service Provider (CSP)** is a company which
- provides multiple Cloud Services e.g. tens to thousands of services
- those Cloud Services **can be chained together** to create cloud architectures
- those Cloud Services are accessible **via Single Unified API** eg. AWS API
- those Cloud Services utilized **metered billing** based on usage e.g. per second, per hour
- those Cloud Services have **rich monitoring** built in eg. AWS CloudTrail
- those Cloud Services have an **Infrastructure as a Service (IaaS)** offering
- those Cloud Services offers **automation** via Infrastructure as Code (laC)

![[Pasted image 20230423182429.png|center]]

## Landscape of CSPs

| Tiers                   | Description                                                                                        | Providers                                      |
| ----------------------- | -------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| **Tier-1 (Top Tier)**   | Early to market, wide offering, strong synergies between services, well recognized in the industry | AWS, Azure, GCP, Alibaba Cloud                 |
| **Tier-2 (Mid Tier)**   | Backed by well-known tech companies, slow to innovate and turned to specialization.                | IBM Cloud, Oracle Cloud, Rackspace (Openstack) |
| **Tier-3 (Light Tier)** | Virtual Private Servers (VPS) turned to offer core IaaS offering. Simple, cost-effective           | Vultr, Digital Ocean, Linode                   | 


# Gartner Magic Quadrant for Cloud

Magic Quadrant (MQ) is a series of market research reports published by IT consulting firm [Gartner](https://www.gartner.com/en) that rely on proprietary qualitative data analysis methods to demonstrate market trends, such as direction, maturity and participants.

![[Pasted image 20230423183332.png]]

# Common Cloud Services

The four most common types of cloud services (*the 4 core*) for IaaS sould be

- **Compute**: A virtual computer that can run applications, programs and code.
- **Networking**: A virtual network defining internet connections or network isolations between services or outbound to the internet
- **Storage**: A virtual hard-drive that can store files
- **Databases**: A virtual database for storing reporting data or a database for general purpose web-application

AWS has over **200+** cloud services

# AWS Technology Overview

The 4 core cloud service offerings from AWS are

- **Compute** - EC2 Virtual Machines
- **Networking** - VPC Private Cloud Network
- **Storage** - EBS Virtual Hard drives
- **Database** - RDS SQL Databases

Outside of the 4 core would be
- Analytics
- Application Integration
- AR & VR
- AWS Cost Management
- Blockchain
- Business Applications
- Containers
- Customer Engagement
- Developer Tools
- End User Computing
- Game Tech
- Internet of Things
- Machine Learning
- Management & Governance
- Media Services
- Migration & Transfer
- Mobile
- Quantum Technologies
- Robotics
- Satellites
- Security, Identity & Compliance

A lot right?

# Types of Cloud Computing

## SaaS (Software as a Service)

A product that is run and managed by the service provider.
> *Dont worry about how the service is maintained. It just works and remains available*

Target: For Customers
Example: Gmail, Office365, etc.

## PaaS (Platform as a Service)

Focus on the deployment and management of your apps.
> *Dont worry about, provisioning, configuring, or understanding the hardware or OS*

Target: For Developers
Example: Elasticbeanstalk, Heroku, Google App Engine

## IaaS (Infrastructure as a Service)

The basic building blocks for cloud IT. Provides access to networking features, computers and data storage space
> *Don't worry about IT staff, data centers, and hardware*

Target: For Administrators
Example: AWS, Azure, GCP

# Cloud Computing Deployment Models

## Public Cloud

**Everything** (the workload or project) is build on the CSP or also known as **Cloud-Native** or **Cloud First**

## Private Cloud

Everything built on company's datacenters also known as **On-Premise**. The cloud could be **OpenStack**

## Hybrid Cloud

Utilizing both **On-Premise** and a **Cloud Service Provider**.

## Cross-Cloud

Using **Multiple Cloud Providers** Aka multi-cloud. Example **Azure Arc** and **GCP Anthos**.

# Deployment Model Use Cases

| Cloud                                                                                                                                                 | Hybrid                                                                                                                                                                                                                               | On-Premise                                                                                                                                                                                                                                               |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Fully utilizing cloud computing                                                                                                                       | Using both Cloud and On-Premise                                                                                                                                                                                                      | Deploying resources on-premises, using virtualization and resource management tools, is sometimes called "private cloud"                                                                                                                                 |
| Companies that are starting out today or are small enough to make the leap from a VPS to a CSP (Startups, SaaS Offerings, New projects and companies) | Organizations that started with their own datacenter, can't fully move to cloud due to effort of migration or security compliance (Banks, Fintech and Investment Management, Large professional service providers, Legacy on-remise) | Organizations that cannot run on cloud due to strict regulatory compliance or the sheer size of their organization (Public sector e.g. Government, Super sensitive Data e.g. Hospitals, Large enterprise with heavy regulation e.g. Insurance Companies) | 

___

Previous:
[[0001 - Introduction]]

Next:
[[0003 - Getting Started]]

[^1]:  https://www.ibm.com/topics/cloud-computing