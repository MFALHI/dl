---

copyright:
  years: 2020, 2021
lastupdated: "2021-05-12"

keywords:  

subcollection: dl

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
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
{:help: data-hd-content-type='help'}
{:support: data-reuse='support'}

# Ordering {{site.data.keyword.dl_full_notm}} Dedicated
{: #how-to-order-ibm-cloud-dl-dedicated}
{: help}
{: support}

To order {{site.data.keyword.dl_short}} Dedicated, you must determine the location connecting to IBM Cloud, complete the required configuration information, then click **Create** to submit your order.
{:shortdesc}

## Planning considerations
{: #before-you-begin-dedicated}

* Before you begin, determine the location connection to IBM Cloud by verifying your colocation provider's or service provider's capabilities to reach the Meet Me Room and cross-connect into IBM Cloud.
* All subnets of the VPC or classic network will be connected to the direct link. When creating VPCs, make sure to create the VPCs with non-overlapping prefixes and unique subnets. To ensure successful connectivity with the classic infrastructure, do not use IP addresses for your VPCs in the `10.0.0.0/14`, `10.200.0.0/14`, `10.198.0.0/15`, and `10.254.0.0/16` blocks.
* {{site.data.keyword.cloud_notm}} VPC permits the use of RFC-1918 and IANA-registered IPv4 address space, privately within your VPC, with some exceptions in the IANA Special-Purpose ranges, and select ranges assigned to {{site.data.keyword.cloud_notm}} services.  When using IANA-registered ranges within your enterprise, and within VPCs in conjunction with {{site.data.keyword.cloud_notm}} Direct Link, custom routes must be installed in each zone. For more information, see [Routing considerations for IANA-registered IP assignments](/docs/vpc?topic=vpc-interconnectivity#routing-considerations-iana).

## Ordering instructions
{: #instructions-dedicated}

To order {{site.data.keyword.dl_full}} Dedicated, follow these steps.
{:shortdesc}

1. Log in to your [{{site.data.keyword.cloud_notm}}](https://{DomainName}/){:external} account.
1. Click Menu ![Menu icon](images/menu_icon.png) on the upper left, then click **Interconnectivity**.
1. Scroll to locate the Dedicated tile, then click **Order {{site.data.keyword.dl_short}}** to order.

   Alternatively, you can click **Direct Link** in the left navigation pane to view the Direct Link page, which lists existing Direct Link instances. From this page, you can click **Order Direct Link** > **Direct Link Dedicated** tile.
   {: tip}

1. Optionally, click **Open checklist** to review the ordering process (described in [Completing the connection](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-dedicated#complete-connection)).
1. In the Configuration section, complete the following information:
   * Type a name for your {{site.data.keyword.dl_short}} Dedicated connection.
   * Choose a resource group to create the {{site.data.keyword.dl_short}} connection. Resource groups help manage and contain resources associated with an account. Select **Default** if you don't have other groups defined in the drop-down list.

   For more information about resource groups, see [Best practices for organizing resources in a resource group](/docs/account?topic=account-account_setup).
   {: note}

   * Choose a connection speed. The speeds supported for the {{site.data.keyword.dl_short}} Dedicated offering are 1 Gbps, 2 Gbps, 5 Gbps, and 10 Gbps.

   Speeds above 1 Gbps require 10 Gbps service from the client's carrier and equipment. If you intend to upgrade the speed for this gateway, select 2 Gbps to start with; otherwise, you will not be able to upgrade to a higher speed on this gateway.
   {: tip}

   * Type your company name and carrier provider.
   * For Billing, select **Metered** or **Unmetered**. Metered pricing is paying only for what you use. Unmetered is unlimited access, for a predicable, monthly fee. See [Pricing for {{site.data.keyword.dl_full_notm}}](/docs/dl?topic=dl-pricing-for-ibm-cloud-dl) for details.

      ![Configuration section](/images/dl-config.png)   

1. In the Location section, select a geography, followed by a market, type, site, and routing option.

      Local and global routing options are supported. When you select a routing option, the location details with reachable sites are displayed.  
      {:note}

   ![Location section](/images/dl-location.png)   

1. In the BGP and connections section, complete the following information:

   * Select the IBM cross-connect router for the {{site.data.keyword.dl_short}} connection. The number of direct links associated with your account for each router is shown next to the router name.   
   * Select a BGP peering subnet for the {{site.data.keyword.dl_short}} connection. There are two choices for BGP subnets.

      * Select **Auto-select IP** for IBM to assign an IP address from IP range, `169.254.0.0/16`.
      * Select **Manual-select IP** to specify two of your own IP addresses (in CIDR format) from the ranges `10.254.0.0/16`, `172.16.0.0/12`, `192.168.0.0/16`, `169.254.0.0/16`, or `Public` (a public IP address that you own). Manual-select is useful when trying to avoid conflicts with an existing subnet in use.

      Make sure that any self-provided BGP addresses do not conflict with blocks that are used by IBM, or by resources external to your {{site.data.keyword.dl_short}} deployment.
      {: important}

   * For BGP ASN, use either the default value of `64999` or select an ASN from the specified allowed ranges.

      Allowed ASN ranges are:

      * For a 2-byte range, enter a value between `1-64495` or the default `64999`.
      * For a 2-byte or 4-byte range, enter a value between `131072-4199999999`.
      * For a 4-byte range, enter a value between `4201000000-4201064511`.

      Excluded ASNs: 64512, 64513, 65100, 65201-65234, 65402-65433, 65500, and 4201065000-4201065999

      ![BGP section](/images/dl-bgp.png)   

   * Optionally, select the network connection to be attached to the {{site.data.keyword.dl_short}} gateway and enter a connection name. To add multiple network connections to the {{site.data.keyword.dl_short}} gateway, click **Add connection +**. You can create one of the following connections:

      * **Classic infrastructure** networks allow you to connect to {{site.data.keyword.cloud_notm}} classic resources. Only one classic infrastructure connection is allowed per {{site.data.keyword.dl_short}} gateway.
      * **VPC** networks can contain either first or second generation compute resources, allowing you to connect to your account’s VPC resources.

      ![Add connection section](/images/dl-conn.png)   

    You cannot request a connection to a network in another account when you create a gateway. However, you can request connection to a network in another account after a gateway is provisioned. You also can create classic infrastructure and VPC connections after a gateway is created. For more information, see [Adding virtual connections to a {{site.data.keyword.dl_short}} gateway](/docs/dl?topic=dl-add-virtual-connection).
    {: tip}

    The routing option that you select determines the reachability of the resources in the selected location. If you select the **Global** routing option along with your location selections, the **Region** menu list displays all the regions that are globally available in the specific account. After selecting a region, you can select any VPC from the **Available connections** menu. If you select **Local** routing, then only the region that corresponds to the selected location is available to select. When selected, the VPCs available in the local region for your account are shown.
    {: note}

1. An order summary shows pricing estimates for your review. Read and agree to the [**{{site.data.keyword.dl_short}} prerequisites**](/docs/dl?topic=dl-ibm-cloud-dl-prerequisites) and review Cloud Services [**Terms**](https://www.ibm.com/software/sla/sladb.nsf/sla/bm-8695-01). Then, click **Create** to complete your order.  

   If you want to add GB egress data to your estimate, click **Add to estimate** to calculate the cost. You can also click the **About** tab for links to {{site.data.keyword.dl_short}} pricing tables and other helpful resources.
   {: tip}

Complete your connection, using the following instructions.

## Completing the connection
{: #complete-connection}

After you submit your {{site.data.keyword.dl_short}} order, the {{site.data.keyword.dl_short}} table indicates an **LOA creation in progress** connection status. Click the name of the connection to open its details page. Then, view the Actions section to see if you have any actions pending.

Here's how the process works:

1. IBM Cloud uploads a Letter of Authorization (LOA) containing a Connecting Facility Assignment (CFA). In turn, the connection status changes to **Waiting LOA review**. At this time you can click the corresponding buttons to preview and accept the LOA. After accepting the LOA you can download the LOA document.
2. After accepting the LOA and downloading it the connection status changes to **Waiting completion notice upload**. You must now take the LOA document to your carrier and get the completion notice. To do so, you can:

   * Supply the LOA/CFA to your colocation provider and have them order a cross connect and any required inter-campus connectivity.
   * Supply the LOA/CFA to your service provider and have them order a third-party cross connect, as well as the circuit between your on-premises and the appropriate Meet Me Room.

3. After receiving the completion notice from your carrier, upload it. The completion notice must be in PDF format with the name **completion_notice.pdf** in order for the automation to process it properly. The specific connection shows an option in the {{site.data.keyword.cloud_notm}} console to upload the completion notice. Notice that the connection status changes to **Completion notice review in progress**.

4. The IBM Cloud team reviews the completion notice and accepts it. The IBM Cloud team then places the cross-connect fiber in the ports mentioned in the LOA. This completes the {{site.data.keyword.dl_short}} configuration and the connection status changes to **Provisioned**.

5. You must then configure the BGP parameters on the Customer Edge Router (CER) for BGP session establishment. After this completes, the **BGP status** indicates **Established** and **Link status** indicates **Up**.  

  It can take up to 30 minutes for the link status to update.  
  {:note}

## Locations
{: #dedicated-locations}

The table gives details about the {{site.data.keyword.cloud_notm}} data centers where {{site.data.keyword.dl_short}} Dedicated (2.0) is available:

|**IBM Location Code** | **Location Type** | **Meet Me Room Operator**| **Operator Site Code** | **Operator Address** |
|-----------------|-----------------|-----------------|--------------------|--------------------|
| **Americas** |  |  |  |  |
| Chicago 1 |  PoP | Equinix  | CH4 |  350 E. Cermak |
| Dallas 3 | PoP 1 | Equinix | DA1 | 1950 N. Stemmons Freeway |
| Dallas 4 | PoP 2 | Digital Realty | DFW14 | 2323 Bryan St |
| Dallas 10 | DC(AZ1) | QTS | IRV | 6431 Longhorn Drive |
| Dallas 12 | DC(AZ2) | Digital Realty | DFW18 | 907 Security Row |
| Dallas 13 | DC(AZ3) | CyrusOne | Carrollton - Frankford | 1649 W. Frankford Rd |
| Miami 1 | PoP  | TERREMARK | MI1 | 50 NE 9th Street |
| San Jose 2 | PoP | Equinix | SV111 | Great Oaks Blvd |
| San Paulo 2 | PoP | Equinix | SP4 | Avenida Ceci, 1900, Tambore, Barueri, SP, 06460 120 BR, Brazil |
| Sao Paulo 3 | PoP  | ODATA | SAO03 | 39,2, Estr. dos Romeiros |
| Sao Paulo 4 | DC(AZ1) | ODATA | SAO04 | 943 - Votuparim, Estr. dos Romeiros |
| Sao Paulo 5 | DC(AZ2) | ASCENTY | SAO05 | Avenida 2, n.º 50, Quadra G1 1B Parte A Gleba 1B |
| Seattle 2 | PoP | Digital Reality (The Westin Building) | WBX | 2001 6th Avenue |
| Toronto 1 | DC | Digital Realty | TOR01 | 371 Gough Rd Suite #130 Markham, Ontario |
| Toronto 2 | PoP | Cologix | TOR02 | 151 Front Street, Toronto |
| Toronto 3 | PoP | Equinix | TOR03 | 45 Parliament Street, Toronto |
| Toronto 4 | DC(AZ1) | Server Farm | TOR04 | 300 Bartor Road, North York |
| Toronto 5 | DC(AZ2) | Digital Reality | TOR05 | 1 Century Place, Vaughan |
| Washington DC 2 | PoP 1 | Equinix | DC2 | 21715 Filigree Ct |
| Washington DC 4 | DC(AZ1) | Digital Realty | IAD38 | 44060 Digital Loudoun Plaza (Bldg K) |
| Washington DC 5 | PoP 2 | Coresite | DC2 | 12098 Sunrise Valley Dr |
| Washington DC 6 | DC(AZ2) | Raging Wire | VA2 | 44610 Guilford Drive |
| Washington DC 7 | DC(AZ3) | Sabey | Sabey Intergate.Ashburn | 21741 Red Rum Dr |
| **APAC** |  |  |  |  |
| Hong Kong 3 |	PoP |	Equinix |	HKG2 |	17/F Kerry Warehouse |
| Osaka 1 | PoP | Equinix | OS1 | Nishi-Shinsaibashi Bldg., 1-26-1 Shin-machi, Osaka  |
| Osaka 21  | DC(AZ1)| IDC Frontier (SoftBank) | OSA021 | 6-1 Saitoaokita Mino-shi |
| Osaka 22  | DC(AZ2) | IDC Frontier (SoftBank) | OSA022 | 6-1 Saitoaokita Mino-shi |
| Osaka 23  | DC(AZ3) | IDC Frontier (SoftBank) | OSA023 | 6-1 Saitoaokita Mino-shi |
| Sydney 1 | DC(AZ1) | Global Switch | SYD01 | 400 Harris Street aka 273 Pyrmont St Ultimo |
| Sydney 2 | PoP 1 | Equinix | SY3 | 47 Bourke Rd |
| Sydney 3 | PoP 2 | NextDC | SYD03 | 4 Eden Park Drive, Marquarie Park |
| Sydney 4 | DC(AZ2) | Digital Realty | SYD10 | 1-11 Templar Rd, Erskine Park |
| Sydney 5 | DC(AZ3) | Equinix | SY4 | 200 Bourke Road |
| Tokyo 1 | Pop | Equinix | TY2  | 7th Floor, 3-8-21 Higashi-Shinagawa |
| Tokyo 2 | DC | At Toyko | TOK02 | Shin-Toyosu Cube, 6-2-12 Toyosu, Koto-ku |
| Tokyo 3 | PoP 2 | Equinix | TY4 | Chiyoda-ku |
| Tokyo 4 | DC(AZ2) | Softbank | | Saitama |
| Tokyo 5 | DC(AZ3) | NTT |  | Kawasaki Kangagawa |
| **EMEA** |  |  |  |  |
| Amsterdam 2 | PoP | Equinix | AMS02 | Luttenbergweg 4, 1101 EC |
| Frankfurt 1 | PoP 1 | Digital Realty (InterXion) | FRA01 | Hanauer Landstrasse 302 |
| Frankfurt 2 | DC(AZ1) | CyrusOne (Zenium) | FRA1 | Leonhard - Heisswolf Str 4., Frankfurt am Main |
| Frankfurt 3 | PoP 2 | Equinix | FRA6 | Larchenstrasse 110, Frankfurt Griesheim |
| Frankfurt 4 | DC(AZ2) | E-Shelter | Frankfurt 1 | Eschborner Landstrasse 100, Building H |
| Frankfurt 5 | DC(AZ3) | Digital Realty (InterXion) | FRA05 | Weismüllerstraße 40 |
| London 1 | PoP | Equinix (Telecity) | LD8 | 6/7 Harbour Exchange E14 9GE |
| London 2 | DC | Digital Realty | LHR13 | Fountain Court, Cox Lane, Suites 210 and 230 |
| London 3 | PoP 2 | Equinix | LD5 | 8 Buckingham Ave |
| London 4 | DC(AZ1) | ARK | A103 | A57 Cody Technology Park Old, Victor Way, Farnborough |
| London 5 | DC(AZ2) | Gyron |  | Maxted Cl, Hemel Hempstead  |
| London 6 | DC(AZ3) | CyrusOne (Zenium) | LON1 | 12 Liverpool Rd, Trading Estate |
| Paris 3 | PoP | Equinix | PA3 | 114 Rue Ambroise Croizat, Saint Denis |
