# DDNS-Updater-Bash-Script
This script updates IPv4 and/or IPv6 addresses in the DNS of your domain through the API URL of your DDNS provider.

# Supported DDNS Providers
- All-Inkl.com
- DuckDNS.org
- Dynu.com
- Google Domains (You need to add Google twice if you like to update IPv4 and IPv6 as Google does not offer a method to update both at the same time)
  

Execute this script every 5 minutes (custom cron */5 * * * *) through the user scripts Plugin. It opens the DDNS URL only if the IPv4 or IPv6 has changed. By default the IPv4 is obtained through a web service like icanhazip.com and the IPv6 through the servers ethernet interface.

Optionally you can obtain the IPv6 from a specific container:
```ipv6=$(docker inspect "Nginx-Proxy-Manager-Official" --format='{{range .NetworkSettings.Networks}}{{.GlobalIPv6Address}}{{end}}')```


If you want to delete all status files generated through this script, execute this:
```rm /tmp/*.ddns```
