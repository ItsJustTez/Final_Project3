# Red Team: Summary of Operations

### Table of Contents
- Exposed Services
- Critical Vulnerabilities
- Exploitation

# Exposed Services

Nmap scan results for each machine reveal the below services and OS details.
- $ nmap -sV 192.168.1.110


This scan identifies the services below as potential points of entry:
- Target 1
     -     22/tcp       open ssh                      OpenSSH 6.7p1 Debian 5+deb8u4
     -     80/tcp	      open http                     Apache httpd 2.4.10 ((Debian))
     -     111/tcp     open rpbind                 2-4 (RPC #100000)
     -     139/tcp     open netbios-ssn        Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
     -     445/tcp     open netbios-ssn        Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
 


The following vulnerabilities were identified on each target:
- Target 1:

	- Critical Vulnerability #1:
		Weak password for Michael. The password was his name with no capital letters.

	- Critical Vulnerability #2: 
		Steven’s password requirements were weak and easily cracked by John the Ripper.

	- Critical Vulnerability  #3:
		MySQL Server login contained login credentials in plain text and was easily noticed. 

	- Critical Vulnerability  #4:
		While logged into Steven’s account, python code was able to be executed to escalate to root privileges.


















# Exploitation

The Red Team was able to penetrate `Target 1` and retrieve the following confidential data:
 - Target 1

	 - `flag1.txt`: b9bbcb33e11b80be759c4e84486242d


![image](Pictures\Flag1_Project3.png)
















	- `flag2.txt`: fc3fd58dcdad9ab23faca6e9a36e581c


![image](Pictures\Flag2_Project3.png)


### Exploit Used

 - Accessed Michael’s server by using SSH with his IP address and password:
	 - ssh michael@192.168.1.110  password: ‘michael’

