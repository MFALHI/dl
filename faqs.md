---

copyright:
  years: 2020, 2021
lastupdated: "2021-04-20"

keywords:  

subcollection: dl

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}
{:support: data-reuse='support'}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:term: .term}  
{:generic: data-hd-programlang="generic"}
{:download: .download}  

# FAQs for {{site.data.keyword.dl_short}}
{: #faqs}

You can review answers to some frequently asked questions about {{site.data.keyword.dl_full}} (2.0).
{:shortdesc}

## How does the new {{site.data.keyword.dl_short}} (2.0) differ from {{site.data.keyword.dlc_short}}?
{: #differentiators}
{: faq}
{: support}

The new {{site.data.keyword.dl_short}} (2.0) offering differs from the {{site.data.keyword.dl_short}} classic infrastructure in that {{site.data.keyword.dl_short}} (2.0) is decoupled from classic IaaS, and exists only in the local cross-connect router (XCR). This design enables native connectivity to VPC and future capabilities without being forced into the classic IaaS network.

The (2.0) offering allows connectivity to both classic IaaS as well as VPCs, whereas {{site.data.keyword.dlc_full_notm}} always connects to the IaaS network and a global VRF first. {{site.data.keyword.dlc_full_notm}} can only reach the VPC on a limited basis using a feature named Classic Access and by adding global routing to the direct link. See [Setting up access to your Classic Infrastructure from VPC](/docs/vpc?topic=vpc-setting-up-access-to-classic-infrastructure) for more information.

For more information about the differences between the new {{site.data.keyword.dl_short}} (2.0) offering and the classic version, see [How do I know which {{site.data.keyword.dl_short}} solution to order?](/docs/direct-link?topic=direct-link-get-started-with-ibm-cloud-direct-link#get-started-solution-to-order).
{: tip}

## What is planned for {{site.data.keyword.dl_short}} Exchange?
{: #exchange-eom}
{: faq}
{: support}

The marketplace has evolved since {{site.data.keyword.dl_short}} Exchange was established. With data center operators now blurring the lines as network service providers, IBM will be combining the Exchange offering with Connect on the new "next generation" platform to reflect both this change and simplify the {{site.data.keyword.dl_short}} portfolio. {{site.data.keyword.dl_short}} Exchange will service only the {{site.data.keyword.dl_short}} classic infrastructure. After migrations of the partner inter-connections to the XCRs are complete, Exchange will be moved to End of Marketing (EoM).

## Will {{site.data.keyword.dl_short}} (2.0) be available in non-MZRs, or is it only a solution for MZRs?  
{: #dl-mzr}
{: faq}
{: support}

Initial rollout plans are for the Multi-Zone Regions (MZRs) to be prioritized. Other PoPs across the portfolio will support the new {{site.data.keyword.dl_short}} access model, enabling access to the classic infrastructure and VPC expansions as they occur.

## If {{site.data.keyword.dl_short}} (2.0) is not available for Single-Zone Regions (SZRs), how do financial services clients handle the data that they need to keep in their regions?
{: #roadmap-szrs}
{: faq}

Any existing customers on classic IaaS can remain in classic IaaS and continue to access classic IaaS data centers using {{site.data.keyword.dl_short}} (2.0) or {{site.data.keyword.dlc_full_notm}}. VPC connectivity is fully supported ONLY on {{site.data.keyword.dl_short}} (2.0).

## Where are the  {{site.data.keyword.dl_short}} (2.0) offerings enabled?
{: #offerings-enabled}
{:faq}
{: support}

For the most up-to-date information, see [{{site.data.keyword.dl_short}} Dedicated](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-dedicated#dedicated-locations) and [{{site.data.keyword.dl_short}} Connect](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-connect#connect-locations) locations.

## How do I interconnect the classic infrastructure and VPC?
{: #interconnect}
{:faq}
{: support}

You can connect the classic infrastructure and VPC with classic peering as described in [Setting up access to your Classic Infrastructure from VPC](/docs/vpc-on-classic-network?topic=vpc-on-classic-setting-up-access-to-your-classic-infrastructure-from-vpc).

Classic access features of VPC are an option at VPC setup and can only be enabled at the initial VPC creation. For more information, see [Creating and managing network resources in VPC](/docs/vpc-on-classic?topic=vpc-on-classic-creating-and-managing-network-resources-in-vpc).

## Is there a way to connect {{site.data.keyword.dl_short}} (2.0) to VPC without using the classic infrastructure?
{: #connect-wo-using-classic}
{:faq}
{: support}

Yes, this is possible on {{site.data.keyword.dl_short}} (2.0). The VRF created is local to the XCR versus global on the classic infrastructure. Route targeting to VPC then enables {{site.data.keyword.dl_short}} (2.0) to be used with VPC natively using the UI (without touching the classic infrastructure).

When routing on-premises subnets from the direct link through a VPC, you must create a route in the VPC routing table. For more information, see [Creating a route](/docs/vpc?topic=vpc-create-vpc-route).
{: note}

## Are there documented limitations on {{site.data.keyword.dl_short}}?
{: #direct-link-vpc-limitations}
{:faq}
{: support}

Yes, they are listed in Virtual Private Cloud [Quotas](/docs/vpc-on-classic?topic=vpc-on-classic-quotas) documentation.

## How do I move from  {{site.data.keyword.dlc_full_notm}} to the new  {{site.data.keyword.dl_short}} (2.0)?
{: #move-classic-to-new}
{:faq}

{{site.data.keyword.dl_short}} (2.0) has a new user interface and records system, requiring you to place a brand new {{site.data.keyword.dl_short}} (2.0) order.

## Are there any performance impacts affected by moving from {{site.data.keyword.dlc_full_notm}}?
{: #move-classic-to-new-performance}
{:faq}

The new {{site.data.keyword.dl_short}} (2.0) performs better as it's not required to exist inside your global VRF for classic IaaS. It is a true access platform to all of {{site.data.keyword.cloud_notm}}.

## In terms of cost, what do I pay for?
{: #cost}
{:faq}

There are two pricing plans: metered and unmetered. Metered has a port fee and bill per GB egressed across the {{site.data.keyword.dl_short}} (2.0).
Unmetered billing has a higher port fee and no usage charges, which are ideal for customers who consistently egress traffic across their direct link.

## How does {{site.data.keyword.dl_full_notm}} work?
{: #how-does-ibm-cloud-dl-work}
{:faq}

For every {{site.data.keyword.dl_short}} customer, the {{site.data.keyword.cloud}} team assigns a small private subnet to build a point-to-point network between the {{site.data.keyword.cloud_notm}} cross-connect router (XCR) and your edge router (CER). Then, you and {{site.data.keyword.cloud_notm}} configure the Border Gateway Protocol (BGP) to exchange routes between the environments. Finally, {{site.data.keyword.cloud_notm}} places you into a VRF to allow for the implementation of non-unique routes to the private address space of your remote network.

## If I order a direct link with local routing, is it possible to upgrade and switch to global routing later?
{: #order-local-routing-then-switch}
{:faq}

Yes, you can change the routing option any time after creating the gateway. To do so, click **Actions** on the gateway's details page and then click **Edit**. This is not a disruptive change. The gateway is billed for global routing for the month, even if the change takes effect halfway through the month.

## When does billing begin with {{site.data.keyword.dl_short}}?
{: #when-does-billing-begin-with-dl}
{:faq}

The fees for {{site.data.keyword.dl_short}} cover the cost of service termination on the {{site.data.keyword.cloud_notm}} infrastructure.

Infrastructure services are billed in advance and begin upon acceptance of a client’s order. However, due to the nature of {{site.data.keyword.dl_full_notm}}, the {{site.data.keyword.dl_short}} service billing begins when a BGP session is established with {{site.data.keyword.cloud_notm}}, or 30 days after the service key is provided to the client.

Billing stops after (1) you request a circuit to be deleted, and (2) the provider has de-provisioned the circuit.

## What extra charges will I incur from other parties with {{site.data.keyword.dl_short}}?
{: #what-additional-charges-will-i-incur-from-other-parties-with-dl}
{:faq}

You might have extra charges from your provider. See to your carrier or service provider for their fee information.

## How can I achieve redundancy with {{site.data.keyword.dl_short}} (2.0)?
{: #how-can-i-achieve-redundancy-with-ibm-cloud-dl}
{:faq}

{{site.data.keyword.dl_short}} does not provide an inherently redundant service. {{site.data.keyword.dl_short}} can provide diverse connections that enable you to create redundancy using BGP. You can achieve diversity with {{site.data.keyword.dl_short}} by connecting to more than one {{site.data.keyword.dl_full_notm}} Dedicated provider for {{site.data.keyword.cloud_notm}}.

## What's the difference between the default local routing and the global routing add-on for {{site.data.keyword.dl_short}}?
{: #what-is-the-difference-between-the-default-local-routing-and-the-global-routing-add-on-for-dl}
{:faq}

The local routing option is the default routing option. If your {{site.data.keyword.dl_short}} is connected at the local PoP, it provides access to all data centers within that same market. In some markets, local routing is applicable for stand-alone PoP locations and direct links that are terminated at the data center.  

With our standard {{site.data.keyword.dl_short}} offering, you can send traffic between the data centers in your selected region. If you need access to other data centers outside the specified region, you must order the global routing add-on. For example, you might use global routing to share workloads between dispersed {{site.data.keyword.cloud_notm}} resources, such Dallas to Ashburn, or Dallas to Frankfurt.

## Why does a global routing add-on package exist for {{site.data.keyword.dl_short}}?
{: #why-does-a-global-routing-add-on-package-exist-for-dl}
{:faq}

The global routing add-on prevents you from experiencing unexpected data costs when traversing outside of your data center's local market. It lowers costs, and, if you have a global presence, allows you to reach all regions easily. However, usually you require only a local bandwidth package.

## If I am connected to a {{site.data.keyword.dl_short}} in a region, such as Dallas, can I access other regions in the US through {{site.data.keyword.dl_short}}?
{: #if-i-am-connected-to-a-dl}
{:faq}

Yes, you are able to gain access to areas outside of your local market if you choose the global routing add-on. If this option is not selected, your {{site.data.keyword.dl_short}} traffic is limited to the local market for the PoP or data center location you selected. See [Pricing for {{site.data.keyword.dl_full_notm}}](/docs/dl?topic=dl-pricing-for-ibm-cloud-dl) for details.

## Can I connect to any available region from a given {{site.data.keyword.dl_short}} location?
{: #can-i-connect-to-any-available-region-from-a-given-dl-location}
{:faq}

Yes, if you order {{site.data.keyword.dl_short}} with the global routing add-on.

## Can I restrict the regions that my {{site.data.keyword.dl_short}} can reach?
{: #can-i-restrict-the-regions-that-my-dl-can-reach}
{:faq}

No. {{site.data.keyword.cloud_notm}} offers two options: (1) A local market only, or (2) all regions with the global routing add-on.

## Does IBM Support IPv6 over {{site.data.keyword.dl_short}}?
{: #can-ibm-support-ipv6-over-dl}
{:faq}

Not for the BGP session. We must assign our `/30` from IPv4, and we need the same in return from you.

## Does IBM do IPV6 on the private network?
{: #can-ibm-do-ipv6-on-the-private-network}
{:faq}

No. IPv6 is public only.

## Does {{site.data.keyword.dl_short}} support any type of Quality of Service (QoS)?
{: #does-dl-support-any-type-of-qos}
{:faq}

We are unable to support any QoS guarantees. QoS requires MPLS mapping between each of our service suppliers and {{site.data.keyword.cloud_notm}}. Cloud service providers generally cannot support QoS because it must reach from end-to-end and involve every device in between. No workaround is currently available by "tunneling" or any other method.

## Does {{site.data.keyword.dl_short}} support Jumbo frames?
{: #does-dl-support-jumbo-frames}
{:faq}

Jumbo frames (up to 9214 bytes) are supported on Dedicated and Dedicated Hosting.

## How easy is it to upgrade the bandwidth of my {{site.data.keyword.dl_short}} connection, for example 1 - 5 GB?
{: #how-easy-is-it-to-upgrade-the-bandwidth-of-my-dl-connection}
{:faq}

Typically, IBM installs speeds of 1 GB and lower on 1 GB optics. For speeds of 2-10 GB, IBM installs 10 GB optics. As a result, an upgrade of 1-5 GB would require new optics to be assigned or inserted. It would be a service affecting event. If you anticipate that type of growth, it's possible to request 10 GB optical fibers to be installed at the beginning of your {{site.data.keyword.dl_short}} deployment, or to order 2 GB initially so that the 10 GB optics are in place.

## Is ECMP the way to go for redundant {{site.data.keyword.dl_short}} connections? What alternatives exist?
{: #is-ecmp-the-way-to-go-for-redundant-dl-connections}
{:faq}

ECMP isn’t for redundant connections, but for balancing the load over the two links. With ECMP, both connections must terminate to the same {{site.data.keyword.cloud_notm}} cross-connect router (XCR), which makes it a single point of failure. In other words, ECMP can be provisioned only as two sessions on the same {{site.data.keyword.cloud_notm}} XCR.

ECMP is a feature of BGP. If you are looking for redundancy, you should get two {{site.data.keyword.dl_short}} connections, one going into each XCR. If you want to use ECMP and have redundancy, you need two {{site.data.keyword.dl_short}} connections on each XCR so that you can have 2 ECMP sessions running simultaneously.

Alternatively, some customers set up two links into a different XCR in the same data center (for example, WDC02) and then failover as needed by using BGP configurations. This configuration is less redundant (less safe) than having {{site.data.keyword.dl_short}} connections into two separate data centers, such as WDC02 and WDC05.

## Is there a Service Level Agreement (SLA) on the {{site.data.keyword.dl_short}} XCR connections up to the account’s BCR connection?
{: #is-there-an-sla-on-the-diret-link-xr-connections}
{:faq}

There is no SLA on {{site.data.keyword.dl_short}} today. You can achieve 99.99% effectively with two or more direct links that are properly configured for failover by using BGP, but IBM cannot control that or provide an SLA on it.

## For Direct Link (2.0) offerings, does IBM set a BGP password?
{: #on-direct-link-exchange-does-ibm-set-a-bgp-password}
{:faq}

By default, BGP passwords for Direct Link aren't set up. IBM does not support enabling a BGP password.
