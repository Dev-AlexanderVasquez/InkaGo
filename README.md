# InkaGo
InkaGO: Optimización en la Distribución de Suplementos contra la Anemia Infantil
📋 Descripción del Proyecto
Este proyecto fue desarrollado para el curso de Complejidad Algorítmica de la Universidad Peruana de Ciencias Aplicadas (UPC). Su objetivo principal es diseñar e implementar un algoritmo eficiente que optimice la logística de distribución de galletas nutritivas ("Nutri H") en el departamento de San Martín, Perú. El sistema prioriza las zonas críticas y los casos más graves de anemia en niños de 3 a 10 años, minimizando los tiempos de entrega y los costos operativos.

📊 Conjunto de Datos (Dataset)
La solución utiliza datos oficiales de la Plataforma Nacional de Datos Abiertos del Gobierno Peruano. El dataset original cuenta con registros detallados de casos de anemia (ubicación geográfica, gravedad del caso, establecimiento de salud, etc.).  Para el prototipo actual, se aplicó un filtro y procesamiento de datos para enfocar el análisis en un subgrupo estratégico:  
Población objetivo: Niños entre 3 y 10 años con diagnóstico de anemia. 
Muestra filtrada: 1,505 registros procesados a partir del 20 de julio de 2023. 
Variables clave: Severidad (Leve, Moderada, Severa), Coordenadas Geográficas (Latitud/Longitud) y Redes de Salud. 

🛠️ Metodología y Tecnologías Utilizadas
📌 Arquitectura del Grafo
El problema se modeló matemáticamente como un grafo donde:  
Nodos: Representan casos individuales de niños con anemia, clasificados por colores según su gravedad (Verde: Leve, Amarillo: Moderado, Rojo: Severo).  Aristas: Representan las distancias geométricas (en kilómetros) entre los centros de atención, limitadas a un radio máximo de 100 km para optimizar el procesamiento. 

💻 Stack Tecnológico
(Python)Pandas: Lectura, limpieza y manipulación del dataset. 
Geopy: Cálculo de distancias ortodrómicas utilizando latitud y longitud. 
Numpy: Construcción eficiente de la matriz de adyacencia de $1505 \times 1505$.  
NetworkX: Generación y visualización del grafo de conexiones.

🚀 Técnicas y Algoritmos 
Fuerza Bruta (Fase Inicial)Uso: Se evaluaron todos los pares posibles de centros de atención sin restricciones previas para estructurar la matriz de distancias inicial (generando un dataframe secundario de 21,945 filas).  
2. Algoritmos en Consideración / Próximas Implementaciones
Para llevar el prototipo a una solución de distribución a gran escala, se contempla el uso de:
Breadth-First Search (BFS): Detección de comunidades locales y agrupaciones geográficas críticas dentro de un radio $\le$ 10 km.  
Algoritmo de Dijkstra: Determinación de las rutas más cortas y eficientes entre nodos de distribución para logística de emergencia. 
Algoritmo de Kruskal (MST): Diseño de una red troncal óptima (Árbol de Expansión Mínima) para conectar los puntos de salud con la menor distancia total posible sin bucles. 

👥 Autores
Gianmarco Fabian Jiménez Guerra   
Alexander Felipe Vasquez Roncal   
Eric Marlon Olivera Barzola
