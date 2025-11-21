# Proyecto Sistemas Operativos

## Problema
Desarrollar un programa en C que procese en paralelo
un conjunto de transacciones simuladas utilizando hilos 
(`pthread`), midiendo los tiempos de ejecución por 
transacción y total, comparando con un procesamiento 
secuencial, y aplicando mecanismos de sincronización 
para evitar condiciones de carrera.

El objetivo es simular un conjunto de transacciones 
reales (como procesamiento de archivos o cálculos 
independientes) y analizar el rendimiento del 
paralelismo.

## Procedimiento de ejecución
# Abrir terminal en Ubuntu
cd src

# Compilar el programa
gcc -pthread main.c -o main

# Ejecutar el programa
./main

# El programa mostrará en la consola:
# - Líneas procesadas por cada hilo.
# - Tiempo total de ejecución paralelo.
# - Tiempo de ejecución secuencial.
# - Speedup obtenido.

## Resultados de ejecución

### Salida de consola
===== PROCESAMIENTO PARALELO =====
Hilo 0 procesó archivo1.txt -> 30 líneas en 0.0000 s
Hilo 1 procesó archivo2.txt -> 30 líneas en 0.0000 s
Hilo 2 procesó archivo3.txt -> 30 líneas en 0.0000 s
Hilo 3 procesó archivo4.txt -> 30 líneas en 0.0000 s

Total líneas PARALELO: 120
Tiempo total paralelo: 0.0046 s
Suma de tiempos individuales: 0.0001 s

===== PROCESAMIENTO SECUENCIAL =====
[Secuencial] Archivo archivo1.txt -> 30 líneas
[Secuencial] Archivo archivo2.txt -> 30 líneas
[Secuencial] Archivo archivo3.txt -> 30 líneas
[Secuencial] Archivo archivo4.txt -> 30 líneas

Total líneas SECUENCIAL: 120
Tiempo total secuencial: 0.0005 s

========== COMPARACIÓN ==========
Paralelo:    0.0046 s
Secuencial:  0.0005 s
Speedup:     0.1025 x
==================================


### Imagen de resultados
![Resultado de la ejecución](resultados/ejecucion.png)

## Observaciones
- Los archivos `archivo1.txt` a `archivo4.txt` contienen
-  transacciones simuladas (líneas de texto).  
- Cada hilo procesa un archivo y cuenta las transacciones,
-  simulando procesamiento concurrente.  
- Se utilizó un mutex para sincronizar el acceso a las
- variables compartidas (`lineas_totales_paralelo` y `
- tiempo_total_hilos`).  
- Se observó un **speedup menor a 1**, lo cual es razonable
-  debido a que el procesamiento por línea es muy rápido y
-  el overhead de creación de hilos domina.  

## Conclusión
El programa cumple con los objetivos del proyecto:
- Procesamiento paralelo con hilos.
- Sincronización correcta.
- Medición y comparación de tiempos de ejecución.
- Simulación de un conjunto de transacciones.

El repositorio está listo para ser revisado y presentado.
