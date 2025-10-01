
## Análisis y Reflexión sobre la Tabla de Símbolos

---

### Función para Obtener el Tamaño del Tipo de Dato

El operador fundamental en C++ para determinar el espacio que un tipo de dato o una variable ocupará en la memoria es **`sizeof`**. Este operador devuelve el tamaño en **bytes**.

* **Propósito:** `sizeof` es esencial para la **gestión de memoria** y la **portabilidad del código**, ya que indica al compilador el bloque exacto de memoria que necesita asignar para almacenar el valor de la variable.

### Relación del Tamaño de Tipo de Datos con las Direcciones de Memoria

La relación es **directa** y crucial:

* El **tamaño** de un tipo de dato (`sizeof`) dicta cuántos **bytes contiguos** debe reservar el compilador para la variable.
* La **dirección de memoria** (posición) que se registra en la Tabla de Símbolos es la **dirección base** (el primer byte) de ese bloque reservado.

Por ejemplo, si un `int` (típicamente 4 bytes) se asigna a la dirección $0\text{x}3000$, la variable ocupa las direcciones desde $0\text{x}3000$ hasta $0\text{x}3003$.

### ¿Por qué la Tabla de Símbolos Almacena Direcciones en Hexadecimal?

Las direcciones de memoria se representan en **hexadecimal** ($0\text{x}...$) por razones de eficiencia y arquitectura:

1.  **Compactación y Legibilidad:** Es la forma **más compacta y legible** para representar números binarios grandes, que son las direcciones reales de memoria.
2.  **Arquitectura y Alineación:** El hexadecimal facilita la visualización de la **alineación de memoria** y las fronteras de los bytes, lo cual es vital para el acceso eficiente a la memoria por parte del procesador.

---

## 4) Tabla de Símbolos con Código Corregido y Direcciones Reales de Memoria

Las direcciones mostradas son **hipotéticas** (varían según el sistema) pero respetan el tamaño típico de los tipos de datos en una arquitectura de $64$-bits y la asignación de espacio contiguo.

| Nombre | Tipo | Valor | Ámbito | Tamaño ($\text{bytes}$) | Dirección (Hexadecimal Hipotética) |
| :--- | :--- | :--- | :--- | :---: | :--- |
| `km_to_miles` | `float` | $0.621371$ | Global | $4$ | $0\text{x}2000$ |
| `temp_celsius_global` | `int` | $0$ | Global | $4$ | $0\text{x}2004$ |
| `convertirUnidades` | `void()` | - | Global | - | $0\text{x}1000$ (Código) |
| `distancia_km` | `float` | $10.0$ | `convertirUnidades` | $4$ | $0\text{x}3000$ |
| `resultado_millas` | `float` | $6.21371$ | `convertirUnidades` | $4$ | $0\text{x}3004$ |
| `temp_celsius_local` | `float` | $25.5$ | `convertirUnidades` | $4$ | $0\text{x}3008$ |
| `temp_fahrenheit` | `double` | $77.9$ | `convertirUnidades` | $8$ | $0\text{x}300\text{C}$ |
| `unidad` | `char` | 'C' | `convertirUnidades` | $1$ | $0\text{x}3014$ |
| `main` | `int()` | - | Global | - | $0\text{x}10\text{A}0$ (Código) |

