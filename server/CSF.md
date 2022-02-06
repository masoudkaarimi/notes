# ConfigServer Security & Firewall (CSF)

ConfigServer Security & Firewall (CSF) is a Firewall software installed on your server to keep it secure. It provides an
advanced and easy-to-use web-based interface to manage firewall settings. You can also manage your firewall
settings/configuration via the Secure Shell.


## Useful CSF commands

| Command | Description  | Example               |
|---------|--------------|-----------------------|
| csf -e  | Enable CSF   | root@server[~]#csf -e |
| csf -x  | Disable CSF  | root@server[~]#csf -x |
| csf -s  | Start the firewall rules | root@server[~]#csf -s |
| csf -f  | Flush/Stop firewall rules (note: lfd may restart csf) | root@server[~]#csf -f |
| csf -r  | Restart the firewall rules | root@server[~]#csf -r |
| csf -a [IP] [Optional comment] | Allow an IP and add to /etc/csf/csf.allow | root@server[~]#csf -a 187.33.3.3 Home IP Address |
| csf -td [IP] [Optional comment] | Place an IP on the temporary deny list in /var/lib/csf/csf.tempban | root@server[~]#csf -td 55.55.55.55 Odd traffic patterns |
| csf -tr [IP] | Remove an IP from the temporary IP ban or allow list. | root@server[~]#csf -tr 66.192.23.1 |
| csf -tf | Flush all IPs from the temporary IP entries | root@server[~]#csf -tf |
| csf -d [IP] [Optional comment] | Deny an IP and add to /etc/csf/csf.deny | root@server[~]#csf -d 66.192.23.1 Blocked This Guy |
| csf -dr [IP] | Unblock an IP and remove from /etc/csf/csf.deny | root@server[~]#csf -dr 66.192.23.1 |
| csf -df | Remove and unblock all entries in /etc/csf/csf.deny | root@server[~]#csf -df |
| csf -g [IP] | Search the iptables and ip6tables rules for a match (e.g. IP, CIDR, Port Number) | root@server[~]#csf -g 66.192.23.1 |
| csf -t  | Displays the current list of temporary allow and deny IP entries with their TTL and comments | root@server[~]#csf -t |


## Other Command and Options:

You can view all the CSF command line options by using either:

```shell
man csf

# or

csf -h
```