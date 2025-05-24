# RETO05
## Funciones.
Para cada punto cree un programa individual. Utilizando funciones:
---
### 1. Dado la figura de la imagen, desarrolle:
![image](https://github.com/user-attachments/assets/7d0e2a40-6459-430a-b6c1-3f963a4ce0a6)

   * Una función matemática para calcular el volumen y el área superficial, crar dos funciones en python para calcular los valores antes establecidos, al ingresar por teclado r1, r2 y h, usando import math y math.pi.
     
**Fórmulas del tronco de cono**

**Área superficial:**

A = π (r₁ + r₂) · √[(r₁ − r₂)² + h²] + π·r₁² + π·r₂²

**Volumen:**

V = (1/3) · π · h · (r₁² + r₁·r₂ + r₂²)    

**Funciones en python**
```
#función
import math
def volumen_cono(r1, r2, h):
    return (1/3) * math.pi * h * (r1**2 + r1 * r2 + r2**2)

def superficie_cono(r1, r2, h):
    generatriz = math.sqrt((r1 - r2)**2 + h**2)
    return math.pi * (r1 + r2) * generatriz + math.pi * r1**2 + math.pi * r2**2

#ingreso de datos por teclado
r1 = float(input("ingrese el radio mayor: "))
r2 = float(input("ingrese el radio menor: "))
h =float(input("ingrese la altura: "))

volumen = volumen_cono(r1, r2, h)
area = superficie_cono(r1, r2, h)

print("volumen del cono truncado: ", volumen)
print("area de superficie del cono truncado: ", area)
```
---
### 2. Dado la figura de la imagen, desarrolle:
   ![image](https://github.com/user-attachments/assets/fa691a72-89c2-4dd6-987f-c5cae76341e3)
   * Una función matemática para calcular el área y el perimetro, cree dos funciones en python para calcular los valores antes establecidos, al ingresar por teclado r, a y b, usando import math y math.pi  
     
**Fórmulas de la figura compuesta**

La figura está compuesta por un **rectángulo** y **dos círculos**.

**Área total:**

A = Área del rectángulo + Área de los dos círculos  
A = a · b + 2 · π · r²

**Perímetro total:**

P = 2 · a + b + 4 · π · r

**Función en python**
```
import math
def area_figura(r, a, b):
    area_rectangulo = a * b
    area_circulos = 2 * math.pi * r**2
    return area_rectangulo + area_circulos 

def perimetro_figura(r, a, b):
    return 2 * a + b + 4 * math.pi * r 

#entrada de datos por teclado
r = float(input("ingrese el radio de los circulos:"))
a = float(input("ingrese la altura del rectangulo:"))
b = float(input("ingrese la base del rectangulo:"))

area = area_figura(r, a, b)
perimetro = perimetro_figura(r, a, b)

#resultados
print("area de la figura es:", area)
print("perimetro de la figura es:", perimetro)
```
---
### 3. Diseñe una función que calcule la cantidad de carne de aves en kilos si se tienen N gallinas, M gallos y K pollitos cada uno pesando 6 kilos, 7 kilos y 1 kilo respectivamente.

**Funcion en python**
```
def calcular_cantisas_carne(n_gallinas, m_gallos, k_pollitos):
    peso_gallinas = 6
    peso_gallos = 7
    peso_pollitos = 1

    kilos_carne = (n_gallinas * peso_gallinas) + (m_gallos * peso_gallos) + (k_pollitos * peso_pollitos)
    return kilos_carne

#ingreso de datos por teclado
n = int(input("Ingrese el numero de gallinas: "))
m = int(input("Ingrese el numero de gallos: "))
k = int(input("Ingrese el numero de pollitos: "))

total_carne = calcular_cantisas_carne(n, m, k)

#resultado
print("La cantidad de carne de aves en kilos es:", total_carne)
```
---
### 4. Haga un programa que utilice una función para calcular el valor de un préstamo C usando interés compuesto del i por n meses.

**Función en python**
```
def calcular_prestamo(C, i, n):
    return C * (1 + i) ** n

#Ingreso de datos por teclado
capital = int(input("Ingrese el monto del prestamo : "))
intereses = float(input("Ingrese la taza de interés mensual (en decimal): "))
meses = int(input("Ingrese el numero de meses: "))

valor_final = calcular_prestamo(capital, intereses, meses)

#resultado
print("El valor final del préstamo es: ", valor_final)
```
---
### 5. Escriba un programa que pida 5 números reales y calcule las siguientes operaciones usando una función para cada una:
* El promedio
* El promedio multiplicativo (multilplica todos y luego calcula la raíz de la cantidad de operandos)
* La potencia del mayor número elevado al menor número
* La raíz cúbica del menor número
En este caso se usa una función principal. De esta manera:

**Función en python**
```
import math

#Promedio
def promedio(a: float, b: float, c: float, d: float, e: float) -> float:
    return (a + b + c + d + e) / 5
 
#promedio multiplicativo
def promedio_multiplicativo(a: float, b: float, c: float, d: float, e: float) -> float:
    producto = a * b * c * d * e
    return producto ** (1/5)

#La potencia del mayor número elevado al menor número
def potencia(a: float, b: float, c: float, d: float, e: float) -> float:
    nmayor = max(a, b, c, d)
    nmenor = min(a, b, c, d)
    return nmayor ** nmenor

#La raíz cúbica del menor número
def raiz_cubica(a: float, b: float, c: float, d: float, e: float) -> float:
    nmenor = min(a, b, c, d, e)
    return math.copysign(abs(nmenor) ** (1/3), nmenor)

if __name__ == "__main__":
    print("Ingrese 5 numeros reales:" )
    n1 = float(input("Número 1: "))
    n2 = float(input("Número 2: "))
    n3 = float(input("Número 3: "))
    n4 = float(input("Número 4: "))
    n5 = float(input("Número 5: "))

prom = promedio(n1, n2, n3, n4, n5)
prom_mult = promedio_multiplicativo(n1, n2, n3, n4, n5)
pot = potencia(n1, n2, n3, n4, n5)
raiz_cub = raiz_cubica(n1, n2, n3, n4, n5)

#resultados
print("Promedio: ", prom)
print("Promedio multiplicativo: ", prom_mult)
print("Mayor elevado al menor: ", pot)
print("Raíz cúbica del menor: ", raiz_cub)
```
---
### 6. Consultar qué es y cómo funciona pip en python.
    es el gestor de paquetes de Python. Permite instalar, actualizar y desinstalar paquetes de terceros que no vienen incluidos en Python por defecto. Es una herramienta esencial para trabajar con librerías como numpy, pandas, matplotlib, requests, etc.
---
### 7. Hacer un listado de módulos populares para python que se puedan instalar com pip y consultar cómo instalarlos.
    La manera de instalar todos a continuación es copiar ¨pip install modulo¨ 
    * Numpy: Sirve para operaciones y ecuaciones matemáticas. Su comando de instalación es ¨pip install Numpy¨
    * pandas: Manejo y análisis de datos en tablas. Su comando de instalación es ¨pip install pandas¨
    * matplotlib:	Crea gráficos como barras, líneas, pasteles, entre otras en 2D.	Su comando de instalación es ¨pip install matplotlib¨
    * requests: Sirve para hacer peticiones HTTP fácilmente (APIs, sitios web). Su comando de instalación es	¨pip install requests¨
    * scikit-learn:	Ofrece algoritmos de machine learning listos para usar. Su comando de instalación es	¨pip install scikit-learn¨
    Es posible instalarlos todos en una sola línea en tu terminal: ¨pip install numpy pandas matplotlib requests scikit-learn¨
---

Gracias...





     
