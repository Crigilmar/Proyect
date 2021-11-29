# Proyecto del Primer Cuatrimestre Fundamentos de Programacion (Curso 21-22 )
Cristian Daniel Gil Martin 

UVUS : Crigilmar



## Estructura de las carpetas del proyecto
CARPETA SCR : 
Desaparecidos:Tiene las funciones 
TestDesaparecidos:Tiene las funciones para imprimir las funciones de Desaparecidos
    
## Estructura del *dataset*

EL DATASET : DESAPARECIDOS_INDIA_2018_220.CSV TIENE 9 COLUMNAS CADA UNA TIENE SU PROPOSITO : 

Tipo_de_sangre: Los tipos de sangre que Existen
Nombres: Nombre de los desaparecidos

Genero : sexo de los desaparecidos

Cuerpo: aspecto fisico de los desaparecidos

Distrito: Distrito donde Desaparecieron

DENUNCIADO : si fue denunciado

Estatura: cuanto miden los desaparecidos

Edad: Edad de los desaparecidos

Cuando_Desparecio : Fecha de los desaparecidos


## Tipos implementados

import csv

from collections import namedtuple







Almacenamiento_de_datos = namedtuple('Almacenamiento_de_datos','Tipo_de_sangre,Nombres,Genero,Cuerpo,Distrito,'
                                                           'DENUNCIADO,Estatura,Edad,Cuando_Desparecio')




def abrir_csv (Doc):

    with open(Doc, encoding='utf-8') as f:
    
        lector = csv.reader(f)
        
        next(lector)
        
        contenido = [Almacenamiento_de_datos(Tipo_de_sangre, Nombres, Genero, Cuerpo, Distrito, DENUNCIADO,
                                              float(Estatura), int(Edad), Cuando_Desparecio) for Tipo_de_sangre, Nombres,Genero, Cuerpo, Distrito,DENUNCIADO, Estatura, Edad,Cuando_Desparecio in lector]
                                              
        return contenido
        
"""
abre el archivo csv y lo almacena en un namedtuple ('Almacenamiento_de_datos',

'Tipo_de_sangre,Nombres,Genero,Cuerpo,Distrito,'DENUNCIADO,Estatura,Edad,Cuando_Desparecio')

ENTRADA: RUTA DEL ARCHIVO CSV 

@:param contenido :es la lista de tuplas donde se guarda las columnas de los archivos csv 

SALIDA : TUPLAS PARA ITERAR CON LOS DATOS DEL FICHERO.

@:type [str,str,str,str,str,str,float,int,str,]

"""


def Filtrar_Contenido (Doc): #filtrar contenido

    contenido1 = ("{}".format(s.Edad)for s in Doc)
    
    contenido2 = ("{}".format(s.Cuando_Desparecio) for s in Doc)
    
    Respuesta= print("EDADES:","{}".format(list(contenido1)))
    
    Respuesta_1 = print("FECHA DE DESAPARICION:","{}".format(list(contenido2)))
    
    return

"""
ENTRADA: Contenido 1 y 2 almacena las columnas para agregarlas en una tupla

@:param entran las columnas s.edad y s.Cuando_Desaparecio  

SALIDA : Respuesta , Respuesta_1 : imprimie una lista de todas los datos de edades y todos las fechas 

@:type Respuesta : Edad*1000 , Respuesta : (str)Fechas*1000

"""

def DISTRITO(Doc): #suma total

    contenido3 = {"{}".format(s.Distrito) for s in Doc}
    
    Respuesta_2 = print("TOTAL DE DISTRITOS :{}".format(len(contenido3)))
    
    return
"""
ENTRADA: Invocamos a s.Distrito y lo guardamos en un conjunto donde quita las variables repetidas

@:param {s.Distrito}

SALIDA : Respuesta 2 es el total de distritos que hay en el csv 

@:type Respuesta_2 : len{s.Distrito}



#bloque 2


def MAXEDAD(Doc): #Valor Maximo y Minimo

    C=set()
    
    for s in Doc:
    
        C.add(s.Edad)
        
    c=(min(C))
    
    d =(max(C))
    

    contenido4 = print("La edad minima es {} año y la maxima es {} años.".format(c,d))
    
    return contenido4
    

"""
ENTRADA: invocamos a s.Edad para que esté en un conjunto donde se elimina las variables repetidas

@:param c= set(S.Edad) == (-int,int,int,+int) 

SALIDA : contenido4 =

@:type contenido4 = {c(C=(min(s.edad)},{d(max(s.edad)}

"""





def EDADCONDI(Doc): #Lista por una propiedad

    C=[]
    
    for s in Doc:
    
        C.append(s.Nombres)
        
    if C != 'B' or 'M':
    
       z = C
       
    print("Nombres sin M o B: {}".format(z))
    
"""
ENTRADA: invocamos a s.Nombre por medio de una condicion hacemos que nos imprima lo que queremos

@:param s.Nombres !=  M o B:

SALIDA : se imprime un conjunto donde solo sale los nombres que no comienzan con M o B 

@:type C=[s.nombres]

"""



### \<test modulo test\>


# -*- coding: utf-8 -*-
from Desaparecidos import *

>Importe de Desaparecidos

def TestFiltro_nombres(fichero):

    print("\n""------------------NOMBRES DE LAS PERSONAS DESAPARECIDAS-------------" "\n")
    
    print((Filtrar_Contenido(fichero)))
    
#IMPRIME lo filtrado

def TestDistritos(fichero):

    print("------------------NUMERO DE DISTRITOS QUE HAY EN TOTAL------------------")
    
    print((DISTRITO(Doc)))
    
>imprime el numero total de distritos 

def TestMin(fichero):

    print("------------------CUAL ES LA EDAD MINIMA Y LA MAXIMA DE LOS DESAPARECIDOS?------------------ ")
    
    print(MAXEDAD(Doc))
    
>Imprime el maximo y el minimo de edad

def TestEDADCONDI(fichero):

    print("------------------NOMBRES QUE NO COMIENZEN CON B Y M------------------ ")
    
    print(EDADCONDI(Doc))

>filtra los nombres sin palabras que comienzan por B o M
>

Doc = abrir_csv('../data/DESAPARECIDOS_INDIA_2018_2020.csv')

> variable donde almacena el csv y llama la funcion abrir_csv para que se pueda leer
> 

TestFiltro_nombres(Doc)


TestDistritos(Doc)


print("\n","BLOQUE II","\n")

TestMin(Doc)

TestEDADCONDI(Doc)




