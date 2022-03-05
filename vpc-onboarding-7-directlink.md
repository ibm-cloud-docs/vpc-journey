---

copyright:
  years: 2021,2022
lastupdated: "2022-02-22"

subcollection: vpc-journey

---

{{site.data.keyword.attribute-definition-list}}

# Setup Direct Link Connectivity
{: #vpc-directlink}

## Journey Map
{: #vpc-directlink-map}
![Architecture](images/directlink/journey-map.png){: class="center"}

## Overview
{: #vpc-directlink-overview}

In this part of the journey, we will cover how to **establish provides private connectivity between VPC and on-prem**. To accomplish this, {{site.data.keyword.Bluemix_notm}} Direct Link will be used. You'll find there are different types of {{site.data.keyword.Bluemix_notm}} Direct Link services available to you:

- {{site.data.keyword.Bluemix_notm}} Direct Link Connect (DL 1.0 and DL 2.0)
- {{site.data.keyword.Bluemix_notm}} Direct Link Dedicated (DL 1.0 and DL 2.0)
- {{site.data.keyword.Bluemix_notm}} Direct Link Dedicated Hosting on Classic (DL 1.0)
- {{site.data.keyword.Bluemix_notm}} Direct Link Dedicated Exchange on Classic (DL 1.0)

Direct Link on Classic is also referred to as Direct Link 1.0 and is traditionally used in an environment mainly focussed around {{site.data.keyword.Bluemix_notm}} Classic Infrastructure. **As we will be working with a VPC based environment, this deployment guide will focus on Direct Link 2.0.** (A decision tree which which leads to Direct Link 2.0 can be found in the [documentation](https://{DomainName}/docs/direct-link?topic=direct-link-get-started-with-ibm-cloud-direct-link#get-started-solution-to-order).)
{: tip}

When reviewing location names in the Direct Link documentation, be aware that Dallas and Washington are unique in that their datacenter ids do not match the VPC zone numbers. Dallas 10, Dallas 12, and Dallas 13 map to Dallas 1 (Zone1), Dallas 2 (Zone2), and Dallas 3 (Zone3) in VPC. Likewise, Washington DC 4, Washington DC 6, Washington DC 7 map to Washington DC 1, Washington DC 2, and Washington DC 3 in VPC. 
{: tip}

Before moving on, be aware of the following attributes of the Direct Link 2.0 service and its [limitations](https://{DomainName}/docs/dl?topic=dl-known-limitations):


| Feature                                     | Direct Link (2.0)                                            |
| ------------------------------------------- | ------------------------------------------------------------ |
| Locations                                   | All {{site.data.keyword.Bluemix_notm}} MZRs have support and SZR support is being rolled out on a location-by-location basis. Please see the [Direct Link location table](https://{DomainName}/docs/direct-link?topic=direct-link-get-started-with-ibm-cloud-direct-link#get-started-solution-to-order) for a detailed listing. |
| Connectivity/Peering to {{site.data.keyword.Bluemix_notm}}           | Supports connectivity to multiple VPCs, VPCs in another {{site.data.keyword.Bluemix_notm}} Account, {{site.data.keyword.Bluemix_notm}} Classic Infrastructure, and Transit Gateway |
| BGP ASN supported                           | Allowed to use any ASN outside these blocked ranges: 0, 13884, 36351, 64512, 64513, 65100, 65201‍–‍65234, 65402‍–‍65433, 65500 and 4201065000‍–‍4201065999 |
| BGP Authentication                          | Supported for Dedicated and Connect offerings through automation. Need to store the MD5 secret in Key Protect or an HPCS instance in the customer account. |
| Default BGP IP address range for automation | 169.254.0.0/16.                                              |
| Manual IP address ranges supported          | 172.16.0.0/12, 192.168.0.0/16, 10.254.0.0/16, any public IP addresses |
| Bring Your Own IP (BYOIP)                   | Supports BYOIP for non-overlapping RFC-1918 IP ranges between VPC networks and on-premise networks (see [Routing considerations for IANA-registered IP assignments](https://{DomainName}/docs/vpc?topic=vpc-interconnectivity#routing-considerations-iana) for details).  **<u>ADDITIONAL NOTE</u>**: While we are focussed on a VPC environment, in some cases you may still have resources on IBM Classic Infrastructure which you will need to include as part of the on-prem connectivity. Be aware that IBM Classic Infrastructure uses a 10.0.0.0/8 range so additional considerations with BYOIP may need to be made as described in the [documentation](https://{DomainName}/docs/vpc?topic=vpc-interconnectivity#routing-considerations-iana). |
| MACsec                                      | MACsec support is available in CHI01 and WDC02. Compatible with Cisco switches. |
| Bi-directional Forwarding Detection(BFD)    | All MZRs have Direct Link (2.0) offering support.            |
| Billing/Pricing                             | Metered based on the data utilization and unmetered flat rate support. Inbound data transfer to IBM Cloud is free. Data transfer for [egress](https://{DomainName}/docs/dl?topic=dl-pricing-for-ibm-cloud-dl#metered-data-transfer-charge) varies based on region. Global routing (access to all IBM Cloud data centers globally) is free. |

## Connection Patterns
{: #vpc-directlink-patterns}

## Ordering Direct Link
{: #vpc-directlink-order}

* Detailed steps (including screenshots) to order **Direct Link Dedicated** are available in the [documentation](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-dedicated).
* Detailed steps (including screenshots) to order **Direct Link Connect** are available in the [documentation](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-connect)




## Next Steps
{: #vpc-overview-next-steps}

The next step on the deployment journey is:
* [Extend to Advanced Elements](/docs/vpc-journey?topic=vpc-journey-vpc-advanced-elements)
