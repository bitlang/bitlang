# Bit language (Bitlang)
The Bit language is a shell-like scripting, programming, and configuration language for humans.

See some Bit code for yourself:
```bit
#!/usr/bin/bitlang

print "Hello world!"
```
See some Bit configuration for yourself:
```bit
port 9000
ip 0.0.0.0
root /var/www/html/
```
(which can be serialized to / is equivalent to:)
```json
{
    "port": 9000,
    "ip": "0.0.0.0",
    "root": "/var/www/html"
}
```
```yaml
port: 9000
ip: 0.0.0.0
root: /var/www/html
```