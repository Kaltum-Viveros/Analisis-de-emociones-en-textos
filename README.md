# Clasificación de Emociones en Texto con TF-IDF y Embeddings (MiniLM)

Este proyecto final de Minería de Datos tiene como objetivo desarrollar un modelo capaz de identificar emociones en textos escritos por estudiantes universitarios, a partir de respuestas generadas en un formulario.  
Se exploran dos enfoques de representación de texto: **TF-IDF** y **embeddings generados con MiniLM**. Posteriormente, se entrenan y comparan varios algoritmos de clasificación para evaluar su desempeño y resultados.

---

## -> Requisitos e instalación

**Requisitos:**
- Python 3.10 o superior  
- Google Colab (recomendado para facilitar instalación)  
- Si se ejecuta localmente: acceso a terminal con permisos de instalación  

**Instalación:**

1. Clona este repositorio:

```bash
git clone https://github.com/Kaltum-Viveros/Analisis-de-emociones-en-textos.git
```

2. Instala las dependencias desde requirements.txt:

```bash
pip install -r requirements.txt
```

3. Descarga el modelo de spaCy para español:

```bash
python -m spacy download es_core_news_sm
```

4. (Opcional – solo si usas el corrector gramatical fuera de Colab):

**Para Linux:**

```bash
sudo apt update -y
sudo apt install openjdk-17-jdk -y
update-alternatives --install /usr/bin/java java /usr/lib/jvm/java-17-openjdk-amd64/bin/java 1
update-alternatives --set java /usr/lib/jvm/java-17-openjdk-amd64/bin/java
java -version
```

**Para Windows:**  
1. Descarga el instalador oficial de OpenJDK 17:  
   https://adoptium.net/temurin/releases/?version=17  

2. Instala el JDK usando el instalador descargado.  

3. Configura las variables de entorno:  
   - En Variables del sistema, edita la variable `Path` y añade la ruta donde se instaló Java (ej. `C:\Program Files\Eclipse Adoptium\jdk-17\bin`).  
   - Añade también la variable `JAVA_HOME` con la ruta de instalación (ej. `C:\Program Files\Eclipse Adoptium\jdk-17`).  

4. Verifica la instalación:  

```bash
java -version
```

---

## -> Ejecución del proyecto

1. Abre y ejecuta el archivo `proyecto_final_minería_de_datos.py`.  
2. Asegúrate de tener el dataset `Nuevo_Dataset_Patrones_Emocionales.csv` en la ruta esperada (`/data/`).  
3. El código realiza:  
   - Limpieza, corrección y lematización del texto.  
   - Vectorización con TF-IDF y embeddings MiniLM.  
   - Entrenamiento de modelos: KNN, Naive Bayes, SVM, Random Forest.  
   - Evaluación de métricas y visualización de resultados.  
   - Almacenamiento automático de los modelos y encoders en `.pkl`.  

---

## 📂 Estructura esperada del proyecto

```
📁 Analisis-de-emociones-en-textos/
│
├── data/
│   └── Nuevo_Dataset_Patrones_Emocionales.csv
│
├── models/
│   ├── modelo_nb_tfidf.pkl
│   ├── modelo_svm_embeddings.pkl
│   ├── label_encoder_tfidf.pkl
│   ├── label_encoder_embeddings.pkl
│   └── vectorizador_tfidf.pkl
│
├── proyecto_final_minería_de_datos.py
├── requirements.txt
└── README.md
```

---

## -> Algoritmos implementados

- **K-Nearest Neighbors (KNN)**  
  - Distancia Euclidiana para TF-IDF  
  - Distancia Coseno para embeddings  

- **Naive Bayes**  
  - MultinomialNB para TF-IDF  
  - GaussianNB para embeddings  

- **Support Vector Machine (SVM)**  
  - Con kernel lineal y valores de C ajustados  

- **Random Forest**  
  - Versiones base, con poda leve y profundidad extendida  

---

## -> Métricas evaluadas

- Accuracy  
- Precision  
- Recall  
- F1-score  
- ROC-AUC  
- Matriz de confusión normalizada  
- Curvas ROC por clase  
- Gráficas de métricas por emoción  

---

## -> Notas adicionales

- El modelo de embeddings se generó con `sentence-transformers` (MiniLM).  
- Para la corrección gramatical se usó `language-tool-python`, que requiere Java si se ejecuta fuera de Google Colab.  
- Los modelos entrenados se guardan automáticamente y pueden ser reutilizados sin reentrenar.  

---

## -> Contacto

Proyecto desarrollado como parte del curso de Minería de Datos, Benemérita Universidad Autónoma de Puebla.  

**Colaboradores:**  
- Kaltum Abdala Viveros Gómez  
- Esmeralda Urbina Cinto  
- Nelson Ricardo Sosa Francisco  
- Josue Saúl Torres Zamora
- Luis Yael Méndez Sánchez
