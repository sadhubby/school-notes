

# Virtualization and Cloud Computing

There are three types of deployments - traditional (bare metal), virtualization (still private cloud), Cloud (either public or private)

## Traditional 
- physical servers and datacenters to deliver computing and other IT  services
- used to be a practice dati
- Mostly telcos 
	- Server tells you when you've done your planned number of calls
- Host computer would typically be installed with a single OS directly sa hardware. Also called Blackbox. Lahat ng proprietary nila. 
- Possible issues: resource allocation, difficulty in scaling. 
	- Kung gusto ko magupgrade, madidispose yung mga lumang hardware. So essentially, its costly. 
![[Pasted image 20250508185301.png]]
**Image 1:** *Tranditional / Physical server*

In the physical server, install an OS then you can install a specific application to do what it needs to do. Ang problema it only does ONE specific function, so like One App in One Server. If the demand of that app goes down, it becomes under-utilized, and then masasayang kung magkano yung binayad mo for that server

Let's say magnitude is growing in  data center. if mga 5 to 15% lang ginagamit, its a huge waste of IT resources.

## Virtualization

- is a technology (Cloud is a service)
- create virtual representations of servers, storage and networks of other physical machines and resources
- Virtual Software mimics the functions of physical hardware
- So we use a lot of Virtual Machines. Three applications that are Virtualized now share the same hardware.

How to achieve virtualization 
	We dynamically allocate/deallocate VMs

VM Profile - CPU, Memory, Storage, Network Interfaces.
So we install then a Hypervisor which managers Virtual Machines which now share the same physical servers. Hypervisors allow multiple virtual machines to run on a single physical server

![[Pasted image 20250508190041.png]]
**Image 2:** *We get to do the same things as traditional with less cost*

One advantage of Virtualized, is that we can take what we call a Snapshot. In traditional, pag may mangyari sa server, there is a huge risk na mawawala lahat ng data sa server. Pero in virtualized, we can take a Snapshot to create a VMI (VM Image) which if you install ulit sa hypervisor, it will do the same thing with the same data (an exact replica) of the virtual machine.

- Virtual Machine - self contained, independent, isolated software container with an operating system and an application inside.
- Multiple VMs on a single computer results in several OS and applications to run on one physical server or host.

Buying a phone, you dont buy a phone for each possible need. You buy a phone, a single phone, that can do all requirements you need. 

Withour Virtualization, huge inefficiences and excessive operating costs 
With virutlization, economies of scale and greater efficiency 

## Cloud Computing 

- On demand delivery of IT resources. Virtualization is a tech, CLoud is a service which is that first sentence. 
- The tech of virtualization enables the services that Cloud can offer
- You can access tech services such as computing power, storage and databases, on as-needed basis from a provider like Amazon Web Services
- Cloud computing is a general term for anything that involves delivering hosted services over the internet.
- The goal of cloud computing is to provide easy, scalable access to computing resources and IT services. 

### Benefits

1. On-demand like Netflix
	- Cloud services are on-demand which means you can access the service anywhere and anytime
2. Cheaper
	- You don't need to purchase computers, rent office space or hire staff. Various models of cloud services offer one or all of those options. Meaning huge savings on company
3. It's Flexible
	- Since you only pay for what you want and what you want is accessible anywhere, you can increase or decrease the scope of projects as needed
4. Mobility
	- Storing information in cloud means that users can access it from anywhere
5. Disaster Recovery
	- Storing data in cloud guarantees that users can always access their data even if devices are inoperable. 
	- With cloud based services, organizations can quickly recover their data in the event of emergencies such as natural disasters or power outages.

### Cloud Computing vs Traditional Web Hosting

1. Users can access large amounts of computing power on demand
	1. You can change the computing power to accommodate depending on your needs 
2. Elastic -> user can have as much or as little of a service any given time
3. Service is fully managed by provider. Significant innovations in virtualization and distributed computing as well as improved access to high-speed internet have accelerated interest in cloud computing

### Types of Cloud Computing

Iaas, Paas, Saas

**Pizza as a Service**
![[Pasted image 20250508192230.png]]
**Image 3:** *Pizza as a service*

A disadvantage of SaaS, in terms of customization, mas maliit macucustomize

![[Pasted image 20250508192719.png]]
**Image 4:** *Chart of examples*

### Cloud Deployment Models

The  deployment model is defined according to where the infrastructure for the deployment resides and who has control over that infrastructure. 

Basically, the decision depends on the value propositions and different costs associated with it. 

The consideration usually is ano mas madali ano mas cheaper

#### Public Cloud
- Sells services to anyone on the internet. 
- This type of cloud deployment model supports all users who want to make use of a computing resources such as hardware or software on a subscription basis
- Di mo talaga owned yung mga servers.
- Most common uses are for application development, file sharing, email service

#### Private Cloud
- Sayo ito
- Operated solely for the organization. 
- Infrastructure will only host a company's applications. 
- So kanila mga location, kanila data centers. 
- More expensive than public clouds due to the capital expenditure involved in acquiring and maintaning them.
- But better able to address security and privacy concerns

#### Hybrid Cloud
- Interconnected private and public cloud infrastructure.
- Make use of this model ****

![[Pasted image 20250508193550.png]]
**Image 5:** *Cloud deployment chars*

Cloud Computing is on demand delivery of IT resoruces
Three basic tpyes Saas, Iaas, Paas
Public, Private, Community and Hybrid deployment models

