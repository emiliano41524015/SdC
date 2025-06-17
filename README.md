# SdC TP1

Armar una lista de benchmarks, ¿cuales les serían más útiles a cada uno ? ¿Cuáles podrían llegar a medir mejor las tareas que ustedes realizan a diario ? 

🔹 1. Benchmarks para CPU y Cómputo en General
Útil para:

Evaluar el rendimiento de procesamiento en tareas generales, cálculos intensivos y simulaciones.
Comparar la eficiencia entre diferentes procesadores.
Algunos ejemplos: 

  - AIDA64  
  - 7-Zip  
  - PCMark 
  
🔹 2. Benchmarks para Memoria RAM
Útil para:

Medir la velocidad de lectura/escritura y la latencia de la memoria RAM.

Algunos ejemplos:

  - AIDA64
  - Novabench

Ver cómo afecta la velocidad de la RAM al rendimiento del sistema.

🔹 3. Benchmarks para GPU (Cómputo y Gráficos)

Útil para:

Medir el rendimiento de la GPU en tareas gráficas y de cómputo paralelo.

Evaluar la capacidad de la GPU en Machine Learning, rendering y videojuegos.

Algunos ejemplos:

  - Cinebench R15
  - Unigine Heaven 
  - 3DMark

🔹 4. Benchmarks para Discos SSD/HDD

Útil para:

Medir la velocidad de lectura/escritura y la latencia del almacenamiento.

Evaluar el impacto del almacenamiento en el rendimiento del sistema.

Algunos ejemplos:

  - CrystalDisk Mark
  - NovaBench

🔹 5. Benchmarks para Redes y Servidores

Útil para:

Evaluar la velocidad de la red, latencia y rendimiento de servidores.

Comparar diferentes configuraciones de red.

Algunos ejemplos:

  - ApacheBench 
  - LoadRunner

🔹 6. Benchmarks para Bases de Datos
Útil para:

Evaluar el rendimiento de consultas SQL y bases de datos NoSQL.

Medir la latencia y throughput en bases de datos.

Algunos ejemplos:

  - TPC Benchmark
  - MySQL Benchmark Suite

-------------------------------------------------------------------------------------------------------------------------------------

Pensar en las tareas que cada uno realiza a diario y escribir en una tabla de dos entradas las tareas y que benchmark la representa mejor.

---------------------------------------------------------------------------------------------------------------------------------
## Benchmark Linux Kernel Compilation

Cual es el rendimiento de estos procesadores para compilar el kernel de linux ?
Intel Core i5-13600K
AMD Ryzen 9 5900X 12-Core

Benchmark elegido: build-linux-kernel-1.16.x  - Build: defconfig
 
![image](https://github.com/user-attachments/assets/fd479084-e191-4ee8-8073-f1bd0363672a)
![image](https://github.com/user-attachments/assets/6208a47f-96c8-4b79-9e66-8306e1bb69d0)

¿Cual es la aceleración cuando usamos un AMD Ryzen 9 7950X 16-Core?
Tomando como referencia los datos provistos en el sitio web openbenchmarking.org se obtienen los siguientes datos

|        Procesador       |  Nucleos  |  Tiempo   | SpeedUp | 
|-------------------------|-----------|-----------|---------|
|    AMD Ryzen 9 5900X    |     12    |     97    |   1.00  |
|   Intel Core i5-13600K  |     14    |     83    |   1.16  |
|   AMD Ryzen 9 7950X     |     16    |     53    |   1.83  |

También se realizó este mismo test para el procesador AMD Ryzen 5 2600

![benchmark_kernel](https://github.com/user-attachments/assets/26ff9a58-c574-4dba-acbe-e53942eb7eb8)

Viendo los resultados se puede realizar la siguiente tabla:

|        Procesador       |  Nucleos  |  Tiempo   | SpeedUp | 
|-------------------------|-----------|-----------|---------|
|    AMD Ryzen 5 2600     |     6     |    231    |   1.00  |
|    AMD Ryzen 9 5900X    |     12    |     97    |   2.38  |

## Tutorial de Gprof

### Paso 1 y 2: creación de perfiles habilitada durante la compilación y ejecución del código

Se crearon los archivos propuestos por la guía para luego compilarlos y ejecutar su código.
Las pruebas se realizaron en un microprocesador AMD Ryzen 5 2600 @ 3.4GHz

![paso1_2](https://github.com/user-attachments/assets/98810844-3015-45f1-9ed1-3fe7b9fdc6d1)

### Paso 3: Ejecución de la herramienta gprof

Los resultados guardados en gmon.out se pueden visualizar ejecutando el comando gprof utilizando de parámetros el ejecutable del archivo que compilamos y el gmon.out

![paso3](https://github.com/user-attachments/assets/ef3ff50e-1847-473a-9233-c4d2082076d7)

Gprof también nos permite mostrar la información que sea de interés mediante distintos parámetros.
Por ejemplo, se puede imprimir solamente el perfil plano usando el parametro -p:

![paso3a](https://github.com/user-attachments/assets/9995182b-a12f-415c-8951-1a4a63ed551e)

## Profiling con Linux Perf

![Linuxperf1](https://github.com/user-attachments/assets/f1a171f6-8120-4855-8172-bc65aa5c0586)

![Linuxperf2](https://github.com/user-attachments/assets/dfe648db-89a6-41c4-a1a9-8212ccfa7bd0)



