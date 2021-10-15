### Step - 1 prequisites
- `sudo add-apt-repository universe && sudo apt update`

### Step - 2 Setup
- `wget https://download.zulip.com/server/zulip-server-latest.tar.gz`
- `tar -xvf zulip-server-latest.tar.gz`      
- `cd zulip-server-*`
- `/scripts/setup/install --certbot --email=YOUR_EMAIL --hostname=YOUR_HOSTNAME`
##### Note :  if it gives an error try using without --certbot
- `./scripts/setup/install  --email=emailid --hostname=myhost name`
```javascript
    --email=                 (This is admin ID for getting error email from server)
    --hostname=              (The user-accessible domain name for this Zulip server. )
    --self-signed-cert       (With this option, the Zulip installer generates a self-signed SSL certificate for the server. This isn’t suitable for production use, but may be convenient for testing.)
    --certbot                (With this option, the Zulip installer automatically obtains an SSL certificate for the server using Certbot.  If you’d prefer to acquire an SSL certificate yourself in any other way, it’s easy to provide it to [Zulip](https://zulip.readthedocs.io/en/stable/production/ssl-certificates.html#manual-install))
```

### Step - 3 Setup Org
- On success, the install script prints a link. (The link is a secure one-time-use link. If you need another later, you can generate a new one by running `manage.py generate_realm_creation_link` on the server.)

-  Open the link in a browser. Follow the prompts to set up your organization, and your own user account as an administrator. Then, log in!

### Step 4: Configure and use
- Set up outgoing email so Zulip can confirm new users’ email addresses and send notifications.
    - [setup email](https://zulip.readthedocs.io/en/stable/production/email.html)
- Use gmail as complicated so you have to read setup email.



### For new Link

`su zulip`
`./manage.py generate_realm_creation_link`




- `cd /tmp`
- `wget https://download.zulip.com/server/zulip-server-latest.tar.gz`
- `tar -xvf zulip-server-latest.tar.gz`
- `./scripts/setup/install --email=mehul.akbari@gmail.com --hostname=army.rainit.in`

# ./zulip-server-*/scripts/setup/install --email=mehul.akbari@gmail.com --hostname=army.rainit.in --certbot

### Errors

### Error - 1
- `https://askubuntu.com/questions/1053167/ubuntu-error-errors-were-encountered-while-processing-redis-server`
```javascript
apt install redis-server
- bind 127.0.0.1 ::1       
        to
+ bind 127.0.0.1
```

### Error - 2
- bmemcached.Client((cache["LOCATION"],), **cache["OPTIONS"]).flush_all()
```javascript
- cd /etc/sasl2/
- rm memcached.conf
- rm memcached-zulip-password
```

### Error - 3
- Supervisor - Can't start supervisorctl as root or user
- `nano etc/superisord/superisord.conf`
```javascript
[unix_http_server]
file=/tmp/supervisor.sock   ; (the path to the socket file)
chmod=0700                ; socket file mode (default 0700)
username=root              ; (default is no username (open server))
```
