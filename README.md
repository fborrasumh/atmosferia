# AtmosferIA

El laboratorio de meteorología, climatología y agrometeorología. Aplicación web de un solo fichero.

**Usar la app:** https://fborrasumh.github.io/atmosferia/

**Idiomas:** español (por defecto), inglés, portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Qué hace

Sigue el sílabo de Meteorología y Climatología de la Carrera de Agropecuaria (UPEC) en nueve pantallas y una sección de práctica:

- **Atmósfera.** Clasificar frases como tiempo o clima. Perfil de la Atmósfera Estándar Internacional con temperatura y presión a cualquier altitud. Mapa de calor de la radiación extraterrestre (FAO-56) por latitud y día del año, con la duración del día. Perfil esquemático de los Andes del Carchi, del Pacífico a la Amazonía, con franjas de cultivo que cambian con el gradiente térmico. Mapa del Ecuador con estaciones de Costa, Sierra y Amazonía.
- **Estación meteorológica virtual.** Garita, psicrómetro, termómetros de máxima y mínima, barómetro, anemómetro y veleta, piranómetro y heliógrafo, pluviómetro, pluviógrafo, tanque evaporímetro y estación automática. Cada instrumento tiene su descripción y, cuando procede, un simulador: humedad relativa y punto de rocío, marcha diaria, presión frente a altitud, rosa de los vientos, Ångström-Prescott.
- **Precipitación.** Lectura de la probeta del pluviómetro, pluviograma con ventana móvil de intensidad y regímenes de lluvia del Ecuador.
- **Anuario.** Carga de datos diarios de varias fuentes: estación de ejemplo ficticia con errores puestos a propósito, CSV propio, datos pegados o reanálisis ERA5 de cualquier punto vía Open-Meteo. Control de calidad por código: faltantes, rango, mínima mayor que la máxima, saltos, lluvia negativa y sensor atascado. Tabla mensual con la regla 3/5 de la OMM, climograma de Walter-Lieth, clasificación de Köppen-Geiger (criterios de Peel et al., 2007) explicada paso a paso y balance hídrico de Thornthwaite-Mather. Exporta a Word y CSV.
- **Fenología.** Grados-día y fechas previstas de cada etapa para papa, maíz suave, haba, cebada, quinua, arveja y fréjol. Riesgo de heladas por mes y demanda de agua del cultivo (Hargreaves y Kc de la FAO-56) frente a la lluvia. Incluye cuatro casos agrometeorológicos.
- **Atlas climático mundial.** Mapa interactivo en proyección Equal Earth con zoom. Muestra 37 estaciones de referencia coloreadas por su clasificación de Köppen, bandas de radiación del día, día y noche con el punto subsolar, y búsqueda de lugares. Al pulsar una estación aparecen su climograma y su comparación con Tulcán; desde cualquier punto se pueden descargar sus datos reales.
- **Cambio climático.** CO₂ de Mauna Loa y simulador de forzamiento radiativo (ΔF = 5,35·ln C/C₀, con sensibilidad ajustable). Escenarios SSP del IPCC (AR6). Subida de las isotermas y de las franjas de cultivo en los Andes, con su efecto en el ciclo del cultivo y en las heladas. Índice didáctico de vulnerabilidad, ejercicio de clasificar medidas como adaptación o mitigación, y cronología de compromisos internacionales y normativa ecuatoriana.
- **Ensayo y artículos.** Editor de ensayo argumentativo sobre el clima del Carchi, con datos comprobados para citar y un aviso de las cifras que no coinciden con los datos. Lectura crítica de artículos.
- **Problemas individualizados.** Trece tipos (psicrometría, presión, temperatura y altitud, viento, radiación, pluviómetro, intensidades, tabulación con faltantes, Köppen, grados-día, ETo, forzamiento). Cada estudiante recibe los suyos según su código. El código calcula la solución y diagnostica errores típicos recalculándolos.
- **Práctica de parcial.** Dos parciales con problemas, casos y preguntas de opción múltiple, corregidos y explicados.

Interfaz en español, inglés y portugués.

## Cómo se usa la IA

Es **opcional**. Solo se usa en dos tareas: leer artículos y hacer preguntas sobre el ensayo, sin poner nota. Cada persona usa su propia clave de OpenAI, Google Gemini o Anthropic Claude, que se guarda solo en su navegador. El código comprueba lo que propone la IA:
- verifica que cada cita aparezca literalmente en el texto;
- señala las cifras que no están en el texto ni en los datos;
- retira las frases que ponen nota.

Todo lo demás funciona sin clave y sin IA.

## Privacidad

Las respuestas, los datos, el ensayo y el progreso se guardan solo en el navegador (IndexedDB). Fuera solo sale:
- **a Open-Meteo**: la latitud, la longitud y el año, únicamente si se piden datos reales o se busca un lugar;
- **al proveedor de IA**: únicamente lo que se pide analizar, con correos, documentos de identidad y teléfonos enmascarados. Antes del primer envío se muestra una muestra de lo que sale.

## Datos y fuentes

- Fórmulas: FAO-56 (Allen et al., 1998), Atmósfera Estándar Internacional, Köppen-Geiger según Peel et al. (2007), Thornthwaite (1948), Myhre et al. (1998).
- CO₂: medias anuales de Mauna Loa (NOAA GML), redondeadas. Escenarios: IPCC AR6, Grupo de Trabajo I, Tabla SPM.1.
- Datos reales: [Open-Meteo](https://open-meteo.com) (CC BY 4.0), reanálisis ERA5 y ERA5-Land de Copernicus.
- Contornos de países: Natural Earth (dominio público), vía world-atlas.

## Límites

- Las **normales de las estaciones de referencia** son aproximadas y redondeadas, para aprender; no sustituyen a las normales oficiales del INAMHI o de la OMM.
- Las **temperaturas base, los grados-día por etapa, los Kc y las franjas de cultivo** son orientativos y cambian con la variedad y la zona.
- Un **reanálisis no es una estación**: en montaña puede diferir varios grados de una estación real.
- **Un año de datos describe el tiempo de ese año, no el clima.** Los meses que no cumplen la regla 3/5 se estiman para el climograma y se marcan como provisionales.
- La ETP de Thornthwaite suele subestimar la demanda en la alta montaña tropical. El forzamiento solo considera el CO₂. El índice de vulnerabilidad es didáctico.
- Probada con IA simulada (OpenAI, Gemini y Claude), Open-Meteo simulado, en escritorio y móvil y en los tres idiomas. **No se ha probado con claves reales de IA.**
- No sustituye las clases, la visita a la estación ni el examen.

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche) y Francisco Javier Méndez Bravo (Universidad Politécnica Estatal del Carchi).

Sigue el sílabo de Meteorología y Climatología (0811BMC3UB-AJ2025, nivel 3, Carrera de Agropecuaria, UPEC) del profesor Francisco Javier Méndez Bravo: sus contenidos, sus dos parciales, la visita a la estación meteorológica, el anuario y la fenología, el cambio climático y el ensayo sobre el clima del Carchi.

ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573) · Francisco Javier Méndez Bravo [0009-0005-4934-6533](https://orcid.org/0009-0005-4934-6533)

## Cómo citar

Borrás Rocher, F. y Méndez Bravo, F. (2026). *AtmosferIA* (v1.0.0) [Software]. (DOI en trámite)

## Licencia

MIT. Véase [LICENSE](LICENSE).
