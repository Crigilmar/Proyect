# Proyecto del Primer Cuatrimestre Fundamentos de Programación (Curso 21-22 )
Cristian Daniel Gil Martin Crigilmar



Personas desaparecidas en India :
Son datos de gente desaprecida , con fecha , sexo , nombre 



## Estructura de las carpetas del proyecto
CARPETA SCR : 
MODULO 1 : ESTAN LAS INSTRUCCIONES DONDE LEE EL ARCHIVO , LO CONVIERTE A TUPLA 
MODULO TEST : EN TEST TINE LOS ARCHIVOS EJECUTABLE PARA EJECUTAR LOS CODIGOS
    
## Estructura del *dataset*

EL DATASET : CLEANDATA.CSV TIENE 12 COLUMNAS CADA UNA TIENE SU PROPOSITO : 

Name: Nombre de los desaparecidos

Gender : sexo de los desaparecidos

Relative :posibles nombres de los desaparecidos

Address: Dirreccion de los desaparecidos

AgeStart : Minimo de edad que podrian tener cuando desaparecieron

AgeEnd: Minimo de edad que podrian tener cuando desaparecieron


Built :Cuerpo fisico 

Dist : ? 

State : Estado donde desaparecieron

## Tipos implementados

C = namedtuple('C','Name,Gender,Relative,Address,AgeStart,AgeEnd,HeightStart,HeightEnd,Built,Date,Dist,State')

guardar los datos en C (me gusta guardarlos con letras matusculas para encontrarlos mas rapido )

## Funciones implementadas
Añade aquí descripciones genéricas de las funciones, que luego debes acompañar con comentarios de tipo documentación en el código

### \<modulo 1\>

import csv
from collections import namedtuple

C = namedtuple('C','Name,Gender,Relative,Address,AgeStart,AgeEnd,HeightStart,HeightEnd,Built,Date,Dist,State')

clean = '..\data\cleandata.csv'

with open(clean, encoding='utf-8') as f:
    lector = csv.reader(f)
    next(lector)
    Co2 = [(Name, Gender, Relative, Address, int(AgeStart), int(AgeEnd),HeightStart,HeightEnd,Built,Date,Dist,State)
           for Name, Gender, Relative, Address, AgeStart,AgeEnd,HeightStart,HeightEnd,Built,Date,Dist,State in lector]

def imprimir_total(file):
    print('\n' "total de registro que tiene el archivo : ", len(Co2), '\n')

def imprimir_3p(file):
    print("los 3 primeros son: ", Co2[:3], '\n')

def imprimir_ul(file):
    print("los 3 ultimos son : ", Co2[-3:])
    
    abre el csv lo convierte a tupla y despues puede ejecutar 3 codigos : el total de los datos , los 3 primeros , o los 3 ultimos 

### \<test modulo test\>
from modulo1 import *
Titulo = "PROYECTO 1 "

inicio = int(input("ELEGIJA LO QUE QUIERE HACER : "
               "1)IMPRIMIR CUANTOS DATOS HAY EN TOTAL"
               "2)LOS PRIMEROS 3 REGISTROS"
               "3)LSO ULTIMOS 3 REGISTROS : "))
if inicio == 1:
    imprimir_total(Co2)
elif inicio == 2:
    imprimir_3p(Co2)

elif inicio == 3:
    imprimir_ul(Co2)
else:
    print("solo hay 3 opciones")

mini interfaz donde el ususario puede elegir que quiere hacer 

