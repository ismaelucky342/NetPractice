# Nivel 5: Introducción a las Rutas

Este nivel introduce el concepto de **rutas**. Una ruta contiene dos campos principales:

1. **Destino:** Especifica a dónde se enviarán los paquetes salientes.
2. **Próximo salto:** Es la dirección IP de la siguiente interfaz (router o internet) a la que la máquina actual debe enviar sus paquetes.

## Destino

- El destino **default** es equivalente a `0.0.0.0/0`, lo que significa que los paquetes se enviarán indiscriminadamente a la primera dirección de red que encuentren.
- Por ejemplo, una dirección de destino `122.3.5.3/24` enviaría los paquetes a la red `122.3.5.0`.

## Próximo salto

El **próximo salto** es la dirección IP de la siguiente interfaz de router (o internet) a la que la interfaz de la máquina actual debe enviar sus paquetes.

## Ejemplo: Cliente A

1. El Cliente A solo tiene una ruta disponible para enviar sus paquetes. No es necesario especificar un destino numerado.
2. El destino **default** enviará los paquetes por el único camino disponible.
3. La dirección del próximo salto debe ser la IP de la interfaz del siguiente router en el camino de los paquetes.
4. En este caso, la siguiente interfaz es la **Interfaz R1**, con la dirección IP `54.117.30.126`.
5. Nota: La siguiente interfaz **no** es la Interfaz A1, ya que esta es la propia interfaz del remitente.

---

**Resumen:**  
Las rutas permiten definir cómo y a dónde se envían los paquetes en una red, utilizando los campos de destino y próximo salto para guiar el tráfico correctamente.
