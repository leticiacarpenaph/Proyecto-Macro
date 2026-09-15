Objetivos, datos a utilizar y problema a resolver
# Factores que explican el nivel de actividad económica por departamento en Uruguay



## Problema a resolver

¿Qué factores socioeconómicos explican las diferencias en el nivel de actividad económica entre los departamentos de Uruguay? Uruguay presenta una fuerte heterogeneidad territorial en su desarrollo económico, concentrada históricamente en el área metropolitana. Este trabajo busca identificar qué variables demográficas, laborales, educativas y sociales están asociadas a un mayor o menor nivel de actividad económica departamental, y en qué medida lo explican.

## Objetivo general

Identificar y cuantificar los factores que explican el nivel de actividad económica por departamento en Uruguay, mediante un modelo estadístico que use variables socioeconómicas como predictoras.

## Objetivos específicos

- Construir un dataset panel (departamento × año) integrando el índice de actividad económica departamental con variables socioeconómicas de fuentes oficiales.
- Explorar mediante análisis exploratorio (EDA) la relación entre cada variable predictora y el nivel de actividad económica. ???
- Estimar un modelo de regresión (lineal múltiple / panel data) que explique el peso relativo de cada factor. ???
- Identificar departamentos cuyo nivel de actividad económica se desvía de lo que predice su perfil socioeconómico (análisis de residuos).

## Datos a utilizar

Panel departamento-año, 19 departamentos, período acotado a **2008-2018** .

### Variable dependiente

| Variable | Fuente | Link | Período |
|---|---|---|---|
| Índice Departamental de Actividad Económica (IDAE) / Participación departamental en la actividad económica | OPP — Observatorio Territorio Uruguay (OTU) | https://otu.opp.gub.uy/mapa?id=2180 (tabla de datos: https://otu.opp.gub.uy?q=listados/listados_datos_formato&id=2180&deptos=1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19&fecha=2016-01-01) | 2008-2018 |

### Variables explicativas

| Variable | Fuente | Link | Período |
|---|---|---|---|
| Desempleo por departamento | MIDES — Observatorio Social (INE-ECH) | https://www.gub.uy/ministerio-desarrollo-social/indicador/tasa-desempleo-segun-departamento-total-pais | 2006-2023 |
| Salario / ingreso per cápita por departamento | MIDES — Observatorio Social (INE-ECH) | https://www.gub.uy/ministerio-desarrollo-social/indicador/promedio-ingresos-per-capita-valor-locativo-pesos-constantes-segun-departamento-total | 2006-2023 |
| Pobreza (% de personas) por departamento | MIDES — Observatorio Social (INE-ECH) | https://www.gub.uy/ministerio-desarrollo-social/indicador/porcentaje-personas-situacion-pobreza-segun-departamento-total-pais | 2006-2023 |
| Esperanza de vida al nacer según sexo, por departamento | MIDES — Observatorio Social (INE) | https://www.gub.uy/ministerio-desarrollo-social/indicador/esperanza-vida-nacer-segun-sexo-departamento-total-pais | Variable |
| Nivel educativo máximo alcanzado (mayores de 24 años) por departamento | MIDES — Observatorio Social (INE-ECH) | https://www.gub.uy/ministerio-desarrollo-social/indicador/distribucion-porcentual-personas-mayores-24-anos-segun-maximo-nivel-educativo-alcanzado-4 | 2006-2023 |
| Tasa de analfabetismo (15 años y más) por departamento | MIDES — Observatorio Social (INE-ECH) | https://www.gub.uy/ministerio-desarrollo-social/indicador/tasa-analfabetismo-personas-15-anos-segun-departamento-total-pais | 2006-2023 |
| Población por sexo y edad, según departamento | INE — Estimaciones y Proyecciones de Población | https://www.gub.uy/instituto-nacional-estadistica/datos-y-estadisticas/estadisticas/estimaciones-proyecciones | 1996-2025 |
| Si el departamento tiene o no puerto | [Puerto o no departamento.xlsx](https://github.com/user-attachments/files/31523105/Puerto.o.no.departamento.xlsx)




## Decisiones

- **Ventana temporal**: el IDAE (variable dependiente) solo tiene datos públicos hasta 2018. El panel final del modelo va a quedar acotado a 2008-2018, aunque varias variables explicativas tengan series más largas.
- **n pequeño**: con 19 departamentos y ~11 años, el panel tiene ~200 observaciones, pero muchas variables van a estar correlacionadas entre sí (ej. pobreza y desempleo). Conviene revisar multicolinealidad antes de interpretar coeficientes.


