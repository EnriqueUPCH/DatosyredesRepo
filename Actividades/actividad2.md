![logo-upch](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/31865330-15f7-4eff-9875-e93f67331fa1)

# Actividad 2: Implementación de conectividad básica

## Tabla de asignación de direcciones:
![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/9f8bd200-3a5d-438a-8aa7-8f30266cd9d5)
## Parte 1: Configuración básica en S1 y S2

Configura las contraseñas de la consola y del modo EXEC privilegiado.

Contraseña de la consola: password checha.

Contraseña del modo EXEC privilegiado: enable secret jeka

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/502e396d-f8a3-42ce-b3eb-c4692c762a71)

## Configura un aviso de MOTD.
Utiliza el comando: banner motd **Acceso autorizado únicamente. Los infractores se procesarán en la medida en que lo permita la ley.**

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/7278263c-39fa-4fc7-bebd-b5eb47c28d40)
### Repita los pasos para configurar el S2.

## Parte 2: Configuración de las PC
Configura PC1 y PC2 con direcciones IP.

Utiliza la dirección IP y máscara de subred proporcionadas en la tabla de asignación de direcciones.

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/85efcc72-062c-4026-9d45-b1cac4dc2f96)

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/5d6435d3-e3e3-4433-94f8-fe0851ba1f7c)

## Parte 3: Configuración de la interfaz de administración de switches

**Configuración del S1 y S2 con direcciones IP**

Configura el S1 y el S2 con direcciones IP en la VLAN 1.

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/557a6dcf-af31-44b9-9117-dbafd95416f5)

Verificación de la conectividad de la red

Verifica la configuración de direcciones IP en el S1 y el S2.

Utiliza el comando: **show ip interface brief** o **show running-config.**

![image](https://github.com/EnriqueUPCH/DatosyredesRepo/assets/117322038/2e60cdf0-a1ef-46f7-bc8a-27e429acf64d)

Verifica la conectividad de la red utilizando el comando ping desde PC1 y PC2 hacia S1 y S2.

Si los pings tienen éxito, la configuración es correcta. Si no, revisa la configuración para detectar errores.

