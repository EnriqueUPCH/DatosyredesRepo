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

## Métodos de modulación para mitigar interferencia co-canal

### FHSS (Frequency Hopping Spread Spectrum):

 Este método cambia la frecuencia de
transmisión según un patrón predefinido. Al saltar entre diferentes frecuencias, se reduce la
interferencia y es más difícil para un atacante interceptar las transmisiones.

### DSSS (Direct Sequence Spread Spectrum): 

 Este método esparce la señal sobre un
amplio rango de frecuencias usando códigos únicos para cada transmisión. Esto hace que
la interferencia y el ruido sean menos impactantes.

## Explicación del algoritmo
### Retroceso Exponencial: 
Si el canal está ocupado, el algoritmo espera un tiempo creciente
basado en un factor exponencial. Esto reduce la probabilidad de colisiones.
### Vector de Inicialización (IV): 
Se usa para asegurar la transmisión. Es un valor aleatorio que
se combina con la transmisión para agregar seguridad.
Confirmación de Recepción (ACK): Después de transmitir, el dispositivo espera una
confirmación del destinatario. Si no recibe confirmación, el proceso se reinicia con un tiempo
de espera mayor.
### Límite de Intentos: 
Si se excede el número máximo de intentos, el algoritmo devuelve un
mensaje de error indicando que la transmisión no fue exitosa.
Esta estructura permite mejorar el período libre de contención en redes ad hoc inalámbricas,
utilizando retroceso exponencial y mecanismos de confirmación para minimizar colisiones.
La adición de vectores de inicialización aumenta la seguridad de las transmisiones en redes
ad hoc.

Parte 1
import random
import time
class Channel:
def __init__(self):
self.is_occupied = False
self.last_transmitter = None
def is_busy(self):
# Simula si el canal está ocupado
return random.choice([True, False])
def occupy(self, node_id):
self.is_occupied = True
self.last_transmitter = node_id
def release(self):
self.is_occupied = False
def transmit(self, node_id):
if not self.is_busy():
self.occupy(node_id)
print(f"Node {node_id}: Transmitiendo datos")
time.sleep(1) # Simula el tiempo de transmisión
print(f"Node {node_id}: Transmisión completada")
self.release()
else:
print(f"Node {node_id}: Canal ocupado, intentando nuevamente")
class Node:
def __init__(self, node_id):
self.node_id = node_id
def transmit(self, channel, attempt_limit=5):
attempt = 0
while attempt < attempt_limit:
if channel.is_busy():
backoff_time = self.exponential_backoff(attempt)
print(f"Node {self.node_id}: Aplicando backoff por {backoff_time} segundos")
time.sleep(backoff_time)
attempt += 1
else:
channel.transmit(self.node_id)
break
def exponential_backoff(self, attempt):
return random.uniform(0, 2**attempt) # Backoff exponencial
# Simulación de múltiples nodos compitiendo por el canal
channel = Channel()
nodes = [Node(1), Node(2), Node(3)]
# Cada nodo intenta transmitir datos
for node in nodes:
node.transmit(channel)
Parte 2
# Codificación DSSS
def dsss_encode(data, chip_code):
encoded = []
for bit in data:
# Si el bit es 1, el chip_code se mantiene; si es 0, se invierte
encoded_bit = [chip * int(bit) for chip in chip_code]
encoded.extend(encoded_bit)
return encoded
# Decodificación DSSS
def dsss_decode(encoded_data, chip_code):
decoded = []
index = 0
while index < len(encoded_data):
# Extrae segmentos del tamaño del chip_code
segment = encoded_data[index:index + len(chip_code)]
# Suma los valores y determina el bit decodificado
decoded_bit = 1 if sum(segment) > 0 else 0
decoded.append(decoded_bit)
index += len(chip_code) # Avanza al siguiente segmento
return decoded
# Ejemplo de uso
data = "1010" # Datos originales
chip_code = [1, -1, 1, -1] # Código de dispersión
# Codificación
encoded_data = dsss_encode(data, chip_code)
print("Datos codificados:", encoded_data)
# Decodificación
decoded_data = dsss_decode(encoded_data, chip_code)
decoded_str = "".join(map(str, decoded_data))
print("Datos decodificados:", decoded_str)
Parte 3:
import random
# Función para ajustar el backoff según la tasa de éxito
def adjust_contention_window(success_rate):
if success_rate < 0.5:
return increase_backoff()
else:
return decrease_backoff()
# Aumenta el tiempo de backoff
def increase_backoff():
backoff_factor = random.randint(2, 4) # Incremento aleatorio para simular variabilidad
print("Incrementando el tiempo de backoff")
return backoff_factor
# Disminuye el tiempo de backoff
def decrease_backoff():
backoff_factor = random.randint(1, 2) # Decremento aleatorio para simular ajuste
print("Disminuyendo el tiempo de backoff")
return backoff_factor
# Función que ajusta la ventana de contención basándose en la tasa de éxito
def contention_window_adjustment():
success_rate = calculate_success_rate() # Simula la tasa de éxito
backoff_adjustment = adjust_contention_window(success_rate) # Ajusta el backoff
return backoff_adjustment
# Simula el cálculo de la tasa de éxito
def calculate_success_rate():
# Devuelve un valor aleatorio entre 0 y 1 para simular la tasa de éxito
return random.random()
# Ejemplo de uso para el ajuste dinámico
contention_window_adjustment()
Parte 4
import random
import time
# Clase para el canal compartido
class Channel:
def __init__(self):
self.is_occupied = False
self.last_transmitter = None
def is_busy(self):
# Simula si el canal está ocupado
return random.choice([True, False])
def occupy(self, node_id):
self.is_occupied = True
self.last_transmitter = node_id
def release(self):
self.is_occupied = False
# Clase para representar un nodo con CSMA/CA
class Node:
def __init__(self, node_id):
self.node_id = node_id
def transmit(self, channel, attempt_limit=5):
attempt = 0
while attempt < attempt_limit:
if channel.is_busy():
backoff_time = self.exponential_backoff(attempt)
print(f"Node {self.node_id}: Aplicando backoff por {backoff_time} segundos")
time.sleep(backoff_time)
attempt += 1
else:
channel.occupy(self.node_id)
print(f"Node {self.node_id}: Transmitiendo datos")
time.sleep(1) # Simula el tiempo de transmisión
print(f"Node {self.node_id}: Transmisión completada")
channel.release()
break
def exponential_backoff(self, attempt):
# Backoff exponencial
return random.uniform(0, 2**attempt)
# Codificación y decodificación DSSS
def dsss_encode(data, chip_code):
encoded = []
for bit in data:
encoded_bit = [chip * int(bit) for chip in chip_code]
encoded.extend(encoded_bit)
return encoded
def dsss_decode(encoded_data, chip_code):
decoded = []
index = 0
while index < len(encoded_data):
segment = encoded_data[index:index + len(chip_code)]
decoded_bit = 1 if sum(segment) > 0 else 0
decoded.append(decoded_bit)
index += len(chip_code)
return decoded
# Ajuste dinámico del período de contención
def adjust_contention_window(success_rate):
if success_rate < 0.5:
return increase_backoff()
else:
return decrease_backoff()
def increase_backoff():
print("Incrementando el tiempo de backoff")
return random.randint(2, 4)
def decrease_backoff():
print("Disminuyendo el tiempo de backoff")
return random.randint(1, 2)
def calculate_success_rate():
# Simula la tasa de éxito
return random.random()
# Ejemplo de uso
channel = Channel() # Creamos el canal compartido
nodes = [Node(1), Node(2), Node(3)] # Tres nodos en la simulación
# Codificamos datos utilizando DSSS
chip_code = [1, -1, 1, -1] # Código de dispersión
data = "1010"
encoded_data = dsss_encode(data, chip_code)
decoded_data = dsss_decode(encoded_data, chip_code)
print("Datos codificados:", encoded_data)
print("Datos decodificados:", "".join(map(str, decoded_data)))
# Simulamos transmisiones de nodos con ajuste de contención
for node in nodes:
success_rate = calculate_success_rate() # Simulamos una tasa de éxito aleatoria
adjust_contention_window(success_rate) # Ajustamos el backoff
node.transmit(channel) # El nodo intenta transmitir datos
