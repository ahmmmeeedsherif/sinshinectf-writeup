## Enumeration
**First I make nmap scan and I found SSH and HTTP Ports opened**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/1.png" style="width: 100%;"/>
**as the HTTP is opened so we will make directory enumeration to find hidden directories**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/2.png"/>
**I found wordpress directory **
## Initial Access
**I entered /wordpress/wp-login.php**
**I entered the username and password admin and I found that the username admin is already registered **
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/3.png" style="width: 100%;"/>
**I made brute forcing on the user admin and I found the password**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/4.png" style="width: 100%;"/>
**I found a plugin called uploader so I will use it **
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/6.png" style="width: 100%;"/>
**I entered the the Pages to use the Plugin**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/7.png" style="width: 100%;"/>
**I used by `[uploader]`**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/8.png" style="width: 100%;"/>
**I can upload any file so I uploaded a simple backdoor**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/9.png" style="width: 100%;"/>
**I found a note file in the root directory**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/10.png" style="width: 100%;"/>
**I made cat /note**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/11.png" style="width: 100%;"/>
**I found directory called note so I entered it**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/12.png" style="width: 100%;"/>
**I found .id_rsa and .note so I read both of them**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/14.png" style="width: 100%;"/>
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/15.png" style="width: 100%;"/>
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/16.png" style="width: 100%;"/>
**I take a copy from id_rsa and I put it in a file in my machine then I use john to make it as a hash to get the passphrase of it**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/17.png" style="width: 100%;"/>
**I used john to crack the passphrase**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/18.png" style="width: 100%;"/>
**I used the passphrase sunshine to enter the machine through the ssh using private key**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/19.png" style="width: 100%;"/>
**I entered the Desktop and I found the user flag**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/20.png" style="width: 100%;"/>
## Privesc 
**I made this command to exploit SUID Binaries**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/21.png" style="width: 100%;"/>
**I found the vim.tiny so I make a hash using openssl**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/25.png" style="width: 100%;"/>
**I use the vim.tiny to edit the file /etc/passwd to edit the root password**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/26.png" style="width: 100%;"/>
**I edited the password hash**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/27.png" style="width: 100%;"/>
**I made su root and type the password I generated and I have root priv now
and I found the flag**
<img src="https://github.com/ahmmmeeedsherif/sunshinectf-writeup/blob/main/28.png" style="width: 100%;"/>
