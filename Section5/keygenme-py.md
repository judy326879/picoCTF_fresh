-> vs打開code  
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/7ff1eca6-f24b-49ab-b445-ab9cbe36301a" />  
```python
key_part_static1_trial = "picoCTF{1n_7h3_kk3y_of_"
key_part_dynamic1_trial = "xxxxxxxx"
key_part_static2_trial = "}"
```
-> 找出中間八個字元  
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/e7f71bf2-4c02-4fe4-a8b2-3c7c11a1a3e9" />
-> find enter_license  
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/b2192e2c-8af5-4af9-b874-f88309660a4e" />  
-> 連續判斷式 找到username_trial (ctrl+f尋找)  
-> 順序45362718  
->開新檔直接輸出  
```python
import hashlib
import base64
ans = hashlib.sha256("BENNETT".encode()).hexdigest()
print(ans[4]+ans[5]+ans[3]+ans[6]+ans[2]+ans[7]+ans[1]+ans[8])
#45362718
```   
xxxxxxxx = 08c46aa4
