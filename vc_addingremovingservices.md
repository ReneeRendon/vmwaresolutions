---

copyright:

  years:  2016, 2017

lastupdated: "2017-10-05"

---

# Ordering, viewing, and removing services for vCenter Server instances

You can order services for your VMware vCenter Server instances, such as a disaster recovery solution. When you no longer need these services, you can remove them from your instances.

## Available services for vCenter Server instances

The service installation and removal process is automated. After you select to install or remove a service, all the procedures for the successful installation or removal of the service are completed automatically.

The following services are available to vCenter Server instances.

### Veeam on IBM® Cloud

This service integrates seamlessly with your VMware environment to help you manage the backup and restore of all the virtual machines (VMs) in your environment, including the backup and restore of the management components. It can help provide a recovery point objective (RPO) of less than 15 minutes upon configuration for your data.

This service is initially configured to back up the management VMs immediately upon deployment for your instance. If you do not order this service, there is no backup of the management VMs.

When you order this service, configure the following settings:
* **Number of VMs to License**: A minimum of 4 VMs for licenses is required for management.
* **Storage Size**: The capacity that meets your storage needs. A minimum of 2,000 GB of storage is required for management. For considerations when estimating storage size, see [Estimating Repository Capacity](https://bp.veeam.expert/resource_planning/repository_planning_sizing.html).
* **Storage Performance**: The IOPS (Input/output Operations Per Second) per GB based on your workload requirements.

For more information about Veeam on IBM Cloud, see [Managing Veeam on IBM Cloud](../services/managingveeam.html).

### F5 on IBM Cloud

This service optimizes performance and ensures availability and security for applications with the F5 BIG-IP Virtual Edition (VE).

When you order this service, configure the following settings:
* **License Model**: Select **Good**, **Better**, or **Best** according to your requirements. For more information about what is provided for each license option, click **Learn More** on the **F5 on IBM Cloud** service card.
* **Maximum Bandwidth**:  The maximum data transfer rate for the network connection.

For more information about F5 on IBM Cloud, see [Managing F5 on IBM Cloud](../services/managing_f5.html).

### Fortinet on IBM Cloud

This service deploys an HA-pair of FortiGate Security Appliance (FSA) 300 series devices that can provide firewall, routing, NAT, and VPN services to protect the public network connection to your environment. For more information, see [Managing Fortinet on IBM Cloud](../services/managingfsa.html).

### Zerto on IBM Cloud

This service provides replication and disaster recovery capabilities to help protect your workloads. For more information, see [Managing Zerto on IBM Cloud](../services/managingzertodr.html).

## Procedure

1. Click **Deployed Instances** from the left navigation pane. Click the **vCenter Server** tab.
2. Click the instance for which you want to install or view services, or from which you want to remove services.
3. Click the **Services** tab.
4. To install services, complete the following steps:
   1. On the **Add Services** tab, find the services that you want to install and click **Select Service** on the service cards.
   2. If you accept the default selection for Veeam on IBM Cloud, specify the required settings in the **Configure Veeam** area.
   3. If you want to install F5 on IBM Cloud, specify the required settings in the **Configure F5 on IBM Cloud** area.
   4. After completing all selections for the services you want, scroll down on the **Add Services** page and click **Install**.
   5. In the **Order Summary** window, click the link or links of the terms that apply to the services, and ensure that you agree with the terms before you install the services.
   6. Review the estimated cost of the services by clicking the price link under **Estimated Cost**.
   7. Click **Place Order**. After your request to install the services is accepted, the status of the services is changed to **Installing**.
5. To view details about a service, complete the following steps:
   1. On the **Installed Services** tab, find the service that you want to view details for and click **View Details** on the service
   card.
   2. Review the information about the selected service, such as the service status and so on.
   3. For Veeam on IBM Cloud, you can access the Veeam console with the credentials provided on this page by using Remote Desktop Protocol (RDP). For more information, see [Accessing the Veeam console by using RDP](../services/managingveeam.html#accessing-the-veeam-console-by-using-rdp).
   4. For F5 on IBM Cloud, you can log in to the primary or secondary console with the credentials provided on this page to manage the service by clicking **View BIG-IP Primary Web UI** or **View BIG-IP Secondary Web UI**.
   5. For Fortinet on IBM Cloud, you can log in to the FortiGate 300 series console with the credentials provided on this page to manage the service by clicking **View FortiGate Console**.
   6. For Zerto on IBM Cloud, you can log in to the Zerto console with your vCenter credentials to manage the service by clicking **View Zerto Console**.
6. To remove a service, complete the following steps:
   1. On the **Installed Services** tab, find the service that you want to remove.
   2. Click the overflow menu icon in the upper right of the service card, and then click **Remove Service**.
   3. In the **Remove Service** window, review the considerations or warnings if there are any. Click **I Understand**. After your
   request for service removal is accepted, the service status changes to **Removing**.

## Results

When the installation of the service is completed successfully, you are notified by email, and the service is displayed on the **Installed Services** tab with the **Installed** status.

**Important**: After the Fortinet on IBM Cloud service is installed successfully, you can manage and configure firewall
rules for the FSA from the FortiGate console. You must ensure that the FSA firewall rules are defined to allow outbound HTTPS (TCP port 443) communications that are initiated by management components such as the IBM CloudDriver virtual machine or Zerto Virtual Manager to
communicate with the external management database on IBM Bluemix over the internet. The outbound HTTPS (TCP port 443) communications originate from the public IP address of the management services VMware NSX Edge Services Gateway (ESG) in your instance.

When the removal of the service is completed successfully, you are notified by email, and the service is removed from the **Installed Services** tab.

**Attention**: You are billed until the end of the IBM Bluemix Infrastructure (SoftLayer) billing cycle for the removed services.

## Related links

* [Ordering vCenter Server instances](vc_orderinginstance.html)
* [FAQ](../vmonic/faq.html)