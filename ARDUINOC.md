## ARDUINO C
## 2. TIPOS DE DATOS, OPERADORES Y EXPRESIONES
### 2.1 Variables

* Existen algunas restricciones en los nombres de las variables y de las constantes (las palabras clave estan reservadas, Ej: if, else, int, float, delay, etc)
* La practica tradicional del lenguaje C es usar letras minusculas para nombres de variables y mayusculas para constantes
* Es conveniente elegir nombres que esten relacionados con el próposito de la variable

### 2.2 Tipos y tamaño de datos (para la plataforma Arduino UNO)

| Tipo           | Longitud (byte)           | Rango |
|--------------- |:-----------------------:  | -----:|
| bool           | 1                         | True or False |
| char           | 1                         | -128 a +127 |
| unsigned char  | 1                         | 0 a 255     |
| byte           | 1                         | 0 a 255     |
| int            | 2                         | -32768 a 32767|
| unsigned int   | 2                         | 0 a 65535     |
| word           | 2                         | 0 a 65535     |
| short          | 2                         | -32768 a 32767|
| long           | 4                         | -2147483648 a 2147483647|
| unsigned long  | 4                         | 0 a 4294967295|
| float          | 4                         | -3.4028235E+38 a 3.4028235E|
| double         | 4                         | -3.4028235E+38 a 3.4028235E|
| string         |                           |          |
| String()       |                           |      |
| array          | 2                         | colección de variables a las que se accede con un número indice|
| void           | 0                         | Es un descriptor usado con funciones que no tienen un valor de salida. Indica que no se espera que la función devuelva información|


### 2.3 Constantes

#### Enteros

* Una constante entera como 123 es por defecto tratado como _int_
* Una constante long se escribe con una _l_ o _L_ terminal Ej: _123456789L_
* Una constante sin signo se escribe con una _u_ o _U_ terminal: Ej: _33u_
* Si queremos que sea long y sin signo se escribe con _ul_ o _UL_ terminal Ej: _32767ul_

El valor de un entero puede especificarse en otras bases (octal, hexadecimal y binaria)

| Base             | Ejemplo        | Formato |
|-----------       |:-------------- | ----------------:|
| 10 (decimal)     | 123            |                  |
| 2 (binaria)      | 0b1111011      | se antepone "0b" |
| 8 (octal)        | 0173           | se antepone "0"  |
| 16 (hexadecimal) | 0x7B           | se antepone "0x" |


#### Punto flotante

* Las constantes de punto flotante contienen un punto decimale o un exponente 
```c
float n = 0.007;   // 0.007 es una constante de punto flotante
float e = 2.34E5;  // 2.34E5 es equivalente a 2.34*10^5 = 234000
```

### 2.4 Declaraciones

Todas las vairables deben ser declaradas entes de uso

```c
int lower;   // declara la variable lower como entera
char c;      // decalara la variable c como char
```

Una variable puede ser inicializada en su declaración

```c
int i = 0;    // declara la variable i como entera y se inicializa con el valor 0
```

### 2.5 Operadores aritméticos

* Los operadores aritméticos son +, -, *, / y el operador módulo %
* La división entera trunca cualquier parte fraccionaria

### 2.6 Operadores de relación y lógicos

* Los operadores de relación son >, >=, <, >=, == y !=

### 2.7 Operadores de incremento y decremento

* El operador ++ agrega 1 a su operando
* El operador -- le resta 1 a su operando
* Los operadores de incremento y decremento pueden ser utilizados como prefijos (antes de la variable) o como postfijos (despues de la variable)
* La expresión ++n incrementa a n antes que su valor de utilice
* La expresión n++ incrementa a n después que su valor de utilice

### 2.8 Operadores para el manejo de bits

* El lenguaje C proporciona seis operadores para manejo de bits y solo pueden ser aplicados a operadores enteros (char, short, int, long con y sin signo)

    &    AND 
    |    OR 
    ^    XOR 
    <<   corrimiento a la izquierda
    >>   corrimiento a la derecha
    ~    NOT

## 3. Control del Flujo

* Las sentencias de un programa en C se ejecutan secuencialmente
* C dispone de varias sentencias para modificar este flujo secuencial: las bifurcaciones (permiten elegir entre dos o mas opciones segun cierdas condiciones) y los blucles (permiten ejecutar repetidamente un conjunto de instrucciones)


### 3.1 Proposiciones y bloques

* Una proposición es una instrucción completa en C.
* Todas las proposiciones terminan con punto y coma (;)

```c
i = 50;
i++ ;
print(...);
```

* Un bloque consiste en una agrupación de declaraciones y proposiciones. Se emplean llaves {} para agrupar.

### 3.2 If-else

* La proposición if-else se utiliza para expresar decisiones. La sintaxis es:
```c
if (expresión) {
    proposición1
else
    proposición2
    }
```
done la parte del else es optativa

* La expresión se evalua; si es verdadera (esto es si la expresión tiene un valor diferente de cero), la proposición1 se ejecuta. Si es falsa (expresión cero) y si existe una parte de else, la proposición 2 se ejecuta en su lugar.


### 3.3 Else-If

* La construcción a continuación es la forma mas general de construir una decisión multiple:
  
```c
if (expresión)
    proposición
else if (expresión)
    proposición
else if (expresión)
    proposición
else
    proposición
```

* Las expresiones se evaluan en orden; si cualquier expresión es verdadera, la proposición asociada se ejecuta, y esto termina toda la cadena. La parte del ultimo else maneja el caso de "ninguno de los anteriores" o caso por omisión cuando ninguna de las otras condiciones se satisface. En algunos casos no hay una acción explicita para la omisiñon y el else del final puede omitirse.

  

Ejemplo:

```c
if (temperature >= 70) {
      // Danger! Shut down the system.
    }
    else if (temperature >= 60) { // 60 <= temperature < 70
      // Warning! User attention required.
    }
    else { // temperature < 60
      // Safe! Continue usual tasks.
    }
```

### 3.4 Switch

Es una decisión multiple que prueba si una expresión coincide con un número de valores constantes enteros

Ejemplo:

```c
switch (expresion) {
      case label1:
        // statements
        break;
      case label2:
        // statements
        break;
      default:
        // statements
        break;
    }
```

* Se evalúa **expresion** y se considera  el resultado de dicha evaluación. Si coincide con el valor constante label1, se ejecutan las proposiciones correspondientes
* Si ninguna expresion coincide se ejecuta la proposición que esta s continuación de **default**
* La proposición **break** provoca una salida inmediata del switch

  



    

    
  

















