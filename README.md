# CHRONODECK: La Venganza del Azimut (1986)

Videojuego arcade de estética **Sinclair ZX Spectrum (48K / 128K +2A)** desarrollado íntegramente en un único archivo autoejecutable (`index.html`) mediante HTML5 Canvas y Web Audio API en Vanilla JavaScript, sin dependencias externas ni activos multimedia pregrabados.

El proyecto traduce a mecánicas de juego los procesos técnicos de la **preservación forense del software español de 8 bits (1983-1992)** y el concepto normativo de **Depósito de Entorno** aplicado a la Biblioteca Nacional de España (BNE).

---

## Por qué

Este videojuego nace como un artefacto práctico complementario al Trabajo Fin de Máster (TFM) *«Preservación forense del patrimonio de software español (1983-1992): el concepto de 'Depósito de Entorno' como propuesta normativa para la Biblioteca Nacional de España (BNE)»* (UC3M). Su propósito es ilustrar de forma interactiva la tesis central de la investigación: preservar software histórico exige ir más allá de la simple copia de bits, capturando también el comportamiento físico de la señal magnética, la arquitectura exacta del hardware original y su contexto documental estandarizado.

---

## Contexto y Narrativa

El jugador asume el control del **Agente Forense Francesc**, encargado de rescatar el patrimonio magnético antes de que la degradación física del soporte (*Bit Rot*) y los bloqueos administrativos destruyan el código original. Para completar la ingesta en el archivo de la BNE, el jugador debe superar cuatro fases que replican el flujo real de preservación:

1. **Fase 1 — La Cueva del Azimut (Calibración Mecánica):** Alineación del entrehierro del cabezal reproductor de casete observando curvas de Lissajous y ondas senoidales en un osciloscopio. Es necesario mantener la señal en fase durante 5 segundos corrigiendo la deriva mecánica antes de que falle el frenado de cinta.
2. **Fase 2 — El Templo de Nyquist-Shannon (Muestreo FSK):** Captura de pulsos de modulación por desplazamiento de frecuencia (FSK) a resolución estándar de preservación (`44.1 kHz / 16-bit PCM WAV`) para consolidar un contenedor `.TZX` íntegro, esquivando el ruido físico, los *dropouts* y el sobremuestreo innecesario (`96 kHz`).
3. **Fase 3 — El Laberinto de la BNE (Metadatos y Ontologías):** Nivel de plataformas por los depósitos de la Biblioteca Nacional. El objetivo es recolectar los paquetes normativos (`PREMIS`, `JSON-LD`, `SKOS`, `OWL`, `SHA-256` y `BNE-DEP`) esquivando trámites de obras huérfanas y registros volátiles de la CPU Z80.
4. **Fase 4 — Batalla Final Chronodeck (Estabilización de Reloj):** Enfrentamiento directo contra *Bit Rot Prime*. Para vulnerar su escudo de corrupción estática, el jugador debe cargar el módulo **CHRONODECK**, inyectar estados de espera (*wait states*) que fijen la frecuencia del procesador Z80 a exactamente `3.546900 MHz` y disparar bloques de verificación `SHA-256`.

---

## Especificaciones Técnicas

| Componente | Implementación Técnica |
| :--- | :--- |
| **Arquitectura** | *Zero-dependency*, código monolítico en un único archivo (`index.html`). |
| **Resolución Lógica** | `320x240` píxeles internos (`256x192` de área activa ULA + `32px` de borde). |
| **Paleta Gráfica** | Paleta estricta de 16 colores del hardware Sinclair (8 colores base + 8 *Bright*). |
| **Gráficos y Sprites** | Generación procedural mediante matrices de caracteres en código y primitivas de `CanvasRenderingContext2D` con `image-rendering: pixelated`. |
| **Motor de Sonido** | Síntesis en tiempo real con `Web Audio API` nativa: ondas cuadradas para el *beeper* de 1 bit, barridos de frecuencia y buffers de ruido blanco para percusión y errores de carga. |
| **Bucle de Tiempo** | `requestAnimationFrame` desacoplado de la tasa de refresco mediante cálculo de *DeltaTime* (`dt`). |

---

## Controles

El juego soporta control por teclado en escritorio y botonera táctil integrada para dispositivos móviles o tabletas.

| Acción | Teclado (Opción 1) | Teclado (Opción 2) | Móvil / Táctil |
| :--- | :--- | :--- | :--- |
| **Mover / Ajustar Azimut** | `Flecha Izquierda` / `Derecha` | `A` / `D` | Botones `<` y `>` en pantalla |
| **Saltar / Disparar / Activar Chronodeck** | `Espacio` / `Flecha Arriba` | `Z` / `W` / `Enter` | Botón `ACCIÓN / Z` |
| **Filtro CRT (Scanlines)** | Ratón sobre `CRT: ON/OFF` | — | Toque sobre `CRT: ON/OFF` |
| **Silenciar Beeper** | Ratón sobre `AUDIO BEEPER` | — | Toque sobre `AUDIO BEEPER` |

---

## Instalación y Ejecución

No requiere compiladores, gestores de paquetes (`npm`) ni servidores de aplicaciones.

### Ejecución directa en local
1. Clona este repositorio o descarga el archivo `index.html`:
   ```bash
   git clone [https://github.com/tu-usuario/chronodeck-azimut.git](https://github.com/tu-usuario/chronodeck-azimut.git)
   cd chronodeck-azimut
