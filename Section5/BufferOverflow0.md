-> 先從main函式再看到vuln函式(string互換)  
-> 但因buf1[100]和buf2[16]空間大小不同 交換會導致buffer overflow  
-> 陣列 > buf2 就會產生 overflow  
python3 -c "print('A' * 32)" | nc saturn.picoctf.net 59363  
-> -c : commend 直接在webshell執行  
-> | : pipe左指令直接傳送給右指令  
