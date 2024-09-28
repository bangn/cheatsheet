# Cheatsheet collection

## Fix Pihole readonly error

```bash
sudo pihole -r
```

If it does not work try

```bash
sudo usrmod +G pihole:www-data
sudo pihole -r
```

## Run ansible with specific tag

```sh
ansible-playbook --ask-become-pass -i inventories/localhost playbook.yml --tag packages
```

## Troubleshoot exim4

### Test if mail setting is correct

```sh
echo "hello" | mail -s "Test" thebangnguyen@gmail.com
```

### Tail exim4 log

```sh
sudo tail -f /var/log/exim4/mainlog
```

### Change client password

```sh
sudo vi /etc/exim4/passwd.client
```

and update the password to the google's one

### Restart exim4

```sh
sudo service exim4 restart
```

### Remove message from queue

```sh
exim -bp | awk '/^ *[0-9]+[mhd]/{print "exim -Mrm " $3}' | bash
```
