# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system

## OUTPUT:

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/eb8c36ab-9e69-4f8f-9b6d-2ade910569ef)

## Invoke msfconsole:

## OUTPUT:

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/9578829f-6de0-4cc3-a96e-1a46537f124e)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT :

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/5dc07658-553e-45eb-a2ee-4ceb998c693e)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT :

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/f27a26ea-73c8-4e9b-920e-f0e785315722)


use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT : 

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/5dc17034-b05e-4510-91b5-7d8ee7a9e40c)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT :

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/87f0d83d-fb6b-4ca0-abdf-9e72f033c862)

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/a9537d13-db5c-478d-bb94-edb37d33e3e1)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/fb2c99fc-35c1-4339-b006-fb15084a9827)

The info command provides information regarding a module or platform

## OUTPUT :

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/c703dc7b-c1b4-4686-ba4e-0ecac3ee225d)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/00d59401-8663-4024-af15-f5629ccc1951)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/e6f84718-6671-49af-8f47-577cf3427922)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/a7970dd9-4120-4281-a417-7987ecdfb49c)


Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/3c87ffe5-cd16-45ee-add5-c2c0fe2efee7)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/d9dd975d-be20-42bf-bc97-c2d71ad2dc94)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/priya672003/Metasploit-for-reconnaissance/assets/81132849/e0f621da-21be-4aba-bd6b-9233ca83bc69)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
