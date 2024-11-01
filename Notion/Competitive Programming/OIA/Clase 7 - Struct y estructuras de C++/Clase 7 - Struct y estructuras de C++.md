cuando usamos un for adentro de otro, normalmente se usa la variable "i" para iterar en el loop de afuera, y la variable "j" para el loop de adentro.

Para iterar dos variables dentro de un vector:

```C++
for(int i=0;i<n;i++)
{
		for(int j=0; j<i;j++)
		{
			cout<< i << ' ' << j;
		}
}
```

ahí veríamos todas las combinaciones de índices de un vector

---

Struct: Nos permite almacenar datos juntos, aunque sean de distinto tipo. Como un pair, pero del largo que queramos.

Para Declarar un **Struct** y sus **Variables:**

```C++
struct Nombre
{
		string Valor1, Valor2; ///por ejemplo, si tenemos dos valores de string
		int Valor3, Valor4;	///si tenemos además dos valores de int
		///como podemos ver, combinamos dos o más valores, incluso si son de distinto tipo
};
```

Para darle valor a las variables:

```C++
Nombre N; ///N puede ser cualquier letra -> Provincia P; por ejemplo
N.Valor1 = "string1";///para dar valor, letra asignada-.-nombre de variable.
///podría ser N.NumMax = 999; --- S.apellido = "Giacobbe"
```

```C++
///Otra forma de darle valor a las variables
Nombre N = {"Leonel", "Giacobbe", 14, 2004}///Leonel se asigna a valor 1, 14 a valor 3, y así
///importante usar llaves"{","}" y separar los valores por coma ","
```

**Podemos usar un struct varias veces.** Por ejemplo de arriba: Nombre N(con sus variables) Nombre x(tiene el mismo tipo de variables, pero con otros valores). Todos los nombres de este struct tienen las mismas variables, pero con valores que no se superponen.

---

Para asociar un archivo con un struct (leer o escribir en el .txt):

podemos crear un vector que de tipo sea struct → vector <struct> nombre(tamaño);

luego creamos un for para añadir los valores. quedaría:

```C++
for(int i=0;i<n;i++)
    {
        string dato1, dato2;///declaramos dato1 y 2
        int dato3, dato4;///declaramos dato3 y 4
        cin>>dato1>>dato2>>dato3>>dato4;///ingresamos los datos declarados anteriormente
        nombrevector.push_back({dato1,dato2,dato3,dato4})///asignamos lo ingresado 
				///importante usar () y {}, delpush_back y del struct
				
    
```

Cuando hacemos un cin de un archivo para guardarlo en variables dentro de un struct, hace la separación cuando encuentra un espacio, un tab o enter. así si, por ejemplo:

dato1=Buenos-Aires// Dato2= BA// Dato 3=17541141, y así.

![[/Untitled 26.png|Untitled 26.png]]

---

Operator<:

es una función booleana que toma dos valores por referencia:

```C++
	bool operator<const NombreStruct&a; NombreStruct&b)
{
			return a.valor1 < b.valor1///si esto se cumple, devuelve true; si no se
                                /// cumple devuelve false
}
```

Sort: para ordenar un vector de menor a mayor (puede ser según el operator<, si lo usamos anteriormente)

sort(vectorN.begin(), vectorN.end())

---

**Estrcutura de Datos Estándar en C++:**

- Para incluir toda la biblioteca standar de c++: \#include <bits\stdc++.h>
- Anidación: los elementos de una estructura son a su vez estructura de datos
- Matriz: creamos una tabla de enteros organizados en "filas" y "columnas". Se hace así:

```C++
vector<vector<int>> Matriz<(N,vector<int>(M,O);
Matriz.size()///Nos da la cantidad de filas N.
Matriz[0].size()///Nos da la cantidad de columnas, M.
///Nos da el largo de la primera fila. Es importante en el caso de que las filas tengan
///diferente longitud.
///Dentro de un for, con i como variable itinerante:
matriz[i].size ///nos da el largo de la i-esima fila
matriz[i]///accedemos a la i-esima fila
///dentro de un for, que a su vez está dentro de otro for(j dentro de i):
matriz[i][j]///accedemos al j-esimo elemento de la i-esima fila
----------------------------------------------------------------------------------------
///podemos hacer sort, reverse, etc.
sort/reverse(matriz[i].begin(),matriz[i].end());
///podemos ordenar a toda la matriz en orden lexicográfico, o a una fila en particular
///(esa fila es llamada matriz[i], siendo "i" una variable itinerable dentro de un for
----------------------------------------------------------------------------------------
///no hay una forma directa de acceder a las columnas, sino que tenemos que acceder a un
///mismo subíndice(ej[j]) de las diferentes filas(que en realidad son vectores)
```

![[/Untitled 1 10.png|Untitled 1 10.png]]

Acá, A,B y C son vectores. Podemos acceder a ellos a través de subíndices. Sin embargo, si queremos a una columna (la de 2,7,12, por ejemplo) debemos acceder al subíndice [1] de la fila o vector a, b y c. Sería a[1], b[1] y c[1]=2,7,12

En realidad no existen las columnas, sino que las "formamos" accediendo al mismo subíndice de las diferentes filas o vectores

Podemos inicializar una matriz de manera manual:

```C++
vector<vector<int> > matriz={

	{valor1,valor2,valor3},///se ponen los valores entre llaves, separados por coma
	{valor4,valor5},///al final del vector, afuera de las llaves, va una coma
};
///las filas pueden tener diferente longitud
```

Órden FIFO: First in First Out. El primer dato que ingresamos a la estructura va a ser el primero en salir.

**Queue:**

```C++
queue<tipo> Nombre;///la cola comienza vacía.
///dentro de una queue, tenemos las siguientes operaciones:
Q.empty();/// nos indica si no hay elementos en la cola
Q.size();///nos indica la cantidad de elementos en la cola
Q.push(x);///agrega el elemento "x" al final de la cola
Q.front();///nos devuelve el elemento al final de la cola(siguiente a ser atendido)
Q.pop();///elimina el elemento al final de la cola. (ultimo a ser atendido, x ej)
///es mas eficiente usar una queue que un vector
///el operador [i] no está definido para la cola, no podemos acceder a un subindice 
///en la cola solo podemos ver al elemento que está por salir, que está primero en orden
///si imaginamos como en la cola del super, la cajera solo puede ver al que está primero
///en la fila, se ve con ".front()", y el último de la fila lo podemos ver con ".pop()"
```

Cola de prioridad (priority_queue): sabe siempre cual es el elemento con prioridad dentro de la cola, no es FIFO.

La priority queue siempre pone al elemento mayor al frente.

```C++
Para crear una priority queue:
priority_queue<int>PQ;//La cola comienza vacía
///la sintaxis es igual a la queue normal, salvo que usamos TOP en vez de FRONT
PQ.top();//nos devuelve el elemento mayor, prioritario
///       (equivalente a front en una queue normal)
PQ.pop();//borra el mayor elemento, el prioritario
```

Conjunto: una agrupación de elementos, sin importar su órden y repeticiones.

```C++
{1,2,3}
{3,2,1}
{1,1,1,2,2,3}
///los tres conjuntos son iguales, ya que solo mira a los valores, e ignora el 
///órden y la cantidad de repeticiones.
```

en esta idea, se implementa la estructura "SET"(conjunto)

operaciones con set:

```C++
set<int> S;///el conjunto comienza vacío
S.empty();///nos indica si hay o no elementos en el conjunto
S.size();///nos da la cantidad de elementos en un conjunto
S.insert(x);///agrega o inserta un valor al set.
(S.find(x)!=S.end());///nos indica si X está en el conjunto. True si x esta, False si no
S.erase(x);///borra el elemento X del conjunto, si existe.
```

podemos inicializar un set con sus valores ya declarados:

```C++
set <int> S= {1,2,3}; ///crea el set con los elementos entre llaves
(S1=S2);///Para comparar si S1 y S2 son iguales (ambos son Sets)
(*S.begin());//nos da el elemento menor del Set, utilizando el asterisco.
///dentro de un set, el elemento S.begin() es el mas chico, y S.end() el mas grande
```

Mapear: es asignarle a cada elemento de un conjunto, un elemento de otro conjunto.

Se implementa en la estructura "Map". Se puede pensar también como un vector donde el índice es un elemento de cualquier tipo, y las posiciones se crean cuando accedemos a ellas.

```C++
///un map relaciona dos tipos de datos
///ejemplo: string con enteros
map<string,int> Nombre;///el map comienza vacío.
```

Dentro de la estructura "Map" tenemos las siguientes operaciones:

```C++
//los elementos que usamos como índices se los llama key o llaves -> M[X]
M.empty();//nos indica si el map está vacío o no.
M.size()//nos da la cantidad de elementos en el map
M[X];///accedemos a la posición X del map
(M.find(X)!=M.end();///indica si X es llave en el map
M.erase(X);///elimina el dato que se encuentra en la llave X del map.
///si en M[X], x es menor a mil millones, nos conviene usar vector.
///si queremos leer algo que no inicializamos, nos da el valor x defecto (int=0, x ej)
```

Si por ejemplo queremos acceder a la posición $7^9$﻿, no crea $7^9$﻿posiciones, si no que crea esa sola, es decir que va creando a medida que accede.

---

For auto: iterar estructuras de datos: en c++ hay estruct. en las que podemos recorrer los elementos que contienen. Para hacerlo:

```C++
for(auto x : v){
			///código.
}
///en este caso, x toma el valor de c/u de los elementos de v en el orden en el que están.
///cada valor es una iteración del ciclo.
```

Además, podemos crear referencias a los valores de v. Esto quiere decir que si los modificamos dentro del for, también se modifican en V.

Para hacerlo:

```C++
for(auto & x : v){
		///código.
}
```

Podemos hacer lo mismo con un set:

```C++
///x pasa por valor, sin referencia
for(auto x : S){ ///donde x es la variable iterable y S es un set.
		///código.
}
///x pasa por valor con referencia.
for(auto &x : S){ ///donde x es la variable iterable y S es un set.
		///código.
}
```

For de Rango: Se puede hacer con sets, vectores, etc. Dos opciones.

Con tipo de dato.

For(TipoDato variable : vector)

Cout<<x.valor1<<x.valor2<<x.valor3, etc.

Con auto:

For(auto variable : vector)

Cout<<x.valor1<<x.valor2<<x.valor3, etc.

Si agregamos un "&" al nombre ("&nombre"), no se crea una copia del valor, sino que directamente se muestra.

Si no ponemos el "&" se crea una copia

---

En el caso de un mapa, los elementos están ordenados según su llave, de manera creciente. Al iterar vamos a recibir un pair, con la llave correspondiente y el valor asociado.

Entonces:

for(auto x : M){

///Código.

}

En este caso, x.first es el la llave o key, y x.second el valor. Lo podemos pasar por referencia o no, según convenga

---

Map: se podría usar para asignar valores numéricos a strings, por ejemplo: DNIs a Personas.

Set: puede ser que se use para calcular cuánta plata le debemos a un proveedor a fin de mes, si durante ese mes le pagamos más de una vez.