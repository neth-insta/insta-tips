# Go to specific part of page but hide by top navigation bar
```javascript
$(document).on('click', 'a[href^="#"]', function (event) {
    event.preventDefault();
    $('html, body').animate({
        scrollTop: $($.attr(this, 'href')).offset().top + -65
    }, 100);
});
```