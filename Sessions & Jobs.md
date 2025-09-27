- Msfconsole can manage multiple modules at the same time.
- ==`Sessions`== are responsible for doing it. It creates dedicated control interface for all the deployed modules.

## Using Sessions:
- While running any available exploits or auxiliary modules in msfconsole, the user can background the session as long as the user form a channel of communication with the target host.
	- ##### Ways of backgrounding the Sessions:
		- `Ctrl + Z`
		- use `background` command in the case of `Meterpreter` stages
			- This command will prompt a confirmation message
	- After backgrounding a session the msfconsole will allow user to use another module.

	- #### Listing Active Sessions:
		
		- For listing all background sessions use command ==`sessions`==
	
	- #### Interacting with a Session:
		
		- To interact with the background session use command 
			- sessions -i `<index_no. of_the_session>`
			- example:
				- ==`sessions -i 1`==
	
- # Jobs:
	
	-  ==`Jobs`== command are used to look after active tasks running in the background and terminate the old ones to free up the port.
	- Other type of tasks inside sessions can also be converted into jobs to run in the background.
	
	- ##### Viewing the jobs Command help menu:
		
		- use `job -h` command to know more about its functionality and its options.
		
	- ##### Running an Exploit as a Background Job:
		
		- use command:
			- `exploit -j` command to run an exploit in background.
	
	- ##### Listing Running Jobs:
		
		- use command:
			- `jobs -l` command to list all the jobs that are running in msfconsole.