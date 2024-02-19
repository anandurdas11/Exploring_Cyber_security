## Perform Denial of Service (DoS) attacks using ARP Cache Poisoning attacks. ##

## Tool used Here ##

## Ettercap ##


The DoS (Denial of Service) attack plugin in ettercap is used to overload a target system or network with traffic in order to prevent the system or network from operating normally. This attack aims to prevent authorised users from accessing the target system or network. The way the DoS attack plugin in ettercap operates is by flooding the target with a lot of network traffic. Requests sent over the network, such as HTTP or DNS inquiries, might be considered genuine traffic.

Scan for hosts

![Screenshot 2024-02-19 142815](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/978fde9d-f338-4213-9627-da88c0fb5a53)


![Screenshot 2024-02-19 142844](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/3dd9432f-31cd-49d7-843d-838c53027be4)


> We first start the MITM attack after that we will perform the dos attack.

![Screenshot 2024-02-19 142924](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/8f80c882-3952-4b80-9a91-ed97e5760ee3)


> So the arp posining is started 

And now run the dos_attack plugin.

![Screenshot 2024-02-19 143053](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/0d5c6872-7dbf-4b23-a6a7-f834f8b03543)


> We add the victim ip.

![Screenshot 2024-02-19 143145](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/40b6a357-acfa-43f9-afe3-ab425952a8fd)


> Then we add an unused ip

![Screenshot 2024-02-19 143413](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/f534c8f3-b6f5-47b3-9534-59eba3027e8e)


> So the attack is started


As soon as we activate the plugin, the victim becomes unresponsive because the target IP starts bombarding the victim with packets. Consequently, the victim's internet searches never seem to finish loading.

![Screenshot 2024-02-19 144039](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/c2860019-fc85-4c91-b7fe-a8b47fe9500e)


> The victim was not able to load the website so out attack was successful.

## ICMP redirect (ARP poisoning)

Now, open Ettercap and start host scanning then, add victim’s IP to target 1 and default gateway to target 2

![Screenshot 2024-02-19 144039](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/33db5ebd-a38e-40dd-9266-bf4f0d02a9a9)

After adding the respective hosts as targets start Arp poisoning. And after starting ARP poisoning simultaneously run the Wireshark in the background.

![Screenshot 2024-02-19 144516](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/32f46074-22e0-4f37-832d-7bf39ceea374)


![Screenshot 2024-02-19 144643](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/c35a9412-3766-4140-8401-a31f6dd6d446)


Choose icmp redirect and add the mac address and ip address of the default gateway.

![Screenshot 2024-02-19 144823](https://github.com/anandurdas11/Exploring_Cyber_security/assets/83402050/32b9a986-bb1e-4fd7-8d74-3604c97e665b)


As we can see , the redirected message displayed in wireshark.
