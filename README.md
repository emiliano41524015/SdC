# SdC TP1

## Introduccion
El rendimiento del hardware es un aspecto fundamental en la evaluación de sistemas informáticos, ya que determina su eficiencia en diversas aplicaciones. Para cuantificar este rendimiento, se emplean benchmarks, herramientas diseñadas para medir el desempeño de distintos componentes como CPU, memoria, GPU, almacenamiento y redes. Estos permiten comparar dispositivos y optimizar configuraciones en función de requerimientos específicos.

En este informe, se presentan diferentes benchmarks y su aplicabilidad en distintos entornos, analizando su utilidad en la medición de capacidades computacionales. Asimismo, se examinan pruebas específicas, como la compilación del kernel de Linux en distintos procesadores y el impacto del cambio de frecuencia en el desempeño y consumo energético de un sistema embebido.


Armar una lista de benchmarks, ¿cuales les serían más útiles a cada uno ? ¿Cuáles podrían llegar a medir mejor las tareas que ustedes realizan a diario ? 

| #  | Nombre del Benchmark              | Categoría                         | Utilidad |
|----|-----------------------------------|-----------------------------------|----------|
| 1  | Geekbench, Cinebench              | CPU y Cómputo en General          | Evaluar el rendimiento en tareas generales, cálculos intensivos y simulaciones.<br>Comparar la eficiencia entre diferentes procesadores. |
| 2  | AIDA64, MemTest86                 | Memoria RAM                       | Medir la velocidad de lectura/escritura y la latencia de la memoria.<br>Ver cómo afecta la velocidad de la RAM al rendimiento del sistema. |
| 3  | gputorch, DeepBench               | GPU - Cómputo / Deep Learning     | Medir el rendimiento de la GPU en tareas de cómputo intensivo y entrenamiento de modelos de deep learning.<br>Evaluar la capacidad para procesamiento de datos en paralelo. |
| 4  | 3DMark, Unigine Superposition     | GPU - Gráficos                    | Medir el rendimiento en tareas gráficas y de renderizado.<br>Evaluar la capacidad de la GPU en videojuegos y aplicaciones visuales. |
| 5  | CrystalDiskMark, AS SSD Benchmark | Discos SSD/HDD                    | Medir la velocidad de lectura/escritura y la latencia del almacenamiento.<br>Evaluar el impacto del almacenamiento en el rendimiento del sistema. |
| 6  | iPerf, Netperf                    | Redes y Servidores                | Evaluar la velocidad de la red, latencia y rendimiento de servidores.<br>Comparar diferentes configuraciones de red. |
| 7  | SysBench, TPC-C                   | Bases de Datos                    | Evaluar el rendimiento de consultas SQL y bases de datos NoSQL.<br>Medir la latencia y throughput en bases de datos. |

-------------------------------------------------------------------------------------------------------------------------------------

Pensar en las tareas que cada uno realiza a diario y escribir en una tabla de dos entradas las tareas y que benchmark la representa mejor.

| Actividad           | Benchmark Representativo              |
|-----------------|-------------------------------------------|
| Gaming          | 3DMark                                    |
| Compilar código | Geekbench                                 |
| Contenido multimedia (Netflix, Google Meet)     | iPerf     |

---------------------------------------------------------------------------------------------------------------------------------

Cual es el rendimiento de estos procesadores para compilar el kernel de linux ?
Intel Core i5-13600K
AMD Ryzen 9 5900X 12-Core

![image](https://github.com/user-attachments/assets/fd479084-e191-4ee8-8073-f1bd0363672a)
![image](https://github.com/user-attachments/assets/6208a47f-96c8-4b79-9e66-8306e1bb69d0)


Cual es la aceleración cuando usamos un AMD Ryzen 9 7950X 16-Core

| Procesador                         | Tiempo (segundos) | Speedup (vs. AMD Ryzen 9 7950X) |
|------------------------------------|-------------------|-------------------------------|
| AMD Ryzen 9 5900X 12-Core          | 97                | 97 / 53 ≈ 1.83                |
| Intel Core i5-13600K               | 83                | 83 / 53 ≈ 1.57                |
| AMD Ryzen 9 7950X 16-Core (base)    | 53                | 1 (referencia)                |

----------------------------------------------------------------------------------------------------------------------------------

## Cambio de frecuencia 
### Tiempos de ejecucion con frecuencia variable
Se uso un proyecto con platform.io, utilizando el framework de arduino, dadas las complicaciones con los debuggers stlink no originales, se utiliza el modo debugging para ver el transcurso del tiempo.
Para una linea base, partimos la frecuencia del procesador a la mitad, dividiendo la configuracion del PLL a la mitad, y por prueba y error con dos bucles llegamos a un tiempo  aproximado de 10 segundos.
![Tiempo media frecuencia](https://github.com/user-attachments/assets/8bdaa1db-2987-4e50-a943-bb178df43bf4)
Luego, volvimos a la configuracion base, llevando el multiplicador del PLL a 16, y encontramos que el tiempo de ejecucion se redujo casi exactamente a la mitad.
![Tiempo doble frecuencia](https://github.com/user-attachments/assets/21768c3b-45fa-4b9c-9900-b68e7b304ac4)

### Consumo con frecuencia variable
Tambien analizamos el consumo de corriente por la placa a partir de la salida del debugger para asi no considerar el consumo propio del stlink.
Encontramos que con la mitad de la frecuencia la stm consumia entre 18 y 20 mA:

https://github.com/user-attachments/assets/08604497-871e-4cfa-bc41-241cd3d08864

Mientras que al duplicar la frecuencia, este consumo estaba entre 27 y 31 mA:

https://github.com/user-attachments/assets/75c2ed71-ac3d-4f7e-a128-b426d23f26c1




