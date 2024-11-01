https://www.cplusplus.com/reference/

---

modulo → resto de una division. ej→ 5/2. el resto (o mod) es 1.

para hallar el reto de una division, usamos el modulo. Para hallar el cociente, hacemos la division normal

para ver la cantidad de caracteres en un string o la cantidad de valores en un vector:

```C++
string s ="hola";
int tam = s.size();
cout<<tam<<endl;
```

podemos hacer lo mismo, pero con un vector en vez de un string para ver la cantidad de valores que contiene. para un tamaño X de un vector, la última celda accesible es la X-1.

para acceder a los valores dentro de un vector usamos el índice → vector[N]. Notar que "N" representa a un valor y no un caracter, asi que por ejemplo el numero 45 esta dentro de un mismo valor, y no de dos.

usando la operacion min(a,b), si ponemos dos valores que son iguales, no nos devuelve un error.

para pegar un valor en la consola, primero lo copiamos con ctrl v y luego hacemos click derecho en la consola.

---

Cuando creamos un vector con datos inciales, esos datos se llaman constructor. Por ejemplo:

vector <int> v(N) → ese vector va a tener una cantidad N de datos.

tambien tenemos → vector <int> v(N, K) donde el vector tiene N elementos, y todos son K. Si no aclaramos que número es K, va a tomar por defecto a 0.

para agregar un valor a un vector → vector.push_back(valor).

---

bool → variable que tiene dos posibles valores: true o false.

---

podemos crear funciones que adentro tengan un codigo que creemos que vamos a ejecutar más de una vez. para eso, creamos la funcion, ponemos el codigo a reutilizar adentro, y luego ponemos los parametros necesarios en el parentesis. Recordar el tipo de funcion de acuerdo a lo que queramos que nos devuelva.

Al llamar la funcion, nada mas ingresamos los parametros y nos va a devolver el resultado.

en una funcion, al poner return x; la funcion termina, y devuelve ese mismo valor, posiblemente ignorando el resto del codigo que falta procesar. Esto nos puede servir cuando buscamos un numero o palabra entre muchos, y apenas lo encontremos ya tenemos el resultado de que sí existe, y no necesitamos ejecutar el resto del codigo, por ejemplo.

---

sort: sirve para ordenar un vector. para usarla, al principio debemos poner → \#include<algorithm>

lleva dos valores:

sort(vector,begin(), vector,end());

---

reverse: sirve para dar vuelta un vector(el primer valor pasa a ser el ultimo, el ultimo pasa al primero, y así).

lleva dos valores:

reverse(vector,begin(), vector,end());