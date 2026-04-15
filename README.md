# Network Traffic Analysis Wireshark

## Overview 
I used Wireshark to analyze real world PCAP files containing malicious network traffic. I also investigated simulated SOC scenarios to identify infected hosts, extract the indicators of compromise, and document the findings as an incident report.

## Tools Used
- Wireshark
- malware-traffic-analysis.net PCAP exercises

## Objectives 
- Locate the C2 communication between internal hosts and the external malicious IPs
- Extract the host information including IP, MAC address, hostname, and user account
- Identify infected hosts from the network traffic using Wireshark filters
- Document my findings in the format of a SOC incident report

## Exercise Analyzed
- Exercise 1: Easy as 123 (2026-02-28)

## Skills Demonstrated 
- Analyzing network packets using Wireshark
- Identifying C2 communication as well as suspicious traffic patterns
- Using NBNS, Kerberos, and DNS filters to extract the host as well as the user information
- Incident documentation and reporting

## Exercise 1 Findings 
**Scenario**
A SIEM alert flagged NetSupport Manager RAT activity from the external IP 45.131.214.85 over the TCP port 443. The task was to identify the infected host from the retrieved packet capture.
**Infected Host Details**
- IP Address: 10.2.28.88
- MAC Address: 00:19:d1:b2:4d:ad
- Hostname: DESKTOP-TEYQ2NR 
- User Account: brolf
- Full Name: Becka Rolf
**Analysis**
I filtered the traffic by the known C2 IP which was 45.131.214.85 to confirm 10.2.28.88 was the communicating internal host. Then I used the NBNS filter to be able to identify the hostname and the Kerberos AS-REP packet to be able to extract the user account name.
**Malware**
- NetSupport Manager RAT: This is a remote access tool that is used by attackers to maintain persistent access to compromised machines. 
