# Usando dispositivos y redes ajenos

No es fácil estar protegido en Internet usando nuestros propios dispositivos en redes de confianza.
Pero es más complicado cuando usamos dispositivos o redes que no controlamos.

Este documento explica factores a tener en cuenta en estas situaciones.

Hay varios conceptos en este documento que se introducen en una sección y se utilizan de nuevo en secciones siguientes.
Es recomendable leer todo el documento y no saltar directamente a la sección que nos interesa.

## Usando redes no controladas

En general, los sistemas operativos modernos de ordenadores, móviles y demás, están preparados para funcionar en redes no controladas.

Pero lo primero que debemos preguntarnos es, ¿realmente necesitamos usar una red ajena?

Si estamos en un espacio público con nuestro móvil y portátil, una red inalámbrica pública puede funcionar mejor que nuestra conexión de datos móviles (aunque no siempre).
Pero en general, usar nuestra conexión de datos móvil desde nuestro propio móvil o vinculando nuestro portátil o tablet al móvil suele ser suficiente.
Por tanto, en general la opción más segura es no conectarnos a redes en las que no confiemos a no ser que sea absolutamente necesario.

En otras circunstancias, si decidimos conectarnos a una red que no sea de confianza, deberemos considerar los siguientes factores.

El primero, es que aunque los sistemas operativos modernos están preparados para funcionar en redes no controladas, no se puede asegurar nunca que sean completamente seguros.
Todo sistema operativo puede ser susceptible a tener vulnerabilidades que pueden ser atacadas por agentes maliciosos que tengan acceso a la red en la que estamos conectados.
Este tipo de vulnerabilidades son poco comunes, muy especialmente en sistemas operativos actualizados.
En teoría, sólo los agentes maliciosos de gran envergadura tienen acceso a vulnerabilidades que afecten a sistemas operativos actualizados.

Así que en general, desde el punto de vista de la seguridad de nuestro sistema operativo, existen riesgos pero a no ser que haya agentes maliciosos especialmente interesados en nosotros, es razonable aceptar estos riesgos.

### Redes abiertas

La mayoría de redes inalámbricas hoy en día están cifradas.
Los sistemas operativos suelen diferenciar claramente las redes cifradas con un candado y anotar claramente las redes no cifradas.

En una red no cifrada, todos el tráfico que circule por la red es susceptible de ser interceptado fácilmente por cualquiera que pueda conectarse a la red.
Es decir, en una cafetería con una red sin cifrar, cualquier otro cliente puede observar todo el tráfico del resto de clientes conectados a la misma red.

Hoy en día, la inmensa mayoría de aplicaciones que se comunican por Internet, incluidos los navegadores y las páginas web a las que se conectan, usan su propio cifrado.
Esto quiere decir que aunque la red no esté cifrada, gran parte de los datos que se transmiten tienen su propio cifrado que no se puede descifrar fácilmente.

Fuera de esto quedan algunos datos interesante, como por ejemplo las direcciones IP entre las que se establecen las comunicaciones y los identificadores que tienen todos los dispositivos de red.

Las direcciones IP pueden dar algo de información sobre los sistemas a los que nos conectamos.
Por ejemplo, en muchos casos podemos saber a qué servicio o empresa se está conectando una conexión que observamos en una red sin cifrar.
(En muchos casos, una IP puede estar asociada a ciertos proveedores de servicios en Internet que usan muchas páginas web distintas, con lo que esta identificación no es posible.)

Así mismo, todos los dispositivos de red tienen un identificador único.
En general, esto se puede usar para identificar un dispositivo si le hemos visto conectarse en dos redes distintas, aunque no es algo tan útil.
Además, muchos sistemas operativos utilizan identificadores aleatorios en cada red que se conectan, dificultando este tipo de seguimiento.

Finalmente, en el uso de Internet en general siempre usamos el sistema DNS para poder introducir direcciones con texto (`example.com`) en vez de usar direcciones IP numéricas (192.168.10.33).
Tradicionalmente, el sistema DNS no estaba cifrado, con lo que además de saber a qué dirección IP nos estamos conectando, en muchos casos también se puede averiguar el dominio al que nos conectamos.
Sin embargo, muchos sistemas operativos configuran por defecto servidores DNS cifrados que impiden esto.

Por supuesto, cualquier comunicación no cifrada puede ser interceptada y manipulada en una red no cifrada.
Los navegadores modernos frecuentemente hacen muy evidente que estamos usando comunicaciones no cifradas.

En definitiva, una red abierta en general no constituye un riesgo elevado para nuestra seguridad, pero incrementan un poco los riesgos.

(Las conexiones a red por cable son poco comunes hoy en día, pero aunque existen redes cableadas cifradas, son poco comunes.
Por tanto, si nos conectamos por cable a una red, salvo que tengamos indicación de lo contrario, debe considerarse una red abierta sin cifrado.)

### Portales cautivos

Los portales cautivos son una funcionalidad de seguridad que podemos encontrar en redes abiertas.

De cara a poder identificar a personas que hagan uso malicioso de una red (tanto abierta como cifrada), muchos operadores de redes utilizan un portal cautivo.
En un portal cautivo, antes de poder acceder a cualquier cosa fuera de la red, se nos redirige al portal, donde típicamente debemos identificarnos de alguna manera.

En estas situaciones, debemos tener en cuenta que el operador de red puede asociar cualquier tráfico en la red a los datos identificativos que hayamos introducido.

(En una red sin portal cautivo, es bastante más complejo asociar una comunicación específica con una persona específica.)

### Redes cifradas

Las redes cifradas reducen, pero no eliminan, los riesgos de las redes abiertas.

Lo primero que debemos considerar también es si la red usa un portal cautivo o la manera en la que accedemos a la red.

Si hay un portal cautivo, o las credenciales de acceso a la red nos identifican, volver a estar en la situación en el que el operador de la red puede asociar nuestra actividad a nuestra persona.

Una vez conectados, a diferencia de las redes abiertas donde cada persona que tiene acceso a la red puede acceder al tráfico que circula por ella, sólo el operador de la red puede ver todo el tráfico.
De esta manera, los riesgos por agentes maliciosos se reducen bastante en la mayoría de situaciones.
Pero el operador de red sigue teniendo casi todas las posibilidades de ataque que se dan en las redes abiertas.

## Usando dispositivos no controlados

Aunque las redes no controladas suponen un riesgo, el riesgo de usar dispositivos que no controlamos es mucho mayor.

Salvo muy contadas excepciones y pequeños resquicios, alguien que controla el dispositivo que usamos, controla absolutamente todo lo que sucede en ese dispositivo.

El caso más extremo, pero que no es complicado de hacer, es que el dispositivo retransmita todo lo que aparece en pantalla, toda pulsación de teclado, y todo fichero del dispositivo.
Sin tener que manipular redes, mediante la instalación de programas de control remoto, el propietario del dispositivo tiene acceso total.

Curiosamente, es posible que aunque esta técnica en teoría ofrece el mayor grado de control, también puede requerir más esfuerzo.
Examinar todo lo que aparece en pantalla y todas las pulsaciones de teclado puede requerir bastante esfuerzo.
Por tanto, es posible que la mayoría de mecanismos de control que se utilicen sean menos intrusivos (pero igualmente muy efectivos).

Lo que es más común es instalar un software que intercepta el tráfico de red del dispositivo.
Con acceso administrativo al dispositivo, se pueden desconectar la mayoría de medidas de seguridad que supone el cifrado de datos en Internet.

En general, cuando establecemos una conexión cifrada, el sistema de certificados de Internet requiere del uso de certificados.
Estos certificados vienen firmados por una entidad, y los sistemas operativos y navegadores tienen una lista limitada de los firmantes en los que confían.
En teoría, los firmantes aceptados por sistemas operativos y navegadores están sujetos a controles y regulaciones que hacen que sólo el propietario de un dominio pueda emitir un certificado que sirva para las comunicaciones con ese dominio.

Con esto, si usamos conexiones cifradas y la lista de firmantes admitidos no ha sido manipulada, las comunicaciones entre nosotros y un servicio en Internet son prácticamente indescifrables.

(Este sistema ha sido susceptible a muchas vulnerabilidades y problemas que han comprometido esta seguridad, pero son bastante infrecuentes.)

Sin embargo, el administrador de un dispositivo puede manipular la lista de firmantes aceptados, con lo que puede reemplazar los certificados verdaderos por los suyos e interceptar todo el tráfico.

(Existen protecciones frente a estos ataques, pero en general debemos asumir que se pueden desconectar.)

Por tanto, en general debemos asumir que en un dispositivo no controlado, el administrador del dispositivo puede recolectar absolutamente toda la información de qué servicios usamos y los datos que intercambiamos con ellos (incluidas contraseñas).
Adicionalmente, como en las redes abiertas y comunicaciones sin cifrar, este administrador puede *manipular* los datos, sustituyendo el contenido transferido por otro.

(Uno de los motivos por los que es recomendable cifrar todo el tŕafico es que sin este cifrado, los proveedores de Internet podrían poner anuncios en las páginas web que visitamos y lucrarse con ello.
Los autores de los navegadores y el software que usamos para conectarnos a otros servicios de Internet siguen teniendo esta posibilidad.)

## Recomendaciones

* Evitar el uso de redes no controladas, prefieriendo el uso de nuestras conexiones de datos móviles.
* Asumir que todo uso de un dispositivo que no controlamos puede ser examinado y manipulado por el administrador del dispositivo.
