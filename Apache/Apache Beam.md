# 🅱️ Apache Beam

Apache Beam es una **plataforma de procesamiento de datos de código abierto** que ofrece un modelo de programación unificado **para tareas de procesamiento de datos en lote y en streaming**. Permite definir y construir tuberías de procesamiento de datos, y ejecutarlas en diferentes backends de procesamiento distribuido, como Apache Flink, Apache Spark y Google Cloud Dataflow.

Apache Beam funciona mediante un modelo de programación unificado que permite definir y ejecutar pipelines de procesamiento de datos tanto en lote como en streaming. 

### Componentes Clave

- **Pipeline**: Representa el flujo de datos que se procesará. Es una serie de transformaciones que definen las operaciones de procesamiento de datos.
- **PCollection**: Es una colección de elementos de datos que fluyen a través del pipeline. Puede ser un conjunto de datos finito (batch) o un flujo de datos infinito (streaming).
- **PTransform**: Es una transformación que se aplica a una PCollection para generar una nueva PCollection. Ejemplos incluyen operaciones de filtrado, mapeo y agrupamiento.
- **Runner**: Es el motor de ejecución que procesa los pipelines en un entorno específico, como Apache Flink, Apache Spark o Google Cloud Dataflow.
- **Windowing**: Permite dividir una PCollection en ventanas basadas en marcas de tiempo, lo que facilita operaciones de agrupamiento sobre colecciones que crecen con el tiempo.
- **Watermark**: Es una estimación de cuándo se espera que haya llegado todo el dato de una ventana.
- **Trigger**: Determina cuándo se deben agregar los resultados de cada ventana.
- **State y Timers**: Son primitivas de bajo nivel que permiten controlar la agregación de colecciones de entrada que crecen con el tiempo.

### Funcionamiento

- **Definición del Pipeline**: Primero, se define el pipeline utilizando uno de los SDKs de Apache Beam (Java, Python, Go, etc.).
- **Leer Datos de Entrada**: Se especifican las fuentes de datos de entrada.
- **Aplicar Transformaciones**: Se aplican transformaciones (PTransforms) a las PCollections para procesar los datos.
- **Ejecutar el Pipeline**: Se especifica un runner adecuado para ejecutar el pipeline en un entorno específico.
- **Ejecutar y Obtener Resultados**: Finalmente, se ejecuta el pipeline y se obtienen los resultados procesados.

### Ejemplo en Python

```python
from apache_beam import Pipeline
from apache_beam.io import ReadFromText
from apache_beam.io import WriteToText
from apache_beam.transforms import Map

# Crear un pipeline
with Pipeline() as p:
    (
        p
        | 'Leer Datos' >> ReadFromText('path/to/input.txt')
        | 'Transformar Datos' >> Map(lambda line: line.upper())
        | 'Escribir Datos' >> WriteToText('path/to/output.txt')
    )
```

Este ejemplo lee datos de un archivo de texto, convierte las líneas a mayúsculas y escribe el resultado en otro archivo de texto.

---

### Casos de uso de Apache Beam:

- **Procesamiento de datos en tiempo real**: LinkedIn utiliza Apache Beam para procesar casi 4 trillones de eventos diarios en tiempo real, mejorando la personalización de la experiencia de los usuarios.

- **Procesamiento de datos transaccionales**: OCTO Technology migró a un minorista francés a un procesamiento de datos en streaming, logrando una reducción del 5x en los costos de infraestructura y un aumento del 4x en el rendimiento.

- **Análisis de riesgo cuantitativo**: HSBC utiliza Apache Beam para escalar y mejorar el rendimiento de sus pipelines XVA, acelerando el tiempo de comercialización y simplificando la distribución de datos para la simulación de escenarios futuros.

- **Protección contra ataques DDoS**: Project Shield utiliza Apache Beam para procesar datos de logs en tiempo real, ayudando a proteger a más de 3000 organizaciones vulnerables en más de 150 países.

---

Fuentes:
1. [beam.apache.org | "Apache Beam Overview"](https://beam.apache.org/get-started/beam-overview)
2. [beam.apache.org | "Case Studies"](https://beam.apache.org/case-studies)
3. [aprenderbigdata.com](https://aprenderbigdata.com/apache-beam)