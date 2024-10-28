# 🐿️ Apache Flink

Apache Flink es un framework de procesamiento de datos de código abierto desarrollado por la Apache Software Foundation. Es una plataforma unificada para el procesamiento de flujos y lotes, lo que significa que puede manejar tanto datos en tiempo real como datos en lote.

### Características Clave

- **Procesamiento de Flujos y Lotes**: Flink puede ejecutar tanto aplicaciones de procesamiento en tiempo real (streaming) como en lote (batch).
- **Procesamiento de Baja Latencia**: Flink está diseñado para procesar datos con baja latencia, lo que lo hace ideal para aplicaciones que requieren respuestas rápidas.
- **Manejo de Estado**: Flink soporta el manejo de estado avanzado, lo que permite realizar cálculos complejos que dependen del historial de eventos.
- **Exactamente Una Vez**: Flink garantiza la consistencia exacta una vez, lo que significa que cada dato se procesa exactamente una vez, incluso en caso de fallos.
- **Procesamiento en Tiempo de Eventos**: Flink permite el procesamiento basado en el tiempo de los eventos, lo que es útil para aplicaciones que necesitan manejar datos desordenados o tardíos.
- **Escalabilidad**: Flink es altamente escalable y puede manejar grandes volúmenes de datos.

### Casos de Uso

- **Aplicaciones Basadas en Eventos**: Procesamiento de eventos en tiempo real, como el análisis de datos de sensores o la monitorización de redes.
- **Análisis de Datos**: Extracción de información y conocimientos de datos en tiempo real, como el análisis de comportamiento de usuarios en aplicaciones web.
- **ETL (Extract, Transform, Load)**: Transformación y movimiento de datos entre diferentes sistemas de almacenamiento, como la migración de datos entre bases de datos.
- **Procesamiento de Transacciones**: Procesamiento de transacciones financieras o comerciales en tiempo real.

### Funcionamiento

- **Definición del Pipeline**: Se define el pipeline utilizando uno de los SDKs de Apache Flink (Java, Scala, Python, SQL).
- **Leer Datos de Entrada**: Se especifican las fuentes de datos de entrada, como Apache Kafka o HDFS.
- **Aplicar Transformaciones**: Se aplican transformaciones a las PCollections para procesar los datos.
- **Ejecutar el Pipeline**: Se especifica un runner adecuado para ejecutar el pipeline en un entorno específico.
- **Ejecutar y Obtener Resultados**: Finalmente, se ejecuta el pipeline y se obtienen los resultados procesados.

---

#### ☕ Ejemplo en Java

```java
import org.apache.flink.streaming.api.datastream.DataStream;
import org.apache.flink.streaming.api.environment.StreamExecutionEnvironment;
import org.apache.flink.api.common.functions.MapFunction;

public class FlinkExample {
    public static void main(String[] args) throws Exception {
        StreamExecutionEnvironment env = StreamExecutionEnvironment.getExecutionEnvironment();
        DataStream<String> data = env.readTextFile("path/to/input.txt");
        DataStream<String> result = data.map(new MapFunction<String, String>() {
            @Override
            public String map(String value) {
                return value.toUpperCase();
            }
        });
        result.writeAsText("path/to/output.txt");
        env.execute("Flink Example");
    }
}
```

#### 🐍 Ejemplo en Python

```python
from pyflink.datastream import StreamExecutionEnvironment
from pyflink.datastream.functions import MapFunction

class ToUpperCaseMapFunction(MapFunction):
    def map(self, value):
        return value.upper()

# Crear el entorno de ejecución
env = StreamExecutionEnvironment.get_execution_environment()

# Leer datos de un archivo de texto
data = env.read_text_file('path/to/input.txt')

# Aplicar una transformación para convertir el texto a mayúsculas
result = data.map(ToUpperCaseMapFunction())

# Escribir los resultados en un archivo de texto
result.write_as_text('path/to/output.txt')

# Ejecutar el pipeline
env.execute('Flink Python Example')
```

---

Fuente: [flink.apache.org](https://flink.apache.org/)