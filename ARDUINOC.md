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

* Una proposición es una instrucción completa en C.
* Todas las proposiciones terminan con punto y coma (;)

```c
i = 50;
i++ ;
print(...);
```






    

    
  

















