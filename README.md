# Portafolio Personal — Mijeli Lucero

## Objetivo del proyecto

Este proyecto consistió en desarrollar una página web de presentación personal utilizando HTML5 semántico y Bootstrap 5, aplicando los conceptos de diseño responsive y personalización mediante CSS vistos en el curso de Desarrollo Web. El objetivo principal fue aprender a integrar un framework CSS moderno sin perder la identidad visual del sitio, construyendo un perfil digital propio que refleje quién soy como estudiante de Ingeniería en Sistemas de Información y Ciencias de la Computación.

## Cómo ejecutar la página

1. Clonar o descargar este repositorio.
2. Abrir la carpeta del proyecto en el editor de código (recomendado: Visual Studio Code).
3. Abrir el archivo `index.html` con la extensión **Live Server**, o simplemente hacé doble clic sobre el archivo para abrirlo directamente en el navegador.
4. No requiere instalación de dependencias ni herramientas adicionales — Bootstrap, Bootstrap Icons y la tipografía se cargan vía CDN, por lo que se necesita conexión a internet para que el sitio se vea correctamente.

## Componentes de Bootstrap utilizados

- **Navbar**: barra de navegación responsive con menú colapsable en móvil (`navbar-toggler`, `collapse`).
- **Grid System**: `container`, `row` y `col-*` en todas las secciones, con distintas combinaciones de breakpoints (`col-12`, `col-md-*`, `col-lg-*`) según el contenido de cada bloque.
- **Cards**: utilizadas en la sección de Proyectos, con `card-img-top`, `card-body`, `card-title` y `card-text`.
- **List Group**: utilizado en la sección de Intereses y Habilidades para organizar los intereses personales, académicos y profesionales.
- **Badges**: utilizados en Biografía (experiencias), Visión Profesional (objetivos) y en las tecnologías dentro de cada card de proyecto.
- **Botones** (`btn`, `btn-outline-light`, `btn-light`): utilizados en la navbar, el footer y las cards de proyectos.
- **Utilidades de Flexbox** (`d-flex`, `flex-wrap`, `justify-content-center`, `align-items-center`): utilizadas para organizar la fila de íconos de tecnología y varios bloques de contenido.
- **Utilidades de espaciado y texto** (`mb-0`, `mt-3`, `text-center`, `text-uppercase`, `fw-bold`, entre otras): aplicadas en distintos puntos del sitio para ajustes rápidos sin necesidad de CSS adicional.
- **Bootstrap Icons**: utilizados en el ícono del navbar, los íconos de redes sociales del footer y algunos detalles visuales.

## Elementos personalizados mediante CSS

- **Paleta de colores propia**: definida mediante variables CSS (`:root`) en tonos oscuros y azules, inspirada en referencias de portafolios con estética tecnológica y moderna.
- **Tipografía**: se importó la fuente Poppins desde Google Fonts, aplicada de forma global con distintos pesos según la jerarquía del texto (títulos, subtítulos, párrafos).
- **Navbar**: fondo, colores de texto y hover con transición personalizados, además de comportamiento `sticky` para que permanezca visible al hacer scroll.
- **Encabezado (header)**: fondo con degradado (`linear-gradient`), tamaño de fuente fluido del nombre mediante `clamp()` y saltos de línea condicionales según el ancho de pantalla, además de un efecto de resplandor (`box-shadow`) alrededor de la foto de perfil.
- **Cards de proyectos**: altura uniforme entre las tres tarjetas mediante Flexbox, imágenes recortadas de forma proporcional (`object-fit: cover`), un efecto de degradado entre la imagen y el bloque de información mediante un pseudo-elemento (`::before`), y una animación de elevación (`transform`) al pasar el mouse.
- **Badges personalizados**: rediseñados como bloques tipo tarjeta con fondo translúcido (`color-mix`), bordes y texto multilínea centrado, utilizados en Biografía y Visión Profesional.
- **Altura uniforme en listas**: los bloques de la sección de Intereses y Habilidades se ajustaron con `min-height` para mantener un grid visualmente parejo entre las nueve tarjetas.
- **Divisores responsive en el footer**: líneas divisorias verticales en pantallas grandes y horizontales en pantallas pequeñas, implementadas con pseudo-elementos (`::before`) para controlar su largo exacto.
- **Media queries**: ajustes específicos en distintos puntos del sitio para adaptar tamaños de fuente, espaciados y disposición de elementos en los anchos de 320px, 768px y 1280px.

## Capturas de pantalla (responsive)

A continuación se muestran capturas del sitio funcionando en los tres anchos requeridos.

### 320px (móvil)

![Vista en 320px](/img/pantalla-320.png)

### 768px (tablet)

![Vista en 768px](/img/pantalla-768.png)

### 1280px (escritorio)

![Vista en 1280px](/img/pantalla-1280.png)

## Principales decisiones de diseño

- **Estética general**: se optó por un diseño *dark* con tonos de azul, tomando como referencia varios portafolios profesionales de estilo tecnológico y moderno. Esta paleta se definió mediante variables CSS desde el inicio del proceso de personalización, lo que permitió mantenerla consistente en absolutamente todas las secciones del sitio sin repetir valores hexadecimales sueltos por el código.

- **Separar estructura de estilo**: en vez de ir maquetando y diseñando sección por sección al mismo tiempo, se decidió completar primero toda la estructura HTML semántica y el sistema de grid de Bootstrap en las siete secciones del sitio (header, biografía, habilidades, proyectos, visión profesional y footer), y recién después dedicar una fase completa exclusivamente a la personalización visual con CSS propio. Esta decisión permitió validar que el contenido y el comportamiento responsive funcionaran correctamente antes de invertir tiempo en detalles estéticos, y evitó tener que rehacer estilos cada vez que se ajustaba algo de la estructura.

- **Priorizar accesibilidad desde el HTML, no como un agregado final**: se mantuvo una jerarquía de encabezados correcta y sin saltos de nivel en todo el documento (un único `h1`, seguido de `h2` por sección y `h3` para subtítulos internos), se usó texto alternativo descriptivo y específico en cada imagen, y se agregaron atributos `aria-label` en todos los elementos interactivos que solo contienen íconos (el botón de menú del navbar, los enlaces de redes sociales). Estas decisiones se tomaron durante la construcción de cada sección, no como una revisión posterior.

- **Uso de técnicas de CSS más allá de lo básico**: para lograr efectos visuales específicos de las referencias utilizadas (como el degradado suave entre la imagen y el bloque de información en las cards de proyectos), se investigaron y aplicaron técnicas más avanzadas que un `border` o `background-color` simple, como pseudo-elementos (`::before`) posicionados de forma absoluta, la función `color-mix()` para lograr transparencias sobre la paleta de colores propia, y la propiedad `mask-image` como alternativa para desvanecidos sin bordes visibles.

- **Responsive pensado por comportamiento, no solo por punto de quiebre**: en lugar de limitarse a los tres anchos exigidos por la rúbrica, se trabajó el comportamiento intermedio del sitio (por ejemplo, el tamaño del nombre en el encabezado o la disposición de los divisores del footer) para que la transición entre anchos se sintiera natural en cualquier punto, no solo en los tres valores fijos de prueba.