Algoritmo de la división: nos dice que al dividir un dividendo, obtenemos un cociente, un resto, un dividendo y un divisor. Además. **Cociente x divisor, + resto = Dividendo**

![[/Untitled 31.png|Untitled 31.png]]

**R1 siempre es mayor o igual a 0, y menor que N**

**Dos números diferentes pueden ser representados con el mismo resto y módulo. Por ejemplo:**

**35 ≅ 2 (mod 5) y 47 ≅ 2 (mod 5) y 62 ≅ 2 mod (5)**

  

Entonces, podemos decir que:

138 = 12 x 11 + 6. Además, 138 ≅ 6 (mod 11)

≅ significa "congruente" y "mod 11" significa que 138 deja resto 6 al ser dividido por 11.

![[/Untitled 1 13.png|Untitled 1 13.png]]

El resto es la congruencia, y el Mod es el número que se utiliza para dividir.

Entonces, podemos usar esta congruencia para restar dos números con módulo. Hay posibilidad de sacar factor común según N, y la operación final, con congruencia, incluye al resto de ámbos números (sumados o restados) y el módulo N.

![[/Untitled 2 9.png|Untitled 2 9.png]]

Así queda la fórmula resuelta en suma y resta.

  

Si sumamos al mismo numero una cantidad de veces M, el resultado va a ser que la suma, expresada como M.A ≅ M.r1

![[/Untitled 3 8.png|Untitled 3 8.png]]

Si sumamos un número A una cantidad A de veces, un lado de la ecuación nos queda A al cuadrado, y el otro como AKn + Ar1, pero como sabemos que A = Kn + r1, reemplazamos y hacemos la distribución.

![[/Untitled 4 6.png|Untitled 4 6.png]]

Al hacer la resolución de esta propiedad, sin importar la suma, no consideramos a cualquier cosa que esté multiplicada por N, y para al congruencia solo consideramos el resto, multiplicado (o no) por el mòdulo N.

Esta misma propiedad aplica cuando elevamos a A a cualquier potencia. Así:

![[/Untitled 5 6.png|Untitled 5 6.png]]

Todo lo que no contenga N, es considerado como resto.

Cuando sumamos un número A una B cantidad de veces, el resultado va a ser congruente con los restos de ambos números multiplicados (Mód. N)

![[/Untitled 6 4.png|Untitled 6 4.png]]

Al sumar los restos y módulos de dos o más números puede suceder que el resto sea mayor que el divisor, y en ese caso le debemos restar el divisor al resto, ya que **R1 siempre es mayor o igual a 0, y menor que N. EJEMPLO: 80 tiene resto 0 con mod 5, y 6 tiene 1 mod 5. 86 lo obtuvimos al sumar 37 (2 mod 5) y 49 (4 mod 5)**

![[/Untitled 7 3.png|Untitled 7 3.png]]

Si a un resto congruente positivo le restamos el módulo, obtenemos un resto equivalente, pero negativo. Por ejemplo:

![[/Untitled 8 3.png|Untitled 8 3.png]]

Nos conviene usar esto cuando sumamos dos números con restos diferentes, pero vemos que si uno de los restos fueran negativos, nos facilitaría la cuenta, ya que tenemos que restar los restos, pero el módulo queda igual.

  

  

**CLASES DE MÓDULOS:**

Al dividir un número por otro, las opciones de restos que me pueden quedar son iguales al número. Por ejemplo, al dividir por dos, nos quedan 2 posibilidades: 0 o 1. Desde 0 a n-1

Siempre buscamos el resto más pequeño posible, ya sea positivo o negativo.

  

CRITERIOS DE DIVISIBILIDAD

Si queremos ver si un número es divisible por otro, lo podemos separar en milenios, centenas, etc. Y hacer el resto con el módulo el cual queremos dividir. Siempre buscamos el resto más pequeño posible, ya sea positivo o negativo.