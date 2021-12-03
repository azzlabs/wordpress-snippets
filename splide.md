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
