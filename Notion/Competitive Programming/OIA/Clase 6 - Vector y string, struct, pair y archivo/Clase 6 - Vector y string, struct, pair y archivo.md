\#include <bits/stdc++.h> es una librería que contiene en sí a casi todas las librerías, pero tarda un poco mas, que usando otros include particulares.

Cuando un valor booleano tiene como resultado "true" tiene valor numérico 1. Cuando tiene resultado "falso" tiene como valor numérico 0.

si usamos **const vector <int> x**, estamos diciendo que ese vector va a ser constante, es decir que sus valores no van a poder ser cambiados.

Si queremos crear una funcion que devuelva vectores enteros → vector <int> NombreDeFuncion

---

PAIR→ tipo de funcion que nos devuelve dos datos, que pueden ser del mismo tipo o diferentes.

Para declarar la funcion afuera del main → pair <tipo1, tipo2> NombreFuncion( )

Para devolver el resutlado → return {tipo1, tipo2};

Para llamar la funcion → pair <tipo1, tipo2> NombreDeVariable = NombreFuncion( );

ó **auto** NombreDeVariable = NombreFuncion( ); Esto detecta automáticamente que va a devolver la funcion analizando el tipo de dato del return de la función.

El **auto** nada más nos sirve si ya especificamos el tipo de dato, sino tenemos que usar el primer ejemplo.

Usamos res.first y res.second para imprimir el primer y segundo valor.

Si guardamos un pair adentro de otro pair, usamos x.first.first o x.first.second para acceder a sus valores.(un first o un second adentro de otro first o second). Para entender mejor nos conviene mirarlo desde afuera:

![[/Untitled 25.png|Untitled 25.png]]

un Pair sería como un vector, con solo dos elementos, pero que pueden ser de distinto tipo.

---

Cómo convertir de int a string:

podemos hacer el módulo 10 de un número n para obtener el número de las unidades

podemos hacer %100 para las decenas y unidades (dos ceros, dos dígitos de resto)

podemos hacer %1000 para las centenas, decenas y unidades (tres ceros, tres dígitos de resto)

La cantidad de ceros del modulo (%X) nos dice cuantos dígitos nos queda de resto

---

para revertir un string:

\#include <algorithm>

reverse(string.begin(),string.end())

---

para calcular la cantidad de dígitos de un número N:

```C++
int X=N;
int c=0;
while(x!=0)
  {
    x=x/10;
    c++;
  }
```

---

para pasar de string a int:

declaramos un string con el número y un int =0;

hacemos un for para que recorra los dígitos del string, y hacemos:

int dígito = (string[ i ]-'0'); → por ejemplo, el 2 tiene valor ascii 50, y le sacamos al 0 (48) para q de 2

int n = n*10+dígito.

(n es el string pasado a int) n == string (pero de tipo INT)

---

ARCHIVO: para leer y escribir archivos de texto. usamos "include <fstream>"

creamos un archivo .txt. Para leer ese archivo:

ifstream nombre ("nombre del archivo.txt") → el archivo txt debe estar en la misma carpeta que el main. Si no está en la misma carpeta, debemos referirnos al archivo con el PATH. (click derecho, properties, location). tenemos que cambiar \ por /

//////////////////////////////////////////////////////////////////////

Para escribir en un archivo:

ofstream nombre("nombredelarchivo.txt")

para elegir el nombre del archivo desde el mismo código, declaramos una variable y

ofstream nombre("variableingresada.txt")

Para leer de un archivo:

```C++
ifstream cin("nombre.txt");
```