# Taller2Jonathan
Se ingresa el código del  diseño de patrones MVC

Código del Modelo 
class Banda(): # declaracion de las clases que interactuaran en el controlador y las vistas 
   # Clase Banda

    def __init__(self,Genero,nombre):
      
        self.Genero=Genero
        self.nombre=nombre
        print(" Genero {} / Nombre {}".format(self.Genero, self.nombre))


class Musico():

    def __init_(self, instrumento, nombre):
        self.instrumento=instrumento
        self.nombre =nombre
        print("Instrumento {} / Nombre {} ".format(self.instrumento,self.nombre))


class Festival():
    def __init_(self, nombre, fecha):
        self.nombre=nombre
        self.fecha=fecha
        print("nombre {} / fecha {} ".format(self.nombre,self.fecha))
-----------------------------------------------------------------------------------------------------------------------

Código de la vista 

""" En este modulo se declaran todos los métodos y funciones que se veran en la terminal una vez
    que se ejecute el programa por lo que se implementan unos métodos de diseño e impresion """
class Vista_Banda:

    def __init__(self):
        self.breakliner = "***********************"

    def welcome(self):
        print(self.breakliner+'\n'+"Bienvenido al Diseño de Patrones MVC ")
        print(self.breakliner+'\n'+ " Inserte la informacion ")

    def goodbye(self):
        print('\n'"Gracias por usar el programa  ")

    def ver_Banda(self, musicos):
        print(self.breakliner+'\n'+  musicos.Genero + musicos.nombre)
   
    def ver_Musicos(self, instrumentos):
        print(self.breakliner+'\n'+ instrumentos.instrumento + instrumentos.nombre)

    def ver_Festival(self, festival):
        print(self.breakliner+'\n'+ festival.nombre + festival.fecha)

    def mensaje(self,mensj):
        print(mensj+'\n')
        
   -----------------------------------------------------------------------------------------------------------
   Código del controlador 
   # Taller 2 Estudiante Jonnattan Gutierrez Aguero

from Modelo import Banda# dependencias de las librerias entre vista, modelo para ser manipuladas por controlador
from Modelo import Musico
from Modelo import Festival
from Vista import Vista_Banda

from os import system, name  # limpia la terminal

""" Para este módulo es donde se manipulan las declaraciones realizadas en vista y modelo
con el fin de crear listas, el menu de inicio y finalizacion, la captura de datos, el llamado 
de los métodos  para la impresion de datos y validaciones para  la ejecución correcta del
sistema"""

class Controlador:

    def __init__(self):
        # init construct
        self._lista_musicos = []  #creacion de las listas 
        self._lista_instrumentos =[]
        self._lista_Festival =[]
        self.Vista = Vista_Banda() # llama la vista 
        self.Vista.welcome() # mensaje de bienvenida


    def agrega_musicos(self,musicos): #Actualizaciones de listas 
        
        self._lista_musicos.append(musicos)
         

    def agrega_instrumentos(self,instrumentos): 
         
        self._lista_instrumentos.append(instrumentos)

    def agrega_festivales(self,festival): 
        
        self._lista_Festival.append(festival)
    

    def actualizar_vistaMusicos(self): 
        
        self.Vista.mensaje("LISTA DE MUSICOS: "+ str(len(self._lista_musicos))) 
    def actualizar_vistaInstrumentos(self): 
        self.Vista.mensaje("LISTA DE INsTRUMENTOS: "+ str(len(self._lista_Festival))) 
    def actualizar_vistaFestivales(self): 
        self.Vista.mensaje("LISTA DE FESTIVALES: "+ str(len(self._lista_Festival))) 

        if len(self._lista_musicos)==0: 
            self.Vista.mensaje("No se han ingresado datos aun!") 

        else: 
            for musicos in self._lista_musicos: 
                self.Vista.ver_Banda(musicos) 

    def stopProgram(self):# Método de despedida
        self.Vista.goodbye() 

    def cleanTerminal(self): #limpia la pantalla 
        
        if name == 'nt': 
            _ = system('cls') 
    
        else: 
            _ = system('clear') 


    def agregar(self): 
        
        try: # validacion de la informacion del menu  
            userInput = str(input("Desea agregar la informacion de la banda? Y/N")) 
            

            if userInput=='Y':
                _lista_musicos = input("Ingrese el genero  y el nombre separado por coma->Genero,Nombre Apellido [Sin espacios al inicio]: ").split(',') 
                musicoNuevo = Banda(_lista_musicos[0], _lista_musicos[1]) 
                
                _lista_instrumentos = input("Ingrese el Instrumento y el nombre: ").split(',')
                Instrumento_nuevo = Banda(_lista_instrumentos[0],_lista_instrumentos[1])
                self.agrega_musicos( musicoNuevo)

                
                
                self.agrega_instrumentos(Instrumento_nuevo)

                
               
        except:
            
            self.Vista.mensaje("Error en la entrada del usuario") 


    def run(self):# restricciones para el ingreso al ciclo repetitivo while
        
        corriendo = True
        userInput = None

        while corriendo == True: # Validaciones de datos  ciclo y manipulacion del menu
            try: 
                if userInput==None:
                    userInput = input("Y Para ver la lista,Para  continuar/N para salir /O Mas opciones : ")
                if userInput == 'Y':
                    self.actualizar_vistaMusicos() 
                    self.actualizar_vistaInstrumentos()
                
                    userInput = input("Y to display list and continue /N to exit /O for more options: ")
                elif userInput=='N':
                    self.stopProgram()
                    corriendo=False
                else:
                    self.agregar() 
                    self.actualizar_vistaMusicos() 
                    
                    self.Vista.mensaje("Gracias por utilizar -- Re-starting.../// (...loading...)")
                    userInput = input("Desea volver a utilizarlo? Y to continue /N to exit: ")
                    self.cleanTerminal()
            except:
                self.Vista.mensaje("Error en la entrada del usuario")


# metodo principal
if __name__=="__main__":
    control= Controlador()
    control.run()
                    
