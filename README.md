# Fortigate-firewall-configuration-using-Terrafom-


![image](https://github.com/ESUMAILI/Fortigate-firewall-configuration-using-Terrafom-/assets/91162045/a60cf2b6-e499-4876-97ed-8d961d49b74a)

![image](https://github.com/ESUMAILI/Fortigate-firewall-configuration-using-Terrafom-/assets/91162045/ba3173d7-ef18-4905-8cee-f876de056643)


# Terraform Configuration for FortiGate Firewall

This repository contains Terraform scripts to configure a Fortinet FortiGate firewall. The scripts are designed to automate the setup of firewall policies, virtual IPs (VIPs), and other security configurations.

## Prerequisites

Before running the Terraform scripts, ensure you have the following:

- Terraform installed on your local your virtual machine 
- Access to a FortiGate firewall device.
- Appropriate credentials (username and password) for the FortiGate device.
![image](https://github.com/ESUMAILI/Fortigate-firewall-configuration-using-Terrafom-/assets/91162045/e5488778-0d05-4d07-8e36-0de0cd00700b)

  
- FortiGate device reachable from the machine where Terraform will be executed.

## Configuration

### 1. Set up Terraform Provider

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

provider "fortios" {
  hostname = "YOUR_FORTIGATE_IP"
  token    = "YOUR_API_TOKEN"
  insecure = true
  username = "YOUR_USERNAME"
  password = "YOUR_PASSWORD"
}
