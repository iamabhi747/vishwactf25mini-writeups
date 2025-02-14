# Lost Evidence

- Tool used : https://github.com/RickdeJager/stegseek

Tried exiftool if there is hidden information and then used some steganography tools 

``` stegseek lastdays.jpg /usr/share/wordlists/rockyou.txt ```

- Tried with the rockyou.txt that is available 
- Viewed the output file 

```  cat lastdays.jpg.out ```

![alt text](image.png)

- Taken the binary to CyberChef website to decode it 
- Used below recipe to configure the flag from the Binary

![alt text]({754DDAAD-32F6-4D1C-AC8C-5767AD8CDA5F}.png)

VishwaCTF{Shad0ws_H1de_Truth}