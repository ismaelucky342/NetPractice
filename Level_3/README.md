# Ejercicio: Uso del Switch

Este ejercicio introduce el uso del switch (Switch S en este ejemplo). El switch conecta múltiples hosts dentro de la misma red.

## Instrucciones

1. **Configuración de la máscara de subred:**  
	El Cliente A, el Cliente B y el Cliente C están en la misma red. Por lo tanto, todos deben tener la misma máscara de subred.  
	- Cliente C ya tiene la máscara `255.255.255.128` (notación slash: `/25`).
	- La Interfaz B1 y la Interfaz A1 también deben usar la máscara `255.255.255.128`.

2. **Asignación de direcciones IP:**  
	La dirección IP de la Interfaz B1 y la Interfaz C1 debe estar en el mismo rango de red que la IP del Cliente A.  
	- Rango de red válido:  
	  ```
	  104.198.241.1 - 104.198.241.126
	  ```
	- Nota: Se excluyen la dirección de red (`104.198.241.0`) y la dirección de broadcast (`104.198.241.127`).

## Notas

- Asegúrate de que todas las interfaces y clientes estén configurados correctamente dentro del rango y con la máscara indicada.
- El switch simplemente conecta los dispositivos; no requiere configuración adicional para este ejercicio.

