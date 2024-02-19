
# NMAP #

###  Use the tool NMAP [Command line only]to perform the below task. Run Wireshark in the background and capture only the necessary packets to showcase for the corresponding question. ###

#### a) Explain the subnet and use the NMAP Command to scan the services for the whole subnet.

>An IP network's logical component is called a subnet, short for subnetwork. It makes it possible to split up a bigger network into more manageable chunks. The main goals of subnetting are to increase network organization, security, and performance. Every device connected to a network is given an IP address, and subnetting facilitates effective data packet routing throughout the network.

> Command to scan entire subnet `nmap -sV <subnet/CIDR notation>`

Victim ip

![Screenshot 2024-02-19 102055](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/0cde3d6d-fcab-4f32-a2b8-8fcde377762d)


`192.168.219.152` 

> Using the attacking machine we will scan whole subnet.

![Screenshot 2024-02-19 102421](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/eae1baed-424d-4489-a849-71a73e4ff05c)


> So we can see here the live hosts there services that they are running.


#### b) What is a firewall,andmention its types. Use the NMAP command to detect that a firewall protects the host.

#### Firewall

- A firewall is a type of network security appliance that keeps an eye on and regulates inbound and outgoing network traffic in accordance with pre-established security rules. Its main goal is to defend devices and networks from malicious activity, assaults, and unauthorised access. It is possible to deploy firewalls using hardware, software, or a combination of the two. They function by looking at network traffic packets and comparing them to the administrator's preset rules or policies.
    
- A packet is permitted to get across the firewall if it matches a rule. If it doesn't fit any of the rules, it's either rejected or forwarded to another place for more examination.
    

#### Firewall types

- Software firewall.
- Hardware firewall.
- Packet filtering firewall.
- Circuit-level gateway.
- Proxy service application firewall.

#### The NMAP command to detect if a host is protected by a firewall. Here’s an example of how you might do this:

`nmap -sS -p- <target-ip>`

In this command:

`-sS` option tells NMAP to perform a SYN scan, which is a type of stealth scan. `-p-` option tells NMAP to scan all 65535 ports. This command will send a TCP SYN packet to each port on the target host. If the port is open, the target will respond with a SYN/ACK packet. If the port is closed, the target will respond with a RST packet. If there is no response, or the packet is dropped, it’s likely that a firewall is protecting the host.

### First we enable the firewall in victim machine ###

![Screenshot 2024-02-19 102843](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/fa5541ac-3713-40ad-a49c-3a88b031969f)


> So we can see that firewall in enabled.

![Screenshot 2024-02-19 104224](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/acb873c4-6239-4fd5-b2d4-bf1820656a24)


> There was no response to ports means the firewall in turned on .

![Screenshot 2024-02-19 104350](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/f799f5ec-c407-4a49-9633-e29399a78a15)


> Now we disabled the firewall and we will try to scan it.

![Screenshot 2024-02-19 104436](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/16e4fe2a-dd4f-4b7f-9043-fbb0283d68ed)


> Now it's showing the open ports and services.

#### d) What are vertical and horizontal scanning?

- `Horizontal scanning`  sends requests to the same port on different hosts. Attackers use horizontal scanning to prepare for a mass attack.
- `Vertical scanning` sends requests to different ports on the same host. Attackers typically use vertical scanning to look for vulnerabilities in a preselected target.

#### e) Use the NMAP command to scan multiple hosts.

> So we can use the `nmap target1 target2 ` and specify the ip addresses that we have to scan.

Target 1

![Screenshot 2024-02-19 132808](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/518d742e-ef39-47fd-a104-b5dba2bb9ef5)

And the ip is `192.168.219.129`

Target 2

![Screenshot 2024-02-19 133022](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/3570d73a-f4af-48a1-b1a8-9921b6f7767d)


And the ip is `192.168.219.152`

Now we will scan both the target

![Screenshot 2024-02-19 133613](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/b64d914d-7d98-408a-aba7-bf9c9eaca855)


> So we can the scan result for both targets.



#### f) Use NMAP commands to export the output in XML format.

Use the `nmap -sV <target-ip> -oX name.xml`

![Screenshot 2024-02-19 133850](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/d44814d7-d656-41e2-9575-29317a414fcb)


#### g) Use the NMAP command to get OS information about a host.

We use the flag `-O` get the os information about the target.

![Screenshot 2024-02-19 134003](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/f300937b-6524-48e7-be3f-74ea5cf3f6dd)


> So we can here see the os info.


#### h) Explain ping sweeping and Perform ping sweeping using Nmap

#### Ping Sweep

>A method of network reconnaissance called "ping sweeping" is used to find out which IP addresses are active and reachable within a network. To find out which IP addresses are reachable and available, it entails sending a string of ICMP echo request messages, or pings, to a variety of addresses, usually in a sequential manner.

>Network administrators frequently use ping sweeping to map the network and find active hosts.

Nmap command to perform ping sweep - `nmap -sn <network address>/<CIDR>`.

![Screenshot 2024-02-19 134140](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/a276870e-9357-4807-b033-9d72ed3e3772)




#### Try these below questions after completing the above commands.

#### 1. What is a web application firewall? How do you use Nmap to detect a WAF? Perform WAF fingerprint detection using NMAP.

>- A Web Application Firewall (WAF) is a security tool designed to protect web applications from various attacks, such as SQL injection, cross-site scripting (XSS), and other common web exploits. WAFs monitor and filter HTTP traffic between a web application and the Internet, identifying and blocking malicious requests before they reach the application.
    
>- To detect a WAF using Nmap, you can use its HTTP WAF fingerprinting feature. This feature sends specially crafted HTTP requests to the target web server and analyzes the responses to identify patterns that indicate the presence of a WAF.
    

`sudo nmap --script http-waf-fingerprint <target>`

![Screenshot 2024-02-19 134950](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/7dc13387-abd8-4ec7-a194-f127d0f95901)


#### 2.What is EXIF data? Tryto find EXIF data of images on a website using NMAP NSE.

#### EXIF DATA

-EXIF (Exchangeable Image File Format) data is a standard for storing metadata in image files, typically used by digital cameras and smartphones. This metadata can include information such as the camera model, exposure settings, GPS coordinates, and timestamps.

-To find EXIF data of images on a website using Nmap NSE (Nmap Scripting Engine), you can use the http-exif-spider script. This script crawls a website, downloads images, and extracts EXIF data from them. Here's how you can do it:

`sudo nmap --script http-exif-spider <website>`


![Screenshot 2024-02-19 135957](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/13a4c531-a1ac-4f7b-8b2a-4c0b3b301304)


#### 3. Use NMAP NSE to find all subdomains of the website.

All the nse scripts are loacated in `/usr/share/nmap/scripts/`

`sudo nmap --script dns-brute <website>`

![Screenshot 2024-02-19 140234](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/a044d50e-813f-4ebb-bb36-0b9c8451290a)



## 4. Perform a vulnerability scan on the target host using NMAP NSE.

Command - `nmap -sV --script=vuln <target ip>`

![image](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/bb83decd-0a70-4bea-97a6-ace6ce106cd5)


> We were able to find some vulenrablity


