Si tocamos el boton Build (forma de engranaje) se guarda el código como archivo ejecutable en la carpeta "bin"

[http://juez.oia.unsam.edu.ar/](http://juez.oia.unsam.edu.ar/) → creamos un usuario → archivo de enunciados → todos los problemas → envíos. (para ver y enviar soluciones a problemas).

---

if(condición) (sin punto y coma al final).

resultado

Para comparar si dos valores son iguales se usa el == y no el = (osea, se usa un signo de igual doble).

Podemos escribir un if o un else dentro de un if u otro else, siempre que respetemos bien la sintaxis.

Para poner un condicional con dos condiciones separadas, usamos "or" ó ||. Ejemplo:

if (x=3 **or (**x=6))

Para ponber un condicional con dos condiciones juntas, usamos "and" ó "&&". Ejemplo:

if (x=3 **and** y=4)

Para agregar otro condicional en la misma estructura, usamos **else if**

/** = comentario de bloque (empezar)

**/ = comentario de bloque (terminar)

---

While: mientras que una condicion se cumpla, se va a seguir ejecutando el código indicado. Por ejemplo:

while ( X ≤ 100)

cout << x << endl;

X = X + 1;

Esto imprimiría los números consecutivos hasta que no se cumpla la condicion indicada al principio del loop ( X ≤ 100, en este caso).

---

For: muy parecido al while. Tiene 3 partes:

For(parte_1;parte_2;parte_3)

parte_1 → creación, inicialización o declaración de variables. (podemos usar variables creadas afuera del **For Loop**.

parte_2 → condición que se tiene que cumplir para ejecutar el código.

parte_3 → incremento de variables.

Si dejamos alguna de las partes vacías, el punto y coma tiene que ir para indicarle al programa que parte corresponde (al principio y final).

---

Para sumarle uno a una variable tipo int, podemos usar:

- x = x +1
- x++
- x += 1

---

Cuando hacemos una division de integers en C++ nos da el valor redondeado para abajo. Por ejemplo 36(A)/5(B) da 7, y no 7,2 u 8.

En cambio, si queremos redondear para arriba, tenemos que hacer (A+B-1)/B. Osea (36+5-1)/5