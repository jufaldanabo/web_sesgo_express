# Rebranding de sesgoexpress.com — instrucciones para Claude

Eres el desarrollador encargado de rebrandear el sitio web de **Sesgo Express** (fábrica de sesgo de Medellín, desde 2006) con su nueva identidad de marca. El sitio actual es una landing de una sola página publicada en **Netlify** con el dominio **sesgoexpress.com**. Trabaja sobre el repositorio o la carpeta del sitio actual.

## Objetivo
Que un comprador de fábrica, taller o mercería entienda en 5 segundos qué vendemos, confíe en la marca y **escriba por WhatsApp para cotizar**. Toda la página empuja a un solo llamado: **"Cotiza por WhatsApp"**.

## Archivos que te entrega el dueño
- `sesgo-express-kit-logo.zip` → usa `svg/imagotipo-horizontal-01-color-principal.svg` (fondos claros), `svg/imagotipo-horizontal-05-negativo-azul.svg` (fondos azules), `svg/isotipo-azul-oscuro.svg`, `svg/isotipo-blanco.svg`, `png/favicon-32.png`, `png/favicon-512.png`.
- `sesgo-express-iconos.zip` → íconos sueltos en `svg/<nombre>-azul|fucsia|blanco.svg`.
- Fotos de sectores y corte (imágenes generadas para la marca): pijama, edredón, maletín, gorra, almohada, rollos de corte. Si no están, deja marcos con `alt` descriptivo y un comentario `TODO: foto`.
- No uses el logo anterior (carrete + letra cursiva) en ningún lugar.

## Identidad: reglas obligatorias

### Color (variables CSS)
```css
:root {
  --azul: #1E2447;        /* base, textos, fondos oscuros */
  --azul-tono: #2B3260;   /* SOLO la S gigante tono sobre tono sobre --azul */
  --azul-80: #4B506C;     /* textos secundarios */
  --azul-20: #D2D3DA;     /* bordes, separadores */
  --fucsia: #E5195E;      /* protagonista: botones, palabras resaltadas */
  --fucsia-80: #EA477E;   /* hover de botones */
  --rosado: #FCE8EF;      /* fondo suave */
  --gris-perla: #E6E7EB;
  --blanco: #FFFFFF;
}
```
- No inventes colores fuera de esta lista (salvo la carta de 30 colores de producto).
- Contraste: texto pequeño solo blanco sobre azul o azul sobre blanco/rosado. Fucsia sobre azul solo en títulos grandes. Nunca fucsia sobre fucsia.

### Tipografía
- **Poppins** desde Google Fonts, pesos 400, 500 y 600. Respaldo: Arial.
- Títulos: 600, `letter-spacing: -0.02em`. Texto: 400, 16–18 px, `line-height: 1.6`.
- Sin itálicas, sin pesos 700–900 en frases largas, alineado a la izquierda.

### Palabras resaltadas (recurso estrella)
- Las palabras normales van en 400 y minúscula; las palabras clave en `<span class="hl">` = 600, MAYÚSCULA, color `--fucsia` (sobre fucsia, en `--azul`).
- Máximo dos grupos resaltados por frase.

### Sistema gráfico
- **Sello** "<5 DÍAS · HÁBILES · TODO EL PAÍS": rectángulo fucsia con la esquina superior derecha cortada a 45° (`clip-path`), isotipo a la izquierda, "<5 DÍAS" grande y "HÁBILES · TODO EL PAÍS" pequeño con interletrado amplio.
- **Cinta de colores**: los 30 colores de la carta, en orden, como franjas inclinadas a 45°; úsala como borde de secciones o del pie, nunca detrás de texto.
- **S gigante**: el isotipo muy grande, recortado por el borde de la sección (tono sobre tono `--azul-tono` sobre `--azul`, o blanca sobre `--fucsia`).
- **Fotos**: enmarcadas en fucsia (8 px) con radio 24 px. Nunca fotos con marcas de terceros.
- **Íconos**: los del zip, dentro de un cuadro redondeado (azul sobre `--rosado`, o blanco sobre azul).
- Sin sombras, sin degradados, sin emojis.

### Componentes
- Botón principal: fondo `--fucsia`, texto blanco 600, forma de píldora, hover `--fucsia-80`.
- Botón secundario: borde azul 2 px, texto azul.
- Tarjetas: radio 24 px.
- Botón flotante de WhatsApp en todas las pantallas (fucsia, ícono blanco, abajo a la derecha).

### Tono de voz
Directo, enérgico, cercano, tuteo, términos del oficio (ribetear, embone, carreta, rollo, ancho). Nada de jerga corporativa. Término oficial: **Embone** (nunca "empitado" ni "embonado").

## Correcciones al sitio actual
| Hoy | Nuevo |
|---|---|
| "Entrega rápida" sin plazo | "Despacho en menos de 5 días hábiles desde la confirmación del pago" |
| "+20 años" | "Desde 2006" |
| "∞ colores" y carta no visible | "30 colores" con la carta visible |
| "Empitado/embonado" | Embone |
| "Venta al por mayor" vs. "Servicio exclusivo" | Pedido mínimo 1.000 m · corte desde 5 m |
| "Llámanos" vs. "pedidos solo por redes" | Un solo canal: WhatsApp |
| Teléfono ausente en contacto | WhatsApp, teléfono y dirección visibles |
| Menú sin "Colores" | Menú completo |
| Sectores duplicados | Lista única |
| © 2025 fijo | Año automático con JavaScript |

## Estructura y textos (usa estos textos tal cual)

**Menú:** Productos · Corte · Colores · Sectores · Nosotros · Contacto · [botón] Cotiza por WhatsApp

1. **Hero** (fondo azul, S gigante tono sobre tono)
   - H1: Tu sesgo llega en <span class="hl">MENOS DE 5 DÍAS</span> a <span class="hl">TODO EL PAÍS</span>
   - Subtítulo: Fábrica de sesgo abierto, planchado y embone en 30 colores. Calidad y rapidez desde 2006.
   - Botones: "Cotiza por WhatsApp" (principal) · "Ver productos" (secundario, ancla a #productos)
   - Sello "<5 DÍAS · HÁBILES · TODO EL PAÍS" · foto de rollos de corte o edredón.
2. **Barra de cifras** (blanco): Desde 2006 · 30 colores · <5 días hábiles · Despacho a todo el país.
3. **Productos** (#productos, blanco), tarjetas:
   - Sesgo planchado — Doblado y planchado, listo para ribetear. Anchos: 13, 16, 20, 25 y 30 mm.
   - Sesgo abierto — Tira sin doblar, a la medida que necesites.
   - Embone — En carretas de 50 m, para máquina embonadora.
   - Debajo: Materiales: poliéster, algodón y satín · Pedido mínimo 1.000 m.
4. **Servicio de corte** (#corte, rosado)
   - Título: ¿Tienes tu tela? Te la cortamos <span class="hl">DESDE 5 METROS</span>
   - Texto: Corte al hilo, al través o al sesgo (45°) sobre la tela que nos traes. · Foto de rollos de corte.
5. **Cómo funciona** (azul)
   - Título: <span class="hl">&lt;5 DÍAS HÁBILES</span>, de tu pago a tu taller
   - Pasos: 1. Nos escribes por WhatsApp con tipo, ancho, color y metros · 2. Te cotizamos hoy · 3. Pagas y fabricamos · 4. Despachamos a tu ciudad
   - Nota pequeña: Despacho en menos de 5 días hábiles contados a partir de la confirmación del pago.
6. **Carta de colores** (#colores, blanco)
   - Título: <span class="hl">30 COLORES</span> desde mil metros
   - Cuadrícula de las 30 muestras (número + nombre, colores de la tabla de abajo).
   - Aviso: Colores de referencia en pantalla. Pide tu muestra física. · Botón: Pide la carta por WhatsApp
7. **Sectores** (#sectores, rosado), tarjetas con foto enmarcada en fucsia:
   - Pijamas y lencería — El <span class="hl">EMBONE</span> que define cada borde
   - Hogar — Ribetes que <span class="hl">TERMINAN BIEN</span> tu edredón
   - Marroquinería — Bordes que <span class="hl">AGUANTAN</span> el viaje
   - Gorras y dotación — Por dentro también se nota la <span class="hl">CALIDAD</span>
   - Almohadas — Ribetes que <span class="hl">TERMINAN BIEN</span> tu almohada
   - Lista sin foto: confección industrial y uniformes, moda y camisetas, ropa de bebé, tapicería y cojinería, calzado, mercerías.
8. **Nosotros** (#nosotros, blanco)
   - Título: Fabricando sesgo <span class="hl">DESDE 2006</span>
   - Texto: Somos una fábrica de Medellín con más de veinte años en el oficio. Producimos con maquinaria automática para entregarte rápido sin sacrificar calidad: mismo ancho, mismo doblez, rollo tras rollo.
   - Ventajas con íconos: Despacho en menos de 5 días · Todo el país · 30 colores · Calidad constante · Atención directa por WhatsApp
9. **Testimonios**: NO publicar hasta tener citas reales. Deja la sección comentada en el HTML.
10. **Preguntas frecuentes** (acordeón accesible con `<details>`):
    - ¿Cuál es el pedido mínimo? — 1.000 m en sesgo abierto, planchado y embone; el corte es desde 5 m.
    - ¿En cuánto tiempo despachan? — En menos de 5 días hábiles desde la confirmación del pago.
    - ¿Despachan a mi ciudad? — Sí, a cualquier ciudad de Colombia.
    - ¿Qué anchos manejan? — Planchado: 13, 16, 20, 25 y 30 mm. Abierto: a la medida. Embone: carretas de 50 m.
    - ¿Qué materiales tienen? — Poliéster, algodón y satín.
    - ¿Cómo pido? — Por WhatsApp, con tipo de sesgo, ancho, color (número de la carta) y metros.
11. **Contacto** (#contacto, azul): WhatsApp 305 360 5645 (botón) · Tel. 321 543 5224 · Cra 70 # 94-64, Medellín · Lunes a viernes, 8:00 a. m. – 5:30 p. m. · Instagram @sesgoexpress (https://www.instagram.com/sesgoexpress/)
12. **Pie**: imagotipo en negativo, menú, contacto, cinta de colores en el borde superior, "© [año] Sesgo Express · Calidad y rapidez".

## Enlaces de WhatsApp
- General: `https://wa.me/573053605645?text=Hola%20Sesgo%20Express%2C%20quiero%20cotizar%20sesgo`
- Carta: `https://wa.me/573053605645?text=Hola%2C%20quiero%20recibir%20la%20carta%20de%20colores`
- Corte: `https://wa.me/573053605645?text=Hola%2C%20necesito%20servicio%20de%20corte`

## Carta de 30 colores (HEX de referencia en pantalla)
01 Blanco #F0EDF5 · 02 Negro #212227 · 03 Amarillo Quemado #FFD12D · 04 Rojo #D01525 · 05 Azul Rey #1A3B82 · 06 Verde Antioquia #078930 · 07 Naranja #F95D32 · 08 Gris Perla #918E8A · 09 Gris Medio #5B5B62 · 10 Gris Oscuro #3F4352 · 11 Morado #40235D · 12 Azul Oscuro #1E2A4B · 13 Fucsia #EC3063 · 14 Vinotinto #6C1E32 · 15 Kaky #CFB683 · 16 Verde Turquesa #0D8481 · 17 Rosado #F99AB6 · 18 Azul Turquesa #0379BC · 19 Azul Cielo #6AAEE5 · 20 Verde Limón #80D951 · 21 Lila #D686C8 · 22 Verde Militar #463E35 · 23 Hueso #F8F6DE · 24 Café #3B272C · 25 Verde Agua #B8F0CA · 26 Amarillo Claro #F9F6A9 · 27 Azul Hortensia #6E94C5 · 28 Salmón #EDA08B · 29 Palo Rosa #D78190 · 30 Verde Botella #0B3D2E

## SEO y técnico
- `<title>`: Sesgo Express | Fábrica de sesgo en Medellín · Despacho a todo Colombia
- `<meta name="description">`: Fábrica de sesgo planchado, abierto y embone en 30 colores. Pedido mínimo 1.000 m. Despacho en menos de 5 días hábiles a todo el país. Cotiza por WhatsApp.
- `lang="es-CO"`, favicons del kit, Open Graph (si no hay imagen OG, usa `isotipo` sobre azul y deja `TODO: og-image 1200×630`).
- Datos estructurados JSON-LD `LocalBusiness` (nombre, dirección, teléfono, horario, sameAs Instagram).
- `alt` descriptivo en todas las imágenes; imágenes en WebP con `loading="lazy"` (menos el hero).
- Diseño móvil primero; probar a 375 px, 768 px y 1280 px.
- HTML, CSS y JS ligeros; sin frameworks pesados. Mantén el despliegue en Netlify.
- Agrega eventos de clic en los botones de WhatsApp si hay analítica instalada.

## Cómo trabajar
1. Lee el sitio actual y haz una lista de lo que vas a cambiar antes de editar.
2. Crea una rama nueva (no trabajes directo en la principal).
3. Aplica identidad, estructura y textos de este documento.
4. Revisa el checklist de abajo y muéstrame capturas en móvil y escritorio.
5. No publiques en producción sin mi aprobación.

## Checklist de aceptación
- [ ] No queda rastro del logo ni los colores anteriores.
- [ ] Solo colores de la paleta; Poppins cargada; sin itálicas ni sombras.
- [ ] Todas las frases destacadas usan `.hl` con máximo dos grupos.
- [ ] "Embone", "Desde 2006", "<5 días hábiles", "30 colores" y "mínimo 1.000 m" aparecen donde corresponde.
- [ ] Todos los botones de contacto van a WhatsApp con mensaje prellenado; botón flotante visible.
- [ ] Teléfono, dirección y horario visibles en contacto.
- [ ] Sectores sin duplicados; menú completo; año del pie automático.
- [ ] Contraste AA en todos los textos; navegable con teclado.
- [ ] Se ve bien a 375 px, 768 px y 1280 px.
