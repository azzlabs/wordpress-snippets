# Snippet CSS utili
### CTA & bottoni
```css
.page-content .cta {
    margin-top: 35px;
}
.page-content .cta .btn {
    margin-right: 25px;
}
.page-content .btn {
    --color: var(--color-green);
    color: #ffffff;
    background-color: var(--color);
    font-size: 0.75em;
    padding: 10px 32px;
    text-decoration: none;
    border-radius: 5px;
    display: inline-block;
    transition: opacity 0.2s;
    opacity: 1;
    border: none;
    cursor: pointer;
    font-family: "Poppins", Arial, Tahoma, sans-serif;
}
.page-content .btn:hover {
    opacity: 0.9;
    border: none;
}
.page-content .btn:active {
    --color: var(var(--color-green-darker));
}
```
### Form custom (cf7 compliant)
```css
.custom-form {
    padding: 0 35px;
}
.custom-form *[class^="col-"] {
    padding-left: 0.4rem;
    padding-right: 0.4rem;
}
.custom-form input[type="text"], 
.custom-form input[type="tel"], 
.custom-form input[type="email"], 
.custom-form input[type="number"], 
.custom-form textarea, 
.custom-form select, 
.custom-form .form-input {
    font-family: "Raleway", Arial, Tahoma, sans-serif;
    width: 100%;
    padding: 10px 12px;
    background-color: #ffffff;
    border: none;
    margin: 0.4rem 0;
    font-size: 0.8em;
    resize: vertical;
    max-height: 200px;
    display: block;
    line-height: normal;
    position: relative;
    -webkit-appearance: none;
    -moz-appearance: none;
    text-indent: 1px;
    text-overflow: '';
}
.custom-form input[type="checkbox"] {
    display: none;
}
.custom-form input[type="checkbox"] ~ span {
    padding-left: 28px;
    display: block;
    line-height: 1.8em;
    position: relative;
    font-size: 0.65em;
}
.custom-form input[type="checkbox"] ~ span::before {
    content: " ";
    width: 20px;
    height: 20px;
    background-color: #FFFFFF;
    border: 4px solid #ffffff;
    display: block;
    position: absolute;
    left: 0;
    top: 2px;
    transition: background-color 0.2s;
    background-size: contain;
}
.custom-form input[type="checkbox"]:checked ~ span::before {
    background-color: #363b35;
}
.custom-form select {    
    background-image: url(dropdown_arrow_border.png);
    background-position: right;
    background-repeat: no-repeat;
    background-size: contain;
}
.custom-form .wpcf7-list-item {
    margin: 0;
}
.custom-form .wpcf7-not-valid-tip {
    font-size: 0.6em;
    line-height: 0.8em;
    padding-left: 6px;
    white-space: nowrap;
}
.custom-form .wpcf7-response-output {
    font-size: 0.7em;    
    margin: 20px -0.6rem !important;
    border: none !important;
    background-color: rgba(186, 0, 0, 0.2);
    padding: 10px 20px !important;
}
.custom-form .submit {
    text-align: right;
    margin-top: 0.4rem;
}
.custom-form .submit .wpcf7-spinner,
.custom-form .submit .has-spinner {
    float: right;
}
.custom-form .submit input:disabled {
    opacity: 0.65;
}
```
### Accordions
CSS
```css
.acc-container {
    margin: 0;
    padding: 0 35px;
    list-style-type: none;
}

.acc-container .acc-panel {
    padding: 20px 25px;
    background-color: #464D44;
    border-bottom: 4px solid var(--color-green);
    position: relative;
    cursor: pointer;
    margin-bottom: 20px;
}
.acc-container .acc-panel:hover { 
    background-color: #3c423a;
}
.acc-container .acc-panel:active { 
    background-color: #353a33;
}
.acc-container .acc-panel .panel-content { 
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.5s;
}
.acc-container .acc-panel.open .panel-content { 
    max-height: 500px;
}
.acc-container .acc-panel::after {
    content: " ";
    position: absolute;
    right: 25px;
    top: 25px;
    width: 15px;
    height: 15px;
    border-left: 4px solid var(--color-green);
    border-top: 4px solid var(--color-green);
    transform: rotate(225deg);
    border-radius: 3px;
    transition: transform 0.2s;
}
.acc-container .acc-panel.open::after { 
    transform: rotate(45deg) translate(5px, 5px);
}
.acc-container .acc-panel h4 {
    font-weight: 400;
    padding-right: 25px;
}
```
jQuery
```javascript
$('.acc-panel').click(function() {
    $(this).toggleClass('open');
});
```
