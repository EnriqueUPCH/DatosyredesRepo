![logo-upch](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/a91ea453-8e7c-4567-a300-1492f2435a93)

# Actividad 6: Crear una red con un switch y un router- Modo Físico

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/8c51ab93-38b3-4f6f-aad7-90a580c1a90c)

## Tabla de asignación de direcciones:

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/64e37506-37b4-4b72-8898-29f95deb709f)

## Parte 1: Configuración de la topología de red

1.	Mueve los dispositivos al Rack y la Mesa según la topología proporcionada.
2.	Conecta los dispositivos según la tabla de asignación de direcciones.
3.	Enciende todos los dispositivos.

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/bd4931d1-55e1-4415-9d3f-92fdfdb90a98)
![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/f2cc4fe8-af45-4a3a-842a-25175c6499e8)

## Parte 2: Configuración y verificación de la conectividad

Configuración de las PCs:

1.	Configura las direcciones IP en PC-A y PC-B.

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/e5305ae5-053c-4dc4-a5e5-d17a0b706b06)
![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/19d7f7d0-4db0-4da5-bc99-7efd86702ca3)

2. En una ventana con el símbolo del sistema en la PC-A, haga ping a la PC-B.

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/66544b34-f41a-4fb0-a06e-54471c2db971)

### ¿Por qué los pings no fueron correctos?
Los pings no fueron correctos porque las configuraciones necesarias en los switches y routers para establecer la conexión aún no se han completado.

### Configuración del router:
Configura las contraseñas y nombres de dispositivos.
Activa las interfaces.
Habilita el enrutamiento IPv6.
Configura el reloj.
Prueba la conectividad entre PC-A y PC-B.

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/145bb236-6c44-4278-a758-a8bf3c1ab265)
![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/bffcd705-2a1d-40ec-9b11-b14b7c64e8ce)

### Configuración del switch:
Configura el nombre de dispositivo.
Configura la interfaz VLAN y la puerta de enlace predeterminada.
Prueba la conectividad entre PC-A y PC-B desde el switch.

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/0bcc35cd-239a-4f85-ba66-7fe9611ed00f)

### ¿Qué código se utiliza en la tabla de enrutamiento para indicar una red conectada directamente?
El código utilizado es "C".
### ¿Cuántas entradas de ruta están codificadas con un código C en la tabla de enrutamiento?
La cantidad de entradas de ruta con código C es 2.
### ¿Qué tipos de interfaces están asociadas a las rutas con código C?
Las interfaces asociadas a las rutas con código C son las interfaces     g0/0/0 y g0/0/1    .
### ¿Cuál es el estado operativo de la interfaz G0/0/1? 
El estado operativo puede ser "up" (activo) o "down" (inactivo), dependiendo de si la interfaz está funcionando correctamente o no
### ¿Cuál es la dirección de control de acceso a los medios (MAC) de la interfaz G0/0/1? 
0060.4731.8102
### ¿Cómo se muestra la dirección de Internet en este comando?
Se muestra en la dirección IP y la máscara de subred en formato CIDR.

## Parte 3: Mostrar información del dispositivo

Muestra la tabla de enrutamiento en el router.
Muestra información de la interfaz en el router.
Muestra una lista de resumen de las interfaces en el router y el switch


![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/6bb67e55-c2f5-441e-ac6e-a7beb6fb1999)
![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/0471b35a-091e-467c-a94e-dfe631fcdb7c)

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/b59d7d98-f292-4190-8c87-8a1834cab005)


1.	Si la interfaz G0/0/1 se mostrará administratively down, ¿qué comando de configuración de interfaz usaría para activar la interfaz? 

El comando de configuración de interfaz que se usaría para activarla sería: no shutdown

2.	¿Qué ocurriría si hubiera configurado incorrectamente la interfaz G0/0/1 en el router con una dirección IP 192.168.1.2? 

Probablemente ocurriría una falta de conectividad en la red. Esto se debe a que la dirección IP configurada no coincide con la red a la que pertenece el router o puede estar duplicada con otra dirección IP dentro de la misma red.




