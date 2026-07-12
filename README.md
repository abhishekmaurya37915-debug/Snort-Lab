## Snort Intrdustion:
Snort is the foremost Open Source Intrusion Prevention System (IPS) in the world. Snort IPS uses a series of rules that help define malicious network activity and uses those rules to find packets that match against them and generates alerts for users.
## Deployment Modes:
 An IPS (Intrusion prevention System) is detects and malicious traffic in real time.
An IDS (Intrusion Detection system) is detected the malicius activity and genreates alerts but does not block traffic.
## Snort-Lab
# Building Snort Lab | IDS/IPS | By Abhishek Maurya
Snort is a powerful open-source network intrusion detection and prevention system (IDS/IPS).
Important Note : If any problem occur while installation search it on YouTube rather than Google.

# Steps Before Installation.
 Open Terminal and run some commands

# sudo apt update.
<img width="561" height="230" alt="image" src="https://github.com/user-attachments/assets/21f6fcfc-f27b-48ca-b286-234321693146" />


# sudo apt upgrade.
<img width="550" height="210" alt="image" src="https://github.com/user-attachments/assets/7cf7c349-3fa0-4558-818c-9411495d1c54" />


# Installation on snort on Kali Linux.

# Open command terminal.
# (Sudo apt-get install snort)

<img width="530" height="266" alt="image" src="https://github.com/user-attachments/assets/04e9d904-653a-4d03-b50c-2f6c2e755598" />

# Check snort is install or not by checking version.

# (sbort -V)

<img width="550" height="210" alt="image" src="https://github.com/user-attachments/assets/7142883e-068c-4199-b85c-26521c3f4829" />


# Fast check ip address (ipconfig)

For me it is eno1 and ip address is 192.168.211.128

<img width="530" height="266" alt="image" src="https://github.com/user-attachments/assets/52a2a1e3-fc61-4096-88a1-1fbbcafdd3b8" />

For turning on promisc ip type command

# sudo ip link set <Your config> promisc on

sudo ip link set  eth0 promisc on

Type your configuration in Your config

<img width="321" height="122" alt="image" src="https://github.com/user-attachments/assets/ae360951-5b3b-4b7c-a115-2b38207398e6" />

Go the the directory

# sudo nano /etc/snort/snort.conf

Do some changes in file
ipvar “HOME_NET any “ will be shown change any to your ip addres

# 192.168.0.0/24

Your ip address will be different
if your ip is 192.168.1.125 so type your ip as
192.168.211.0/24

<img width="487" height="222" alt="image" src="https://github.com/user-attachments/assets/8c37003e-5568-479e-824f-fac715eb9079" />

# Writing Rules in Snort
Basic rules Can be written as the following

Enter Command

# sudo vim /etc/snort/rules/local.rules

type your rules 

1: alert icmp any any -> any any (msg:"ICMP Ping Detected"; sid:1000001; rev:1;)
2: alert tcp any any -> any 80 (msg:"HTTP Traffic Detected"; sid:1000002; rev:1;)

<img width="682" height="200" alt="image" src="https://github.com/user-attachments/assets/b967244b-e9e2-4abc-88cc-aeeafeaf28af" />

Type command for checking the logs

# sudo snort -R /etc/snort/rules/local.rules -i eth0 -A alert_fast

<img width="1075" height="711" alt="image" src="https://github.com/user-attachments/assets/9be7d991-301b-4e8e-bc3f-1dbc0b629546" />




