- The ==`Meterpreter`== Payload is a specific type of multi-faceted, extensible Payload that uses ==`DLL injection`==.
- It ensure the connection to the victim host.
- Can be configured to be persistent across reboots or system changes.
- Meterpreter resides entirely in the memory of the  remote host and leaves no traces on the hard drive

	- making it difficult to detect.

-  The purpose of Meterpreter is to specifically improve the post-exploitation procedure.
- It also offer the user hand-picked set of relevant tools.
- Meterpreter helps user to find:
	
	- `various privilege escalation`
	- `AV evasion techniques`
	- `vulnerability research`
	- `pivot and etc.`

- ## Running Meterpreter:
	
	-  To run Meterpreter, the user only need to select any version of it from the `show payloads` output.
	- When the exploit is completed, the following events occur.
		
		- The target executes the initial stager. This is usually bind, reverse, findtag, passivex, etc
		- The stager loads the DLL prefixed with Reflective.
		-  The Meterpreter core initializes, establishes an AES-encrypted link over the socket, and sends a GET. Metasploit receives this GET and configures the client.
		-  Lastly, Meterpreter loads extensions. It will always load `stdapi` and load `priv` if the module gives administrative rights. All of these extensions are loaded over AES encryption.
	- Whenever the Meterpreter Payload is sent and run on the target system, the user will receive a  ==`Meterpreter shell`==:
	
		- use ==`help`== command to know more about meterpreter.

- ### Using Meterpreter:
	
	- #### MSF - Network Scanning Target:
		
		- `db_nmap -sV -p- -T5 -A <target_add>`
	
	- #### MSF - Searching for Exploit:
		
		- use `search` command to find all the possible module specially exploit for the target.
			- `search <keywords>`
	
	- #### MSF - Configure Exploit & Payload:
		
		- for configuring the exploits and payload 
		- use set command to assign value to the parameters like `{RHOSTS,LHOST,RPORT,LPORT,SRVHOST,SESSIONS,etc}`
		- `set rhost <value>`
	
