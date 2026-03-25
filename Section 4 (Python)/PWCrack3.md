wget https://artifacts.picoctf.net/c/18/level3.py  
wget https://artifacts.picoctf.net/c/18/level3.hash.bin  
wget https://artifacts.picoctf.net/c/18/level3.flag.txt.enc  
-> 把code和hash丟vs code爆改  
```python
import hashlib

user_pw = open('level3.hash.bin', 'rb').read() #讀anser
pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]

def hash_pw(pw_str): #題目提供 把陣列值hash
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()

for pw in pos_pw_list:
    test_hash = hash_pw(pw)
    if test_hash == user_pw:
        print(pw)
```
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/2fb3fe44-6681-4f53-8106-9569aa2e8217" />
