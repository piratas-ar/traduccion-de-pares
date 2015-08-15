Una prueba de concepto para corrección / traducción de pares.

Se le pasa un texto plano y una lista de participantes.
`traduccion-de-pares` divide el texto en párrafos y le envía uno a cada
par participante.

# Uso

```bash
DRYRUN=true ./traduccion-de-pares instrucciones.txt pares.txt articulo.txt coordinacion@depares.net
```

Donde `instrucciones.txt` es un archivo txt con la invitacion a
participar.  `pares.txt` una lista de direcciones de correo, una por
línea.  `articulo.txt` el articulo a corregir.  al final va la dirección
donde se esperan las respuestas.

Las `instrucciones.txt` pueden tener las siguientes variables:

* `{{titulo}}` el título del artículo, si lo ponemos en la primera línea
  de `texto.txt`
* `{{parrafos_faltantes}}` los párrafos que faltan corregir
* `{{parrafos_q}}` cantidad de párrafos
* `{{posicion}}` número de párrafo

# Requisitos

* `sendmail` funcionando
* `coreutils` vienen en cualquier gnu/linux a menos que use busybox


# Archivos

El programa crea un archivo por cada parrafo, que se puede abrir luego
para aplicar las correcciones.  El archivo terminado en `_cola.txt`
contiene la lista de parrafos enviados, fecha y participante, además del
estado.

El estado puede ser enviado (estado inicial) o corregido.  Los párrafos
corregidos se usan para control y cuenta de los párrafos faltantes.


# TODO

* Reciclar párrafos cuando no fueron respondidos.

* Enviar de a dos párrafos cuando se trata de una corrección de traducción
