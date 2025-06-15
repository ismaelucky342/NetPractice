# Ejercicio: Introducción al Router

Este ejercicio introduce el concepto de router. El router se utiliza para conectar múltiples redes entre sí, utilizando varias interfaces (en este ejemplo: Interfaz R1, Interfaz R2 e Interfaz R3).

## 1. Selección de la Máscara de Subred

Dado que no se ha especificado la máscara en las interfaces B1, A1 y R1, podemos elegir nuestra propia máscara de subred. Una máscara **/24** es ideal, ya que nos deja todo el cuarto byte para las direcciones de host y no requiere cálculos binarios complejos para determinar el rango de direcciones posibles.

## 2. Asignación de Direcciones IP

La dirección IP de la Interfaz B1 y la Interfaz R1 debe tener la misma dirección de red que la dirección IP de la Interfaz A1. Con una subred **/24**, el rango posible es:

```
85.17.5.0 - 85.17.5.255
```
Excluyendo la dirección de red y la dirección de broadcast.

## 3. Nota sobre las Interfaces del Router

No interactuamos con las interfaces R2 y R3 del router, ya que ninguna de nuestras comunicaciones necesita llegar a esos lados del router en este ejercicio.

---

**Resumen:**  
- El router conecta varias redes usando diferentes interfaces.  
- Se recomienda una máscara de subred /24 para facilitar la asignación de direcciones.  
- Solo se utilizan las interfaces necesarias para la comunicación requerida.
