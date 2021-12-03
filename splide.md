# Splide integration

### HTML
```html
<div class="splide" id="splide-slider">
    <div class="splide__track">
        <ul class="splide__list">
          <li class="splide__slide">
              // Slide content
          </li>
          <li class="splide__slide">
              // Slide content
          </li>
        </ul>
    </div>
</div>
```
### JavaScript
```javascript
$(document).ready(function() {
  new Splide('#splide-slider', {
      perPage    : 3
  }).mount();
});
```
### Some CSS
```css
/* SplHIDE - Best pun */
.splide.hide-arrows .splide__arrows,
.splide.hide-pagination .splide__pagination {
    display: none !important;
}

/* Splide custom pagination */
.splide.custom-pagination .splide__pagination {
    padding-left: 0;
    padding-top: 20px;
    width: 100%;
}
.splide.custom-pagination .splide__pagination button {
    border: 1px solid #000000;
    margin: 0 8px;
    border-radius: 50%;
    background: none;
    height: 12px;
    width: 12px;
    cursor: pointer;
    padding: 0;
}
.splide.custom-pagination .splide__pagination button.is-active {
    background-color: #000000;
}
.splide.custom-pagination .splide__pagination button:hover {
    background-color: #111111;
    border: 1px solid #111111;
}

/* Splide custom arrows */
.splide.custom-arrows .splide__arrow {
    position: absolute;
    right: 0;
    top: calc(50% - 20px);
    background: none;
    border: none;
    z-index: 2;
    fill: #e2e2e2;
    cursor: pointer;
    transition: opacity 0.2s;
}
.splide.custom-arrows .splide__arrow:hover {
    opacity: 0.8;
}
.splide.custom-arrows .splide__arrow:active {
    opacity: 0.6;
}
.splide.custom-arrows .splide__arrow:disabled {
    opacity: 0.2;
}
.splide.custom-arrows .splide__arrow.splide__arrow--prev {
    left: 0;
    transform: rotate(180deg);
}
```
