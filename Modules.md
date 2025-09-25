# Lets get deep with Modules part.

- Metasploit `modules` are prepared scripts  with a specific purpose and corresponding functions that have been developed and tested in the wild.
- The exploit category consists of so-called ==`(POCs){proof-of-concept}`== that can be used to exploit existing vulnerabilities in a large automated manner.
- Never think that failure of exploit disproves the existence of the suspected vulnerability.
- Many `exploits` needs ==`customizations`== according to the target host t make exploit work.

### Syntax:

- `<No.> <type>/<os>/<service>/<name>`

	- ##### No. or Index number:
	
		- The `No.` tag will be displayed to select the exploit. 
	
	- ##### Type:
	
		- The `Type` tag is the first level of segregation between the Metasploit modules.
		- Some types are not directly usable as an exploit module.
			- Types of `types`:
	
				- `auxiliary` | scanning, fuzzing, sniffing and admin capabilities.
	
				- `encoders` | Ensure that payloads are intact to their destination.
	
				- `exploit` | To exploit or to take advantage of a existed vulnerability.
	
				- `NOPs` | (`No operation code`) keep the payload size consistence across exploit attempts
	
				- `payloads` | Code runs remotely and calls back to the attacker machine to establish a shell.
	
				- `plugins` | Additional scripts can be integrated with msfconsole
	
				- `post` | Wide array of modules to gather information, pivot deeper, etc.
	
	- ##### OS:
	
		- The `os` tag specifies which operating system and architecture the module was created for.
		- metasploit framework works for different `os` platform.
	
	- ##### Name:
	
		- The `name` tag explains the actual action that can be performed using this module 

- ###### Example:
	-  `6   exploit/multi/http/struts_code_exec_classloader`
	- `13  exploit/multi/http/tomcat_mgr_deploy`

## Search for Module:

- Metasploit also offers a well-developed search function for the existing modules.
- with the help of the ==`search`== function the payloads, exploit and others can be found easily.
- ###### `syntax`:
	- `search <keyword>`
	- `help search`
		![[Screenshot 2025-09-25 225627 1.png]]
	
- ## Specific search:
	- The search can be mad a bit more coarse and reduce it to one category of the service.
	- Metasploit-Framework provides the user with an excellent property i.e. `specific search property` :

		- `search type:<mention_type> platform:<mention_paltform> cve:<metion_it_if_exist> rank:<mention_rank_>`

- ## Module Selection:
	
	-  Module can be selected by seeing or using other enumeration tools like:
	
		- `nmap` |  for host version or service discovery.
		- `curl` | for vulnerable server version discovery., etc
	
	- after getting the output or the result from the following ways then the user can boot up the msfconsole and use the appropriate module by using `search` command.

- ## Using Modules:
	
	- Within the interactive module, there are several options that can be specified.
	- for using the searched and selected module the user can ==`use`== command.
		- `use index_no`
		- `use <exploit_option>`
	- To check which options are needed to be set before exploit.
		- use `show options` command
			- this command will list all the options that use may or may not be set for the exploit from the module.
			- Everything required to be set before the exploitation can occur will have a ==`yes`== under ==`required`== column
	- After selecting the module if the user want to know something about the module the use `info` command.
		- this command will give the series of information that can be important.
	- After getting info set everything for the attack.
		- specify the target and the attacker and other required credential using `set` command
		- Example:
			- `set rhost <target>`
			- `set rport <port_number>`
			- `set <listed_options> <value>`

- ## MSF - Permanent Target Specification:
	
	-  there is an option `setg` which specifies options selected by user as permanent until the program is restarted.
	
		- `setg RHOSTS <target>`

- ## MSF - Permanent LHOST specification

	-  `setg Lhost <user_ip_address>`

After setting up everything use ==`run`== or ==`exploit`== command to initiate the modular attack.

[[Introduction to Metasploit]]