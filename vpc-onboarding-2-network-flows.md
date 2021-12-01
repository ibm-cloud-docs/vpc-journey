---

copyright:
  years: 2021
lastupdated: "2021-11-30"

subcollection: vpc-journey

---

{{site.data.keyword.attribute-definition-list}}

# Understanding Network Flows
{: #vpc-network-flows}

Before provisioning your VPC network, it's important to understand what your connectivity requirements will be. Are you an existing IBM Cloud Classic Infrastructure user which requires connectivity to those resources? Will you require private connectivity to on-prem resources? How will interconnectivity between multiple VPCs be managed?  In this section of the deployment guide, the underlying network flows which support these types of scenarios will be reviewed.
{: shortdesc}

Taking the time to understand and plan network flows is a key ingredient to successful deployment. As you review this section, consider the connectivity requirements you have today but may also need in the future.
{: tip}

## Journey Map
{: #vpc-network-flows-map}
![Architecture](images/network-flows/journey-map.png){: class="center"}



## Overview
{: #vpc-network-flows-video-walkthrough}

The following network flows will be covered. Please note that while these represent some common connectivity requirements, not all may be required in your environment. 

1. **VPC to/from On-Prem** connectivity allows for private communication between your on-prem network and the cloud based VPC network, and allows you to access VPC based resources as if they were running locally. The connection also provides a private path for VPC based applications to communicate back to resources on your local network.
2. **VPC to/from VPC and/or Classic Infrastructure** connectivity allows for private communication between multiple VPCs. If you have existing resources still running on the IBM Cloud Classic Infrastructure, a similar flow can also be used to facilitate communication between VPC and Classic infrastructure resources. 
3. **VPC to/from VMware (in Classic Infrastructure)** connectivity allows for private communication between your VPC and Virtual Machines (VMs) running in an IBM Cloud VMware on Classic Infrastructure environment. Typically, in a VMware deployment, an overlay network is defined which allows for BYOIP. This network flow allows for connectivity with this overlay network.
4. **VPC to Internet** connectivity provides for communication from within the VPC to the public Internet.  This network flow leverages a public gateway to allow for egress traffic. Note the traffic flow is one-way.
5. **VPC to Cloud Service Private Endpoints** connectivity provides for private communication from within the VPC to IBM Cloud Service private endpoints. Note the traffic flow is one-way (meaning an IBM Cloud Service cannot initiate a connection into a resource in your VPC).


Additional details for each of these network flows can be found below. 




## Flow1: On-Prem to VPC
{: #vpc-network-flows-1}
![Flow1](images/network-flows/onprem-to-vpc.png)



## Flow2: VPC to VPC and/or Classic Infrastructure

{: #vpc-network-flows-2}
![Flow2](images/network-flows/vpc-to-vpc.png)




## Flow3: VPC to VMware (Overlay Network for VMs)
{: #vpc-network-flows-3}
![Flow3](images/network-flows/vpc-to-vmware.png)




## Flow4: VPC to Internet
{: #vpc-network-flows-4}
![Flow4](images/network-flows/vpc-to-internet.png)




## Flow5: VPC to Cloud Service Private Endpoints
{: #vpc-network-flows-5}
![Flow5](images/network-flows/vpc-to-cse.png)



## Next Steps
{: #vpc-network-flows-next-steps}
The next step on the deployment journey is:
* [Configure IAM Roles](/docs/vpc-journey?topic=vpc-journey-vpc-iam-roles)
