# Dynamic DNS for Directadmin
Want to attach your home server to a subdomain but don't know how?
Use this either of these scripts with a cronjob to dynamically update your DNS records!

Create a file in `/opt/dyndns/credentials.json` or in the current directory.

```
{
	"username": "myusername",
	"password": "mypassword",
	"hostname": "webXXXX.zxcs.nl",
	"domain": "mydomain.com",
	"port": "2222",
	"subdomains": [
        {
            "subdomain": "mysubdomain",
            "action": "edit" // or add or delete
        }
    ]
}
```
If you have 2FA enabled, create a login key with only access to `CMD_API_DNS_CONTROL`.
Make sure to create a strong password.

## Running it
To try it out, try `python3 dyndns.py`. You might need to run `pip install requests`.

Then to have it update on a regular schedule, add a cron job for it!
See [crontab(5)](https://man.archlinux.org/man/crontab.5.en) for instructions and examples.
