# tarea6-
En esta actividad debe realizar lo siguiente:   Crear un módulo alelos.py con las tres funciones de "Creación de la población", "Cuantificación de frecuencias de alelos" y "Creación de la población hijo". Cada función debe tener una sección de explicación de lo que hace, la explicación de las variables de entrrada y salida. Crear un Júpiter Notebook tarea6_alelos.ipynb, cargar el módulo alelos y ejecutar las funciones hasta obtener la generación 100. Asegurarse que este cuaderno de jupyter tenga sus datos personales, texto de explicación del ejercicio y de los resultados. Inserte al menos una imagen (logo de Ikiam). Asegurarse que el cuaderno tiene los resultados de ejecución de los bloques de código. Crear un repositorio en GitHub de nombre tarea6 y guardar los dos archivos de la tarea. El repositorio debe tener una Readme con los detalles de la actividad. Pegar el enlace del repositorio en la actividad T6_alelos de Moodle

#! /bin/bash
importar scipy # para números aleatorios

def construir_población(N, p):
    " " " cada cromosoma tiene un alelo y N es el numero de individuos
    " " "
   # En esta funcion se estan creando tuplas con la lista de los alelos A ya segun el numero de individuos
    población = []
    for  i  in range(N):    # se crea un bucle for casual con las variables ay A, para ir agregando alelos aleatorios
                         # al final de cada alelo ao A en construir poblacion
        alelo1 = " A "   
        if  scipy.random.rand () > p: # la probabilidad de tener alelos ay A debe ser mayor a 0.43
            alelo1 = " a "
        alelo2 = " A "
        si  scipy.random.rand () > p:
            alelo2 = " a "
        población.append (( alelo 1 , alelo 2 ))
    población de retorno

build_population(N = 25, p = 0.43) # para 25 individuos con probabilidad de 0.43, devolver la poblacion con alelos Aay aA al azar

# FUNCIÓN 2. Conteo de pares de alelos
def computar_frecuencias(población):
    # Cuenta los genotipos y devuelve un diccionario de frecuencias genotípicas según los alelos que haya
    AA = población.recuento (( "A" , "A" ))
    Aa = población.recuento (( "A" , "a" ))
    aA = población.recuento (( "a" , "A" ))
    aa = población.recuento (( "a" , "a" ))
    return({ " AA " : AA, " aa " : aa, " Aa " : Aa, " aA " : aA}) # forma el diccionario
my_pop = build_population(500, 0.21)
fmy_pop = compute_frequencies(my_pop) # ver las frecuencias de los alelos aleatorios creados en la funcion 1
imprimir (fmy_pop)
print (( 500 - fmy_pop["aa"]) / 500 ) #ver la cantidad de aa en una poblacion de 500
# FUNCIÓN 3 . Creacion de nueva poblacion
def reproducir_población(población):
    #Para cada N producir una nueva generacion al azar
    nueva_generacion = []
    N = len(población)
    para i en el rango (N):
        # entero aleatorio entre 0 y N- 1
        dad = scipy.random.randint(N) #recibe cromosoma de papa
        mom = scipy.random.randint(N) #recibe cromosa de mama
        #ver que cromosoma viene de mama
        chr_mom = scipy.random.randint( 2 )
        descendencia = (poblacion[mama][chr_mom], poblacion[papa][ 1 - chr_mom]) #ver la descendencia entre mama y papa
        #si descendencia == ("a", "a"):
          #Siguiente()
        new_generation.append(offspring) #ir creando las nuevas generaciones al final de cada cromosoma
    volver nueva_generación
imprimir (compute_frequencies (my_pop ))
new_pop = reproducir_population(my_pop) # ver la nueva reproduccion en cada individuo, segun los alelos generados de mama y papa
new_pop2 = reproducir_población(new_pop)
imprimir (compute_frequencies (new_pop))
imprimir (compute_frequencies (new_pop2))
