# Tipos y scopes de variables en GOLANG

En GOLANG existen tres tipos de variables:
- Variables numéricas (int)
- Variables de tipo String (string)
- Variables de tipo boolean (bool)

Cada uno de los tipos anteriores se dividen en varios grupos, por ejemplo las variables numéricas se dividen en:
- Enteros (int, int8, int16, int32, int64)
- Enteros sin signo (uint, uint8, uint16, uint32, uint64)
- flotantes (float32, float64)

GOLANG es un lenguaje tipado, esto quiere decir que al declarar una variable tenemos que indicar de que tipo es.

#¿Cómo declaramos una variable?

Las podemos declarar fuera de funciones (se puede usar en todas las funciones que pertenecen al paquete) y dentro de funciones (sólo se puede usar dentro de usa función).

Podemos declarar las variables usando la palabra reservada "var":
```var numero int```
```var texto string```
```var booleano bool```

declararlas con var y asignarle un valor:
```var booleano bool = true```

O asignandoles un valor sin usar "var" ni indicar el tipo (en base al valor GOLANG detecta que es un entero):
```numero := 4```

También me permite declarar y asignarle un valor a diferentes variables en la misma línea (incluso si las variables son de distinto tipo):
```numero2, numero3, texto2 :2, 3, "texto"```

Cuando declaramos una variable en GOLANG, sea del tipo que sea, las inicializa:
- variables de tipo entero = 0
- variables de tipo string = ""
- variables de tipo booleano = false

#¿Cómo podemos declarar variables y funciones para que se pueda acceder a ellas desde otro paquete?

Para poder acceder a variables y funciones desde otro paquete basta con poner la primera letra en mayúscula, por ejemplo:

```var Numero int```

```func MostrarNumero()  {}```

#¿Cómo podemos convertir de un tipo de variable a otro?

GOLANG no permite hacer conversiones de forma explícita, por ejemplo si tengo una variable de tipo float32 ```var numero1 float32 = 1``` y otra de tipo int ```var numero2 int = 1``` no puedo convertir numero1 a int de esta forma ```numero2 = numero1```, tendría que hacer lo siguiente ```numero2 = int(numero1)```.

Si quiero convertir el número entero  ```var numero int = 1``` a string tendría que hacer lo siguiente: ```var texto = fmt.Sprintf("%d", numero)```. La función "Sprintf" del paquete "fmt" convierte todo a texto, hay que indicarle cual es el tipo de parámetro que voy a pasarle, en el caso de nuestro ejemplo es "%d".

Hay un paquete que se llama "strconv" que tiene muchas funciones para conversiones, por ejemplo podríamos convertir el entero ```var numero int = 1``` a string ```var texto = strconv.Itoa(numero)```. La función "Itoa" sólo acepta valores de tipo int, si tuvieramos ```var numero float32 = 1``` tendriamos que convertir primero la variable de tipo float32 a int ```var texto = strconv.Itoa(int(numero))``.




