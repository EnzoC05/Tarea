import os
import time

class Persona:
    def __init__(self, nombre, edad, direccion):
        self.nombre = nombre
        self.edad = edad
        self.direccion = direccion 

    def saludar(self):
        print(f"Hola, mi nombre es: {self.nombre}")
        time.sleep(2.5)
    
    def comer(self, hora):
        if 7 < hora < 10:
            print("¡Hora del desayuno!")
        elif 12 < hora < 15:
            print("¡Hora del almuerzo!")
        elif 19 < hora < 21:
            print("¡Hora de la cena!")
        else:
            print(f"{self.nombre} no tiene hambre")
        time.sleep(2.5)

def menu():
    print("¿Qué hará Enzo?: ")
    print("1. Saludar")
    print("2. Comer")
    print("3. No hacer nada (Salir)")

def obtener_hora():
    while True:
        hora = float(input("Ingrese la hora (Formato HH.MM por ejemplo 20.02): "))
        if 0 <= hora <= 24:
            return hora
        else:
            print("Hora inválida, intente de nuevo.")

Enzo = Persona("Enzo", 19, "Calle Padre Olivares")

while True:
    os.system("cls" if os.name == "nt" else "clear")  # Limpiar pantalla según el sistema operativo
    menu()
    
    eleccion = int(input("Elija una opción (1/2/3): "))
    
    if eleccion == 1:
        Enzo.saludar()
    elif eleccion == 2:
        hora = obtener_hora()
        Enzo.comer(hora)
    else:
        print("No hará nada")
        break
