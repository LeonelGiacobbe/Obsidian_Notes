Para calcular la cantidad posible de combinaciones de números sin repeticiones, multiplicamos la cantidad de números que pueden ir al principio, por la cantidad de números que pueden ir en los dígitos que siguen, según la cantidad de dígitos que tengamos, y que debamos averiguar.

  

Por ejemplo: tenemos 5 números y debemos calcular las posibilidades de números de dos dígitos. Sabemos que el primero de los dos números en cada combinación puede ser cualquiera de los 5 números que tenemos, por lo que hacemos 5 x 4 (4 representa la cantidad de números que nos quedan al haber agotado uno para el primer número).

  

# **Permutaciones**

Si tenemos que calcular la cantidad de permutaciones con unos numeros dados, tenemos que ver cuantos números hay, y hacer su versión factorial (x!). Entonces, si tenemos que calcular las permutaciones de nueve números, debemos hacer (9! = 362880)

**Esto funciona cuando todos los números son diferentes entre sí.**

Si, en cambio, tenemos números que se repiten, hacemos el procedimiento con el factorial como antes, pero lo dividimos por el factorial de los números que se repitan. (Si hay 4 números que se repiten, y 6 en total, dividimos a 6!/4! → el 4! hace referencia a la cantidad de repeticiones de los números que no son únicos). Cuando hay dos pares de números que se repiten, hacemos sus factoriales y los multiplicamos en el denominador.

Por ejemplo:

![[/Untitled 28.png|Untitled 28.png]]

  

**Para calcular los divisores de un número:**

Si ese número está expresado como potencia, nos fijamos en los exponentes de sus números. Por ejemplo, si hay 3 números, tenemos que multiplicar a sus potencias, agregandole 1 a cada una. Si es a^5, b^7 y c^3, multiplicamos (5+1) (7+1) (3+1), osea 6 x 8 x 4 = 192.

Ejemplo:

![[/Untitled 1 11.png|Untitled 1 11.png]]

Cualquier multiplicación de potencias menores a las de la multiplicaciçon original van a ser un divisor del número.

Cuando debemos pensar la cantidad total de casos, con excepción de aquellos casos con ciertas condiciones, podemos pensar a la cantidad total de situaciones posibles, y restarle la cantidad total de situaciones en la que sí se cumple lo que nosotros no buscamos, para obtener la cantidad de lo que SÍ buscamos. Recordar que al agrupar números, los contamos como uno a la hora de hacer un factorial. (Si tenemos 6 números, y agrupamos 2 en un paquete, las posibles combinaciones van a ser 5!, 4 individuales y el paquete.)