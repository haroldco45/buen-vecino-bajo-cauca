# Buen Vecino Bajo Cauca

**Biblioteca Legal Colombiana — Volumen 11: Convivencia Ciudadana**

PWA offline que traduce la **Ley 1801 de 2016** (Código Nacional de Seguridad y Convivencia Ciudadana) al lenguaje del barrio, para los residentes de **El Triángulo**, **Colinas del Portal** y **Altos de San Juan** en Caucasia, Antioquia.

> Desarrollada por **Vibras Positivas HM** — Derechos de Autor Reservados

---

## Qué resuelve

Los conflictos vecinales del Bajo Cauca casi siempre nacen del mismo problema: **la gente no sabe qué dice la ley ni cuánto cuesta incumplirla**. Este volumen ataca eso con cifras reales y una ruta clara de qué hacer antes de llamar a la Policía.

## Contenido de la app

| Pestaña | Qué hace |
|---|---|
| **Inicio** | Las tres ideas base y las cuatro categorías del artículo 6 |
| **Consultar** | Buscador de 20 comportamientos contrarios a la convivencia, en formato comparendo, con el texto legal y su traducción al barrio |
| **Multas 2026** | Calculadora en vivo sobre el SMMLV. Tarifa de los cuatro tipos + valor con descuento por pronto pago |
| **Qué hacer** | Ruta de escalamiento en 6 pasos: diálogo → constancia → JAC → cuadrante → querella → Fiscalía |
| **El Pacto** | Los 10 acuerdos del Pacto del Buen Vecino, con progreso guardado y envío por WhatsApp |
| **Ponte a prueba** | Quiz de 8 preguntas con retroalimentación legal en cada respuesta |
| **Cartas** | Generador de 4 documentos listos: carta al vecino, mediación JAC, querella a la Inspección y solicitud de Frente de Seguridad |
| **Líneas** | 123, 119, 155, 141 con marcado directo + espacio para guardar el número del cuadrante |
| **Normas** | Las 9 normas concordantes que se pueden citar en asamblea o querella |

## Cifras legales aplicadas

| Concepto | Valor 2026 |
|---|---|
| SMMLV (Decreto 1469 del 29/12/2025) | $1.750.905 |
| Auxilio de transporte (no computa para multas) | $249.095 |
| SMDLV | $58.363,50 |
| Multa Tipo 1 (4 smdlv) | $233.454 |
| Multa Tipo 2 (8 smdlv) | $466.908 |
| Multa Tipo 3 (16 smdlv) | $933.816 |
| Multa Tipo 4 (32 smdlv) | $1.867.632 |

La calculadora recalcula todo al cambiar el SMMLV, así que la app **no se vence en enero**: solo se actualiza el número.

## Marco normativo cubierto

- **Ley 1801 de 2016** — Código Nacional de Seguridad y Convivencia Ciudadana
- **Ley 2000 de 2019** — consumo en espacio público, perímetros de restricción
- **Ley 2197 de 2022** — Ley de Seguridad Ciudadana
- **Ley 2166 de 2021** — Régimen de Acción Comunal (comité de convivencia y conciliación)
- **Ley 1774 de 2016** — protección animal
- **Ley 675 de 2001** — propiedad horizontal
- **Ley 2220 de 2022** — Estatuto de Conciliación (conciliadores en equidad)
- **Constitución Política, art. 95** — deberes ciudadanos
- Acuerdos del Concejo y decretos del Alcalde de Caucasia (poder subsidiario, art. 12)

Artículos desarrollados: **6, 26, 27, 33, 35, 111, 124 y 180**.

## Instalación

```bash
git clone https://github.com/vibraspositivashm/convivencia-bajo-cauca.git
cd convivencia-bajo-cauca
python3 -m http.server 8080
```

### Publicar en GitHub Pages

1. Crea el repositorio `convivencia-bajo-cauca`.
2. Sube los 6 archivos a la raíz de la rama `main`.
3. Settings → Pages → Source: `main` / `(root)`.
4. Queda en `https://vibraspositivashm.github.io/convivencia-bajo-cauca/`.

> **Antes de publicar:** si el usuario u organización de GitHub es distinto, reemplaza la URL en las tres etiquetas `og:image`, `og:url` y `twitter:image` del `index.html`, y en la constante `SITE` del script. Si no se corrige, la tarjeta de WhatsApp no muestra la imagen.

## Archivos

```
index.html      App completa, un solo archivo, sin dependencias externas
manifest.json   Manifiesto PWA
sw.js           Service worker (cache-first, funciona sin señal)
og-image.png    Tarjeta social 1200×630
icon-192.png    Icono PWA
icon-512.png    Icono PWA / maskable
README.md       Este archivo
```

## Decisiones técnicas

- **Sin CDN, sin frameworks, sin llamadas a API.** GitHub Pages bloquea peticiones externas y el barrio tiene señal intermitente. Todo corre local.
- **Tipografía del sistema.** Condensada en mayúsculas para títulos, monoespaciada para datos legales: el lenguaje visual del comparendo. Cero fuentes remotas, cero espera en 3G.
- **Almacenamiento tolerante a fallos.** `localStorage` envuelto en `try/catch` con respaldo en memoria, para que funcione también en navegadores con almacenamiento restringido o en modo incógnito.
- **Hora real de Colombia** vía `Intl.DateTimeFormat` con `timeZone: "America/Bogota"` (UTC-5). Las cartas se fechan solas.
- **Accesibilidad:** foco visible, `prefers-reduced-motion` respetado, objetivos táctiles ≥ 44 px, contraste AA.

## Cómo se usa en la asamblea

1. Se comparte el enlace por los grupos de WhatsApp de los tres barrios.
2. En la reunión se proyecta **Multas 2026**. Ver el valor real de una fiesta ruidosa ($933.816) es lo que cambia el comportamiento.
3. Se vota el **Pacto** punto por punto y se recogen firmas.
4. Se imprime **Qué hacer** y se pega en la caseta comunal.
5. Se repite el **quiz** en cada asamblea para medir avance.

## Aviso legal

Material pedagógico de divulgación. Resume y traduce la ley, pero **no reemplaza el texto oficial ni la asesoría de un abogado**. Los valores de multa dependen del salario mínimo vigente y pueden variar por decisiones judiciales, decretos del Alcalde o acuerdos del Concejo. Consulte siempre el texto vigente de la Ley 1801 de 2016.

## Licencia

© 2026 Vibras Positivas HM — Harold Augusto Marín Machado. Caucasia, Antioquia, Colombia.
Uso comunitario y educativo libre citando la fuente. Derechos de autor reservados.
