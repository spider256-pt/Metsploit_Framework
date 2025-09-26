- ==`Plugins`== are readily available software that has already been released by third parties and have given approval to the creators of Metasploit to integrate their software inside the framework.
- Plugins make a pentester's life easy by bringing the functionality of well-known software into the msfconsole or Metasploit Pro environment.
- Plugins work directly with the API and can be used to manipulate the entire framework.

## Using Plugins:

- To start using plugins:
	- Ensure that it is installed in the correct directory on the machine
		- Navigate to:
			- `/usr/share/metasploit-framework/plugins`
		- if the plugins is found, then we can access it by using msfconsole.
	
	- ### Example of using plugins: (nessus.rb)
		
		- to load or to use a specific plugins use 
			- ==`load <plugins_name>`==
			- `load nessus`
		- if the plugin is not installed correctly, then the msfconsole will throw a error like:
			- `load <plugin_that_does_not_exist>`
			- ###### Error:
				-` [-] Failed to load plugin from /usr/share/metasploit-framework/plugins/Plugin_That_Does_Not_Exist.rb: cannot load such file -- /usr/share/metasploit-framework/plugins/Plugin_That_Does_Not_Exist.rb`
# Installing new Plugins:

- https://github.com/darkoperator/Metasploit-Plugins.git
- The above link can use to install all the plugins for the msfconsole.
- The link above get a couple if Ruby `(.rb)` files which can directly place in the folder.
	- `git clone https://github.com/darkoperator/Metasploit-Plugins.git`
	- `ls Metasploit-Plugins.git`
	
	- #### MSF - Copying Plugins to MSF:
		
		- `cp ./Metasploit-Plugins/<plugin_name.rb> /usr/sahre/metasploit-framework/plugins/<plugin_name.rb>` 

# Mixins:

- The Metasploit Framework is written in Ruby, an OOP language.
- This plays a big part in what makes msfconsole excellent to use
- `Mixins`  offers flexibility to both the creator of the script and the user.
	- Mixins are classes that act as methods for use by other without having to be the parent class.
		- They are mainly used when we:
			- `Want to provide a lot of optional features for a class`
			- `Want to use one particular feature for a multitude of classes`
		- Most of the Ruby programming language revolves around Mixins as Modules.
		- The concept of Mixins is implemented using the word `include`, to which a name of the module is passed as a parameter.
	
[[Introduction to Metasploit]]