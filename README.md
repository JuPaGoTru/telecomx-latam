# 📉 Análisis de Evasión de Clientes (Churn) – Telecom X

Este proyecto tiene como objetivo analizar los factores que influyen en la **cancelación del servicio (Churn)** por parte de los clientes de Telecom X. El análisis busca revelar patrones de comportamiento, identificar perfiles de riesgo y proponer estrategias para **mejorar la retención de clientes**.

---

## 🧠 Objetivos

- Entender la distribución general de la evasión de clientes.
- Explorar relaciones entre cancelación y variables como:
  - Tipo de contrato
  - Método de pago
  - Tiempo como cliente (`tenure`)
  - Gasto mensual y total
- Generar visualizaciones que expliquen los hallazgos.
- Proponer recomendaciones basadas en los datos.

---

## 📁 Estructura del proyecto

- 📊 TelecomX_LATAM.ipynb # Análisis exploratorio (EDA), visualizaciones y conclusiones
- 📄 README.md # Este archivo
- 📄 informe.md # Informe final

---

## 📊 Dataset

El dataset contiene información de más de **7.000 clientes**, con columnas relacionadas a:

- Datos personales: género, edad, dependientes
- Servicios contratados: Internet, teléfono, seguridad
- Información financiera: cargos mensuales, cargos totales
- Cancelación (`Churn`): si el cliente canceló o no

**Nota**: Algunas columnas estaban anidadas como diccionarios (`customer`, `account`, `phone`), por lo que fue necesario normalizar los datos antes de analizarlos.

---

## 🔍 Principales hallazgos

- La tasa de cancelación es de aproximadamente **25%**.
- **Clientes con contratos mes a mes** cancelan mucho más que quienes tienen contratos largos.
- **Tenure bajo** y **gasto diario alto** se asocian con mayor churn.
- Métodos de pago automáticos y clientes con más tiempo tienden a permanecer más tiempo.
- El tipo de servicio (`Fiber optic`) muestra mayor tasa de cancelación.

---

## ✅ Recomendaciones

- Fomentar contratos a largo plazo con incentivos.
- Implementar seguimiento a clientes nuevos durante sus primeros meses.
- Analizar causas de cancelación en usuarios con fibra óptica.
- Ofrecer beneficios por pago automático o anticipado.

---

## 📌 Tecnologías utilizadas

- Python
- Pandas
- Seaborn / Matplotlib
- Google Colab

---


## 📬 Contacto

Este proyecto fue realizado con fines educativos y de análisis de datos.
Para dudas o sugerencias, puedes abrir un issue o contactarme directamente.

---