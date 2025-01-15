# Card Slider Project

Este proyecto es un deslizador de tarjetas simple utilizando HTML, CSS y JavaScript con SwiperJS.

## Descripción

El proyecto consiste en un deslizador de tarjetas que permite a los usuarios navegar entre diferentes tarjetas. Utiliza la biblioteca SwiperJS para proporcionar una experiencia de deslizamiento suave y personalizable.

### Características

- **Adaptabilidad**: El deslizador es responsive y se adapta a diferentes tamaños de pantalla.
- **Reutilizabilidad**: El componente está diseñado para ser reutilizable, con un enfoque en la funcionalidad más que en los estilos específicos.

## Implementación
1. **Añadir el CDN de Swiper**:
```html
<link rel="stylesheet" href="https://unpkg.com/swiper/swiper-bundle.min.css" />
<script src="https://unpkg.com/swiper/swiper-bundle.min.js"></script>
```
2. **Copiar código HTML**
```html
  <!-- CARD SLIDER -->
  <div class="swiper">
    <!-- SLIDER -->
    <div class="slider-wrapper">
      <!-- CARD LIST -->
      <div class="card-list swiper-wrapper">
        <!-- CARD -->
        <div class="card-item swiper-slide">Card 1</div>
        <div class="card-item swiper-slide">Card 2</div>
        <div class="card-item swiper-slide">Card 3</div>
        <div class="card-item swiper-slide">Card 4</div>
        <!-- MORE CARDS -->
      </div>
      <!-- PAGINATION -->
      <div class="swiper-pagination"></div>
      <!-- CONTROLS -->
      <div class="swiper-slide-button swiper-button-prev"></div>
      <div class="swiper-slide-button swiper-button-next"></div>
    </div>
  </div>
```

3. **Añadir enlace al código CSS**
```html
<link rel="stylesheet" href="path/to/card-slider.css">
```
4. **Copiar código CSS**
```css
/* START CARD SLIDER */
.swiper{
  height: 80%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  background-color: rgb(61, 61, 61);

  .slider-wrapper {
    max-width: 1200px;
    height: 100%;
    margin: 0 70px 55px;
    display: flex;
    flex-direction: column;
    overflow: hidden;
    background-color: rgb(124, 124, 124);

    .card-list .card-item {
      height: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      user-select: none;

      background: rgb(184, 184, 184);
    }

    .swiper-pagination-bullet {
      background: #fff; /* BULLET COLOR */
      height: 13px;
      width: 13px;
      opacity: 0.5;
    }
    .swiper-pagination-bullet-active {
      opacity: 1;
    }

    .swiper-slide-button {
      color: #fff;
      margin-top: -55px;
      transition: 0.2s ease;
    }

    .swiper-slide-button{
      opacity: 0.6;
      transition: 0.5s ease;
    }
    .swiper-slide-button:hover {
      opacity: 1;
    }
  }
}
@media (max-width: 768px) {
  .slider-wrapper {
    margin: 0 10px 40px;
  }

  .slider-wrapper .swiper-slide-button {
    display: none;
  }
}
/* END CARD SLIDER */
```
> **Nota**: Asegúrate de que el contenedor del elemento tenga un `height` establecido porque `.swiper` toma un `height` porcentual.
5. **Importar el código JS**
```html
<script src="path/to/card-slider.js"></script>
```
6. **Copiar código JS**
```javascript
const swiper = new Swiper('.slider-wrapper', {
  loop: true,
  grabCursor: true,
  spaceBetween: 30,

  // Pagination bullets
  pagination: {
    el: '.swiper-pagination',
    clickable: true,
    dynamicBullets: true
  },

  // Navigation arrows
  navigation: {
    nextEl: '.swiper-button-next',
    prevEl: '.swiper-button-prev',
  },

  // Responsive breakpoints
  breakpoints: {
    0: {
      slidesPerView: 1
    },
    768: {
      slidesPerView: 2
    },
    1024: {
      slidesPerView: 3
    }
  }
});
```



