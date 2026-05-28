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

| Prueba      | Límite configurado en uMEC 100 | Tipo de límite |     Valor simulado en OxSim OX-1 | Valor mostrado en uMEC 100 | ¿Alarma activa? | Tiempo de respuesta | Observaciones                                   |
| ----------- | -----------------------------: | -------------- | -------------------------------: | -------------------------: | --------------- | ------------------: | ----------------------------------------------- |
| Bradicardia |  No aplica / valor por defecto | Bajo FC        |                40 bpm, SpO₂ 95 % |  FC: ___ bpm / SpO₂: ___ % | Sí / No         |               ___ s | Registrar si aparece alarma de FC baja          |
| SpO₂ baja   |                           90 % | Bajo SpO₂      |                80 bpm, SpO₂ 85 % |  FC: ___ bpm / SpO₂: ___ % | Sí / No         |               ___ s | Verificar alarma sonora y visual después de 5 s |
| SpO₂ alta   |                           97 % | Alto SpO₂      | 80 bpm, SpO₂ 99 %, Low Perfusion |  FC: ___ bpm / SpO₂: ___ % | Sí / No         |               ___ s | Registrar si la onda se distorsiona             |
| Taquicardia |     Valor configurado: ___ bpm | Alto FC        |               140 bpm, SpO₂ 98 % |  FC: ___ bpm / SpO₂: ___ % | Sí / No         |               ___ s | Registrar si se activa alarma de FC elevada     |

## Procedimiento experimental
La práctica inició con el encendido del monitor de signos vitales Mindray uMEC 100, posteriormente se verificó que el equipo cargara correctamente la pantalla principal de monitorización y se seleccionó el modo Monitor, correspondiente al modo de vigilancia clínica continua, después se revisó que el canal de SpO₂ estuviera activo y disponible para recibir la señal del sensor de pulsioximetría.

Posteriormente, se conectó la pinza de pulsioximetría del uMEC 100 al simulador Pronk OxSim OX-1, la pinza se ubicó sobre el dedo óptico del simulador, procurando que el emisor y el receptor del sensor quedaran bien alineados, continuando se esperó a que el monitor detectara la señal y estabilizara los valores de saturación de oxígeno y frecuencia de pulso en la pantalla.

Para la primera prueba, se configuró el OxSim OX-1 en una condición de paciente bradicárdico, simulando una frecuencia de pulso de 40 bpm y una SpO₂ de 95 %, cuando la lectura del uMEC 100 se estabilizó, se registraron los valores mostrados por el monitor para SpO₂ y frecuencia de pulso. Con estos datos se calcularon el error absoluto y el error porcentual, tomando como referencia los valores simulados por el OxSim.

Prueba 1. Simulación de paciente bradicárdico
Se configuró el OxSim OX-1 para simular un paciente bradicárdico con los siguientes valores:

| Variable            |      Valor simulado |
| ------------------- | ------------------: |
| Frecuencia de pulso |              40 bpm |
| SpO₂                |                95 % |
| Índice de perfusión | Aproximadamente 2,0 |

Se registraron los valores mostrados por el uMEC 100 y se calcularon los errores absoluto y porcentual.

| Variable            | Valor simulado | Valor medido en uMEC 100 | Error absoluto | Error porcentual |
| ------------------- | -------------: | -----------------------: | -------------: | ---------------: |
| SpO₂                |           95 % |                    ___ % |          ___ % |            ___ % |
| Frecuencia de pulso |         40 bpm |                  ___ bpm |        ___ bpm |            ___ % |


Después de esta prueba, se configuró en el uMEC 100 el límite inferior de alarma de SpO₂ en 90 %, luego se ajustó el OxSim OX-1 para simular una frecuencia de pulso de 80 bpm y una SpO₂ de 85%, desde el momento en que se seleccionó esta condición en el simulador, se contaron 5 segundos y se verificó si el monitor activaba una alarma visual, sonora o ambas, también se registraron los valores medidos por el uMEC 100 y se calcularon nuevamente los errores absoluto y porcentual para SpO₂ y frecuencia de pulso.

## Prueba 2. Verificación de alarma por SpO₂ baja

En el uMEC 100 se configuró el límite inferior de alarma de SpO₂ en:

```text
Límite inferior de SpO₂ = 90 %
```

Luego, se ajustó el OxSim OX-1 para simular:

| Variable            |      Valor simulado |
| ------------------- | ------------------: |
| Frecuencia de pulso |              80 bpm |
| SpO₂                |                85 % |
| Índice de perfusión | Aproximadamente 2,0 |

A partir del momento en que se seleccionó este modo en el simulador, se contaron **5 segundos** y se verificó si el monitor activaba alarma sonora y/o visual.

### Registro de alarma

| Límite configurado | Valor simulado | Valor medido en uMEC 100 | ¿Alarma activa? | Tiempo de respuesta | Tipo de alarma          |
| ------------------ | -------------: | -----------------------: | --------------- | ------------------: | ----------------------- |
| SpO₂ baja: 90 %    |           85 % |                    ___ % | Sí / No         |               ___ s | Sonora / Visual / Ambas |

### Registro de errores

| Variable            | Valor simulado | Valor medido en uMEC 100 | Error absoluto | Error porcentual |
| ------------------- | -------------: | -----------------------: | -------------: | ---------------: |
| SpO₂                |           85 % |                    ___ % |          ___ % |            ___ % |
| Frecuencia de pulso |         80 bpm |                  ___ bpm |        ___ bpm |            ___ % |

### Interpretación esperada

Como el valor simulado de SpO₂ es 85% y el límite inferior configurado fue 90%, se espera que el uMEC 100 active una alarma de baja saturación. Esta alarma puede ser visual, sonora o ambas, dependiendo de la configuración del monitor.

A continuación, se configuró en el uMEC 100 el límite superior de alarma de SpO₂ en 97%, luego se ajustó el OxSim OX-1 en el modo Low Perfusion**, simulando una SpO₂ de 99% y una frecuencia de pulso de 80 bpm, una vez activado este modo se contaron 5 segundos y se verificó la activación de la alarma visual o sonora en el monitor, en esta prueba también se registraron los valores mostrados por el uMEC 100, se calcularon los errores correspondientes y se observó si la onda fotopletismográfica presentaba distorsión, disminución de amplitud o inestabilidad debido a la baja perfusión simulada.

## Prueba 3. Verificación de alarma por SpO₂ alta en modo Low Perfusion

En el uMEC 100 se configuró el límite superior de alarma de SpO₂ en:

```text
Límite superior de SpO₂ = 97 %
```

Luego, se configuró el OxSim OX-1 en modo **Low Perfusion**, con los siguientes valores:

| Variable            |      Valor simulado |
| ------------------- | ------------------: |
| Frecuencia de pulso |              80 bpm |
| SpO₂                |                99 % |
| Índice de perfusión | Aproximadamente 0,2 |

A partir del momento en que se seleccionó el modo de baja perfusión, se contaron **5 segundos** y se verificó si el monitor activaba alarma sonora y/o visual.

### Registro de alarma

| Límite configurado | Valor simulado | Valor medido en uMEC 100 | ¿Alarma activa? | Tiempo de respuesta | Tipo de alarma          |
| ------------------ | -------------: | -----------------------: | --------------- | ------------------: | ----------------------- |
| SpO₂ alta: 97 %    |           99 % |                    ___ % | Sí / No         |               ___ s | Sonora / Visual / Ambas |

### Registro de errores

| Variable            | Valor simulado | Valor medido en uMEC 100 | Error absoluto | Error porcentual |
| ------------------- | -------------: | -----------------------: | -------------: | ---------------: |
| SpO₂                |           99 % |                    ___ % |          ___ % |            ___ % |
| Frecuencia de pulso |         80 bpm |                  ___ bpm |        ___ bpm |            ___ % |

### Pregunta: ¿La onda fotopletismográfica se distorsiona?

```text
Respuesta:
____________________________________________________
____________________________________________________
```

### Interpretación esperada

En el modo **Low Perfusion**, el índice de perfusión disminuye aproximadamente a 0,2. Esto significa que la señal pulsátil simulada es más débil. Por esta razón, la onda fotopletismográfica puede verse de menor amplitud, menos estable o con mayor dificultad para ser interpretada por el monitor.

Se debe insertar una imagen de la onda observada:

```markdown
![Onda fotopletismográfica - baja perfusión](imagenes/onda_low_perfusion.jpg)
```

---

Finalmente, se configuró el OxSim OX-1 para simular una condición de taquicardia, con una frecuencia de pulso de 140 bpm y una SpO₂ de 98%, se observó la respuesta del uMEC 100 y se verificó si se activaba la alarma de frecuencia cardiaca elevada, dependiendo del límite superior configurado en el monitor, también se registró la onda fotopletismográfica observada, junto con los valores medidos de SpO₂ y frecuencia de pulso. Con estos datos se calcularon el error absoluto y el error porcentual para cada variable.

## Prueba 4. Simulación de taquicardia

Se configuró el OxSim OX-1 para simular una frecuencia elevada con los siguientes valores:

| Variable            |      Valor simulado |
| ------------------- | ------------------: |
| Frecuencia de pulso |             140 bpm |
| SpO₂                |                98 % |
| Índice de perfusión | Aproximadamente 2,0 |

Se observó si el uMEC 100 activó una alarma de frecuencia cardiaca elevada.

### Registro de alarma

| Límite configurado | Valor simulado | Valor medido en uMEC 100 | ¿Alarma activa? | Tiempo de respuesta | Tipo de alarma          |
| ------------------ | -------------: | -----------------------: | --------------- | ------------------: | ----------------------- |
| FC alta: ___ bpm   |        140 bpm |                  ___ bpm | Sí / No         |               ___ s | Sonora / Visual / Ambas |

### Registro de errores

| Variable            | Valor simulado | Valor medido en uMEC 100 | Error absoluto | Error porcentual |
| ------------------- | -------------: | -----------------------: | -------------: | ---------------: |
| SpO₂                |           98 % |                    ___ % |          ___ % |            ___ % |
| Frecuencia de pulso |        140 bpm |                  ___ bpm |        ___ bpm |            ___ % |

### Pregunta: ¿Se dispara la alarma de frecuencia cardiaca elevada?

```text
Respuesta:
____________________________________________________
____________________________________________________
```

Se debe insertar una imagen de la onda observada:

```markdown
![Onda fotopletismográfica - taquicardia](imagenes/onda_taquicardia.jpg)
```

Al finalizar las pruebas, se organizaron los datos obtenidos en tablas de resultados, incluyendo los valores simulados, los valores medidos por el uMEC 100, los errores calculados, la activación o no de las alarmas y el tiempo de respuesta observado. Además, se tomaron fotografías del montaje experimental, de la conexión entre el sensor y el simulador, de las alarmas activadas y de las ondas fotopletismográficas mostradas en pantalla, con el fin de incluirlas como evidencia dentro del repositorio de GitHub.





# Parte C. Documentación de la práctica

## Procedimiento seguido

La práctica inició con la revisión técnica del monitor **Mindray uMEC 100** y del simulador **Pronk OxSim OX-1**, con el fin de identificar los parámetros que podían evaluarse durante la verificación experimental. Posteriormente, se encendió el monitor uMEC 100 y se configuró en modo Monitor para realizar la adquisición de señales fisiológicas.

Después, se conectó el sensor de SpO₂ del monitor al simulador OxSim OX-1. Se verificó que la pinza de pulsioximetría estuviera correctamente ubicada sobre el simulador y que el monitor detectara la señal. Una vez estabilizada la lectura, se realizaron diferentes pruebas de simulación: bradicardia, saturación baja, baja perfusión y taquicardia.

En cada prueba se registraron los valores simulados por el OxSim OX-1 y los valores mostrados por el uMEC 100. Con estos datos se calcularon el error absoluto y el error porcentual para SpO₂ y frecuencia de pulso. Además, se observó la forma de onda fotopletismográfica mostrada en pantalla y se verificó si las alarmas visuales o sonoras se activaban de acuerdo con los límites configurados.

---

## Resultados generales

| Prueba                      | SpO₂ simulada | SpO₂ medida | FC simulada | FC medida | Alarma esperada                                              | Alarma observada |
| --------------------------- | ------------: | ----------: | ----------: | --------: | ------------------------------------------------------------ | ---------------- |
| Bradicardia                 |          95 % |       ___ % |      40 bpm |   ___ bpm | FC baja, si está configurada                                 | Sí / No          |
| SpO₂ baja                   |          85 % |       ___ % |      80 bpm |   ___ bpm | SpO₂ baja                                                    | Sí / No          |
| SpO₂ alta en baja perfusión |          99 % |       ___ % |      80 bpm |   ___ bpm | SpO₂ alta                                                    | Sí / No          |
| Taquicardia                 |          98 % |       ___ % |     140 bpm |   ___ bpm | FC alta, si el límite está configurado por debajo de 140 bpm | Sí / No          |

---

## Análisis

Los resultados obtenidos permiten comparar los valores simulados por el OxSim OX-1 con los valores mostrados por el monitor uMEC 100. Esta comparación es importante porque permite verificar si el monitor se encuentra dentro de los rangos de exactitud esperados para SpO₂ y frecuencia de pulso.

En la prueba de SpO₂ baja, se esperaba la activación de la alarma debido a que el valor simulado de 85 % estaba por debajo del límite inferior configurado de 90 %. En la prueba de SpO₂ alta, se esperaba la activación de la alarma porque el valor simulado de 99 % superaba el límite superior configurado de 97 %. En la prueba de taquicardia, la activación de la alarma dependía del límite superior de frecuencia cardiaca configurado en el monitor.

En el modo de baja perfusión, la onda fotopletismográfica podía presentar menor amplitud o mayor inestabilidad debido a que el índice de perfusión simulado era menor. Esto representa una condición más exigente para el monitor y permite observar su capacidad para detectar señales de baja amplitud.

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

La práctica permitió verificar el comportamiento del monitor **Mindray uMEC 100** frente a diferentes condiciones simuladas mediante el **Pronk OxSim OX-1**. Se evaluaron escenarios de bradicardia, SpO₂ baja, SpO₂ alta en baja perfusión y taquicardia, observando la respuesta del monitor, la activación de alarmas y la forma de onda fotopletismográfica.

A partir de los valores simulados y los valores medidos por el uMEC 100, se calcularon los errores absoluto y porcentual para SpO₂ y frecuencia de pulso. Esto permitió analizar la precisión del monitor y verificar si sus lecturas se encontraban dentro de los rangos de tolerancia esperados.

El uMEC 100 mostró ser útil para la monitorización continua y para la detección de condiciones fisiológicas fuera de los límites configurados. Sin embargo, la confiabilidad de la medición depende de la calidad de la señal, la correcta colocación del sensor y la perfusión periférica simulada. En condiciones de baja perfusión, la onda fotopletismográfica puede disminuir su amplitud o volverse menos estable, lo que puede afectar la lectura de SpO₂.

El OxSim OX-1 es una herramienta útil para comprobar el canal de oximetría de pulso y la respuesta de alarmas del monitor, pero tiene limitaciones porque no reproduce completamente la complejidad de un paciente real. Su simulación se centra en SpO₂, frecuencia de pulso e índice de perfusión, por lo que no permite evaluar de forma completa todos los parámetros cardiovasculares o hemodinámicos de un paciente.

### Referencias

1. Pronk Technologies. *OxSim SpO₂ Simulator Operator’s Manual*. Rev. 07/18/2017. Disponible en:  
   https://mtk-biomed.com/wp-content/uploads/2021/10/OX1_OxSim.pdf

2. Mindray. *uMEC 100/120/150 Patient Monitor Data Sheet*. Disponible en:  
   https://healthtechghana.com/wp-content/uploads/2024/07/Datasheet_uMEC-100-120-150_20230628.pdf

3. Mindray. *uMEC Patient Monitor Operator’s Manual*. Disponible en:  
   https://mindray.sy/wp-content/uploads/2019/09/uMEC-Operator%E2%80%99s-Manual.pdf

4. ISO 80601-2-61:2017. *Medical electrical equipment — Particular requirements for basic safety and essential performance of pulse oximeter equipment*.
