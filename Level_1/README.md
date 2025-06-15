## Ejemplo de Asignación de Direcciones IP y Máscaras de Subred

1. **Clientes en la misma red (máscara 255.255.255.0):**  
	Como el Cliente A y el Cliente B están en la misma red, sus direcciones IP deben compartir los primeros 3 bytes, según la máscara de subred. El cuarto byte identifica al host.  
	**Rango válido:** `104.96.23.1` a `104.96.23.254`  
	**Exclusiones:**  
	- `104.96.23.0`: Dirección de red  
	- `104.96.23.255`: Dirección de broadcast  
	- `104.96.23.12`: Ya asignada al Cliente B

2. **Clientes en una red más grande (máscara 255.255.0.0):**  
	Aquí, los primeros 2 bytes identifican la red y los últimos 2 bytes al host.  
	**Rango válido:** `211.191.0.1` a `211.191.255.254`  
	**Exclusiones:**  
	- `211.191.0.0`: Dirección de red  
	- `211.191.255.255`: Dirección de broadcast  
	- `211.191.89.75`: Ya asignada al Cliente C