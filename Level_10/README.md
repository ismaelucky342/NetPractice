# Nivel 10 - NetPractice

En este nivel, existen 4 redes diferentes:

- **Router R1 a Switch S1**
- **Router R1 a Router R2**
- **Router R2 a Cliente H4**
- **Router R2 a Cliente H3**

## 1. Cobertura de la red por Internet

Internet debe poder enviar paquetes a todos los hosts, por lo que su destino debe cubrir el rango de todas las redes de los hosts.

Las interfaces R11 y R13 ya tienen una dirección IP asignada, que solo difiere en el último byte:  
- **R11:** último byte 1  
- **R13:** último byte 254  

Para cubrir este rango amplio de direcciones IP, se utiliza una máscara **/24** para el destino de Internet, cubriendo el rango **70.101.30.0 - 70.101.30.255**.

## 2. Elección de direcciones IP

Al elegir las direcciones IP, se deben cumplir dos condiciones:

1. La dirección IP debe estar cubierta por el destino de Internet.
2. Los rangos de direcciones IP de las distintas redes no deben solaparse.

Con las direcciones IP ya asignadas (en gris), los rangos cubiertos por las redes son:

- **Router R1 a Switch S1:** 70.101.30.0 - 70.101.30.127 (máscara /25)
- **Router R2 a Cliente H4:** 70.101.30.128 - 70.101.30.191 (máscara /26)
- **Router R1 a Router R2:** 70.101.30.252 - 70.101.30.255 (máscara /30)
- **Router R2 a Cliente H3:** ??? (máscara ???)

Las únicas direcciones IP restantes para la red "Router R2 a Cliente H3" son **70.101.30.192 - 70.101.30.251**. Se puede elegir cualquier máscara que permita tomar 2 direcciones IP de ese rango para asignarlas a la **Interfaz R22** y **Interfaz R31**.
