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
