## Elabora la tabla de símbolos con el código corregido. Sin embargo, antes de hacerlo, es fundamental realizar un análisis y reflexión.

- Investiga la función que permite obtener el tamaño del tipo de dato en el algoritmo proporcionado.
Nota: Asegúrate de que estas funciones se expliquen claramente en el video.

- ¿Qué relación tiene el tamaño de tipo de datos en las direcciones de memoria
(posición) en la tabla de símbolos?

- ¿Por qué en un compilador real, la tabla de símbolos almacena direcciones de
memoria en hexadecimal (ejemplo: 0x1001, 0x2005)?


- R//: Función para Obtener el Tamaño del Tipo de Dato
La función/operador en C++ que devuelve el tamaño en bytes de un tipo de dato o de una variable es sizeof.

Ejemplo: sizeof(int) devuelve el número de bytes que ocupa un entero en el sistema (típicamente 4).

Relación del Tamaño de Tipo de Datos con las Direcciones de Memoria (Posición)
El tamaño (sizeof) dicta cuántos bytes consecutivos deben reservarse para una variable, comenzando en la dirección base asignada.

La Tabla de Símbolos almacena la dirección base (el primer byte) donde comienza la variable.

El tamaño del tipo (ej., un int de 4 bytes) le indica al compilador que, para acceder a la variable, debe leer/escribir N bytes a partir de esa dirección base.

¿Por qué la Tabla de Símbolos Almacena Direcciones en Hexadecimal?
Las direcciones de memoria se representan en hexadecimal (0x...) por estas razones fundamentales:

Compactación de Binario: El hardware trabaja con direcciones binarias (bits). El hexadecimal es la forma más corta y legible para representar grandes números binarios.

Organización de Bytes: Facilita la visualización de la alineación y las fronteras de los bytes en la memoria (cada dígito hexadecimal representa 4 bits o medio byte).

## Tabla de Símbolos con Código Corregido y Direcciones Reales de Memoria


Nombre	Tipo	Valor	Ámbito	Tamaño (bytes)	Dirección (Hexadecimal Hipotética)
km_to_miles	float	0.621371	Global	4	0x2000
temp_celsius_global	int	0	Global	4	0x2004
convertirUnidades	void()	-	Global	-	0x1000 (Código)
distancia_km	float	10.0	convertirUnidades	4	0x3000
resultado_millas	float	6.21371	convertirUnidades	4	0x3004
temp_celsius_local	float	25.5	convertirUnidades	4	0x3008
temp_fahrenheit	double	77.9	convertirUnidades	8	0x300C
unidad	char	'C'	convertirUnidades	1	0x3014
main	int()	-	Global	-	0x10A0 (Código)


