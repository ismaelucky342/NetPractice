# Nivel 6: Introducción a Internet

Este nivel introduce el concepto de Internet. Internet se comporta como un router. Sin embargo, si una interfaz está conectada directa o indirectamente a Internet, **no puede tener una dirección IP** dentro de los siguientes rangos privados reservados:

- **192.168.0.0 - 192.168.255.255** (65,536 direcciones IP)
- **172.16.0.0 - 172.31.255.255** (1,048,576 direcciones IP)
- **10.0.0.0 - 10.255.255.255** (16,777,216 direcciones IP)

---

## Enrutamiento hacia el Cliente A

El siguiente salto de Internet ya está configurado y coincide con la dirección IP de la interfaz R2. Por lo tanto, solo debemos preocuparnos por el destino de Internet.

Internet debe enviar sus paquetes al **Cliente A**. Para ello, el destino de Internet debe coincidir con la **dirección de red** del Cliente A.

### Cálculo de la dirección de red

- **Máscara de Cliente A:** 255.255.255.128 (equivalente a /25)
- **IP de Cliente A:** 40.178.145.227

La máscara /25 indica que los primeros 25 bits de la IP corresponden a la dirección de red.

- Los primeros 24 bits (3 bytes): `40.178.145.?`
- Convertimos 227 a binario: `11100011`
- El primer bit (25º) es `1`, por lo que el último byte de la red es `128` (binario `10000000`).

**Dirección de red:** `40.178.145.128`

**Rango de hosts:** `40.178.145.129 - 40.178.145.254`

---

## Configuración del destino en Internet

Debemos colocar la dirección `40.178.145.128` como destino en Internet. El `/25` indica la máscara aplicada.

> Un destino `40.178.145.227/25` es equivalente a `40.178.145.128/25`, ya que la máscara /25 fuerza los bits posteriores al 25º a 0, obteniendo así la dirección de red.
