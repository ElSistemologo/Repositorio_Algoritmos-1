## Tabla de Contenido
1. [Información del proyecto]
2. [Cálculo de complejidad]

## Información del proyecto
***
Laboratorio 4
Algoritmos
Integrantes:
	Camilo Andres Fierro Fierro
	Cristian Camilo Vargas Morales
	Fabian Leandro Lopez Gomez
	Isaac Zarate Reyes
	Jose Ignacio Suarez Montiel


## Cálculo de complejidad
***
Para algoritmo de fuerza bruta:

# El algoritmo presenta una complejidad de O(n^2) (orden dado para el peor de los casos teniendo en cuenta que el while no solo recorre una si no dos variables ‘x’ y ‘y’)
x=-1000  #O(1) 
def brute_force(x):
    while x <= 1000:   #O(n) ->  orden para bucle  (iteración de x)
        y=(x**5 - 59*(x**4) + 35*(x**3) - 250*(x**2) + x - 70)  #O(n) -> orden para bucle (iteración de y)
        if y >= -40 and y<= 40:   #O(1) -> orden para condicional                                   
            print("la raiz es: {0:.6f}".format(x))
            return           
        x+=0.00001    
brute_force(x)           


Para el algoritmo voraz:
#algoritmo Voraz
def recursionb(a,b):      
    r = (a+b)/2                         
#   if abs(58.47456-r) <= 0.0001:       
#   #Esta sentencia era otra forma de encontrar la raíz por cercanía a la raíz ya conocida, pero la nueva forma tiene más sentido al buscar la cercanía al cero.
#     return r                  
#   else:                               
    y = (a**5 - 59*(a**4) + 35*(a**3) - 250*(a**2) + a - 70)*(r**5 - 59*(r**4) + 35*(r**3) - 250*(r**2) + r - 70)     
    #Se define la ecuación con "a" como la incognita "x" multiplicado por la misma ecuación pero esta vez la incognita se reemplaza con "r"
    if y >= -0.0001 and y<= 0.0001:                
      return r                  
    elif y < 0:               
      return recursionb(a,r)     
    else:                     
      return recursionb(r,b)     

def biseccion(a, b):         
  y = (a**5 - 59*(a**4) + 35*(a**3) - 250*(a**2) + a - 70)*(b**5 - 59*(b**4) + 35*(b**3) - 250*(b**2) + b - 70)   
  if y < 0:                   
    return recursionb(a,b)      
  else:                       
    return "No raíz"                  
    
a = -1000
b = 1000
r = biseccion(a,b)      
print("la raiz es: {0:.6f}".format(r))

Debido al analisis del comportamiento del arbol de recursión se llega a la conclusión de que el  comportamiento es de orden O(N(log(N))
