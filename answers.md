## Tarea 1

Comando:
```bash
grep -Evc '^#' firewall.log
Resultado:1000
## Tarea 2

Comando:
```bash
grep -Ec '^[^ ]+ [^ ]+ (DROP|REJECT) ' firewall.log
Resultado: 60156d