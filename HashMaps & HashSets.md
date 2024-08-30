
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

Un set es una interfaz, no una clase por lo que no podemos crear instancias de una interfaz, así que para crear un set lo haremos de la misma manera en la que trabajamos el Map, con un Hash, en este caso será un HashSet:  

```java
import java.util.Set;
public class Sets{
	public static void main(String[] args){
	
	Set<String> nombres = new HashSet<>();
	
	}
}
```

