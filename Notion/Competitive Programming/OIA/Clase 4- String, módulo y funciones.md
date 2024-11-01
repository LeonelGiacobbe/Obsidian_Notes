char → tipo de dato, como int. ponemos _char variable._ Se usa para almacenar una sola letra dentro de la variable, solo una.

String → otro tipo de dato. ponemos _string variable._ Se usa para almacenar una palabra de más de un carácter.

Letras mayúsculas → valores ASCII del 65 al 90. La A mayuscula vale 65 mientras que la Z mayuscula vale 90.

Letras minúsculas - valores ASCII del 97 al 122. La a minúscula vale 97 mientras que la z minúscula vale 122.

Así, podemos ver is una variable se encuentra dentro de esos valores para saber si es mayúsucula o minúscula.

Las comillas simples →' ' se utilizan cuando ocupamos un solo caracter. Cuando queremos usar una frase se utilizan las dobles comillas " ". Entonces → '4' y "Hello World".

Siempre que mezclamos 'char' y números la operación se va a hacer en números.La diferencia entra una misma letra mayúscula y minúscula es de 32. Así que si queremos cambiarla, debemos sumar o restar 32.

Para ver el valor ASCII de un caracter hacemos int(letra).

char → comillas simples **' '**

string → comillas dobles **" "**

Podemos guardar una muchas palabras con espacios entre ellas menos cuando lo ingresamos por teclado. Si ingresamos muchas palabras por teclado, nada más nos va a reconocer la primera. Los caracteres se separan en palabras cuando usamos espacio, tab o enter.

para ver la cantidad de caracteres de una palabra, creamos una variable int:

int tamaño = variable.size()

Se pueden sumar dos strings o más como números (string1 + string 2) o:

s = "hola"

s += 's' → s= "holas"

s.push_back('caracter'); → agrega la letra entre parentesis al final.

s.pop_back('caracter'); → saca la última letra de la palabra.

---

para converir de char a string:

string variable1 (1,variable2); → variable 1 va a ser el nombre del nuevo string y variable 2 es el nombre del char que convertimos.

---

Para leer una letra específica de un string, usamos string[index]. La primer letra es 0, por lo que

string = "hola" → string[0] = h.

para comparar dos strings usamos "=="; "<" o ">".

---

Vectores: sirve para agrupar varios integers, como si fuera una lista.

Al principio de nuestro código, debajo de donde dice \#include "<iostream>", escribimos

**\#include <vector>.** Para definir un vector → vector<int> nombre;

Para agregar un valor al vector, hacemos nombrevector.push_back(variable con un int);

\n es similar a endl;

---

Funciones:

para declarar una función → tipo nombre(variables) {

código que queremos escribir.

}

tenemos que especificar si va a devolver algo o no:

void → no devuelve nada

si no es void, indicamos que va a devolver (string, int, vector <int>, etc)

Cualquier tipo de funcion que no sea void tiene un return junto con un valor al final. Por ejemplo, si hacemos una funcion que sume dos números a y b, la funcion puede decir return a+b. Si es void, directamente no ponemos el return.

los parametros se declaran en los parentesis cuando creamos una funcion, y debemos rellenarlos al llamarla. Si hay mas de un parametro en la funcion, se separan entre si con comas

---

la funcion min() se usa para ver el minimo entre dos o mas valores, aunque en el parentesis solo pueden ir dos valores (3,6), por ejemplo.

por ejemplo→ min(3, min(4,9)) devolvería 3.

---

cuando una funcion tiene "return" al final, significa como si despues de ejecutar un código nos diera un resultado y nos lo guardaramos en el bolsillo pero no lo mostramos. Para mostrarlo, debemos poner cout << funcion << cuando llamamos a la funcion, o mismo poner un cout adentro de la funcion misma, y no cuando la llamemos. Ejemplo:

==1ra opcion==

int sumas(int a, int b){

==return a+b; ——>== ==me devuelve el valor, pero no lo muestro.==

}

==cout << sumas(int a, int b) << endl; ——>== ==con la ayuda del cout, muestro el valor en la pantalla==

//////////////////////////////////////////

==2da opcion==

int sumas(1,2){

==cout << a+b << endl; ——>== ==con la ayuda del cout, imprimo. (cuando llamen a la funcion)==

}

==sumas(int a, int b) ——>== ==llamo a la función, que adentro tiene el comando de imprimir el resultado==

---

para hacer una referencia a un valor en los parametros de una funcion, usamos el simbolo "&".

ejemplo → int &a → "a" va a tomar referencia del valor que demos afuera de la funcion, y no es que crea una variable aparte.

Al hacer una referencia, lo que nosotros hacemos es que el valor que se use como parametro en la funcion sea la variable original, y no una copia. Así, si el valor con referencia sufre un cambio al realizar la funcion, el cambio va a permanecer afuera de la funcion. En cambio, si no usamos el &, osea la referencia, se copia el valor en otra variable, se usa esa copia en la funcion, y luego se descarta. Si esa copia es transformada, igualmente no afecta al valor original.

---

para encontrar la cantidad de letras en un string:

string a = "hola";

int b =a.length(); ó → a.size();

cout<<b;

---

para imprimir un char o string una cantidad x de veces hacemos:

char(x,'a') ó string(x,'a')