# snow-crash
This project will be an introduction to cyber security.

## Passwords

| User    | Password                  |
| :-----: |:-------------------------:|
| level00 | level00                   |
| flag00  | nottoohardhere            |
| level01 | x24ti5gi3x0ol2eh4esiuxias |
| flag01  | abcdefg                   |
| level02 | f2av5il02puano7naaf6adaaf |

## Script

### level00

```bash
level00@SnowCrash:~$ find / -user flag00 2>/dev/null
/usr/sbin/john
/rofs/usr/sbin/john
```

```bash
level00@SnowCrash:~$ cat /usr/sbin/john
cdiiddwpgswtgt
```

- [identify encryption method](https://www.dcode.fr/identification-chiffrement)
- [decrypt ceasar code](https://www.dcode.fr/chiffre-cesar)

### level01

```bash
flag00@SnowCrash:~$ cat /etc/passwd | grep flag01
flag01:42hDRfypTqqnw:3001:3001::/home/flag/flag01:/bin/bash
```

Using **john the ripper** I was able to find corresponding password.

```bash
user@hostname:~$ echo "42hDRfypTqqnw" > /tmp/password-file && john /tmp/password-file && john -show /tmp/password-file
Loaded 1 password hash (descrypt, traditional crypt(3) [DES 128/128 SSE2-16])
No password hashes left to crack (see FAQ)
?:abcdefg
1 password hash cracked, 0 left
```
