🔧 Understanding Metasploit Modules

A module in Metasploit is a pre-built, reusable script that performs a single offensive or defensive action — from scanning and exploiting to post-exploitation tasks. Modules let you focus on workflow and logic instead of rewriting common attack and enumeration code.

📌 Types of Modules

exploit — Proof-of-concept code that attempts to take advantage of a vulnerability.

auxiliary — Scanners, fuzzers, brute-forcers, and enumeration tools (non-exploit).

payloads — Code executed on the target (reverse shell, Meterpreter, single/staged).

post — Post-exploitation tasks: credential harvesting, persistence, pivoting.

encoders / nops — Helpers for payload shaping (legacy; limited use today).

plugins — Add extra functionality to msfconsole (automation, reporting).

🎯 Why Use Modules?

Modules provide:

Standardized, tested actions you can reuse across engagements.

Faster proof-of-concept and validation of vulnerabilities.

Modularity: mix and match exploits + payloads for flexibility.

Built-in metadata (CVE, references, rank) that speeds triage and research.

🔑 How Modules Work (quick)

Module path: type/platform/service/name
Example: exploit/multi/http/struts_code_exec_classloader

Index: msfconsole may show a numeric index you can use (e.g., use 6).

Common options: RHOSTS, RPORT, LHOST, LPORT, PAYLOAD.

Helpful commands:
