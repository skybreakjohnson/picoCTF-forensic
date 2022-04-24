# picoCTF/forensic

## Name: Lookey here

### looks like a normal text file
```
file anthem.flag.txt

anthem.flag.txt: Unicode text, UTF-8 text
```

### were lazy so just try to grep for 'pico'
```
cat anthem.flag.txt |grep pico

we think that the men of picoCTF{gr3p_15_@w3s0m3_58f5c024}
```
### well..
