
---
# HashMap

Un HashMap nos permite mapear dos valores, por ejemplo podemos asignar un username a un ID, así mismo es posible mapear diferentes tipos de valores como string a integer, etc. En un mapeo vamos a tener dos valores, uno es la clave o key y el segundo es el valor o value. `key/value`

Para poder usa los maps es necesario importar una librería llamada HashMap

```java
import java.util.HashMap;

public class Maps{
	public static void main(String[] args){
		//Code here
	}
}
```

La forma en la que vamos a mapear la información es la siguiente, necesitamos un diamond operator o mejor conocido como pico paréntesis donde apuntemos el tipo de dato que queremos mapear, seguido del nombre de la variable y el argumento, es importante resaltar que los maps no funcionan con valores primitivos, únicamente acepta objetos: 

```java
import java.util.HashMap;

public class Maps{
	public static void main(String[] args){
		HashMap<String, Integer> empID = new HashMap<String, Integer>();
		/*
		A partir de java 7 en adelante no es necesario especificar el tipo de dato en el new HashMap, new HashMap<>();
		*/
	}
}
```

En nuestro código estamos mapeando String a Integers para mapear los nombres a sus respectivos ID's 

De momento el mapeo está vacío, en java el map es una interfaz donde indicaremos al mapeo que tipo de métodos queremos soportar y el HashMap es la implementación misma ya que existen varios tipos de implementación del Map como lo es el Map, HashMap, TreeMap, etc.

Ahora, para agregar un valor a nuestro HashMap tenemos que hacer lo siguiente, vamos a usar el método put, seguido de los valores que declaramos en el HashMap, en este caso un String y un Integer: 

```java
empID.put("Usuario", 1234);
```

```java
import java.util.HashMap;

public class Maps{
	public static void main(String[] args){
		HashMap<String, Integer> empID = new HashMap<String, Integer>();
		
		empID.put("Usuario1", 1);
		empID.put("Usuario2", 12);
		empID.put("Usuario3", 123);
		
	}
}
```

Para visualizar nuestro HashMap podemos hacerlo con un print apuntando al valor `empID` y así podemos ver la clave o key apuntando a nuestro valor:

```java
import java.util.HashMap;

public class Maps{
	public static void main(String[] args){
		HashMap<String, Integer> empID = new HashMap<String, Integer>();
		
		empID.put("Usuario1", 1);
		empID.put("Usuario2", 12);
		empID.put("Usuario3", 123);
		
		System.out.println(empID);
		
	}
}
```

Una cosa a destacar es que no se imprime en un orden específico si no que únicamente se utiliza para almacenar nuestros valores, una forma en la que podemos extraer datos de manera más específica es la siguiente, donde pasaremos el método get junto con el valor clave, así mismo podemos pasarlo a un print para poder visualizar el resultado:

```java
import java.util.HashMap;

public class Maps{
	public static void main(String[] args){
		HashMap<String, Integer> empID = new HashMap<String, Integer>();
		
		empID.put("Usuario1", 1);
		empID.put("Usuario2", 12);
		empID.put("Usuario3", 123);
		
		System.out.println(empID);
		System.out.println(empID.get("Usuario1"));
		
	}
}
```

Ahora, los métodos get y put no son los únicos que podemos utilizar, también podemos validar la existencia de datos y usar otros métodos como por ejemplo `containsKey` o `containsValue` lo que nos daría como resultado un valor de tipo True o False:

```java
System.out.println(empID.containsKey("Usuario1"));
System.out.println(empID.containsValue(2));
```

Otro punto a destacar es que si el valor clave ya existe y nosotros utilizamos nuevamente el método put, este se va a sobrescribir remplazando el valor original por el valor actualizado, si anteriormente el `Usuario1` vale `1` y utilizamos el put nuevamente al `Usuario1` su valor cambiara a el valor que deseamos:

```java
import java.util.HashMap;

public class Maps{
	public static void main(String[] args){
		HashMap<String, Integer> empID = new HashMap<String, Integer>();
		
		empID.put("Usuario1", 1);
		empID.put("Usuario2", 12);
		empID.put("Usuario3", 123);
		
		System.out.println(empID);
		System.out.println(empID.get("Usuario1"));
		
		empID.put("Usuario1", 2);
		System.out.println(empID);
		
	}
}
```

Otro método que podemos utilizar es el `replace`, la diferencia entre `put` y `replace` es que si la llave existe el valor se va a remplazar en ambos casos, si la llave no existe el `replace` no va a crear el valor por lo que nuestra función no va a realizar ninguna acción mientras que el método `put` si nos va a crear el nuevo valor.

Por otro lado también existe el método `putIfAbsent` donde en caso de que el valor no exista si va a crear el nuevo valor, pero si el valor existe, no va a crear nada, por otro lado el `remove` va a eliminar el valor que nosotros le asignemos:

```java
empID.putIfAbsent("Usuario1", 1);
empID.remove("Usuario1");
```

---
# HashSet

Un set es una forma de agrupar objetos y manejarlos como una unidad, podemos agregar objetos, quitarlos, y funciona de una manera similar a lo que sería un array pero con sutiles diferencias.

El nombre HashSet se la otorga debido a que se utiliza una tabla Hash como método de almacenamiento, lo que nos da como ventaja una constante de tiempo, sin importar el largo de nuestro HashSet el tiempo que le va a tomar remover, agregar, validar existencia, etc, va a ser siempre el mismo.

Un set es una interfaz, no una clase por lo que no podemos crear instancias de una interfaz, así que para crear un set lo haremos de la misma manera en la que trabajamos el Map, con un Hash, en este caso será un HashSet:  

```java
import java.util.Set;

public class Sets{
	public static void main(String[] args){
		
		Set<String> nombres = new HashSet<>();
		
	}
}
```

Para agregar valores a nuestro set lo haremos con el método add:

```java
import java.util.Set;

public class Sets{
	public static void main(String[] args){
		
		Set<String> nombres = new HashSet<>();
		
		nombres.add("Usuario1");
		nombres.add("Usuario2");
		nombres.add("Usuario3");
		
		System.out.println(nombres);
		
	}
}
```

Podemos notar que al imprimir el resultado no tienen un orden especifico a diferencia de una lista, así como tampoco podemos agregar mas de un valor en el método add, si no que tenemos que agregarlos uno por uno.

Un set no nos permite agregar duplicados, para remover valores lo haremos con el método `remove`, a diferencia de una lista nosotros no podemos eliminar datos de un HashSet según su índex ya que no tienen un orden específico:

```java
import java.util.Set;

public class Sets{
	public static void main(String[] args){
		
		Set<String> nombres = new HashSet<>();
		
		nombres.add("Usuario1");
		nombres.add("Usuario1");
		nombres.add("Usuario1");
		System.out.println(nombres);
		
		nombres.remove("Usuario1");
		System.out.println(nombres);
	}
}
```

```java
size //Nos indica el tamaño del set
contains //Nos indica si contiene valor 
isEmpty //Nos indica si el set está vacio
clear //Nos permite limpiar el set sin necesidad de ir uno por uno
```

Podemos iterar en bucle por cada uno de los valores almacenados dentro de nuestro set de la siguiente manera:

```java
import java.util.Set;

public class Sets{
	public static void main(String[] args){
		
		Set<String> nombres = new HashSet<>();
		
		nombres.add("Usuario1");
		nombres.add("Usuario1");
		nombres.add("Usuario1");
		
		for (String nombre : nombres){
			System.out.println(nombre);
		}
	}
}
```

Esto se pone interesante cuando sabemos utilizar lambdas en Java ya que podemos iterar por cada objeto en nuestro HashSet haciendo que por cada valor se ejecute la función de la lambda, por ejemplo:

```java
import java.util.Set;

public class Sets{
	public static void main(String[] args){
		
		Set<String> nombres = new HashSet<>();
		
		nombres.add("Usuario1");
		nombres.add("Usuario1");
		nombres.add("Usuario1");
		
		nombres.forEach(System.out::println);
		
	}	
}
```

Algo que podemos ejecutar es un iterador donde mientras haya contenido en nuestro HashSet pasaremos a leer el siguiente valor, para esto necesitamos crear un nuevo iterador:

```java
import java.util.Set;

public class Sets{
	public static void main(String[] args){
	
		Set<String> nombres = new HashSet<>();
		
		nombres.add("Usuario1");
		nombres.add("Usuario1");
		nombres.add("Usuario1");
		
		Iterator<String> Iterador = nombres.iterator();
		white (Iterador.hasNext()){
			System.out.println(Iterador.next());
		}
	}
}
```

Una de las ventajas y utilidades que le podemos dar a los Set's es cuando tenemos una lista con muchos valores duplicados y queremos deshacernos de ellos, un Set no nos permite tener valores duplicados por lo que dumpear esa lista en un Set se encargará de únicamente dejarnos con el valor que queremos sin duplicar. Una forma de realizar lo anterior es de la siguiente manera: 

```java
import java.util.Set;

public class Sets{
	public static void main(String[] args){
		
		List<Integer> numeros = new ArrayList<>();
		numeros.add(1);
		numeros.add(2);
		numeros.add(3);
		numeros.add(3);
		numeros.add(2);
		numeros.add(1);
		System.out.println(numeros);
		
		Set<Integer> setNumeros = new HashSet<>();
		setNumeros.addAll(numeros);
		System.out.println(setNumeros);
		
	}
}
```

Una forma aun más simplificada de dumpear la lista es pasando directamente en el constructor la lista:

```java
		List<Integer> numeros = new ArrayList<>();
		numeros.add(1);
		numeros.add(2);
		numeros.add(3);
		numeros.add(3);
		numeros.add(2);
		numeros.add(1);
		
		Set<Integer> setNumeros = new HashSet<>(numeros);
		System.out.println(setNumeros);
		
	}
}
```

Existen otros tipos de Set como lo puede ser el TreeSet, todo lo que vimos anteriormente funciona exactamente igual que en un HashSet con la diferencia de que los datos no se almacenan en una tabla Hash si no que lo hacen en un árbol por lo que los datos se ordenan de manera numérica o alfabética, la desventaja comparada con el HashSet es que un TreeSet toma mayor tiempo de ejecución por lo que con largas cantidades de datos nos serás más tardado y pesado de ejecutar.

Un LinkedHashSet no nos mantiene un orden alfabético pero si nos mantiene el orden en el que fuimos implementando los datos, es bastante más rápido que el TreeSet sin embargo más lento y pesado que el HashSet
