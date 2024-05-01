# Diseño de un sistema de entrega y recuperación de correo electrónico

Contexto: Una empresa necesita diseñar un sistema de correo electrónico robusto que utilice SMTP, IMAP, y SSL/TLS para la entrega y recuperación segura de correo electrónico.

## Que es SMPT, IMAP Y SSL/TLS?

SMTP, IMAP y SSL/TLS son protocolos de Internet que trabajan juntos para permitir el envío,
recepción y seguridad de los correos electrónicos. SMTP se encarga del envío, IMAP de la recepción y gestión,
y SSL/TLS de la seguridad de la comunicación.

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/01f85864-eeed-4bab-b5d7-694c0c3a3721)

## Descripción de la Integración SMTP, IMAP, y SSL/TLS

El sistema de correo electrónico se basa en tres componentes principales:
●Servidor SMTP (Simple Mail Transfer Protocol): 
Se utiliza para enviar correos electrónicos. Generalmente opera en el puerto 587 para SMTP con TLS/SSL.
●Servidor IMAP (Internet Message Access Protocol):
Permite la recuperación de correos electrónicos. Opera en el puerto 993 para conexiones seguras con SSL/TLS.
●SSL/TLS (Secure Sockets Layer/Transport Layer Security): 
Asegura que las conexiones entre clientes y servidores estén cifradas y autenticadas con certificados X.509

##  Gestión de los certificados X.509 y la importancia de estos para SSL/TLS

Los certificados X.509 son una parte esencial de la infraestructura de seguridad en Internet.
Son parecidos a un pasaporte digital ya que nos otorgan una identificación para ingresar a sitios web o servidores.

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/77b81397-b5d0-4932-8d38-2d4c5bf11b45)

Los certificados X.509 son esenciales para la seguridad en línea y su gestión es la correcta para poder mantener la integridad de los datos que son enviados a través de SSL/TLS.

### Manejo de Direcciones IP Dinámicas y Estáticas en la Red
En redes modernas, las direcciones IP pueden ser dinámicas o estáticas,
y el sistema de correo electrónico debe manejar ambas de manera efectiva. Aquí se explica cómo se gestionan estas direcciones,
considerando DHCP y NAT:

1.Direcciones IP Dinámicas con DHCP:

●El servidor DHCP gestiona un rango de direcciones IP y asigna una dirección a cada dispositivo cuando se conecta.

●Para servidores SMTP e IMAP, es mejor usar direcciones IP estáticas para evitar problemas de conectividad cuando las direcciones cambian.

2.Direcciones IP Estáticas:

●Se asignan manualmente y no cambian con el tiempo, proporcionando estabilidad para servidores críticos.

●Es preferible configurar direcciones IP estáticas para servidores SMTP e IMAP, asegurando que estén siempre accesibles para clientes.

3.Uso de NAT en la Red:

●Si se usa NAT, debes configurar el reenvío de puertos para que el tráfico SMTP e IMAP llegue a los servidores correctos dentro de la red privada.

●Asegúrate de que las reglas de reenvío de puertos sean seguras para evitar problemas de seguridad.

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/adb168cc-65ee-4e88-847f-f1fc0b017029)
![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/ffc2a485-0af3-4808-8799-6617b80f2b27)



