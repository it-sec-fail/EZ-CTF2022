# Bernie
solved 125 points
Solves: 147  Easy
I don't need protection when I have Bernie

Flag format: `EZ-CTF{Hidden_Message}`

## Solving

All the low hanging fruits does not show anything from interesst. So let's look with `steghide`.

```shell
steghide info Bernie.jpeg
"Bernie.jpeg":
  format: jpeg
  capacity: 3,2 KB
Try to get information about embedded data ? (y/n) y
Enter passphrase: 
  embedded file "FlagHere.txt":
    size: 555,0 Byte
    encrypted: rijndael-128, cbc
    compressed: yes
```

Ah okay - the flag is embedded in the image.
Let's extract that and let's try without a password ;-)

```shell
steghide extract -sf Bernie.jpeg
Enter passphrase: 
wrote extracted data to "FlagHere.txt".
```

Okay, that seems like it worked :-)

But if we look at the new file `FlagHere.txt` we will see a bunch of strange strings.
```
\28x\32x\38x\28x\32x\38x\28x\32x\38x\28x\32x\38xE\28x\32x\38x\28x\32x\38xZ\28x\32x\38x-\28x\32x\38xC\28x\32x\38x\28x\32x\38xT\28x\32x\38xF\28x\32x\38x{N\28x\32x\38xO\28x\32x\38xW\28x\32x\38x_\28x\32x\38x\28x\32x\38xY\28x\32x\38x\28x\32x\38xO\28x\32x\38xU_\28x\32x\38xS\28x\32x\38x\28x\32x\38x\28x\32x\38x\28x\32x\38xE\28x\32x\38x\28x\32x\38xE\28x\32x\38x_\28x\32x\38xM\28x\32x\38xE\28x\32x\38x\28x\32x\38x_\28x\32x\38xN\28x\32x\38xI\28x\32x\38x\28x\32x\38xC\28x\32x\38xE\28x\32x\38x}\28x\32x\38x\28x\32x\38x\28x\32x\38x\28x\32x\38x\28x\32x\38x\28x\32x\38x
```
But if we look closly, we can see some interessting chars inside of this string. Maybe if we remove this *uninteresting* chars?

```
cat FlagHere.txt | tr -d '\28x32\'
tr: warning: an unescaped backslash at end of string is not portable
EZ-CTF{NOW_YOU_SEE_ME_NICE}
```
Ah yes - there it is!

>```
cat FlagHere.txt | tr -d '\28x32\'
tr: warning: an unescaped backslash at end of string is not portable
EZ-CTF{NOW_YOU_SEE_ME_NICE}
```
Ah yes - there it is!

>  EZ-CTF{NOW_YOU_SEE_ME_NICE}
