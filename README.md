# Fortigate-firewall-configuration-using-Terrafom-


![image](https://github.com/ESUMAILI/Fortigate-firewall-configuration-using-Terrafom-/assets/91162045/ad3694bc-30af-4b5c-a44d-8c166f0b2acf)  ![image](https://github.com/ESUMAILI/Fortigate-firewall-configuration-using-Terrafom-/assets/91162045/570f8554-763d-42df-af03-a17fb145da8b)



# Terraform Configuration for FortiGate Firewall

This repository contains Terraform scripts to configure a Fortinet FortiGate firewall. The scripts are designed to automate the setup of firewall policies, virtual IPs (VIPs), and other security configurations.

## Prerequisites

Before running the Terraform scripts, ensure you have the following:

- Terraform installed on your local your virtual machine 
- Access to a FortiGate firewall device.
- Appropriate credentials (username and password) for the FortiGate device.
![image](https://github.com/ESUMAILI/Fortigate-firewall-configuration-using-Terrafom-/assets/91162045/3716f1d7-1984-44d8-8be4-984ca0d724e1)


  
- FortiGate device reachable from the machine where Terraform will be executed.
Allow terraform to get access to the provider registry by opening the network or install the provider manually in your laptop

## Configuration

### 1. Set up Terraform Provider
#### 1. Provider Configuration 
Ensure that you have the Fortinet FortiOS provider specified in your Terraform configuration.

```hcl
terraform {
  required_providers {
    fortios = {
      source  = "fortinetdev/fortios"
      version = "1.18.0"
    }
  }
}
```
The script specifies the use of the fortinetdev/fortios provider version 1.18.0. This provider is utilized to manage resources on a Fortinet FortiOS device.

### 2. Fortinet FortiOS Provider

The provider configuration sets up the connection to the Fortinet FortiOS device with the following parameters:
```
provider "fortios" {
  hostname = "YOUR_FORTIGATE_IP"
  token    = "YOUR_API_TOKEN"
  insecure = true for testing or "False" for production
  username = "YOUR_USERNAME"
  password = "YOUR_PASSWORD"
}
```
Replace placeholders (YOUR_FORTIGATE_IP, YOUR_API_TOKEN, YOUR_USERNAME, YOUR_PASSWORD) with your FortiGate details.

hostname: The IP address of the Fortinet device.
token: The authentication token for API access.
insecure: Indicates whether to perform insecure SSL connections (true).
username: The username for authenticating to the Fortinet device.
password: The password for authenticating to the Fortinet device.


### 2. Resource Definitions

#### 1. Firewall Policy
##### 1. Fortinet Firewall Policy Resource (policyEsdras)

Create a firewall policy in main.tf:

action: Accept traffic.
logtraffic: Log traffic for UTM.
name: Policy name.
policyid: Policy ID.
schedule: Always active.
wanopt, wanopt_detection, wanopt_passive_opt, wccp, webcache, webcache_https: Various WAN optimization settings.
wsso: Web Single Sign-On enabled.
status: Policy status (enabled).
