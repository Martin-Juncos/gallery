# Gallery

## Descripción

El proyecto "Gallery" es una galería de imágenes simple desarrollada con HTML, CSS y JavaScript. Este proyecto muestra cómo implementar una funcionalidad de visualización de imágenes que permite a los usuarios navegar a través de una colección de imágenes.

## Funcionalidades

- Visualización de una serie de imágenes.
- Navegación entre imágenes mediante controles.
- Visualización automática de imágenes en un modo de presentación de diapositivas.

## Puesta en Marcha

### Requisitos previos

- Navegador web moderno.

### Instalación

1. Clona el repositorio en tu máquina local:

   ```bash
   git clone https://github.com/Martin-Juncos/gallery.git
   ```

2. Navega al directorio del proyecto:

   ```bash
   cd gallery
   ```

3. Abre el archivo `index.html` en tu navegador web preferido.

## Uso

- Navega entre las imágenes usando los botones "Anterior" y "Siguiente".
- Disfruta del modo de presentación automática que rota las imágenes cada pocos segundos.

## Lógica del Código

La aplicación está estructurada en torno a varios archivos clave: `index.html` para la estructura, `styles.css` para la presentación y `script.js` para la funcionalidad.

### script.js

La lógica de JavaScript controla el comportamiento interactivo de la galería:

- **Inicialización**: Se configura un índice para seguir la imagen actual visible. Se cargan todas las imágenes en un arreglo para facilitar la navegación y el acceso.

  ```javascript
  let currentIndex = 0;
  const images = document.querySelectorAll(".image-container img");
  const nextButton = document.getElementById("next");
  const prevButton = document.getElementById("prev");
  ```

- **Funciones de Navegación**: Se definen funciones para moverse hacia adelante y hacia atrás en la galería. Estas funciones ajustan el índice de la imagen actual y actualizan la visualización.

  ```javascript
  function showNextImage() {
    currentIndex = (currentIndex + 1) % images.length;
    updateGalleryDisplay();
  }

  function showPrevImage() {
    currentIndex = (currentIndex - 1 + images.length) % images.length;
    updateGalleryDisplay();
  }

  nextButton.addEventListener("click", showNextImage);
  prevButton.addEventListener("click", showPrevImage);
  ```

- **Actualizar Visualización**: Una función actualiza la visualización de la galería basándose en el índice actual, asegurando que sólo la imagen correspondiente sea visible.

  ```javascript
  function updateGalleryDisplay() {
    images.forEach((img, index) => {
      img.style.display = index === currentIndex ? "block" : "none";
    });
  }
  ```

- **Autoplay**: Opcionalmente, se puede implementar una funcionalidad de reproducción automática que cambie las imágenes automáticamente cada cierto tiempo.

  ```javascript
  function startAutoplay() {
    setInterval(showNextImage, 3000); // Cambia la imagen cada 3000 milisegundos.
  }

  window.onload = () => {
    updateGalleryDisplay();
    startAutoplay(); // Comentar esta línea si no se desea autoplay.
  };
  ```

## Contribuciones

Si deseas contribuir al proyecto, por favor envía un pull request o abre un issue para discutir los cambios que te gustaría implementar.

## Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo `LICENSE` para obtener más detalles.

## Contacto

Si tienes alguna consulta, puedes contactar a [Martin Juncos](mailto:prof.mcjuncos@gmail.com).

                    ©Prof Martin Juncos
