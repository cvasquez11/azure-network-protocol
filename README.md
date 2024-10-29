<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com/watch?v=xpSPjCKVdW8)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

1. Create and Configure NSGs: Set up Network Security Groups in the Azure portal and define inbound and outbound rules to control traffic flow to and from your virtual machines.
2. Associate NSGs with Resources: Link the NSGs to the relevant subnets or network interfaces of the Azure Virtual Machines to apply the defined security rules.
3. Monitor Traffic with Network Watcher: Enable Azure Network Watcher to gain insights into traffic patterns and performance, allowing you to analyze data flows.
4. Review Flow Logs and Metrics: Utilize NSG flow logs and diagnostic settings to inspect and analyze traffic, helping to identify issues or optimize security configurations.

<h2>Actions and Observations</h2>

<p>

![lplplpl](https://github.com/user-attachments/assets/e8fe2e30-3f85-4815-ae30-faa6e4b687ea)

<p>

1. Create a Network Security Group (NSG): Navigate to the Azure portal and create a new NSG to manage traffic rules for your virtual machines.
2. Define Inbound Security Rules: Add inbound rules to specify which traffic is allowed to reach your VMs, based on source IP, port, and protocol.
3. Define Outbound Security Rules: Set outbound rules to control traffic leaving your VMs, ensuring only authorized traffic can exit.
</p>
<br />

<p>

![bcbcbcbcbc](https://github.com/user-attachments/assets/a6e0ef28-90d2-41d2-8a52-ec51143883aa)

<p>

4. Associate NSGs with Subnets or NICs: Attach the NSG to specific subnets or the network interface cards (NICs) of the Azure Virtual Machines to apply the rules.
5. Enable Azure Network Watcher: Activate Azure Network Watcher in the desired region to provide monitoring and diagnostic capabilities for your network.
6. Inspect Traffic Flow with Flow Logs: Configure NSG flow logs to capture information about allowed and denied traffic, storing logs in an Azure storage account for analysis.
</p>
<br />

<p>
  
![mbmbmbmbm](https://github.com/user-attachments/assets/fbc18f45-aaea-47e2-9918-ccc3a21e4698)

<p>

7. Use Traffic Analytics: Leverage Azure Network Watcher's Traffic Analytics to visualize traffic patterns and identify potential security issues or anomalies.
8. Monitor Network Performance: Utilize tools like Connection Troubleshoot and IP Flow Verify in Azure Network Watcher to diagnose connectivity issues between VMs.
9. Regularly Review and Update Rules: Periodically assess and update NSG rules based on changing security requirements or traffic patterns to maintain optimal security posture.
</p>
<br />
