wget https://artifacts.picoctf.net/c/13/level2.py  
wget https://artifacts.picoctf.net/c/13/level2.flag.txt.enc  
cat level2.py  
-> observe code  -> password = chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36)  
-> build file -> print(chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36)) -> password = de76  
python3 level2.py  
de76
