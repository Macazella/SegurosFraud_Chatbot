# SegurosFraud_Chatbot

# 🤖 Chatbot Inteligente para Detección de Fraudes en Seguros

Bienvenido al proyecto **Seguros_Fraude_Chatbot**, una solución de análisis predictivo potenciada con Inteligencia Artificial y visualizaciones interactivas, que permite detectar fraudes en seguros a partir de lenguaje natural.

🧠 Utiliza un modelo **H2O AutoML** previamente entrenado.  
💬 Cuenta con un chatbot creado en **Streamlit**, conectado en tiempo real a una base de datos **PostgreSQL en Neon.tech**.  
📊 Visualiza resultados dinámicos con **Plotly**.  
📲 ¡Incluye integración con **Telegram Bot** para recibir predicciones al instante!

---

## 🚀 ¿Qué hace este proyecto?

- Recibe preguntas en lenguaje natural sobre posibles fraudes.
- Consulta registros reales almacenados en una base de datos en la nube.
- Ejecuta predicciones usando un modelo entrenado con H2O AutoML.
- Muestra respuestas explicativas acompañadas de gráficos claros.
- Puede enviar los resultados directamente a un usuario de Telegram.

---

## 🗂️ Estructura del Proyecto

```
Seguros_fraude_Chatbot/
│
├── app.py                      ← Interfaz principal en Streamlit (chatbot)
├── modelo_final.py            ← Script para cargar el modelo y predecir
├── requirements.txt           ← Paquetes necesarios para instalar
├── .env                       ← Variables de entorno (conexiones y tokens)
│
├── data/
│   ├── X_train.csv
│   ├── X_val.csv
│   ├── y_train.csv
│   └── y_val.csv
│
├── models/
│   └── StackedEnsemble_H2OModel  ← Modelo entrenado con H2O AutoML
│
└── utils/
    └── db_connection.py       ← Módulo de conexión a Neon.tech PostgreSQL
```

---

## 🔍 Dataset utilizado

📂 **Fuente original**:  
[Insurance Company Benchmark (COIL 2000) – OpenML](https://www.openml.org/d/19)

📈 **Preprocesamiento aplicado**:
- Separación de features (`X_train`, `X_val`) y etiquetas (`y_train`, `y_val`)
- Codificación y limpieza previa antes del entrenamiento con H2O
- Modelo final: `StackedEnsemble_AllModels` generado por AutoML de H2O

---

## 🧰 Tecnologías utilizadas

| Tecnología     | Rol en el proyecto                                |
|----------------|---------------------------------------------------|
| Python         | Lógica general y control del flujo                |
| Streamlit      | Interfaz de usuario para el chatbot               |
| PostgreSQL     | Base de datos alojada en la nube (Neon.tech)      |
| H2O AutoML     | Entrenamiento y carga del modelo predictivo       |
| Plotly         | Visualización de gráficos interactivos            |
| Telegram API   | Envío remoto de predicciones                      |

---

## ⚙️ Instrucciones para ejecutar

1. 🔧 Cloná el repositorio y creá un entorno virtual:

```bash
git clone https://github.com/tuusuario/Seguros_fraude_Chatbot.git
cd Seguros_fraude_Chatbot
python -m venv env
.\env\Scripts\activate
```

2. 📦 Instalá las dependencias:

```bash
pip install -r requirements.txt
```

3. 🔐 Configurá el archivo `.env`:

```env
NEON_DB_URL=postgresql://usuario:contraseña@host/db?sslmode=require
H2O_MODEL_PATH=models/StackedEnsemble_H2OModel
TELEGRAM_TOKEN=tu_token_de_telegram
```

4. ▶️ Ejecutá la aplicación:

```bash
streamlit run app.py
```

---

## ☁️ Carga de base de datos en Neon.tech

1. Crear un proyecto en [https://neon.tech](https://neon.tech).
2. En la sección de SQL Editor, creá la tabla y cargá `X_val.csv`.
3. Usá `utils/db_connection.py` para conectar desde Python.
4. Validá que las columnas coincidan con las del modelo entrenado.

---

## 🤖 Integración con Telegram

- Creá un bot con [@BotFather](https://t.me/BotFather)
- Pegá el token en el archivo `.env`
- El sistema envía automáticamente la predicción al usuario que lo solicite desde Telegram

---

## 📌 Licencia

Este proyecto se publica bajo licencia MIT.  
Libre para usar, modificar y mejorar. 🚀

---

## 💡 ¿Por qué este proyecto importa?

Porque fusiona:
- Machine Learning real
- Visualización en tiempo real
- Interacción natural con usuarios
- Infraestructura **100% en la nube y gratuita**

Ideal para presentaciones, portfolios profesionales o MVPs en seguros e IA.

---
