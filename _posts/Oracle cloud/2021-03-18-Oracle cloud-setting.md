---
title: Oracle Cloud Free Tier
layout: single
author_profile: true
read_time: true
share: true

categories:
- Oracle Cloud
tags:
- Oracle Cloud Free Tier

date: 2021-03-18
last_modified_at: '2021-03-18 09:34:00 +08000'

toc: true
toc_sticky: true
toc_label: Content
---




## What are Always Free cloud services ?

- It is always free cloud services for free
  ![Oracle_Cloud_Free_Tier_01](\assets\images\post\oracle_cloud\oracle_cloud_free_tier.png){: .align-center .open-new}
  

### 1. Infrastructure

 - 2 Compute virtual machines with 1/8 OCPU (1GB memory each)
 - 2 Block Volumes Storage (total 100GB)
 - 10 GB Object Storage
 - 10 GB Archive Storage
 - Resource Manager

### 2. Databases
 - Your choice of Oracle Autonomous Transaction Processing or Oracle Autonomous Data Warehouse
 - Two databases total, each with 1 OCPU and 20 GB storage.

### 3. Management
 - Monitoring: 500 million ingestion datapoints, 1 billion retrieval datapoints.
 - Notifications: 1 million sent through https per month, 1000 sent through email per month.
 - Service Connector Hub: 2 service connectors.

### 4. Additional Services
 - Load Balancer : 1 instance, 10 Mbps
 - Outbound Data Transfer : 10TB per Month

## Oracle Cloud Advantage over Amazon Web Services
![Oracle_Cloud_Free_Tier_ADV](\assets\images\post\oracle_cloud\oci_advantage_01.png){: .align-center .open-new}

<br/><br/>
# 1. Create Account

## 1.1 Homepage
[Oracle Cloud Infrastructure(OCI)]({{ "https://www.oracle.com/cloud/" }}){:target="_blank"}
<br/><br/>
![Oracle_Homepage_01](\assets\images\post\oracle_cloud\oracle_homepage_01.png){: .align-center .open-new}

<br/><br/>

# 2. Oracle Cloud Infrastructure(OCI) Setting
 - [Oracle] [OCI Getting Started]({{ "https://docs.oracle.com/en-us/iaas/pdf/gsg/OCI_Getting_Started.pdf" }}){:target="_blank"}
 - [Oracle] [Setting Up Oracle Cloud Infrastructure (OCI)]({{ "https://docs.oracle.com/en/cloud/paas/casb-cloud/palug/setting-oracle-cloud-infrastructure-oci.html" }}){:target="_blank"} 
## 2.1. Create Instance

 - Menu -> Compute -> Instances
<br/>

![OCI_01](\assets\images\post\oracle_cloud\oci_001.png){: .align-center .open-new}
<br/>

### 2.1.1. Select "Create Instance" menu
![OCI_02](\assets\images\post\oracle_cloud\oci_002.png){: .align-center .open-new}
<br/>

### 2.1.2. Placement and hardware
![OCI_04](\assets\images\post\oracle_cloud\oci_004.png){: .align-center .open-new}
 - Change Image
<br/>

### 2.1.3. Select platform image
![OCI_05](\assets\images\post\oracle_cloud\oci_005.png){: .align-center .open-new}
 - Select Image
<br/>

### 2.1.4. Networking
![OCI_07](\assets\images\post\oracle_cloud\oci_007.png){: .align-center .open-new}
 - Create new virtual cloud network
<br/>

### 2.1.5. Add SSH keys
![OCI_08](\assets\images\post\oracle_cloud\oci_008.png){: .align-center .open-new}
 - Select "Paste public keys"
 - Generate SSH key by "PuTTy Key Generator"
<br/>

#### 2.1.5.1. Download PuTTy Key Generator
[https://www.putty.org/]({{ "https://www.putty.org/" }}){:target="_blank"}
 - Download puttygen.exe

#### 2.1.5.2. Generate and Save SHH key
![SSH_KEY_GENERATOR_01](\assets\images\post\oracle_cloud\ssh_key_setting_01.png){: .align-center .open-new}

 - Generate a public/private key pair
 - Save public key
 - Save private key
 - It is recommended to Set up "Key passphrase"

<br/>

### 2.1.6. Boot volume
![OCI_09](\assets\images\post\oracle_cloud\oci_009.png){: .align-center .open-new}
 - Specify a custom boot volume size
 - "Oracle Cloud Free Tier" provide 2 machines(Instances) and total 100GB storage size
<br/>

## 2.2. Instance Setting

### 2.2.1. Check Instance Status
![OCI_10](\assets\images\post\oracle_cloud\oci_010.png){: .align-center .open-new}
 - Wait for Provisioning status to Running status a few minutes
<br/>

### 2.2.2. Firewall Rules

 - Click Virtual Cloud Network
![OCI_12](\assets\images\post\oracle_cloud\oci_012.png){: .align-center .open-new}
<br/>

 - Click Subnet
![OCI_13](\assets\images\post\oracle_cloud\oci_013.png){: .align-center .open-new}
<br/>

 - Click Security Lists
![OCI_14](\assets\images\post\oracle_cloud\oci_014.png){: .align-center .open-new}
<br/>

 - Click Add Ingress Rules
 <br/>
    -- In initial state, only ssh port(22) is allowed.
    ![OCI_15](\assets\images\post\oracle_cloud\oci_015.png){: .align-center .open-new}
    <br/>

 - Add Specific Ingress Rule
![OCI_16](\assets\images\post\oracle_cloud\oci_016.png){: .align-center .open-new}
<br/>

## 2.3. Connect to OCI Instance
 - Connect to OCI Instance by SSH client (
 [PuTTy]({{ "https://www.putty.org/" }}){:target="_blank"}, 
    [Xshell]({{ "https://www.netsarang.com/en/" }}){:target="_blank"}, 
    [MobaXterm]({{ "https://mobaxterm.mobatek.net/" }}){:target="_blank"} etc..)

### 2.3.1 PuTTy
 - PuTTy Configuration

 ![putty_setting_01](\assets\images\post\oracle_cloud\putty_setting_01.png){: .align-center .open-new}

 ![putty_setting_02](\assets\images\post\oracle_cloud\putty_setting_02.png){: .align-center .open-new}


 - Click "Open"

 ![SSH_connection_01](\assets\images\post\oracle_cloud\ssh_connection_01.png){: .align-center .open-new}

 - Please login as the user "ubuntu" rather than the user "root".

 ![SSH_connection_02](\assets\images\post\oracle_cloud\ssh_connection_02.png){: .align-center .open-new}

