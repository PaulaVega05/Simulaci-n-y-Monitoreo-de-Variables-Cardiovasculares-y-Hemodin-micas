# Simulación y Monitoreo de Variables Cardiovasculares y Hemodinámicas
## Revisión bibliográfica: monitor Mindray uMEC 100 y simulador Pronk OxSim OX-1

### Introducción

En esta revisión bibliográfica se recopiló información técnica sobre el monitor de signos vitales Mindray uMEC 100 y el simulador Pronk OxSim OX-1, con el fin de identificar su funcionamiento básico, los parámetros fisiológicos que pueden ser evaluados o simulados, y las tolerancias o errores máximos permitidos en el ámbito clínico.

El uMEC 100 es un monitor de paciente multiparámetro utilizado para la vigilancia clínica de signos vitales, dependiendo de su configuración, puede medir variables como ECG, frecuencia cardiaca, SpO₂, frecuencia de pulso, presión no invasiva, respiración y temperatura.

El Pronk OxSim OX-1 es un simulador óptico de oximetría de pulso, su función principal es comprobar el funcionamiento del canal de SpO₂ de un monitor, incluyendo el sensor y el cable de extensión, por lo tanto no debe considerarse un simulador multiparámetro completo, sino un simulador especializado en oximetría de pulso.

### a. ¿Cómo colocar al uMEC 100 en modo “monitor”?

En el monitor Mindray uMEC 100, el modo Monitor corresponde al filtro de ECG utilizado para condiciones normales de monitorización clínica; este filtro permite visualizar una señal ECG estable durante la vigilancia continua del paciente.

El procedimiento general para colocarlo en modo monitor es:

1. Encender el monitor uMEC 100.
2. Ingresar a la pantalla principal de monitorización.
3. Seleccionar el área o la onda correspondiente al ECG.
4. Entrar al menú de configuración de ECG, usualmente llamado ECG Setup.
5. Buscar la opción Filter o filtro.
6. Seleccionar la opción Monitor.
7. Verificar que el filtro ECG quede configurado como Monitor.

Este modo se usa para monitorización continua en condiciones normales, no es el modo más adecuado si se requiere análisis diagnóstico detallado del ECG o del segmento ST. Según las especificaciones técnicas del equipo, el filtro en modo Monitor tiene un ancho de banda aproximado de 0,5 Hz a 40 Hz.

### b. ¿Qué tipo de parámetros o variables fisiológicas pueden simularse con el Pronk OxSim OX-1?

El simulador Pronk OxSim OX-1 permite simular principalmente variables asociadas a la oximetría de pulso, entres los principales se encuentra:

#### 1. Saturación periférica de oxígeno - SpO₂

La SpO₂ representa la saturación periférica de oxígeno, es decir, el porcentaje de hemoglobina arterial que se encuentra saturada con oxígeno, en la práctica clínica este valor se obtiene mediante un oxímetro de pulso, que utiliza luz roja e infrarroja para estimar la oxigenación del paciente.

El OxSim OX-1 puede simular diferentes valores de SpO₂ para comprobar si el monitor interpreta correctamente la señal del sensor entee los cuales estan 85%, 95%, 98%, 99% (en modo de baja perfusión).

#### 2. Frecuencia de pulso o frecuencia cardiaca simulada

La frecuencia de pulso corresponde al número de pulsaciones detectadas por minuto a partir de la señal pulsátil periférica, en un monitor de signos vitales, este valor puede aparecer como PR o frecuencia de pulso.

El OxSim OX-1 permite simular diferentes frecuencias para verificar si el monitor detecta correctamente el ritmo pulsátil, entre las cuales estan 40 bpm, 80 bpm y 140 bpm.

*- bpm -> latidos por minuto.*

#### 3. Índice de perfusión - PI

El índice de perfusión o PI, es un indicador de la fuerza de la señal pulsátil detectada por el oxímetro, este representa la relación entre el componente pulsátil y el componente no pulsátil de la señal óptica.

Un PI alto indica una señal periférica fuerte y una mejor perfusión, mientras que un PI bajo indica baja perfusión periférica, lo cual puede dificultar la lectura del oxímetro y generar mediciones inestables.

El OxSim OX-1 permite simular condiciones normales de perfusión y condiciones de baja perfusión, las vlores aproximados usados son PI ≈ 2,0 en modos normales y PI ≈ 0,2 en modo de baja perfusión.


### Modos de simulación del Pronk OxSim OX-1

| Modo del simulador | SpO₂ simulada | Frecuencia simulada | PI aproximado | Uso principal |
|---|---:|---:|---:|---|
| 85 % | 85 % | 80 bpm | 2,0 | Verificar lectura en saturación baja |
| 95 % | 95 % | 40 bpm | 2,0 | Verificar lectura con frecuencia baja |
| 98 % | 98 % | 80 bpm | 2,0 | Verificar lectura en condición normal |
| 140 bpm | 98 % | 140 bpm | 2,0 | Verificar lectura con frecuencia alta |
| Low Perfusion | 99 % | 80 bpm | 0,2 | Verificar respuesta en baja perfusión |


### c. Tolerancias o errores máximos permitidos para cada parámetro fisiológico

Para establecer las tolerancias o errores máximos permitidos, se deben considerar las especificaciones técnicas del monitor y las normas aplicables a equipos de oximetría de pulso, en este caso los parámetros simulados por el OxSim OX-1 son SpO₂, frecuencia de pulso e índice de perfusión.

#### 1. Tolerancia para SpO₂

Según las especificaciones técnicas del monitor Mindray uMEC 100, la exactitud para SpO₂ es:

- Para pacientes adultos y pediátricos: ±2% en el rango de 70 % a 100 %.
- Para pacientes neonatales: ±3% en el rango de 70% a 100%.
- Por debajo de 70%, la exactitud no está especificada.

#### 2. Tolerancia para frecuencia de pulso

La frecuencia de pulso derivada de SpO₂ en el uMEC 100 tiene una exactitud aproximada de ±3 bpm 
(esto aplica dentro del rango operativo del equipo para frecuencia de pulso)

#### 3. Tolerancia para índice de perfusión

El índice de perfusión no tiene un error máximo permitido universal como ocurre con SpO₂ o frecuencia de pulso, esto se debe a que el PI se usa principalmente como un indicador de calidad de señal y de perfusión periférica, no como una variable clínica primaria para diagnóstico directo.

Por lo tanto, en una verificación práctica un PI cercano a 2,0 debe permitir una lectura estable de SpO₂ y frecuencia de pulso mientras que un PI cercano a 0,2 representa baja perfusión y puede generar lecturas más difíciles, inestables o sensibles al sensor utilizado.

En este caso, el criterio de aceptación no debe basarse únicamente en un error numérico del PI, sino en que el monitor sea capaz de detectar la señal y mostrar valores razonables de SpO₂ y pulso en condiciones de baja perfusión.

### Tabla resumen de tolerancias

| Parámetro fisiológico | Valor simulado por OxSim OX-1 | Tolerancia o EMP recomendado | Criterio de aceptación |
|---|---:|---:|---|
| SpO₂ | 85 %, 95 %, 98 %, 99 % | ±2 % adulto/pediátrico; ±3 % neonato | El valor mostrado debe estar dentro del rango permitido |
| Frecuencia de pulso | 40, 80 y 140 bpm | ±3 bpm | El valor mostrado debe estar dentro de ±3 bpm |
| Índice de perfusión | PI ≈ 2,0 o PI ≈ 0,2 | No tiene EMP clínico universal | Se evalúa estabilidad y capacidad de lectura |



## Parte B. Verificación experimental de alarmas en el monitor uMEC 100 usando el Pronk OxSim OX-1

## Objetivo 

Verificar el funcionamiento de las alarmas fisiológicas del monitor de signos vitales Mindray uMEC 100 utilizando el simulador óptico de oximetría de pulso Pronk OxSim OX-1, la práctica se enfoca en la evaluación de las alarmas asociadas a SpO₂ y frecuencia de pulso, además del registro de la forma de onda fotopletismográfica observada en el monitor.

## Fórmulas usadas para el cálculo del error
Para cada variable evaluada se calcularon el error absoluto y el error porcentual.

### Error absoluto

```text
Error absoluto = |Valor medido en el uMEC 100 - Valor simulado en el OxSim OX-1|
```

### Error porcentual

```text
Error porcentual = (Error absoluto / Valor simulado en el OxSim OX-1) × 100
```

Estas fórmulas se aplican para SpO₂, frecuencia de pulso / frecuencia cardiaca

## Tabla general para verificación de alarmas

| Prueba      | Límite configurado en uMEC 100 | Tipo de límite |     Valor simulado en OxSim OX-1 |  Valor mostrado en uMEC 100 | ¿Alarma activa? | Tiempo de respuesta | Observaciones                                            |
| ----------- | -----------------------------: | -------------- | -------------------------------: | --------------------------: | --------------- | ------------------: | -------------------------------------------------------- |
| Bradicardia |                FC baja: 50 bpm | Bajo FC        |                40 bpm, SpO₂ 95 % |     FC: 40 bpm / SpO₂: 96 % | Sí              |                 4 s | Se activó alarma por frecuencia cardíaca baja            |
| SpO₂ baja   |                           90 % | Bajo SpO₂      |                80 bpm, SpO₂ 85 % |     FC: 80 bpm / SpO₂: 83 % | Sí              |                 5 s | Se activó alarma sonora y visual después de 5 s          |
| SpO₂ alta   |                           97 % | Alto SpO₂      | 80 bpm, SpO₂ 99 %, Low Perfusion |     FC: 80 bpm / SpO₂: 99 % | Sí              |                 5 s | Se observó menor amplitud en la onda fotopletismográfica |
| Taquicardia |               FC alta: 120 bpm | Alto FC        |               140 bpm, SpO₂ 98 % | FC: 140,83 bpm / SpO₂: 97 % | Sí              |                 4 s | Se activó alarma de frecuencia cardíaca elevada          |

## Procedimiento experimental

La práctica inició con el encendido del monitor de signos vitales Mindray uMEC 100, posteriormente se verificó que el equipo cargara correctamente la pantalla principal de monitorización y se seleccionó el modo Monitor, correspondiente al modo de vigilancia clínica continua, después se revisó que el canal de SpO₂ estuviera activo y disponible para recibir la señal del sensor de pulsioximetría.

Posteriormente, se conectó la pinza de pulsioximetría del uMEC 100 al simulador Pronk OxSim OX-1, la pinza se ubicó sobre el dedo óptico del simulador, procurando que el emisor y el receptor del sensor quedaran bien alineados, continuando se esperó a que el monitor detectara la señal y estabilizara los valores de saturación de oxígeno y frecuencia de pulso en la pantalla.

Para la primera prueba, se configuró el OxSim OX-1 en una condición de paciente bradicárdico, simulando una frecuencia de pulso de 40 bpm y una SpO₂ de 95 %, cuando la lectura del uMEC 100 se estabilizó, se registraron los valores mostrados por el monitor para SpO₂ y frecuencia de pulso. Con estos datos se calcularon el error absoluto y el error porcentual, tomando como referencia los valores simulados por el OxSim.


# Prueba 1. Simulación de paciente bradicárdico

Se configuró el OxSim OX-1 para simular un paciente bradicárdico con los siguientes valores:

| Variable            |      Valor simulado |
| ------------------- | ------------------: |
| Frecuencia de pulso |              40 bpm |
| SpO₂                |                95 % |
| Índice de perfusión | Aproximadamente 2,0 |

Se registraron los valores mostrados por el D30 y se calcularon los errores absoluto y porcentual.

| Variable            | Valor simulado | Valor medido en D30 | Error absoluto | Error porcentual |
| ------------------- | -------------: | ------------------: | -------------: | ---------------: |
| SpO₂                |           95 % |                96 % |            1 % |           1,05 % |
| Frecuencia de pulso |         40 bpm |              40 bpm |          0 bpm |           0,00 % |

### Registro de la onda fotopletismográfica

Durante la simulación de bradicardia, la onda fotopletismográfica se observó con pulsos más separados entre sí, debido a que la frecuencia de pulso era baja. Esto indica que el intervalo entre cada pulso fue mayor en comparación con una frecuencia cardíaca normal.


[Onda fotopletismográfica - bradicardia](imagenes/onda_bradicardia.jpg)

### Interpretación

En esta prueba, el monitor mostró una lectura estable de la frecuencia de pulso, ya que el valor medido coincidió con el valor simulado. Para SpO₂ se presentó un error absoluto de 1 % y un error porcentual de 1,05 %, lo cual indica una diferencia baja entre el valor simulado y el valor mostrado por el monitor.

---

# Prueba 2. Verificación de alarma por SpO₂ baja

En el D30 se configuró el límite inferior de alarma de SpO₂ en:

```text
Límite inferior de SpO₂ = 90 %
```

Luego, se ajustó el OxSim OX-1 para simular:

| Variable            |      Valor simulado |
| ------------------- | ------------------: |
| Frecuencia de pulso |              60 bpm |
| SpO₂                |                85 % |
| Índice de perfusión | Aproximadamente 2,0 |

A partir del momento en que se seleccionó esta condición en el simulador, se contaron 5 segundos y se verificó si el monitor activaba alarma sonora y/o visual.

### Registro de alarma

| Límite configurado | Valor simulado | Valor medido en D30 | ¿Alarma activa? | Tiempo de respuesta | Tipo de alarma  |
| ------------------ | -------------: | ------------------: | --------------- | ------------------: | --------------- |
| SpO₂ baja: 90 %    |           85 % |                84 % | Sí              |                 5 s | Sonora y visual |

### Registro de errores

| Variable            | Valor simulado | Valor medido en D30 | Error absoluto | Error porcentual |
| ------------------- | -------------: | ------------------: | -------------: | ---------------: |
| SpO₂                |           85 % |                84 % |            1 % |           1,18 % |
| Frecuencia de pulso |         60 bpm |              60 bpm |          0 bpm |           0,00 % |

### Interpretación

Como el valor simulado de SpO₂ fue de 85 % y el límite inferior configurado fue de 90 %, se esperaba que el monitor activara una alarma de baja saturación. En esta prueba, el valor medido fue de 84 %, por lo tanto, se mantuvo por debajo del límite configurado. Debido a esto, se activó la alarma sonora y visual después de 5 segundos.

El error absoluto para SpO₂ fue de 1 % y el error porcentual fue de 1,18 %. Para la frecuencia de pulso no se presentó error, ya que el valor medido coincidió con el valor simulado.

```markdown
![Alarma por SpO2 baja](imagenes/alarma_spo2_baja.jpg)
```

---

# Prueba 3. Verificación de alarma por SpO₂ alta

En el D30 se configuró el límite superior de alarma de SpO₂ en:

```text
Límite superior de SpO₂ = 97 %
```

Luego, se ajustó el OxSim OX-1 para simular una SpO₂ de 99 %. A partir de ese instante, se contaron 5 segundos y se verificó la activación de la alarma sonora y/o visual.

| Variable            |      Valor simulado |
| ------------------- | ------------------: |
| Frecuencia de pulso |              80 bpm |
| SpO₂                |                99 % |
| Índice de perfusión | Aproximadamente 2,0 |

### Registro de alarma

| Límite configurado | Valor simulado | Valor medido en D30 | ¿Alarma activa? | Tiempo de respuesta | Tipo de alarma  |
| ------------------ | -------------: | ------------------: | --------------- | ------------------: | --------------- |
| SpO₂ alta: 97 %    |           99 % |                99 % | Sí              |                 5 s | Sonora y visual |

### Registro de errores

| Variable            | Valor simulado | Valor medido en D30 | Error absoluto | Error porcentual |
| ------------------- | -------------: | ------------------: | -------------: | ---------------: |
| SpO₂                |           99 % |                99 % |            0 % |           0,00 % |
| Frecuencia de pulso |         80 bpm |              80 bpm |          0 bpm |           0,00 % |

### Interpretación

Como el valor simulado de SpO₂ fue de 99 % y el límite superior configurado fue de 97 %, se esperaba que el monitor activara una alarma por saturación alta. En esta prueba, el monitor mostró una SpO₂ de 99 %, por lo que el valor estuvo por encima del límite configurado y se activó la alarma sonora y visual.

El error absoluto y porcentual para SpO₂ fueron de 0 %, ya que el valor medido coincidió con el valor simulado. La frecuencia de pulso también coincidió con el valor simulado, por lo que no presentó error.

```markdown
![Alarma por SpO2 alta](imagenes/alarma_spo2_alta.jpg)
```

---

# Prueba 4. Modo Low Perfusion

En el OxSim OX-1 se seleccionó el modo **Low Perfusion** para evaluar si el monitor D30 mantenía la lectura de SpO₂ cuando la señal pulsátil era débil.

| Variable            |      Valor simulado |
| ------------------- | ------------------: |
| Frecuencia de pulso |              80 bpm |
| SpO₂                |                99 % |
| Índice de perfusión | Aproximadamente 0,2 |

### Registro de lectura

| Variable            | Valor simulado | Valor medido en D30 | Error absoluto | Error porcentual |
| ------------------- | -------------: | ------------------: | -------------: | ---------------: |
| SpO₂                |           99 % |                98 % |            1 % |           1,01 % |
| Frecuencia de pulso |         80 bpm |              80 bpm |          0 bpm |           0,00 % |

### Pregunta: ¿Mantiene el monitor D30 la lectura de SpO₂?

Respuesta:
Sí. El monitor mantuvo la lectura de SpO₂, aunque se observó una ligera variación del valor mostrado. La SpO₂ simulada fue de 99 % y el monitor mostró 98 %, por lo que la lectura se mantuvo cercana al valor esperado.


### Pregunta: ¿La onda fotopletismográfica se distorsiona?

Respuesta:
Sí. En el modo Low Perfusion la onda fotopletismográfica se observó con menor amplitud y menor estabilidad en comparación con las pruebas de perfusión normal. Esto ocurre porque el índice de perfusión disminuye aproximadamente a 0,2, lo que representa una señal pulsátil más débil para el sensor de SpO₂.


### Interpretación

En el modo **Low Perfusion**, el índice de perfusión disminuye aproximadamente a 0,2, lo que representa una señal pulsátil débil para el sensor de SpO₂. Debido a esto, la onda fotopletismográfica puede observarse con menor amplitud, menor estabilidad o con ligeras distorsiones en comparación con una condición de perfusión normal.

Esta condición permite evaluar si el monitor mantiene una lectura confiable de SpO₂ y frecuencia de pulso cuando la señal recibida es débil. En esta prueba, el monitor mantuvo una lectura cercana al valor simulado, aunque la onda presentó menor amplitud. Esto indica que el equipo logró interpretar la señal, pero con una condición de medición más exigente.

```markdown
![Onda fotopletismográfica - baja perfusión](imagenes/onda_low_perfusion.jpg)
```

---

# Prueba 5. Simulación de taquicardia

Con un valor de SpO₂ de 95 %, se configuró el OxSim OX-1 para simular una taquicardia de 150 bpm. Posteriormente, se observó la respuesta del monitor D30, se registró la onda fotopletismográfica y se verificó si se activaba la alarma de frecuencia cardíaca elevada.

| Variable            |      Valor simulado |
| ------------------- | ------------------: |
| Frecuencia de pulso |             150 bpm |
| SpO₂                |                95 % |
| Índice de perfusión | Aproximadamente 2,0 |

### Registro de alarma

| Límite configurado | Valor simulado | Valor medido en D30 | ¿Alarma activa? | Tiempo de respuesta | Tipo de alarma  |
| ------------------ | -------------: | ------------------: | --------------- | ------------------: | --------------- |
| FC alta: 120 bpm   |        150 bpm |             149 bpm | Sí              |                 4 s | Sonora y visual |

### Registro de errores

| Variable            | Valor simulado | Valor medido en D30 | Error absoluto | Error porcentual |
| ------------------- | -------------: | ------------------: | -------------: | ---------------: |
| SpO₂                |           95 % |                95 % |            0 % |           0,00 % |
| Frecuencia de pulso |        150 bpm |             149 bpm |          1 bpm |           0,67 % |

### Pregunta: ¿Se dispara la alarma de frecuencia cardíaca elevada?

Sí. La alarma de frecuencia cardíaca elevada se activó porque el valor simulado fue de 150 bpm y el límite superior configurado en el monitor fue de 120 bpm. Como la frecuencia medida por el D30 fue de 149 bpm, el valor superó el límite establecido y el monitor generó alarma sonora y visual.


### Registro de la onda fotopletismográfica

Durante la simulación de taquicardia, la onda fotopletismográfica se observó con pulsos más cercanos entre sí, debido al aumento de la frecuencia cardíaca. Esto ocurre porque el intervalo entre cada pulso disminuye cuando la frecuencia de pulso aumenta.

```markdown
![Onda fotopletismográfica - taquicardia](imagenes/onda_taquicardia.jpg)
```

### Interpretación

En esta prueba, el monitor identificó una frecuencia cardíaca elevada. El valor simulado fue de 150 bpm y el valor medido fue de 149 bpm, por lo que el error absoluto fue de 1 bpm y el error porcentual fue de 0,67 %. La SpO₂ no presentó error, ya que el valor medido coincidió con el valor simulado.

Como el límite superior de frecuencia cardíaca estaba configurado en 120 bpm, el valor medido superó dicho límite y se activó la alarma de taquicardia. Esto demuestra que el monitor respondió adecuadamente ante una condición simulada de frecuencia cardíaca elevada.

---

## Tabla resumen de errores

| Prueba        | SpO₂ simulada | SpO₂ medida | Error absoluto SpO₂ | Error porcentual SpO₂ | FC simulada | FC medida | Error absoluto FC | Error porcentual FC |
| ------------- | ------------: | ----------: | ------------------: | --------------------: | ----------: | --------: | ----------------: | ------------------: |
| Bradicardia   |          95 % |        96 % |                 1 % |                1,05 % |      40 bpm |    40 bpm |             0 bpm |              0,00 % |
| SpO₂ baja     |          85 % |        84 % |                 1 % |                1,18 % |      60 bpm |    60 bpm |             0 bpm |              0,00 % |
| SpO₂ alta     |          99 % |        99 % |                 0 % |                0,00 % |      80 bpm |    80 bpm |             0 bpm |              0,00 % |
| Low Perfusion |          99 % |        98 % |                 1 % |                1,01 % |      80 bpm |    80 bpm |             0 bpm |              0,00 % |
| Taquicardia   |          95 % |        95 % |                 0 % |                0,00 % |     150 bpm |   149 bpm |             1 bpm |              0,67 % |

---

## Análisis general

Los resultados simulados permiten verificar el comportamiento del monitor D30 frente a diferentes condiciones fisiológicas y patológicas. En la prueba de bradicardia, el monitor identificó una frecuencia de pulso baja y mantuvo una lectura estable de SpO₂. En la prueba de SpO₂ baja, el valor medido estuvo por debajo del límite inferior configurado de 90 %, por lo que se activó la alarma correspondiente.

En la prueba de SpO₂ alta, el valor medido superó el límite superior configurado de 97 %, activando la alarma visual y sonora. En el modo Low Perfusion, el monitor mantuvo la lectura de SpO₂, aunque la onda fotopletismográfica presentó menor amplitud y menor estabilidad debido a la baja perfusión simulada. Finalmente, en la prueba de taquicardia, la frecuencia medida superó el límite superior configurado, por lo que se activó la alarma de frecuencia cardíaca elevada.

En general, los errores calculados fueron bajos. Esto indica que el monitor mostró valores cercanos a los simulados por el OxSim OX-1 y respondió adecuadamente ante las condiciones de alarma configuradas.



# Parte C. Documentación de la práctica

## Procedimiento seguido

La práctica inició con la revisión técnica del monitor de signos vitales y del simulador **Pronk OxSim OX-1**, con el fin de identificar los parámetros que podían evaluarse durante la verificación experimental. Posteriormente, se encendió el monitor y se configuró en modo de monitorización para permitir la adquisición de las señales fisiológicas simuladas.

Después, se conectó la pinza de pulsioximetría, correspondiente al sensor de SpO₂, al simulador Pronk OxSim OX-1. La pinza se ubicó sobre el dedo óptico del simulador, verificando que el emisor y el receptor del sensor quedaran correctamente alineados. Luego, se esperó a que el monitor detectara la señal, estabilizara los valores de SpO₂ y frecuencia de pulso, y mostrara la onda fotopletismográfica en pantalla.

Una vez estabilizada la lectura, se realizaron diferentes pruebas de simulación: bradicardia, saturación baja, saturación alta, baja perfusión y taquicardia. En cada prueba se registraron los valores simulados por el OxSim OX-1, los valores mostrados por el monitor, el tiempo de respuesta de las alarmas, la activación visual o sonora y la forma de onda fotopletismográfica observada.

Para evaluar el comportamiento del monitor, se calcularon el error absoluto y el error porcentual para cada variable medida. Estos cálculos permitieron comparar los valores de referencia generados por el simulador con los valores mostrados por el monitor. Además, se analizaron las condiciones en las que se activaron las alarmas y la estabilidad de la señal fotopletismográfica.

---

## Fórmulas utilizadas

Para cada variable evaluada se calcularon el error absoluto y el error porcentual.

```text
Error absoluto = |Valor medido - Valor simulado|
```

```text
Error porcentual = (Error absoluto / Valor simulado) × 100
```

---

## Resultados generales

| Prueba        | SpO₂ simulada | SpO₂ medida | Error SpO₂ | FC simulada | FC medida | Error FC | Alarma esperada                          | Alarma observada |
| ------------- | ------------: | ----------: | ---------: | ----------: | --------: | -------: | ---------------------------------------- | ---------------- |
| Bradicardia   |          95 % |        96 % |        1 % |      40 bpm |    40 bpm |    0 bpm | FC baja                                  | Sí               |
| SpO₂ baja     |          85 % |        84 % |        1 % |      60 bpm |    60 bpm |    0 bpm | SpO₂ baja                                | Sí               |
| SpO₂ alta     |          99 % |        99 % |        0 % |      80 bpm |    80 bpm |    0 bpm | SpO₂ alta                                | Sí               |
| Low Perfusion |          99 % |        98 % |        1 % |      80 bpm |    80 bpm |    0 bpm | No necesariamente; se evalúa estabilidad | No               |
| Taquicardia   |          95 % |        95 % |        0 % |     150 bpm |   149 bpm |    1 bpm | FC alta                                  | Sí               |

---

## Análisis de resultados

Los resultados obtenidos permiten comparar los valores simulados por el OxSim OX-1 con los valores mostrados por el monitor. Esta comparación es importante porque permite verificar si el equipo responde adecuadamente ante condiciones fisiológicas y patológicas simuladas, y si las alarmas se activan cuando las variables superan los límites configurados.

En la prueba de bradicardia, el simulador generó una frecuencia de pulso de 40 bpm y una SpO₂ de 95 %. El monitor mostró una frecuencia de 40 bpm y una SpO₂ de 96 %, por lo que la frecuencia no presentó error y la SpO₂ tuvo un error absoluto de 1 %. Este resultado indica que el monitor mantuvo una lectura estable durante la simulación de frecuencia cardíaca baja. Además, la onda fotopletismográfica se observó con los pulsos más separados entre sí, lo cual es coherente con una frecuencia cardíaca disminuida.

En la prueba de SpO₂ baja, se configuró el límite inferior de alarma en 90 % y se simuló una saturación de 85 %. El monitor mostró una SpO₂ de 84 %, por lo que el valor estuvo por debajo del límite configurado. Debido a esto, se activó la alarma sonora y visual después de 5 segundos. El error absoluto fue de 1 % y el error porcentual fue de 1,18 %, lo que indica que la medición fue cercana al valor simulado.

En la prueba de SpO₂ alta, se configuró el límite superior de alarma en 97 % y se simuló una SpO₂ de 99 %. El monitor también mostró 99 %, por lo que no se presentó error en esta variable. Como el valor medido superó el límite superior configurado, se activó la alarma correspondiente. Esto evidencia que el monitor detectó correctamente una condición fuera del rango establecido.

En el modo Low Perfusion, se simuló una condición de baja perfusión con SpO₂ de 99 %, frecuencia de 80 bpm e índice de perfusión aproximado de 0,2. El monitor mantuvo la lectura de SpO₂ con un valor cercano al simulado, mostrando 98 %. Sin embargo, la onda fotopletismográfica presentó menor amplitud y menor estabilidad en comparación con las pruebas de perfusión normal. Esto ocurre porque la señal pulsátil es más débil y el monitor debe interpretar una señal de menor calidad.

En la prueba de taquicardia, se simuló una frecuencia cardíaca de 150 bpm con SpO₂ de 95 %. El monitor registró una frecuencia de 149 bpm y una SpO₂ de 95 %. El error absoluto de frecuencia fue de 1 bpm y el error porcentual fue de 0,67 %. Como el límite superior de frecuencia cardíaca se configuró en 120 bpm, el monitor activó la alarma de frecuencia elevada. Además, la onda fotopletismográfica se observó con pulsos más cercanos entre sí, debido al aumento de la frecuencia cardíaca.

En general, los errores calculados fueron bajos. Esto indica que el monitor mostró valores cercanos a los simulados por el OxSim OX-1 y respondió adecuadamente ante las condiciones de alarma configuradas. También se evidenció que la calidad de la señal influye en la estabilidad de la medición, especialmente durante la prueba de baja perfusión.

---

## Relación entre la onda fotopletismográfica y la frecuencia cardíaca

La onda fotopletismográfica representa los cambios pulsátiles detectados por el sensor de SpO₂. Cuando la frecuencia cardíaca es baja, como en la prueba de bradicardia, los pulsos se observan más separados porque el intervalo entre cada latido es mayor.

En cambio, durante la taquicardia, los pulsos aparecen más cercanos entre sí porque el corazón late con mayor frecuencia y el intervalo entre pulsos disminuye. Por esta razón, la forma de onda permite relacionar visualmente la frecuencia de pulso con el patrón observado en pantalla.

La amplitud de la onda también se relaciona con la calidad de la señal. En condiciones de buena perfusión, la onda suele observarse más definida y estable. En baja perfusión, la amplitud puede disminuir y la señal puede volverse más inestable, lo cual puede afectar la confiabilidad de la lectura de SpO₂.

---


## Preguntas para la discusión

### Pregunta 1. ¿Cuál es el principio de operación del Pronk OxSim OX-1 para simular una onda pulsátil?

El Pronk OxSim OX-1 funciona como un simulador óptico de oximetría de pulso. Su principio de operación consiste en generar una señal óptica equivalente a la que produciría un dedo humano durante la medición de SpO₂. Para esto, el simulador modifica la transmisión de luz roja e infrarroja recibida por el sensor de pulsioximetría, imitando los cambios pulsátiles asociados al flujo sanguíneo arterial.

El oxímetro interpreta estas variaciones ópticas como si provinieran de un paciente real. A partir de la relación entre la absorción de luz roja e infrarroja, el monitor estima la saturación periférica de oxígeno. Además, la frecuencia de las variaciones pulsátiles permite simular diferentes frecuencias de pulso, como 40 bpm, 80 bpm o 140 bpm.

Por esta razón, el OxSim OX-1 permite verificar si el monitor detecta correctamente la SpO₂, la frecuencia de pulso y la señal fotopletismográfica bajo diferentes condiciones simuladas.

### Pregunta 2. ¿Por qué la SpO₂ baja puede ser un falso positivo en una situación de mala perfusión?

La SpO₂ baja puede convertirse en un falso positivo cuando existe mala perfusión periférica porque el oxímetro depende de una señal pulsátil arterial adecuada para estimar la saturación de oxígeno. Si la perfusión es baja, la señal detectada por el sensor puede tener poca amplitud, ser inestable o confundirse con ruido, movimiento o interferencias.

En estas condiciones, el monitor puede interpretar incorrectamente la señal y mostrar una saturación baja aunque la oxigenación real del paciente no esté disminuida. Por eso, una alarma de SpO₂ baja no siempre significa hipoxemia real; también puede indicar mala calidad de señal, mala colocación del sensor, baja perfusión periférica, movimiento del paciente o problemas en el sensor.

En el modo Low Perfusion del OxSim OX-1 se simula precisamente una condición de baja amplitud de señal, lo cual permite observar si el monitor mantiene una lectura estable o si la onda fotopletismográfica se distorsiona.

## Conclusión

La práctica permitió verificar el comportamiento del monitor de signos vitales frente a diferentes condiciones simuladas mediante el Pronk OxSim OX-1. Se evaluaron escenarios de bradicardia, SpO₂ baja, SpO₂ alta, baja perfusión y taquicardia, observando la respuesta del monitor, la activación de alarmas y la forma de onda fotopletismográfica.

Los errores obtenidos fueron bajos en todas las pruebas. La SpO₂ presentó diferencias entre 0 % y 1 %, mientras que la frecuencia de pulso presentó errores de 0 bpm en la mayoría de las pruebas y de 1 bpm en la prueba de taquicardia. Esto indica que el monitor mostró lecturas cercanas a los valores simulados por el OxSim OX-1.

También se comprobó que las alarmas se activaron correctamente cuando los valores simulados superaron los límites configurados. La alarma de SpO₂ baja se activó cuando la saturación estuvo por debajo de 90 %, la alarma de SpO₂ alta se activó cuando el valor superó 97 % y la alarma de frecuencia cardíaca elevada se activó durante la simulación de taquicardia.

Sin embargo, se observó que la confiabilidad de la medición depende de la calidad de la señal. En condiciones de baja perfusión, la onda fotopletismográfica puede disminuir su amplitud y volverse menos estable, lo cual puede afectar la lectura de SpO₂. Por esta razón, el personal biomédico y clínico no debe interpretar únicamente el valor numérico, sino también la calidad de la onda y las condiciones de medición.

El OxSim OX-1 es una herramienta útil para verificar el canal de oximetría de pulso y la respuesta de alarmas del monitor. No obstante, presenta limitaciones porque simula condiciones controladas y no reproduce por completo la complejidad de un paciente real, donde pueden intervenir factores como movimiento, baja temperatura periférica, mala colocación del sensor, interferencia lumínica o alteraciones fisiológicas reales.

## Moraleja

La principal enseñanza de este laboratorio es que un monitor de signos vitales no debe evaluarse únicamente por los valores numéricos que muestra en pantalla, sino también por la calidad de la señal, la correcta configuración de las alarmas y las condiciones en las que se realiza la medición. Aunque el simulador permite recrear escenarios como bradicardia, baja saturación, baja perfusión y taquicardia, en un paciente real pueden existir factores que afecten la lectura, como mala colocación del sensor, movimiento o baja perfusión periférica. Por eso, el ingeniero biomédico debe interpretar los resultados de forma crítica, verificando tanto la precisión del equipo como su respuesta ante situaciones de riesgo clínico.


### Referencias

1. Pronk Technologies. *OxSim SpO₂ Simulator Operator’s Manual*. Rev. 07/18/2017. Disponible en:  
   https://mtk-biomed.com/wp-content/uploads/2021/10/OX1_OxSim.pdf

2. Mindray. *uMEC 100/120/150 Patient Monitor Data Sheet*. Disponible en:  
   https://healthtechghana.com/wp-content/uploads/2024/07/Datasheet_uMEC-100-120-150_20230628.pdf

3. Mindray. *uMEC Patient Monitor Operator’s Manual*. Disponible en:  
   https://mindray.sy/wp-content/uploads/2019/09/uMEC-Operator%E2%80%99s-Manual.pdf

4. ISO 80601-2-61:2017. *Medical electrical equipment — Particular requirements for basic safety and essential performance of pulse oximeter equipment*.
