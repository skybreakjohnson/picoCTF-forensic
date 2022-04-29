# picoCTF/forensic

## Name: Wireshark doo dooo do doo...

### lets get an overview of the protocols
```
wireshark shark.pcapng

statistics > protocol hierarchy
```

![alt text](https://github.com/skybreakjohnson/picoCTF-forensic/blob/main/shark1_1.png?raw=true)

### its a lot of tcp and some http 
![alt text](https://github.com/skybreakjohnson/picoCTF-forensic/blob/main/shark1_2.png?raw=true)

### looks like some kerberos sessions, but since we know there no kerberos protocols we go straight into http and look for possible plain text

![alt text](https://github.com/skybreakjohnson/picoCTF-forensic/blob/main/shark1_3.png?raw=true)

### lets dive deeper..

![alt text](https://github.com/skybreakjohnson/picoCTF-forensic/blob/main/shark1_4.png?raw=true)

### looks like rot13, we already have a script for this:

```python
import sys
import codecs

if sys.argv[1] == '--help' or sys.argv[1] == '-h':
    print('Usage: python rot13.py <hash>')
    exit(0)
else:
    print(codecs.encode(sys.argv[1], "rot13"))
```
```
python rot13.py cvpbPGS{c33xno00_1_f33_h_qrnqorrs} 
picoCTF{p33kab00_1_s33_u_deadbeef}
```
