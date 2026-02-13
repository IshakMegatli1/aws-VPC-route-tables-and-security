<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Traffic Flow and Security

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-security)

**Author:** ElHalouf  
**Email:** shakyleboss@gmail.com

---

## VPC Traffic Flow and Security

![Image](http://learn.nextwork.org/lively_blue_beautiful_jellyfish/uploads/aws-networks-security_92b0b0b4)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC lets you launch AWS resources in a logically isolated virtual network you define. It’s useful because you control IP ranges, subnets, routing, and traffic rules to improve security, segmentation, and connectivity.

### How I used Amazon VPC in this project

...

### One thing I didn't expect in this project was...

...

### This project took me...

This project took me 2 hours and 30 minutes

---

## Route tables

Route tables are a set of routes that control where network traffic from a subnet is sent in the VPC or to an Internet gateway ... It determines how traffic is forwarded.

Routes tables are needed to make a subnet public because we need a route like 0.0.0.0/0 that points to an Internet Gateway attached to the VPC for the subnet to be public.

![Image](http://learn.nextwork.org/lively_blue_beautiful_jellyfish/uploads/aws-networks-security_0a07b191)

---

## Route destination and target

Routes are defined by their destination and target, which means where AWS should send that traffic (examples : local, igw ...)

The route in my route table that directed internet-bound traffic to my internet gateway had a destination of 0.0.0.0/0 (any traffic not matched by a more specific route) and a target of igw-09293... (sends that traffic out to the internet). 

![Image](http://learn.nextwork.org/lively_blue_beautiful_jellyfish/uploads/aws-networks-security_0a07b191)

---

## Security groups

Security groups are virtual firewalls for AWS resources in a VPC that control allowed inbound and outbound traffic using rules.

### Inbound vs Outbound rules

An inbound rule is a security group rule that specifies what incoming traffic is allowed to reach the resources associated with that security group. I allowed HTTP traffic from "0.0.0.0/0" (meaning any IP address)
it makes sure that anyone on the internet can access my public resources.

Outbound rules define what traffic my resource is allowed to send out from the security group. By default it allows all outbound traffic

![Image](http://learn.nextwork.org/lively_blue_beautiful_jellyfish/uploads/aws-networks-security_92b0b0b4)

---

## Network ACLs

Network ACLs are used for controlling inbound and outbound traffic at the subnet level

### Security groups vs. network ACLs

The difference between a security group and a network ACL is that a security group applies rules at the resource level while a network ACL acts at the subnet level.

---

## Default vs Custom Network ACLs

### Similar to security groups, network ACLs use inbound and outbound rules

By default, a network ACL's inbound and outbound rules will allow all traffic. 

A custom ACL’s inbound and outbound rules allows or denies traffic into or out of a subnet based on the rule’s protocol, port range, and source/destination CIDR

![Image](http://learn.nextwork.org/lively_blue_beautiful_jellyfish/uploads/aws-networks-security_4faeb056)

---

## Tracking VPC Resources

I created additional ressources (vpc, internet gateway and security group). Instead of my usual region, I used us-east-2.

EC2 Global View is a tool where you can find all your resources from every region. I could even narrow down my search by using filters like region or resource type.

Now that I've learnt about EC2 Global View, I'd use it again when I need to find resources accross region without needing to know where the resources "live"

![Image](http://learn.nextwork.org/lively_blue_beautiful_jellyfish/uploads/aws-networks-security_b03ea6162)

---

---
