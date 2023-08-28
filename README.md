# facilidades
##UNIVERSIDAD CENTRAL DEL ECUADOR##
# Integrantes: Cholango Kevin, José Luis De la Cruz.
# Docentes: Ing. Atahualpa Mantilla, Ing. Bryan Salazar.
#Tema: Concentraciones.

         # Generación del código.
#Llamamos a la librería numpy para realizar cálculos lógicos y matemáticos para las concentraciones.
import numpy as np

#programamos para ingresar todos lo datos requeridos en las concentraciones.
BFPD=int(input('Ingrese la cantidad del fluido en barriles : '))
BOPD=int(input('Ingrese la cantidad del petróleo en barriles: '))
BWPD=int(input('Ingrese la cantidad del agua en barriles: '))
BIOCIDA=int(input('Ingrese los galones de biocida: '))
h=int(input('Ingrese las horas de bombeo de biocida: '))
m=float(input('Ingrese los metros de distancia del WellPad al CPF: '))
d=float(input('Ingrese las pulgadas de diámetro de la tubería: '))

#Calcular la concentración de biosida
GWPH=((BWPD/24*h)*42)+BIOCIDA
cb=1000000*30/GWPH

#Calcular el tiempo de llegada del PIG si la producción total se duplica.
h2=(((d/12/2)**2*np.pi*m*3.28/(2*BFPD*5.61))*24)*60

#Calcular los galones por día que se deben de inyectar.
GWPD=BWPD*42
gdasc=GWPD*30/(1000000-30)

#Impresión de resultados con los datos calculados.
print(f'El biocida tiene un concentración de: {cb:0.4f} ppm')
print(f'El PIG llega en un tiempo de: {h2:0.4f} min')
print(f'El antiescal tiene una inyección de: {gdasc:0.4f} gal/día'
