wget https://artifacts.picoctf.net/c/33/level5.py  
wget https://artifacts.picoctf.net/c/33/level5.flag.txt.enc  
wget https://artifacts.picoctf.net/c/33/level5.hash.bin  
wget https://artifacts.picoctf.net/c/33/dictionary.txt  
->照樣全丟vs code  
```python
import hashlib

flag_enc = open('level5.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level5.hash.bin', 'rb').read()
def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()

with open('dictionary.txt', 'r') as dic: #dic = iterator
    for line in dic: #逐行讀取
        pw = line.strip() #清除換行符
        test_hash = hash_pw(pw)
        if test_hash == correct_pw_hash:
            print(pw)
```
python3 level5.py
-> run file
eee0
