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
<h3>Step 1: Create Network Security Groups (NSGs)</h3>

1. Create NSG:</p>
   - Go to the Azure Portal.</p>

![image](https://github.com/user-attachments/assets/447ab5f3-d6a8-4dc0-b437-2bbe88255611)

<br />
<br />
</p>

   - Navigate to Network Security Groups and create a new NSG or select an existing one</p>

![image](https://github.com/user-attachments/assets/9d7e0057-b407-44e3-990c-e3c454b48053)

<br />
<br />
</p>

   - You can also create multiple NSGs for different subnets or VMs, depending on your security model</p>

![image](https://github.com/user-attachments/assets/e71ae233-2d53-4d58-bc45-f26f44b3b545)
 
<br />
<br /> 
<h3>Step 2: Configure Network Security Groups (NSGs)</h3>

1. Configure NSG Rules:</p>
   - Create inbound and outbound security rules in the NSG to allow or deny traffic.</p>

![image](https://github.com/user-attachments/assets/f3437145-5f86-47bd-a1eb-5cdd1e73c021)

<br />
<br />
</p>

   - Specify the source and destination IP addresses, ports, and protocols. Common use cases include allowing traffic from specific IPs or ports (example -> TCP port 80 for HTTP).</p>

![image](https://github.com/user-attachments/assets/436f8557-281e-4dfb-a8e5-7e01793a5c17)

<br />
<br /> 
<h3>Step 3: Associate NSGs with Subnets or Network Interfaces (NSGs)</h3>

1. You can apply NSGs at the subnet level or NIC (Network Interface Card) level.</p>
   - Subnet level: Apply the NSG to an entire subnet, so all VMs in that subnet will inherit the security rules.</p>

![image](https://github.com/user-attachments/assets/73d570b0-251f-4dba-a4f8-7131cac67a0f)

<br />
<br />
</p>

   - NIC level: You can also directly associate the NSG with individual NICs for more granular control.</p>

![image](https://github.com/user-attachments/assets/9c6e7955-742d-4d95-994f-fc8ef8545295)

<br />
<br /> 
<h3>Step 4: Verify Traffic Flow Between VMs</h3>

1. Ping/ICMP Test:</p>
   - You can test connectivity by running a ping command from one VM to another (ensure ICMP traffic is allowed in your NSG).</p>

![image](https://github.com/user-attachments/assets/29f00ef8-3f11-4ee6-b777-3d3883a782da)

<br />
<br />
</p>

2. Telnet/SSH Test:
   - For testing TCP connectivity (example -> SSH to a VM on port 22), use telnet or nc commands.</p>

![image](https://github.com/user-attachments/assets/9dd37c56-962c-416a-b4db-b743731b14cc)

<br />
<br />
</p>

3. Check Network Interfaces:</p>
   - Make sure that the VMs' NICs are configured properly, and check if the NSG is applied to them.</p>

![image](https://github.com/user-attachments/assets/316f9b1c-eba4-46dd-b0ed-05c8dce67424)

<br />
<br /> 
<h3>Step 5: Use Azure Network Watcher for Traffic Inspection</h3>

1. Enable Network Watcher:</p>
   - Go to Network Watcher in the Azure Portal and enable it in the region where your VMs are located.</p>

![image](https://github.com/user-attachments/assets/8b007738-c7e6-480a-8177-902f61772ef1)

<br />
<br />
</p>

2. Use Flow Logs:
   - Enable Network Security Group Flow Logs under Network Watcher to capture traffic data passing through NSGs.

![image](https://github.com/user-attachments/assets/05fab9b0-3da7-4d58-8778-5178d67633a2)


![image](https://github.com/user-attachments/assets/921f68d6-2647-49f3-b056-a0935ac10adc)

<br />
<br />
</p>

   - Flow logs provide information such as source IP, destination IP, ports, and protocols. This helps in identifying if traffic is being allowed or blocked by the NSG.

![image](https://github.com/user-attachments/assets/650d30da-c221-40ac-938f-55e4dc3f1610)

<br />
<br />
</p>

3. Connection Troubleshoot:</p>
   - Use Connection Monitor or IP Flow Verify in Network Watcher to test the connectivity between the VMs and inspect whether traffic is being blocked or allowed based on the NSG rules.</p>

(Connection Monitor)
![image](https://github.com/user-attachments/assets/be460112-1513-4424-9936-cf22f0412d01)

<br />

(IP Flow Verify)
![image](https://github.com/user-attachments/assets/ba5e83b8-3a96-45d6-8545-89816c757a0b)

<br />
<br /> 
<h3>Step 6: Review and Fine-Tune NSG Rules Based on Traffic Insights</h3>

1. Once you have inspected traffic using Network Watcher and other tools, analyze the flow logs and traffic behavior. You may need to fine-tune your NSG rules to:
   - Allow or block specific ports, IP addresses, or subnets.</p>
   - Modify inbound or outbound traffic rules based on your security requirements.</p>
   - Remove overly permissive rules or tighten up security.</p>

By following these steps, you ensure that the traffic between your Azure VMs is properly controlled and monitored using Network Security Groups, making your Azure environment more secure and resilient.


