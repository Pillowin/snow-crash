# snow-crash
This project will be an introduction to cyber security.

## Passwords

| User        | Password         |
| :---------: |:--------------:|
| level00     | level00        |
| level01     | nottoohardhere |

## Script

### level01

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
