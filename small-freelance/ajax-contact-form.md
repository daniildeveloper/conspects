# Создание контактной формы на AJAX

```js

window.onload = () => {
  $('#form').submit(() => {
    $.ajax({
      type: "POST",
      url: 'mail.php',
      data: $(this).serialize(),
    })
    .done(() => {
      alert('Спасибо за заявку. Мы скоро с вами свяжемся');
    });
    return false;
  })
};

```