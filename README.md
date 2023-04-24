### [ID]
CVE-2023-27105


### [Affected Products and Versions]
Shanling Eddict Player v2.1.3 (Android Application)

Shanling Mtouch OS v3.3 (firmware for Shanling M2x Music Player)


### [Vulnerability Type]
Directory Traversal


### [Description]
A vulnerability in the Wi-Fi file transfer module of "Mtouch OS" allows attackers to arbitrarily read, delete or modify critical system files of music player via http connection. A similar vulnerability also appears in "Eddict Player", which allows attackers to read, delete or modify any files in Android external storage when the files & media permission is given to this application. 

***

When Wi-Fi file transfer module is activated, it will open a http server on port 8888. Normally, its front-end interface can prevent users from accessing the parent directory of the working directory of Wi-Fi file transfer. 
![image1](https://user-images.githubusercontent.com/131645424/233952262-0472c394-9456-409e-972c-3564857bc703.jpg)


However, the front-end restrictions can be simply bypassed by sending parameters in GET requests directly to /list, /delete or /download to list directories, delete files or download files. 
![image2](https://user-images.githubusercontent.com/131645424/233952280-a88c606a-f2cc-449f-8d9a-1b09f2c1a873.jpg)
![image3](https://user-images.githubusercontent.com/131645424/233952297-90755235-819b-4231-8151-71754005f20c.jpg)


The attackers can also upload any kinds of files by sending modified POST requests to ./upload. 


### [Vendor Homepage & Software Link]
https://en.shanling.com/

https://en.shanling.com/download/63

https://play.google.com/store/apps/details?id=com.shanling.eddictplayer

