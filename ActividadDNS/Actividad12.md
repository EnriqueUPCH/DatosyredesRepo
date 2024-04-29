#  Estrategias de mitigación para interferencia en redes Ad Hoc Inalámbricas

## Contexto: 

### En un entorno de red ad hoc inalámbrico, los dispositivos sufren de interferencia co-canal y de problemas de acceso al medio debido a la naturaleza descentralizada de la red.

## Que es una rewd AD HOC

![Cómo-Funciona-una-red-ad-hoc](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/b592e266-ee27-423d-a877-a709a739f4aa)

Es un tipo de red de comunicación inalámbrica en la que los dispositivos se comunican directamente entre sí 
sin la necesidad de un punto de acceso centralizado, como un enrutador.
En una red ad hoc, cada dispositivo puede actuar como un nodo y puede enviar, recibir y retransmitir datos para 
facilitar la comunicación entre los dispositivos en la red. Este tipo de red es útil en situaciones donde no hay
una infraestructura de red establecida o donde es necesario establecer rápidamente una conexión entre dispositivos móviles o en movimiento,
como en entornos militares, de emergencia o en redes de sensores inalámbricos.

## Existen los protocolos CSMA/CA y CSMA/CD, en que difieren y cual es mas adecuado para una red Ad Hoc

  ![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/87c1f5d0-e2a5-4a93-9a31-7dea8111d9df)

Ambos protocolos, CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance) y CSMA/CD (Carrier Sense Multiple Access with Collision Detection), son utilizados en redes de área local (LAN) para regular el acceso al medio de transmisión compartido, como en Ethernet. Sin embargo, difieren en cómo manejan las colisiones y son más apropiados para diferentes tipos de redes.

### CSMA/CD (Carrier Sense Multiple Access with Collision Detection):

1. En este protocolo, los dispositivos comprueban el medio antes de transmitir para detectar si está ocupado. Si el medio está ocupado, esperan un tiempo aleatorio antes de volver a intentar transmitir.
2. Si dos dispositivos intentan transmitir simultáneamente y detectan una colisión, ambos dispositivos detienen la transmisión, esperan un período de tiempo aleatorio y luego vuelven a intentar la transmisión.
3. CSMA/CD es más adecuado para redes cableadas donde es posible detectar colisiones de forma confiable.

   ![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/18aa92c6-2eb9-45a4-9f4e-d52185f43444)


### CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance):
1. En CSMA/CA, en lugar de detectar colisiones después de que hayan ocurrido, se intenta evitarlas por completo.
2. Antes de transmitir, un dispositivo envía un pequeño paquete de solicitud RTS (Request to Send) al destino. Si el destino está libre para recibir, responde con un paquete CTS (Clear to Send), y luego se realiza la transmisión. Si el destino no responde, se interpreta como que está ocupado y se espera un período aleatorio antes de intentar nuevamente.
3. CSMA/CA es más adecuado para redes inalámbricas donde las colisiones son más difíciles de detectar y pueden ser más costosas en términos de energía y ancho de banda.

   ![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/929a6696-ca7f-4018-93dc-ee1458ea4f3e)


En conclusión, para una red Ad Hoc donde los dispositivos no están conectados a una infraestructura central, el poder detectar las colisiones se dificulta, haciendo que el protocolo CSMA/CA sea el más adecuado ya que ayuda a evitar colisiones en vez de detectarlas y haciendo más óptimo el rendimiento en redes Ad Hoc.

## El impacto de la interferencia co-canal 

El impacto en una red inalámbrica puede ser significativo y puede afectar negativamente su rendimiento. La interferencia co-canal ocurre cuando dos o más dispositivos transmiten en el mismo canal de frecuencia dentro del rango de alcance de un receptor, lo que puede causar interferencia y degradar la calidad de la señal
  ![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/67bf9096-b794-4866-8dd5-832063029ed0)

