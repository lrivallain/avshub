---
title: "Workshop Guide"
linkTitle: "Workshop Guide - Start Here"
weight: 1
menu:
  main:
    weight: 20
cascade:
  - type: "docs"
---

## **Training Environment**

> Let's first agree on: AVS = Azure VMware Solution

### **Azure Portal Credentials**

> Replace “**\#**” with your group number.

Connect to [https://portal.azure.com](https://portal.azure.com) with the following credentials:

| **Username** | `groupX@avsgcst.onmicrosoft.com` |
| ------------ | ---------------------------------|
| **Password** | *TO BE SUPPLIED*                 |

### **Environment Details**

#### Workstation

Based on your needs and work habits, you can use the following kind of platform for this Hands-on-lab:

* Your laptop or hardware backed workstation
* A Jump server with egress internet access

Nothing will be to install or configure on the workstation except the VPN access to the lab environment.

#### VPN configuration

1. *(if not already available in your workstation)* [Download](https://www.microsoft.com/p/azure-vpn-client/9np355qt2sqb) and install Azure VPN client from https://www.microsoft.com/p/azure-vpn-client/9np355qt2sqb
2. Open Azure VPN client and import a new configuration based on the XML file shared with attendees.
3. As the client authentication, select the certificate that was previously shared with attendees and localy installed.
4. Save and connect
5. Ensure having some network routes discovered from the VPN

#### **AVS vCenter, HCX, and NSX-T URLs**

Please refer to the **VMware Credentials** section under the AVS blade in the Azure portal to retrieve URLs and Login information for vCenter, HCX, and NSX-T.

> NOTE: Use the same vCenter credentials to access HCX portal if needed.

![](MainPic6.png)

> PLEASE DO NOT CLICK GENERATE A NEW PASSWORD BUTTON UNDER CREDENTIALS IN AZURE PORTAL

**Note**: In a real customer environment, the local
[cloudadmin@vsphere.local](mailto:cloudadmin@vsphere.local) account should be
treated as an emergency access account for "break glass" scenarios in your
private cloud. It's not for daily administrative activities or integration with
other services. For more information see
[here](https://docs.microsoft.com/en-us/azure/azure-vmware/concepts-identity)

In AVS you can predict the IP addresses for vCenter (.2), NSX-T Manager (.3)
 and HCX (.9). For instance, if you choose 10.20.0.0/22 as your AVS Management CIDR block, the IPs will be as following:

| **vCenter**    | **NSX-T**     | **HCX**       |
| -------------- | ------------- | ------------- |
| 10.20.0.**2**  | 10.20.0.**3** | 10.20.0.**9** |

In the current lab, the AVS SDDC is deployed with the following IP addresses:

| **vCenter**       | **NSX-T**        | **HCX**          |
| ----------------- | ---------------- | ---------------- |
| 10.100.100.**2**  | 10.100.100.**3** | 10.100.100.**9** |

### **On-Premises VMware Lab Environment**

If you are in a group with multiple participants you will be assigned a participant number.

> **Replace X with your group number and Y with your participant number.**

#### Generic information

| **Group** | **Participant** | **vCenter IP** | **Username**            | **Password** | **VMs Workload network** |
| --------- | --------------- | -------------- | ----------------------- | ------------ | ------------------------ |
| X         | Y               | 10.X.Y.2       | `administrator@avs.lab` | `MSFTavs1!`  | 10.X.1Y.128/25           |

#### Example for Group number **1** with **9** participants

| **Group** | **Participant** | **vCenter IP** | **Username**            | **Password** | **VMs Workload network** |
| --------- | --------------- | -------------- | ----------------------- | ------------ | ------------------------ |
| 1         | 1               | 10.1.1.2       | `administrator@avs.lab` | `MSFTavs1!`  | 10.1.11.128/25           |
| 1         | 2               | 10.1.2.2       | `administrator@avs.lab` | `MSFTavs1!`  | 10.1.12.128/25           |
| 1         | 3               | 10.1.3.2       | `administrator@avs.lab` | `MSFTavs1!`  | 10.1.13.128/25           |
| 1         | 4               | 10.1.4.2       | `administrator@avs.lab` | `MSFTavs1!`  | 10.1.14.128/25           |
| 1         | 5               | 10.1.5.2       | `administrator@avs.lab` | `MSFTavs1!`  | 10.1.15.128/25           |
| 1         | 6               | 10.1.6.2       | `administrator@avs.lab` | `MSFTavs1!`  | 10.1.16.128/25           |
| 1         | 7               | 10.1.7.2       | `administrator@avs.lab` | `MSFTavs1!`  | 10.1.17.128/25           |
| 1         | 8               | 10.1.8.2       | `administrator@avs.lab` | `MSFTavs1!`  | 10.1.18.128/25           |
| 1         | 9               | 10.1.9.2       | `administrator@avs.lab` | `MSFTavs1!`  | 10.1.19.128/25           |

#### Credentials for the Workload VM/s

| **Username** | root        |
|------------- |------------ |
| **Password** | `1TestVM!!` |