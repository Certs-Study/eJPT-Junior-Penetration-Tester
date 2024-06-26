# LFI - Local File Inclusion

#### What is LFI - Local File Inclusion?

LFI stands for Local File Inclusion, a common vulnerability in web applications. It allows an attacker to include files on a server through the web browser. This vulnerability is often exploited to read sensitive files from the server, such as configuration files or data files, which can lead to further attacks or a breach of confidentiality.

**How it Works:**

* The vulnerability arises when a web application includes external files without properly sanitizing user input.
* An attacker can manipulate input data to include files located elsewhere on the server.
* This could allow the attacker to read sensitive information or execute malicious scripts, depending on the server's configuration.

**Mitigation:**

* Validate and sanitize all user inputs.
* Avoid using user input directly in file inclusion functions.
* Employ proper permissions for files and directories on the server.
* Use security measures like Web Application Firewalls (WAFs) to detect and prevent exploitation attempts.
