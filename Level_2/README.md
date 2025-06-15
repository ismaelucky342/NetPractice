# Ejemplo de Subneteo y Máscaras de Red

## 1. Subred para Clientes A y B

Dado que el Cliente B está en la misma red privada que el Cliente A, ambos deben tener la misma máscara de subred:  
**255.255.255.224**

### Explicación en Binario

- **MÁSCARA:** `11111111.11111111.11111111.11100000`
- **IP (Cliente B):** `192.168.20.222` → `11000000.10101000.00010100.11011101`

Los primeros 27 bits representan la dirección de red, y los últimos 5 bits representan el host.  
Para que los hosts estén en la misma red, los primeros 27 bits deben ser iguales; solo se pueden cambiar los últimos 5 bits.

### Rango de Direcciones Válidas

- **Binario:**  
	`11000000.10101000.00010100.11000000` - `11000000.10101000.00010100.11011111`
- **Decimal:**  
	`192.168.20.192` - `192.168.20.223`

#### Exclusiones

- `192.168.20.192`: Dirección de red (todos los últimos 5 bits en 0)
- `192.168.20.223`: Dirección de broadcast (todos los últimos 5 bits en 1)
- `192.168.20.222`: Ya asignada al Cliente B

---

## 2. Notación Slash "/" y Máscara /30

En la interfaz D1 se utiliza la notación **/30**, lo que significa que los primeros 30 bits representan la red y los últimos 2 bits el host.

- **Máscara /30:**  
	Binario: `11111111.11111111.11111111.11111100`  
	Decimal: `255.255.255.252`

Esta máscara es idéntica a la de la interfaz C1.

### Condiciones para Direcciones Válidas

- Los primeros 30 bits (dirección de red) deben ser idénticos para Cliente D y Cliente C.
- Los últimos 2 bits (host) no pueden ser todos 1 ni todos 0.
- Cliente D y Cliente C no pueden tener la misma dirección IP.
