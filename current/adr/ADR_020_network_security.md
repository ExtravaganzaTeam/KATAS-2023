# Title

Network security

## Status

**accepted**

## Context

Network security is the most important security topic nowadays. 

A DMZ refers to a subnet that is physically or logically separated from the internal network. This subnet is used to separate untrusted devices from trusted devices. Traditionally, in a DMZ you would put all the devices that are required to be Internet-accessible. These can include your web servers, an SFTP server, email exchange servers, etc. Then, access from the DMZ to the internal network is further controlled and closely monitored, usually through a firewall.  

It is important to consider that many of the severs in the DMZ still need to access systems on an internal network. For example, the web server may need to be able to reach into the internal network to access the backup server to perform daily backups or the database server to store information. Therefore, it is important to know that a DMZ is not necessarily blocking all connections, but it is restricting them to only approved connections based on source/port/service/destination.  

Other good but very resource consuming stategy is constant network traffic scanning not only with anty-virus solutions but systems like nVidia Morpheus applying artificial intelligence to protect network resources in real time.  

[nVidia Hardvare Acceleration](https://www.nvidia.com/en-us/industries/cybersecurity/)  
[nVidia Morpheus](https://developer.nvidia.com/morpheus-cybersecurity)  

## Decision

[decision and justification (the “why”)]

We have decided to use DMZ as a well known method to have multiple protection layers on network level. Some of services deployed in datacenter require direct Internet acces and others do not. The DMZ mechanism is well suited for these needs.  

DMZ is used to house those servers and applications that are exposed to the Internet. Many of these are required to be exposed to the Internet with a legitimate business-related justification. You can’t just deny access to your website or you won’t get any business. However, because they are exposed to the Internet, they are at a much higher risk of compromise. Anyone can access these, and any device exposed to the Internet is under constant attack.

DMZ's are an essential part of network protection for both individual users and large organizations. They provides an extra layer of security to the computer network by restricting remote access to internal servers and information, which can be very damaging if breached.

## Consequences

Higher security is always with a cost. More intermediate layers have always impact on overall latency.  

As mentioned above, the systems in the DMZ are still exposed to the Internet and thus have a higher level of residual risk. Because of that, there are some additional security considerations for these devices, including:  

Ensure these devices are hardened using industry-recognized benchmarks. We recommend the Center for Internet Security (CIS) Benchmarks located here.
Use different passwords on these systems than other systems. When an attacker compromises a system, they can dump the contents of memory, which may include passwords.  
Perform regular penetration tests to validate the effectiveness of your controls. This should include external penetration tests to see the exposure of the systems in the DMZ as well as segmentation validation testing that assesses whether an attacker can pivot into the internal network.  

[Go back](./README.md)