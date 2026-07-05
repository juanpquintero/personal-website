# Juan Pablo Quintero — Sitio Personal

Sitio web personal de Juan Pablo Quintero: landing page estática enfocada en backend, arquitectura en la nube, automatización y divulgación tecnológica, con una identidad visual retro-terminal basada en la paleta **Gruvbox**.

Construido con [Astro](https://astro.build) como sitio 100% estático (sin backend ni APIs dinámicas).

## 🚀 Estructura del proyecto

```text
/
├── public/                 # Recursos estáticos (favicons)
├── src/
│   ├── assets/              # Imágenes y SVGs
│   ├── components/          # Componentes de UI (Hero, Terminal, AboutMe, Ecosistema, ZeroGravityBackground)
│   ├── layouts/              # Layout.astro: shell HTML base, fuentes y meta SEO
│   ├── pages/                 # Enrutamiento basado en archivos (index.astro)
│   └── styles/                # global.css: variables del sistema de diseño (colores, tipografía, spacing)
├── ARCHITECTURE.md          # Referencia viva de la arquitectura del proyecto
├── DESIGN.md                 # Guía de identidad visual y de marca (Gruvbox)
└── astro.config.mjs
```

Para más detalle sobre cómo encajan las piezas, consulta [ARCHITECTURE.md](ARCHITECTURE.md). Para la guía de diseño (colores, tipografía, componentes, tono de voz), consulta [DESIGN.md](DESIGN.md).

## 🧞 Comandos

El gestor de paquetes del proyecto es **pnpm**. Todos los comandos se ejecutan desde la raíz del proyecto:

| Comando           | Acción                                              |
| :----------------- | :--------------------------------------------------- |
| `pnpm install`      | Instala las dependencias                              |
| `pnpm dev`          | Inicia el servidor de desarrollo en `localhost:4321`  |
| `pnpm build`        | Compila el sitio de producción en `./dist/`           |
| `pnpm preview`      | Previsualiza localmente el build de producción        |
| `pnpm astro check`  | Verifica tipos en los archivos `.astro`               |

No hay suite de tests ni linter configurados actualmente en este proyecto.

## 👀 Más información

- [Documentación de Astro](https://docs.astro.build)
