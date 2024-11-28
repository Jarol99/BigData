# Proyecto Clase 4
## Jarol Andres Hernandez Rincon - 20162005862
### Reporte de Hallazgos

#### Análisis del Modelo LeNet en el Conjunto de Datos MNIST

El modelo LeNet, aplicado al conjunto de datos MNIST en el código, alcanza una precisión de aproximadamente el 90% en el conjunto de prueba. Este rendimiento puede estar limitado por varios factores:

##### 1. Arquitectura del Modelo
- **LeNet** es una arquitectura simple, diseñada para problemas más básicos. Sus dos capas convolucionales con 6 y 16 filtros son limitadas en comparación con arquitecturas más modernas y profundas, como **ResNet** o **VGG**, que tienen más capas y filtros para extraer características más complejas.
- La función de activación utilizada es **tanh**, que puede provocar problemas como el desvanecimiento del gradiente, ralentizando la convergencia. La activación **ReLU** es más eficiente para redes más profundas y mejora la precisión.

##### 2. Optimizador y Tasa de Aprendizaje
- El modelo utiliza **SGD** (Stochastic Gradient Descent), un optimizador básico, menos eficiente que optimizadores avanzados como **Adam**, que ajusta la tasa de aprendizaje automáticamente, mejorando la convergencia y la precisión.
- Una tasa de aprendizaje mal ajustada también puede dificultar la convergencia, haciendo que el modelo se quede atrapado en un mínimo local de la función de pérdida.

##### 3. Número de Épocas
- El modelo se entrena solo durante **5 épocas**, lo cual es posiblemente insuficiente para alcanzar una precisión óptima. Aumentar el número de épocas podría permitir una mejor convergencia y un rendimiento superior.

##### 4. Regularización y Sobreajuste
- Existe el riesgo de **sobreajuste** (overfitting), donde el modelo aprende detalles específicos de los datos de entrenamiento, lo que afecta su capacidad para generalizar. Se recomienda implementar técnicas de regularización como **dropout** o **L2 regularization** para mejorar la generalización.

##### 5. Preprocesamiento de los Datos
- El preprocesamiento de las imágenes parece adecuado al normalizar los valores de píxeles. Sin embargo, si las imágenes no están centradas en la media o estandarizadas correctamente, el rendimiento podría verse afectado.

##### 6. Características del Conjunto de Datos MNIST
- Aunque MNIST es un conjunto de datos sencillo, su simplicidad podría ser otra razón del rendimiento limitado. Modelos más complejos podrían ser necesarios para mejorar más allá del 90% en tareas más desafiantes.

---

Estas limitaciones sugieren que el modelo LeNet, con su arquitectura y configuraciones actuales, no está optimizado para superar la barrera del 90% de precisión sin realizar ajustes significativos.

