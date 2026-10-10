# APRENDIZAGE-SUPERVISADO-Y-NO-SUPERVISADO-UNIDAD-3--EDWAR-VAYRON-ANDRES
Repositorio de codigo de las actividades de la unidad 3 - Inteligencia Artificial

Este proyecto contiene 2 ejercicios de aprendizaje automático:

1. Sistema supervisado: modelo predictivo para estimar tiempo según la distancia.
2. Sistema no supervisado: clustering de rutas con K-Means para segmentar grupos según relación costo-distancia.

---

## Descripción general

### 1) Sistema supervisado
Se utiliza un modelo de regresión lineal para predecir el tiempo de viaje a partir de la distancia recorrida.

- Archivo principal: `MODELOHORAS.py`
- Función: entrenar el modelo y generar la gráfica con la línea de predicción.
- Resultado: se crea un archivo `modelo_tiempo_minutos.pkl` que luego utiliza la interfaz del sistema supervisado.

### 2) Sistema no supervisado
Se trabaja con datos de rutas y se aplica K-Means para agruparlas en 3 clusters según la relación costo-distancia.

- Archivo principal: `SISTEMA NO SUPERVISADO_V1.py`
- Función: cargar `rutas_transporte.json` y generar el gráfico de clustering.
- Resultado: visualización de 3 grupos de rutas con centroides.

---

## Archivos del proyecto

- `MODELOHORAS.py` - entrenamiento del modelo supervisado
- `SISTEMA SUPERVISADO V2.py` - interfaz gráfica para consultar rutas y obtener tiempo estimado
- `SISTEMA NO SUPERVISADO_V1.py` - clustering no supervisado
- `rutas_transporte.json` - base de datos de rutas
- `README.md` - guía de uso

---

## Requisitos previos

Es importante tener instaladas las librerías necesarias antes de ejecutar los scripts:

```bash
pip install numpy scikit-learn matplotlib joblib PySimpleGUI kanren
```

### Librerías utilizadas
- `numpy`
- `scikit-learn`
- `matplotlib`
- `joblib`
- `PySimpleGUI`
- `kanren`

### Importante
Todos los archivos deben estar en la misma carpeta del proyecto para que el programa pueda localizar:
- `rutas_transporte.json`
- `modelo_tiempo_minutos.pkl`
- los archivos `.py`

---

## Guía de uso

### Ejercicio 1: Sistema supervisado

#### Paso 1: Entrenar el modelo
Ubícate en la carpeta del proyecto y ejecuta:

```bash
python MODELOHORAS.py
```

¿Qué ocurre?
- Se entrena el modelo de regresión lineal.
- Se imprime información del entrenamiento en consola.
- Se genera la gráfica de regresión con la línea de predicción.
- Se guarda el modelo entrenado como:

```bash
modelo_tiempo_minutos.pkl
```

Este paso debe hacerse primero, porque el archivo del modelo será usado por el sistema supervisado con interfaz gráfica.

#### Paso 2: Ejecutar la interfaz del sistema supervisado
Una vez entrenado el modelo, ejecuta:

```bash
python "SISTEMA SUPERVISADO V2.py"
```

La aplicación mostrará una interfaz donde podrás:
- elegir un origen
- elegir un destino
- buscar la mejor ruta
- visualizar el costo total
- ver la distancia
- obtener el tiempo estimado por el modelo

El sistema utiliza la base de rutas desde `rutas_transporte.json` y aplica el modelo entrenado para estimar el tiempo.

#### Observaciones
- El ejercicio supervisado se centra en la predicción de tiempo.
- La gráfica generada por `MODELOHORAS.py` muestra la línea de regresión que representa la relación entre tiempo y distancia.

---

### Ejercicio 2: Sistema no supervisado

#### Ejecutar el clustering K-Means
Ejecuta el siguiente script:

```bash
python "SISTEMA NO SUPERVISADO_V1.py"
```

¿Qué hace este ejercicio?
- Carga las rutas desde `rutas_transporte.json`
- Extrae los datos de distancia y costo
- Aplica K-Means con 3 clusters
- Genera una gráfica donde se segmentan las rutas en 3 grupos

#### Interpretación
La gráfica mostrará:
- eje X: distancia
- eje Y: costo
- 3 clusters distintos que agrupan rutas con características similares
- centroides que representan el centro de cada grupo

Esto permite identificar rutas con patrones parecidos según la relación costo-distancia.

---

## Flujo recomendado de ejecución

Para usar correctamente ambos ejercicios, sigue este orden:

```bash
1. pip install numpy scikit-learn matplotlib joblib PySimpleGUI kanren
2. python MODELOHORAS.py
3. python "SISTEMA SUPERVISADO V2.py"
4. python "SISTEMA NO SUPERVISADO_V1.py"
```

### Recomendación
- Ejecuta primero el modelo supervisado porque genera el archivo necesario para la predicción.
- Luego puedes abrir la interfaz del sistema supervisado y, en paralelo, ejecutar el modelo no supervisado para observar el clustering de rutas.

---

## Solución de problemas comunes

### Error: `ModuleNotFoundError`
Si aparece un error de módulo inexistente, instala las librerías:

```bash
pip install numpy scikit-learn matplotlib joblib PySimpleGUI kanren
```

### Error: archivo no encontrado
Si aparece un mensaje como `No se encontró el archivo ...`, asegúrate de:
- estar en la carpeta correcta
- tener todos los archivos en la misma carpeta
- que el archivo `rutas_transporte.json` exista

### Error al ejecutar el sistema supervisado
Si el modelo no existe, primero ejecuta:

```bash
python MODELOHORAS.py
```

---

## Resumen rápido

- El ejercicio supervisado predice tiempo con regresión lineal.
- El ejercicio no supervisado agrupa rutas con K-Means.
- Debes instalar dependencias.
- Todos los archivos deben estar en la misma carpeta.
- El modelo supervisado debe ejecutarse primero para crear el archivo del modelo.

---

## Créditos
Proyecto de la unidad 3 - Inteligencia Artificial.
