- Databases in msfconsole are used to keep track of our results.
- During more complex machines or target assessments things can get a little fuzzy and complicated due to the sheer amount of search results, entry points, detected issues, discovered credentials, etc.

- Msfconsole has built-in support for the PostgreSQL database  system.
- Database entries can also be used to configure Exploit module parameters with already existing findings directly.

- ## Setting up the Database:
	
	- ### PostgreSQL status:
		
		- Ensure that the PostgreSQL server is up and running on the host machine. Using the command:
			- `service postgresql status`
	
	- ### Start PostgreSQL:
		
		- To start the ==`postgresql`== service use the command: 
			- `systemctl start postgresql` 
	
	- ### MSF - Initiate a Database:
		
		- To create and initialize the MSF database, Use the command:
			- `msfdb init`
			- before initiating the database update the system using 
				- `apt update`
			- To check the status of if the `postgresql`  use:
				- `msfdb status`
	
	- ## MSF - Connect to the Initiated Database:
	
		-  After initiating the MSF database use 
		
			- `msfdb run` command to start
	
	- ## MSF - Reinitiate the Database:
	- 
		- If the database is already configured and are not able to change the password to the MSF username, then reinitiate the database:
			
			- `msfdb reinit`
			- `cp /usr/share/metasploit-fra,work/config/database.yml ~/.msf4/`
			- `service postgresql restart`
			- `msfconsole -q`
			- `msf6` > `db_status`
		- After going through each and every command from above we are good to go.
		- msfconsole offers integrated help for the database.
			- use `help database` command
	
	- ## Using the Database:
	
		- With the help of the database user can manage many different categories and hosts that we had been analyzed by the user.
		- The database can be exported and imported.
		
		- #### Workspace:
		
			- Workspace can be defined as the folders in the project.
			- It can segregate the different scan, results, hosts and extended information by IP, subnet network, or domain.
			- To view the current Workspace list
				- use ==`workspace`== command
					- adding a `-a` or `-d` switch after the command will either add or delete that workspace.
					- `workspace -a <workspace_name>`
					
					
					
	- ## Importing Scan Results:
		
		-  `db_import` command can be used to import the other tool scan result for the parsing the other tool results.
		- it also save the results in the database.
		- `.xml` file type is preferred for `db_import`.
		
			- #### Importing Scan results:
				
				- `db_import Target.xml` 
	
	- ## Data Backup:
		
		- To back up the data with the help of PostgreSQL service.
			- use ==`db_export`== command
			- `db_export -h`
	
	- ## Hosts:
		
		- The ==`hosts`== command displays a database table automatically populated with the:
			- host address
			- hostname, etc.
			- use ==`hosts -h`== command to know more about the functionality of the command.
	
	- ## Services:
		
		- The ==`services`== command functions the same way as the hosts command
		- It contains a table with descriptions and information on the services discovered during scans or interactions.
		- use ==`services -h`== command to know more about the functionality of the command.
	
	- ## Credentials:
		
		- The creds command allows the user to visualize the credential gathered during the interactions with the hosts.
		- add credential manually, match existing credential with the port specification, add descriptions, etc.
			
		- use ==`creds -h`== command to know more about the functionality of the command. 
	
	- ## Loot:
		
		- The ==`loot`== command works in conjunction with the command Credential to offer user an at-a-glance list of owned services and users.
		- use `loot -h` command to to know more about commands