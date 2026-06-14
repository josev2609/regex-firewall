## Tarea 1

Comando:
grep -Evc '^#' firewall.log

Resultado:
1000

Explicación:
Este comando cuenta las líneas del archivo firewall.log que no empiezan con #. La expresión ^# identifica las líneas de encabezado, -v las excluye y -c cuenta las líneas restantes, que corresponden a los eventos del firewall.

---

## Tarea 2

Comando:
grep -Ec '^[^ ]+ [^ ]+ (DROP|REJECT) ' firewall.log

Resultado:
60156

Explicación:
Este comando cuenta los eventos cuya acción es DROP o REJECT. La expresión regular salta los campos de fecha y hora, y luego busca que el tercer campo sea exactamente DROP o REJECT usando alternancia con (DROP|REJECT).

---

## Tarea 3

Comando:
grep -Ec '^[^ ]+ [^ ]+ [^ ]+ [^ ]+ 11\.' firewall.log

Resultado:
33217

Explicación:
Este comando cuenta los eventos cuya IP de origen empieza con 11. La expresión regular salta los primeros cuatro campos: fecha, hora, acción y protocolo. Luego busca 11\. en el campo de IP de origen, usando \. para indicar que el punto debe tomarse literalmente.

---

## Tarea 4

Comando:
grep -Ec ' [0-9]{7}$' firewall.log

Resultado:
2343

Explicación:
Este comando cuenta los eventos cuyo campo final size tiene exactamente 7 dígitos. La expresión [0-9]{7} busca siete números consecutivos y el símbolo $ asegura que esos siete dígitos estén al final de la línea.

---

## Tarea 5

Comando:
grep -Ev '^#' firewall.log | sed -E 's/^([^ ]+) [^ ]+ ([^ ]+) ([^ ]+) .*/\1 \2 \3/' | head -5

Resultado:
2018-05-25 FORWARD TCP
2018-02-22 FORWARD UDP
2018-03-20 REJECT UDP
2018-11-08 REJECT TCP
2018-07-24 REJECT TCP

Explicación:
Este comando primero elimina las líneas de encabezado que empiezan con #. Luego sed -E usa grupos de captura para tomar la fecha, la acción y el protocolo, reconstruyendo la salida con \1 \2 \3. Finalmente, head -5 muestra solo las primeras cinco líneas.

---

## Tarea 6

Comando:
grep -Ec '^[^ ]+ [^ ]+ ACCEPT TCP [^ ]+ [^ ]+ [0-9]+ 80 [0-9]+$' firewall.log

Resultado:
93

Explicación:
Este comando cuenta los eventos donde la acción es ACCEPT, el protocolo es TCP y el puerto de destino es 80. La expresión regular salta los campos de IP origen, IP destino y puerto origen, luego verifica que el penúltimo campo sea 80 y que el último campo sea el tamaño del paquete.

---

## Tarea 7

Comando:
grep -Ec '^[0-9]{4}-[0-9]{2}-[0-9]{2} 0[0-2]:[0-9]{2}:[0-9]{2} ' firewall.log

Resultado:
13138

Explicación:
Este comando cuenta los eventos ocurridos entre 00:00:00 y 02:59:59. La expresión regular valida primero la fecha con formato AAAA-MM-DD, luego busca una hora que empiece con 0[0-2], lo que permite únicamente las horas 00, 01 y 02.