---
title: Oracle Cloud Free Tier
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories:
- Oracle Cloud
description: Oracle Cloud Free Tier
article_tag1: Oracle Cloud
article_section: Structure
meta_keywords: Oracle Cloud Free Tier, Oracle Cloud Free Tier Setting
last_modified_at: '2021-03-18 09:34:00 +08000'
toc: true
toc_sticky: true
toc_label: Content
---

# 1. Create Account

## 1.1 Homepage
[Oracle Cloud Infrastructure(OCI)]({{ "https://www.oracle.com/cloud/" }}){:target="_blank"}
<br/><br/>
![Oracle_Homepage_01](\assets\images\post\oracle_cloud\oracle_homepage_01.png){: .align-center .open-new}

<br/><br/>

# 2. Oracle Cloud Infrastructure(OCI) Setting
 - [Oracle] [OCI Getting Started (Official)]({{ "https://docs.oracle.com/en-us/iaas/pdf/gsg/OCI_Getting_Started.pdf" }}){:target="_blank"}

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
<br/>
 
### 2.1.6. Boot volume
![OCI_09](\assets\images\post\oracle_cloud\oci_009.png){: .align-center .open-new}
 - Specify a custom boot volume size
 - "Oracle Cloud Free Tier" provide 2 machines(Instances) and total 100GB storage size
 
 
## 2.2. Instance Setting

### 2.2.1. Check Instance Status
![OCI_10](\assets\images\post\oracle_cloud\oci_010.png){: .align-center .open-new}
 - Wait for Provisioning status to Running status a few minutes