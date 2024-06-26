# Path Traversal

### Path Traversal Attacks

Path traversal attacks, also known as directory traversal attacks, occur when an attacker exploits vulnerabilities in a web application to access files and directories that are stored outside the web root folder.&#x20;

By manipulating variables that reference files with ".." (dot-dot slash sequences), an attacker can read, modify, or delete sensitive files on the server, leading to unauthorized access or system compromise.

### Prevention

* **Input Validation:** Validate and sanitize all user inputs, rejecting suspicious patterns.
* **Use of Safelists:** Employ safelists for file access and operations, restricting the files that can be accessed.
* **Least Privilege:** Ensure the web server process runs with the minimal privileges necessary.
* **Updated Libraries:** Keep all server software and libraries updated to mitigate known vulnerabilities.

### **How Path Traversal Attacks Work**

At the core of a path traversal attack is the exploitation of the security mechanism that restricts web users to a certain directory—the web root directory. Attackers manipulate variables that reference filesystem paths, using sequences like `../` (dot-dot slash), aiming to break out of this designated directory.&#x20;

For instance, if an application uses unvalidated external inputs to construct file paths, an attacker could craft a request that, instead of accessing intended files (e.g., `webapp/resources/images/logo.png`), accesses sensitive files elsewhere on the server (e.g., `../../etc/passwd`).

This kind of attack leverages the fact that `../` is interpreted by the filesystem as a command to move up one directory.&#x20;

Therefore, by repeatedly inserting `../` into file paths, attackers can traverse upward through the directory structure (a technique often called "dot-dot-slash attack") to reach critical system files or other confidential information, far beyond the intended confines of the web application.
