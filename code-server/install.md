# How to install code server in kali nethunter rootless

### Step 1: Download code server
[Download](https://github.com/coder/code-server/releases/download/v4.19.1/code-server-4.19.1-linux-arm64.tar.gz) the latest code server

### Step 2: Move file
Go to your phone storage's download folder and cut `code-server-4.19.1-linux-arm64.tar.gz`
 file and paste it in kali<br> *(In my case I paste file in kali-arm64/home/kali)*
<br><br>
![](ls.png)

> Use [files app](https://play.google.com/store/apps/details?id=com.marc.files) to move file from phone storage to kali.

### Step 3: Extract file 
Extract the file 
```linux
tar -xvf code-server-4.19.1-linux-arm64.tar.gz
```

### Step 4: Change password 
Change password for code server
```
nano ~/.config/code-server/config.yaml
```
![](pass.png)

> Don't want to type password each time while connecting? [click here](#connect-without-password)

### Step 5: Go to bin
Go to bin folder
```
cd code-server-4.19.1-linux-arm64/bin
```

### Step 6: Run code server 
Run code server
```
./code-server
```
### Step 7: Connection 
Enter this url in Chrome
[http://localhost:8080/](http://localhost:8080/) and type password to connect 

## Connect without password
Change the value of `auth` to `none`
![](none.png)

*Not need to change the `bind-addr` in your case it might be `127.0.0.1:8080`*

<hr>

Need any help?
Contact me on <a href="mailto:himanshukushwaha548@gmail.com">himanshukushwaha548@gmail.com</a>
