# Miniproyecto 2 — Condensación de Bose–Einstein

Proyecto de Física Estadística basado en el enunciado de Johans Restrepo C. (noviembre de 2026) y el libro *Física Estadística: Teoría, Algoritmos y Problemas* (2026).

## Abrir y ejecutar

**Entrega principal:** `Miniproyecto2_BEC.ipynb`, ya ejecutado con los resultados y las gráficas incrustados. Se recomienda visualizarlo en **VS Code** con la extensión Jupyter, o en JupyterLab. No necesita acceso a internet para volver a calcularlo si ya tiene instaladas las dependencias.

En una terminal dentro de esta carpeta:

```powershell
python -m pip install -r requirements.txt
python -m jupyter notebook
```

En VS Code puede simplemente abrir `Miniproyecto2_BEC.ipynb`, seleccionar su intérprete de Python y pulsar **Run All**. Para resultados íntegramente reproducibles, comience siempre desde la primera celda.

## Estructura

```text
Miniproyecto2_BEC/
├── Miniproyecto2_BEC.ipynb         # Entrega principal: modelo, código, gráficos, análisis
├── Guia_de_estudio_y_sustentacion.md  # Explicación de las fórmulas y guion de exposición
├── README.md
├── requirements.txt
├── resultados_curva_principal.csv  # T, N0/N, Nex/N, potencial químico, residuo
├── resultados_resumen.csv          # Comparación numérica-teoría
├── resultados_convergencia.csv     # Sensibilidad al corte energético
└── figuras/
    ├── 01_distribucion_energia.png
    ├── 02_fraccion_condensada.png
    ├── 03_potencial_quimico.png
    ├── 04_efecto_N.png
    ├── 05_efecto_densidad.png
    └── 06_condiciones_frontera.png
```

## Correspondencia con el enunciado

| Requisito | Dónde está cubierto |
|---|---|
| Simulación comentada y reproducible | Notebook, secciones 3–4; parámetros globales y `requirements.txt` |
| ¿Cómo cambia la ocupación por energía? | Sección 5; figura 1 |
| ¿Cómo evoluciona el fundamental con $T$? | Sección 6; figura 2 |
| ¿Puede estimarse la temperatura crítica? | Sección 6: saturación de excitaciones y máxima pendiente; comparación con $T_c$ |
| ¿Cómo afectan $N$ y densidad? | Secciones 7–8; figuras 4–5 |
| ¿Cuáles son las diferencias respecto al límite termodinámico? | Secciones 6–7, 10–11; figura 2 y tablas |
| Pregunta propia | Sección 9; figura 6: condiciones de frontera |
| Modelo, método, validación, resultados y conclusiones | Secciones 2, 3–4, 5–10, 11 |
| Comprenderlo y sustentarlo | Sección 12 del notebook y `Guia_de_estudio_y_sustentacion.md` |

## Enfoque numérico

La implementación no dibuja la fórmula $N_0/N=1-(T/T_c)^{3/2}$ como resultado de simulación. Primero crea niveles discretos y degeneraciones, calcula las ocupaciones Bose–Einstein resolviendo el potencial químico a cada temperatura, y **después** compara con esa predicción teórica. El cálculo mantiene **el número promedio de partículas** y no simula un ensamble canónico exacto ni una evolución dinámica.

En una caja finita no existe una transición de fase singular: se estudia una **región de cruce** y se proponen indicadores de temperatura característica. La masa cercana a rubidio-87 y las densidades seleccionadas solo fijan una escala ilustrativa de temperatura.

## Orden de estudio sugerido

Primero leer las secciones 1–3 del notebook y la derivación de la guía; segundo revisar el código de los niveles y el potencial químico; tercero interpretar las seis figuras; cuarto preparar el guion oral; quinto probar cambios en los parámetros.

**Fuentes:** libro guía y enunciado adjuntos al chat original. Bibliografía complementaria en la última sección del notebook y de la guía, pendiente de validación final por el estudiante.
