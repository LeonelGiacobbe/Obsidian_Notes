MCD: mayor número que divide a dos números A y B.

MCM: menor número que es múltiplo de A y B.

El MCD siempre es divisor del MCM de dos números.

---

Para calcular el MCD, factorizamos en primos, y luego elegimos SÓLO los comunes al MENOR exponente.

Para calcular el MCM, factorizamos en primos y luego elegimos comunes y no comunes al MAYOR exponente.

a.b = MCD . MCM

---

Propiedades del divisor:

Si un número "d" divide a un número "a" y a un número "b", también divide a "a+b". También divide a "a-b".

"d" también divide a a.t y b.t

"d" al cuadrado también divide a a.b

---

Calcular MCD por Euclides.

Para calcular el MCD entre dos números a y b, le restamos el mas chico al más grande hasta que nos queden dos números iguales en a y b. Ejemplo:

![[/Untitled 37.png|Untitled 37.png]]

También podemos hacer con divisiones:

dividimos el mayor por el menor. luego dividimos al menor original por el resto, y hacemos esto hasta que el resto nos quede 0, y el MCD va a ser ell último resto antes que 0.

en este caso 96/30 nos da 3 y resto 6. Luego hacemos 30/6 nos da 5 y resto 0. 0 es el último resto, y el anterior a 0 es 6, nuestro MCD.

Cuando hacemos las divisiones, el último resto pasa a ser el divisor

Si el MCD entre a y b es 1, a y b son coprimos

---

Para ver si una expresión es divisible por un número, debemos tranajar con los posibles restos. Por ejemplo, en división por 3, los restos son 0,1y2. Entonces, si tenemos una expresión (a*a+4), vemos como sería el resto cuando el resto de a vale 0, 1 y 2.

Ej para (a*a+4) divisible x 3.

resto a→0; a=3; (3*3+4)=13, resto 1.

resto a→1; a=4; (4*4+4)=20, resto 2.

resto a→ 2; a=5; (5*5+5)=30, resto 0.

Elegimos valores para "a" que tengan los restos que necesitamos (ej: necesitamos resto 1 en div x 3, elegimos 4, 7, 10, etc.)

---