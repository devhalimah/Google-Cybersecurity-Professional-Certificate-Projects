<h2>Scenario:</h2>
<p>You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DDoS attack, which compromised the internal network for two hours until it was resolved.</p>

<p>During the attack, your organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services.</p>

<p>The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a distributed denial of service (DDoS) attack.</p>

<p>To address this security event, the network security team implemented:</p>
<ul>
  <li>A new firewall rule to limit the rate of incoming ICMP packets</li>

<li>Source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets</li>

  <li>Network monitoring software to detect abnormal traffic patterns</li>

  <li>An IDS/IPS system to filter out some ICMP traffic based on suspicious characteristics</li>
  </ul>

<p>As a cybersecurity analyst, you are tasked with using this security event to create a plan to improve your company’s network security, following the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF). You will use the CSF to help you navigate through the different steps of analyzing this cybersecurity incident and integrate your analysis into a general security strategy:</p>

<ul>
  <li>Identify security risks through regular audits of internal networks, systems, devices, and access privileges to identify potential gaps in security.</li>

<li>Protect internal assets through the implementation of policies, procedures, training and tools that help mitigate cybersecurity threats.</li>

<li>Detect potential security incidents and improve monitoring capabilities to increase the speed and efficiency of detections.</li>

<li>Respond to contain, neutralize, and analyze security incidents; implement improvements to the security process.</li>

<li>Recover affected systems to normal operation and restore systems data and/or assets that have been affected by an incident. </li>
  </ul>
  
<h3>Solution</h3>
  <b>Step 1 (Identification of attack type and systems affected):</b>
<p>
  Type of attack: ICMP flood attack.<br>
  Since the DDos attack that shut the organization’s network services down was due to an incoming flood of ICMP packets, the DoS attack type was an ICMP flood attack.
  <p>The only system affected was the organization's internal network. </p>
</p>

<b>Step 2 (Protection of assets from compromise):</b>
<p>
  <ul>
    <li>A new firewall rule should be created to limit the rate of incoming ICMP packets</li>
    <li>There should be source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets</li>
    <li>Installation of network monitoring software to detect abnormal traffic patterns</li>
    <li>An IDS/IPS system should be installed to filter out some ICMP traffic based on suspicious characteristics</li>
  </ul>
  Since the DDos attack that shut the organization’s network services down was due to an incoming flood of ICMP packets, the DoS attack type was an ICMP flood attack.
  <p>The only system affected was the organization's internal network. </p>
</p>

<b>Step 3 (How to detect similar incidents in the future):</b>
<p>
  By implementing all measures listed in <b>Step 2,</b> incident detection will be a lot easier since the firewalls and IPS/IDS systems would continuously monitor network traffic on network devices to check for suspicious activity, such as incoming external ICMP packets from non-trusted IP addresses attempting to pass through the organization’s network firewall. 
</p>

<b>Step 4 (Creating a response plan for future cybersecurity incidents):</b>
<p>
  After identifying the tools and methods put in place for detecting potential vulnerabilities and threats, there is need to create a response plan in the event of a future incident. This can be carried out by creating an updated security playbook so everyone on the team will understand how to go about incident response in the event of a future incident.
</p>

<b>Step 5 (Recovering from the incident):</b>
<p>
  All pending organizational services and internal or external delivery errors should be fixed and forwarded to intended recipients immediately after the incident has been resolved. With a firewall rule configured to limit the rate of incoming ICMP packets in the organization's internal network, there is minimal possibility of encountering an ICMP flood attack within the organization's network.
</p>
