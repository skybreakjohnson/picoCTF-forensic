# picoCTF/forensic

## Name: enhance

### lets open the image in browser

![alt text](https://github.com/skybreakjohnson/picoCTF-forensic/blob/main/enhance_1.png?raw=true)

### nothing there, lets look at the source code

![alt text](https://github.com/skybreakjohnson/picoCTF-forensic/blob/main/enhance.png?raw=true)

### looks like a flag trys to hide in there, lets write a script to parse the flag out

```python
import html2text

# read the html file
html = open('html.html', 'r')
f = html.read()

# convert to text
h = html2text.HTML2Text()

# ignore converting links
h.ignore_links = True

print(h.handle(f))
```

```
python html_parser.py

image/svg+xml p i c o C T F { 3 n h 4 n c 3 d _ 2 4 3 7 4 6 7 5 }
```
### not beautiful, but we got it 
