# NetPractice Nivel 8

## Descripción

Los clientes **Cliente C** y **Cliente D** enviarán paquetes a Internet, y luego Internet responderá enviando los paquetes de regreso al remitente inicial. Para enviar estos paquetes, Internet utiliza el destino **49.175.13.0/26** para dirigir los paquetes a las redes dentro del rango **49.175.13.0 - 49.175.13.63**.

Todas las redes receptoras deben estar dentro de este rango, sin superponerse entre sí.

---

## División de Redes

En las interfaces **R23** y **R22** se utiliza la máscara **255.255.255.240** (o **/28**), para dividir convenientemente el rango **/26** de la dirección de destino en **4 rangos separados**. Esta separación es necesaria ya que existen las siguientes **3 redes** que no deben solaparse:

- Router R1 a Router R2
- Router R2 a Cliente C
- Router R2 a Cliente D

Cada una de estas redes puede recibir uno de los siguientes rangos de IP con máscara **/28**:

- 49.175.13.0 - 49.175.13.15
- 49.175.13.16 - 49.175.13.31
- 49.175.13.32 - 49.175.13.47
- 49.175.13.48 - 49.175.13.63

> **Nota:** La dirección de red (primera) y la dirección de broadcast (última) deben excluirse de cada rango.

---

## Configuración de Rutas

El destino y el siguiente salto para Internet ya están configurados. Solo es necesario ingresar el siguiente salto para el **Router R2**, que corresponde a la IP en la **Interfaz R21**.
