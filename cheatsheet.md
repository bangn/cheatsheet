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
