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
