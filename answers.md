## Tarea 1

Comando:
```bash
grep -Evc '^#' firewall.log
Resultado:1000
## Tarea 2

Comando:
```bash
grep -Ec '^[^ ]+ [^ ]+ (DROP|REJECT) ' firewall.log
Resultado: 60156
## Tarea 3

Comando:
```bash
grep -Ec '^[^ ]+ [^ ]+ [^ ]+ [^ ]+ 11\.' firewall.log
resultado:33217

## Tarea 4

Comando:
```bash
grep -Ec ' [0-9]{7}$' firewall.log

resultado:2343
## Tarea 5

Comando:
```bash
grep -Ev '^#' firewall.log | sed -E 's/^([^ ]+) [^ ]+ ([^ ]+) ([^ ]+) .*/\1 \2 \3/' | head -5
resultado:
2018-05-25 FORWARD TCP
2018-02-22 FORWARD UDP
2018-03-20 REJECT UDP
2018-11-08 REJECT TCP
2018-07-24 REJECT TCP

## Tarea 6

Comando:
```bash
grep -Ec '^[^ ]+ [^ ]+ ACCEPT TCP [^ ]+ [^ ]+ [0-9]+ 80 [0-9]+$' firewall.log
resultado:
wall.log
93
## Tarea 7

Comando:
```bash
grep -Ec '^[0-9]{4}-[0-9]{2}-[0-9]{2} 0[0-2]:[0-9]{2}:[0-9]{2} ' firewall.log
resultado:
wall.log
13138