---
version: alpha
name: Juan_Quintero - Gruvbox Transformación
description: Identidad visual para marca personal enfocada en backend, arquitectura en la nube y divulgación tecnológica.
colors:
  primary: "#fe8019"
  secondary: "#83a598"
  tertiary: "#b8bb26"
  neutral: "#1d2021"
  surface: "#282828"
  on-surface: "#ebdbb2"
typography:
  headline-lg:
    fontFamily: JetBrains Mono
    fontSize: 40px
    fontWeight: 800
    lineHeight: 1.2
    letterSpacing: -0.02em
  body-md:
    fontFamily: IBM Plex Sans
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.65
  ui-element:
    fontFamily: JetBrains Mono
    fontSize: 14px
    fontWeight: 500
    lineHeight: 1.3
    letterSpacing: 0.02em
  terminal-bold:
    fontFamily: JetBrains Mono
    fontSize: 14px
    fontWeight: 700
    lineHeight: 1.3
    letterSpacing: 0.02em
spacing:
  xs: 4px
  sm: 8px
  md: 16px
  lg: 32px
  xl: 64px
  gutter: 24px
rounded:
  none: 0px
  sm: 2px
  md: 4px
  lg: 8px
  full: 9999px
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.neutral}"
    rounded: "{rounded.sm}"
    padding: 12px
    typography: "{typography.ui-element}"
  card-tutorial:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: "{spacing.lg}"
  terminal-ui:
    backgroundColor: "{colors.neutral}"
    borderColor: "{colors.surface}"
    headerColor: "{colors.surface}"
    promptUser: "juan@quintero:~$"
    promptColor: "{colors.tertiary}"
    systemOutputColor: "{colors.secondary}"
    errorColor: "{colors.primary}"
    typography: "{typography.ui-element}"
    typographyBold: "{typography.terminal-bold}"
---

## Overview

**"Transformando la forma tradicional de construir software"**

Esta identidad visual representa un puente entre la robustez de los sistemas heredados y la agilidad de la ingeniería de software moderna impulsada por la IA y la nube. El estilo evoca la familiaridad de un entorno de desarrollo retro (la "zona de confort" del ingeniero), pero lo presenta de una manera estructurada, cálida y accesible.

La personalidad de la marca es técnica pero profundamente humana y alegre, reflejando las raíces caribeñas a través de la paleta cálida de Gruvbox. Es la identidad de un líder técnico y divulgador que entiende el valor de lenguajes consolidados, pero que impulsa la adopción de herramientas modernas y automatización. Esta guía sirve de base fundamental para la construcción del sitio web personal y los recursos visuales para tutoriales.

## Colors

La paleta se basa en el ecosistema **Gruvbox**, adaptado para priorizar la calidez y el contraste necesario en la web moderna.

- **Primary (#fe8019):** Un naranja vibrante pero terroso. Representa la alegría, la innovación y la disrupción ("la transformación"). Se utiliza para llamados a la acción, botones principales, acentos clave y para destacar palabras clave dentro de los títulos.
- **Secondary (#83a598):** Un azul suave y retro. Evoca estabilidad, orquestación en la nube y tecnicismo. Ideal para enlaces, metadatos y elementos secundarios de navegación.
- **Tertiary (#b8bb26):** Un verde terminal clásico. Se utiliza para indicar éxito, validación o para destacar integraciones de ecosistemas de software.
- **Neutral (#1d2021):** El fondo oscuro profundo de la variante "hard" de Gruvbox. Representa la consola, el backend y el legado estable. Proporciona el lienzo principal de alto contraste sobre el cual brillan los colores cálidos.
- **Surface (#282828):** El tono intermedio utilizado estrictamente para tarjetas, bloques contenedores y elementos modulares, creando una separación jerárquica clara sin recurrir a sombras modernas.
- **On-Surface (#ebdbb2):** El color del texto principal. Un beige cálido que reduce la fatiga visual en comparación con el blanco puro, recordando a los monitores retro de fósforo cálido.

## Typography

La estrategia tipográfica se inclina fuertemente hacia la identidad técnica del desarrollador, manteniendo una legibilidad impecable en la lectura extendida.

- **Headlines & UI (JetBrains Mono):** Esta fuente monoespaciada lidera los títulos principales, subtítulos y todos los componentes de la interfaz de usuario (botones, menús, etiquetas). En tamaños grandes, se configura estrictamente con un peso pesado de 800 y un tracking (letter-spacing) negativo para lograr un bloque visual denso, sólido y de alto impacto técnico. Al colocar una tipografía de código en el diseño jerárquico principal, se refuerza visualmente el entorno de desarrollo y el enfoque ingenieril.
- **Body & Prose (IBM Plex Sans):** Se utiliza para la prosa larga, incluyendo artículos de blog, documentación técnica y guías escritas. Se aplica un leading (line-height) generoso configurado entre 1.55 y 1.7 para asegurar un ritmo de lectura cómodo y descansado. Su diseño de ingeniería humanista equilibra la rigidez de la tipografía monoespaciada, garantizando un tono profesional y limpio.

## Layout

El diseño sigue una cuadrícula de bloques rígidos, inspirada en la forma en que se estructuran las arquitecturas backend y los contenedores en la nube. 

Se utiliza una escala de espaciado estricta basada en múltiplos de 8px. Los componentes de código y los tutoriales ocupan el centro del escenario con un ancho máximo contenido, permitiendo que el texto explicativo respire alrededor de las implementaciones técnicas.

## Elevation & Depth

La profundidad **no** se logra a través de sombras pesadas o desenfoques (blur), ya que esto rompería la estética retro. Inyectando contraste físico, la jerarquía se establece mediante **Bordes Duros** y **Capas Tonales** (pasando del fondo de tono `neutral` hacia los bloques del color `surface`).

- **Animaciones de Estado (Efecto Órbita/Gravedad Cero):** Cuando los elementos interactivos o contenedores principales cambian a un estado de "flotación", no deben usar *motion blur*. La elevación se simula mediante una traslación vertical en el eje Y combinada con una rotación leve (1 a 2 grados) y la expansión de una sombra sólida y dura (ej. `box-shadow: 10px 15px 0px var(--color-surface)`). Esto simula que los bloques de arquitectura se desconectan de la gravedad local sin perder su solidez técnica.

## Shapes

El lenguaje de formas se define por la **Precisión Técnica**. 

Se evita el exceso de redondez en los componentes principales. Los botones, tarjetas de tutoriales y bloques de código utilizan un radio de esquina muy sutil (2px a 4px). Esto mantiene una estética de ingeniería y sistemas (cajas, contenedores, módulos) mientras suaviza lo suficiente los bordes para no ser agresivo a la vista.

## Components

- **Buttons:** Los botones principales utilizan el color `primary` con texto en `neutral` y están tipografiados con `JetBrains Mono`. Al hacer hover, no se desvanecen; en su lugar, pueden invertir sus colores o mostrar un borde sólido de 2px, recordando el comportamiento de selección en terminales antiguas.
- **Interactive Terminal:** Un componente de interfaz embebido (no flotante) que ancla la experiencia de usuario. Debe utilizar de forma estricta la tipografía `JetBrains Mono`. El fondo debe ser `neutral` con una barra superior `surface`. El prompt del usuario siempre debe reflejar la identidad del administrador (`juan@quintero:~$`). Los elementos clave de inicialización, comandos introducidos y respuestas directas del sistema (por ejemplo: `juan@quintero:~$[+] Sistema inicializado correctamente. Listo para codificar.`) deben configurarse obligatoriamente con mayor peso visual (`terminal-bold` / `fontWeight: 700`) para generar un contraste contundente frente a los logs estándar. Las respuestas del sistema utilizan colores semánticos: verde (`tertiary`) para éxitos, azul (`secondary`) para información y naranja (`primary`) para alertas o disrupciones.
- **Code Blocks:** Un componente vital para la divulgación. Deben usar el fondo `neutral` estricto, fuente `JetBrains Mono` y tener resaltado de sintaxis (syntax highlighting) que respete estrictamente los colores de la paleta Gruvbox (naranjas, verdes y azules pastel).
- **Chips / Badges:** Se utilizan para categorizar tutoriales. Deben usar bordes sólidos de 1px con el color `secondary`, fondo transparente y tipografía de interfaz de usuario.

## System Voice & Copywriting

El texto interactivo (especialmente en la terminal o mensajes de error) debe simular un entorno de ejecución real. El tono es compacto, directo y natural, evitando construcciones "robóticas" o corporativas tradicionales.

- **Do:** Usar prefijos técnicos de corchetes como `[+] Iniciando...`, `[SISTEMA INICIADO]`, o `[-] Desconectando...`.
- **Do:** Tratar al usuario como un operador del sistema ("Comandos disponibles", "Navegando a directorio"). Utilizar comandos de demostración que mantengan un enfoque profesional amplio (ej. `orbit`, `init`, `deploy`), en lugar de atarlos a tecnologías o herramientas de terceros específicas.
- **Don't:** Usar un lenguaje excesivamente comercial o genérico (evitar "¡Hola! Bienvenido a mi web, haz clic aquí").

## Do's and Don'ts

- **Do** usar `JetBrains Mono` con peso 800 y tracking negativo en encabezados grandes para consolidar el aspecto robusto de terminal, y destacar palabras clave usando el color `primary`.
- **Don't** usar blanco puro (`#FFFFFF`) o negro puro (`#000000`). Destruiría la calidez característica de la paleta y la vibra del Caribe. Mantente siempre en el espectro `on-surface` y `neutral`.
- **Do** reservar `IBM Plex Sans` con su interlineado generoso (1.55–1.7) estrictamente para párrafos extensos y contenido educativo para relajar la vista del lector.
- **Don't** aplicar sombras suaves (box-shadow con blur elevado). Si un elemento debe resaltar, utiliza la animación de estado de "Gravedad Cero".