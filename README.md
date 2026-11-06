# Caso 6. Brecha digital en Yucatán

Evaluación de la Unidad II · Análisis de Datos e Inteligencia de Negocios

Equipo: Esteban, Suárez y José María Samos Pech (Chema).

Repositorio: https://github.com/chemasamos/caso6-brecha-digital-yucatan

Analizamos los 106 municipios de Yucatán con el ITER del Censo 2020 de INEGI. El universo del análisis es el de viviendas particulares habitadas con características (`VIVPARH_CV`).

## Archivos

| Ruta | Contenido |
|---|---|
| `Caso6_Brecha_Digital_Yucatan.ipynb` | Código, explicación y resultados ejecutados |
| `Caso6_Slides_Ejecutivas.pptx` | Presentación editable con notas |
| `Caso6_Presentacion.pdf` | Presentación para consultar sin PowerPoint |
| `Guion_Exposicion_y_Entrega.pdf` | Guion de 10 minutos, preguntas y pasos de entrega |
| `requirements.txt` | Dependencias para ejecutar el análisis |
| `datos/iter_31_cpv2020_csv.zip` | Paquete original de INEGI, sin modificar |
| `datos/iter_31_cpv2020/` | Datos, diccionario, catálogo y metadatos (se descomprimen al ejecutar) |
| `datos/procesados/brecha_digital_municipios_yucatan_2020.csv` | Indicadores calculados de los 106 municipios |

## Procedencia

- Institución: Instituto Nacional de Estadística y Geografía (INEGI).
- Producto: Principales resultados por localidad (ITER), Censo de Población y Vivienda 2020, Yucatán.
- Página: https://www.inegi.org.mx/programas/ccpv/2020/#datos_abiertos
- Descarga: https://www.inegi.org.mx/contenidos/programas/ccpv/2020/datosabiertos/iter/iter_31_cpv2020_csv.zip
- Consulta original documentada: 28 de octubre de 2026.
- Revisión de reproducibilidad: 6 de noviembre de 2026.
- Versión del paquete: 19 de mayo de 2022. Referencia de los datos: 15 de marzo de 2020.
- Condiciones de uso: https://www.inegi.org.mx/inegi/terminos.html

## Cómo ejecutarlo

1. Instalar Python 3.10 o posterior.
2. Descargar o clonar el repositorio y abrir una terminal en su carpeta raíz.
3. Ejecutar:

```bash
python -m pip install -r requirements.txt
python -m jupyter notebook Caso6_Brecha_Digital_Yucatan.ipynb
```

4. Elegir **Kernel > Restart Kernel and Run All Cells** (reiniciar y ejecutar todo).

Los datos originales están incluidos. Si falta `datos/`, el notebook intenta descargarlos de INEGI. Se necesita Internet únicamente para instalar dependencias o recuperar datos ausentes. También puede subirse el notebook a Google Colab y ejecutarlo desde el inicio.

## Indicadores y resultados

Periodo común: marzo de 2020.

| Indicador | Fórmula | Unidad | Resultado |
|---|---|---|---|
| Acceso a Internet | `VPH_INTER / VIVPARH_CV × 100` | % | Estatal: 51.6 % |
| Complemento de acceso | `VIVPARH_CV - VPH_INTER` | viviendas | Estatal: 317,765 |
| Brecha frente al estado | `% municipal - % estatal` | puntos porcentuales | Mediana municipal: -23.2 pp |
| Participación en el déficit | `sin Internet municipal / sin Internet estatal × 100` | % | Mérida: 27.2 % |

## Hallazgos

- Solo 7 municipios superan el 51.6 % estatal. La mediana municipal es 28.4 %.
- Mérida reporta 71.6 % de acceso y el resto de Yucatán 34.5 %.
- Los diez municipios prioritarios por proporción y por volumen no coinciden. Reúnen, respectivamente, 3.7 % y 56.7 % del déficit observado.

## Recomendación y límites

Actualizar el diagnóstico y combinar proporción y volumen. Tekax, Hunucmá, Chemax, Izamal, Maxcanú y Peto son ejemplos por encima de ambas medianas. Verificar cobertura y motivos de falta de acceso antes de elegir infraestructura o apoyos.

Los datos son de 2020. Miden disponibilidad en la vivienda, sin identificar velocidad, precio ni motivos de falta de acceso. El complemento puede incluir no especificados. Las participaciones del déficit no son estimaciones del impacto de un programa. El análisis usa totales municipales para evitar doble conteo y no sustituye los asteriscos de confidencialidad por ceros.
