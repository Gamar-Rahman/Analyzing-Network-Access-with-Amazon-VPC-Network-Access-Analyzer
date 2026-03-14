# Analyzing-Network-Access-with-Amazon-VPC-Network-Access-Analyzer
Hands-on AWS lab demonstrating how to analyze and validate network paths using Amazon VPC Network Access Analyzer to detect unintended access between AWS resources.
# Analyzing Network Access with Amazon VPC Network Access Analyzer

## Overview

This lab demonstrates how to analyze and validate network access paths in AWS using **Amazon VPC Network Access Analyzer**.

The goal is to understand how network traffic flows between resources inside a VPC and identify potential **unintended exposure or connectivity risks**.

In this environment, I built a custom VPC architecture including subnets, gateways, routing rules, and EC2 instances, then used **Network Access Analyzer** to inspect connectivity paths and verify whether resources were reachable from external networks or other parts of the infrastructure.

This type of analysis is important for **cloud security, network auditing, and least-privilege architecture design**.

---

## What is Amazon VPC?

Amazon **Virtual Private Cloud (VPC)** allows you to create an isolated virtual network within AWS.

Inside a VPC, you can control:

- IP address ranges
- Subnet segmentation
- Routing rules
- Internet connectivity
- Security boundaries between resources

VPC enables organizations to deploy cloud infrastructure while maintaining **fine-grained control over network architecture and security boundaries**.

---

## What is VPC Network Access Analyzer?

Amazon **VPC Network Access Analyzer** helps identify how network connectivity is established between AWS resources.

It evaluates:

- VPC configuration
- Security groups
- Route tables
- Internet gateways
- NAT gateways
- Network ACLs

It then determines whether **a path exists between two resources or network locations**.

Unlike static analysis tools, Network Access Analyzer can **continuously analyze configurations and detect connectivity risks as the infrastructure changes.**

---

## Why This Lab Matters

Cloud environments grow quickly and become complex.  

Misconfigured routing, overly permissive security groups, or incorrect gateway usage can unintentionally expose resources to the internet.

Security teams must answer questions like:

- Can a private resource accidentally be reached from the internet?
- Do routing rules allow unintended communication between subnets?
- Are access controls enforcing the intended architecture?

Network Access Analyzer helps validate that the **network behaves exactly as designed**.

---

## Problem Solved

The problem addressed in this lab:

**How can we verify that our AWS network architecture does not unintentionally expose resources or create unintended connectivity paths?**

Traditional configuration reviews are time-consuming and error-prone.

Network Access Analyzer automates this verification process by analyzing the actual **connectivity graph across the network configuration**.

---

## Why This Solution Makes Sense

This solution makes sense because it provides **automated network visibility and verification**.

Benefits include:

- Detecting unintended internet exposure
- Validating segmentation between subnets
- Understanding traffic paths across routing rules
- Improving security posture in cloud environments
- Supporting compliance and auditing efforts

Instead of manually reviewing dozens of configuration components, Network Access Analyzer maps and evaluates the network automatically.

---

## Architecture Built in This Lab

The environment consists of:

- Custom Amazon VPC
- Public and private subnets
- Internet Gateway
- NAT Gateway
- Route tables
- EC2 instances
- Network Access Analyzer

### Components

**VPC**
- Primary network environment

**Subnets**
- Public subnet for internet-facing resources
- Private subnet for internal workloads

**Internet Gateway**
- Enables communication between the VPC and the internet

**NAT Gateway**
- Allows instances in private subnets to access the internet securely without exposing them directly

**Route Tables**
- Define how traffic flows between subnets and gateways

**EC2 Instances**
- Deployed in the subnets to simulate application resources

**Network Access Analyzer**
- Evaluates connectivity paths between network components

---

## Lab Steps

### 1. Create a New VPC
A custom VPC was created to isolate and control network resources.

### 2. Create Subnets
Public and private subnets were configured to simulate a typical secure architecture.

### 3. Configure Internet Gateway
The Internet Gateway allows resources in the public subnet to communicate with external networks.

### 4. Create NAT Gateway
The NAT Gateway allows instances in private subnets to reach the internet for updates without exposing them publicly.

### 5. Configure Route Tables
Route tables were configured to control traffic flow between subnets and gateways.

### 6. Launch EC2 Instances
Instances were deployed to simulate workloads within the VPC.

### 7. Configure Network Access Analyzer
A **Network Access Analyzer analysis path** was defined to inspect connectivity between resources.

### 8. Run the Analysis
The analyzer evaluated the network configuration and determined whether specific connectivity paths existed.

---

## How It Works

1. AWS builds a model of the network configuration.
2. Network Access Analyzer inspects:
   - Security groups
   - Routing rules
   - Gateways
   - Subnets
3. The tool identifies potential paths between resources.
4. The analysis determines whether the defined access conditions are met.
5. Results highlight whether connectivity exists or is blocked.

This provides **visibility into how traffic actually flows through the network architecture**.

---

## Security Insight

One of the biggest risks in cloud environments is **unintended exposure caused by configuration drift**.

Network Access Analyzer helps detect issues such as:

- Public access to private resources
- Incorrect routing configurations
- Overly permissive security rules
- Misconfigured network segmentation

This lab reinforces a key cloud security principle:

**Trust but verify network architecture.**

Even well-designed infrastructure should be continuously analyzed to confirm that access paths remain secure.

---

## Skills Demonstrated

- AWS networking architecture
- Amazon VPC configuration
- Subnet segmentation
- Internet Gateway and NAT Gateway configuration
- Route table management
- EC2 deployment in VPC environments
- Network path analysis
- Cloud security validation techniques

---

## Key Security

Building secure cloud environments is not just about configuring resources.

It also requires **continuous analysis of how those resources interact across the network**.

Amazon VPC Network Access Analyzer provides valuable insight into connectivity paths and helps ensure that your architecture enforces the intended security boundaries.

