# picoCTF/forensic

## Name: wave a flag

### lets see what we have got here 
```
file warm

warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=3181a501366281ab5eba1c41e54a1f40800e3966, with debug_info, not stripped
```
### looks like a linux executable, so lets just try to execute the file
```
chmod x+ warm
./warm

Hello user! Pass me a -h to learn what I can do!
```

### okey, so lets go for it
```
./warm -h

Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_755f3544}

```
