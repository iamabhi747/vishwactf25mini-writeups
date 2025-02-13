# Compression 

- Tool used : https://github.com/openwall/john

- The initial name of pdf was "Hola solucionador.pdf" but I changed it to "hello.pdf" 

- Used famous john the ripper to crack the password 

- First to find the password of the pdf I used "pdf2john" 

``` pdf2john hello.pdf >> output.txt ```

- Then seen the output of the file 

``` cat output.txt ``` 

![alt text]({6A02E86A-9E3C-4F3F-AB6E-28E5B5EE9802}.png)

- The very next step was followed to get password from the output from "pdf2john"

``` john --wordlist=/usr/share/wordlists/john.lst --rules output.txt ```

- The john.lst here is literally rockyou.txt 😅

``` john --show output.txt ``` 

![alt text]({9D48141D-6D3E-4E07-BBEA-C3083C1C2E0E}.png)

- Got this huge text in the pdf file 

![alt text]({C8EC68A3-51C7-4857-90B3-6B1042F5E6C1}.png)

- In cyberchef it is detected as the zip 

![alt text]({FE63DD9B-4D73-4CF7-BA65-08D7BE5CD363}.png)

- Downloaded from the save button in the cyberchef

![alt text]({03E70752-A8CD-414D-AF25-FE2CCB7BE02A}.png)

- Unzipping the file and then reading it got the flag 

![alt text]({ABB83A58-04FD-443A-B80A-C0AD28270A7D}.png)

VishwaCTF{Spac3_1s_Amaz1ng}