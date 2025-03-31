# SdC TP1

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



