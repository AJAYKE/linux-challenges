## UNDERSTAND THE POWER OF ROOT USER

```bash
adduser ajay
usermod -a -G sudo ajay #we are appending(-a) user ajay to the sudo group(-G)
```

It will prompt for password and other details, password will be used to login to root user
After adding the user, to ssh into the isntance using the same pem key, you should be authorised to login using the pem key.

so, first we should change the user to ajay and add authorized_keys from ubuntu to your user account and login again.

```bash
sudo su -ajay #change user to ajay

mkdir -p ~/.ssh #create an ssh directory

chmod 700 ~/.ssh #give permissions for the folder

cat /home/ubuntu/.ssh/authorized_keys >> /home/ajay/.ssh/authorized_keys  #copy ubuntu user authorized keys to ajay user keys

## Now try to login with the same .pem key but ajay as user
```

you can check all hashed passwords at

```bash
cat /etc/shadow
```

to change password

```bash
passwd

#enter your old password and then your new password

sudo reboot

uptime #to check the system has actually rebooted
```

To change the hostname directly

```bash
sudo hostnamectl sethostname myvm
```

Logout and login and you can see the name change

to see the last few times sudo was typed in commands

```bash
sudo journalctl -e /usr/bin/sudo
```

to change Timezone

```bash
timedatectl #this will show the current timezone and time

timedatectl list-timezones #this will show all the timeszones available

sudo timedatectl set-timezone Asia/Calcutta #this will change the timezone directly

timedatectl #you can see new timezone
```
