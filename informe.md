### 🎯 Objetivo del análisis

El propósito de este análisis es comprender los factores que influyen en la **evasión de clientes (Churn)** en una empresa de servicios de internet.  
La cancelación de servicios por parte de los clientes representa una pérdida directa de ingresos y oportunidades de crecimiento, por lo que es esencial detectar patrones de comportamiento que permitan **prevenir la fuga y mejorar la retención**.

El análisis abarca cuatro etapas clave:
1. Limpieza y transformación de los datos
2. Análisis exploratorio (EDA)
3. Visualización de patrones
4. Conclusiones y recomendaciones estratégicas


### 🔧 Proceso de limpieza

- Se importó un DataFrame con columnas anidadas en formato diccionario: `customer`, `phone`, `internet`, `account`.
- Se **normalizaron** dichas columnas utilizando `pd.json_normalize()` para obtener un DataFrame plano y más analizable.
- Se detectaron y eliminaron valores vacíos en la columna `Churn` (algunos registros no tenían información válida).
- La variable `Churn` fue transformada de texto (`Yes`/`No`) a binaria (`1` = canceló, `0` = no canceló).
- Otras columnas categóricas con valores `Yes`, `No`, `No internet service` o `No phone service` también fueron transformadas a formato binario.
- La columna `Charges`, que contenía diccionarios, fue dividida en:
  - `Charges.Monthly`: gasto mensual
  - `Charges.Total`: gasto total acumulado
- Se creó una nueva variable: `Cuentas_Diarias` = `Charges.Total / tenure`, para analizar gasto promedio por día.

Estas transformaciones permitieron convertir los datos en un formato **estructurado, limpio y listo para el análisis exploratorio**.


### 📊 Distribución de Churn

La tasa general de cancelación fue de aproximadamente **26.5%**, lo cual es considerable para una empresa de este tipo.

Se utilizaron gráficos de barras y gráficos circulares para mostrar la proporción de clientes que se dieron de baja (`Churn = 1`) frente a los que permanecieron (`Churn = 0`).

### 🧠 Variables categóricas vs Churn

Se analizaron variables como `gender`, `Contract`, `InternetService` y `PaymentMethod` para identificar patrones de cancelación:

- Los **clientes con contrato mes a mes** tienen una **mayor tasa de cancelación**.
- **Métodos de pago automáticos** (tarjeta o transferencia) se asocian con **menores tasas de evasión**.
- El tipo de internet `Fiber optic` presenta **una tasa más alta de cancelación** que `DSL`.

### 📈 Variables numéricas vs Churn

Se analizaron `tenure`, `Charges.Total` y `Cuentas_Diarias`:

- Los clientes que cancelan **llevan menos tiempo como usuarios (tenure bajo)**.
- Muchos de ellos **no han acumulado altos gastos totales**, lo cual indica que abandonan el servicio temprano.
- La **distribución del gasto diario** también es más alta en los que cancelan, lo que puede indicar percepción de **alto costo por uso**.

Se utilizaron histogramas y boxplots para visualizar claramente las diferencias entre los dos grupos de clientes.


### ✅ Principales hallazgos

- **El tipo de contrato** es el factor más claramente asociado a la cancelación: los contratos mensuales tienen una tasa de evasión significativamente mayor.
- **Los clientes con menor tiempo de permanencia** (`tenure`) son los que más abandonan.
- **Un mayor gasto diario (Cuentas_Diarias)** se asocia con mayor churn, lo que puede indicar percepción de bajo valor.
- El **tipo de internet "Fiber optic"** presenta una mayor tasa de cancelación, posiblemente por temas de costo, fallos o expectativas no cumplidas.
- **Los métodos de pago automáticos** parecen ayudar a la permanencia del cliente.

Estos patrones permiten identificar perfiles de riesgo y tomar decisiones orientadas a mejorar la experiencia y la retención.


### 💡 Sugerencias para reducir el Churn

1. **Incentivar contratos anuales o bianuales**, ofreciendo descuentos o beneficios adicionales por compromiso.
2. **Detectar clientes nuevos (tenure < 6 meses)** y aplicar campañas de bienvenida y seguimiento personalizado.
3. **Monitorear usuarios con alto gasto diario** y ofrecer planes personalizados o ajustes tarifarios.
4. **Promover métodos de pago automáticos** con descuentos, ya que están asociados a menor evasión.
5. **Analizar problemas técnicos o quejas** relacionadas con el servicio de fibra óptica para reducir cancelaciones.

Con estas acciones se puede mejorar la satisfacción del cliente, reducir el churn y aumentar la retención de usuarios en el tiempo.
