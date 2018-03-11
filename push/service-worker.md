# Service worker in browser

## Особенности сервис воркеров

* Они выполняются в собственном глобальном контексте - ```ServiceWorkerGlobalScope```
* Они не привязаны к конкртной страницк
* Не имеют доступа к DOM

## ЖИзненный цикл service-worker

* Загрузка
* Установка
```js
// Регистрация сервис-воркера
if ('serviceWorker' in navigator) { // if browser has api support
  window.addEventListener('load', () => {
    // register can be called on each page load. Browser will be self decline is it already registred or not
    navigator.serviceWorker.register('/sw.js')  
      .then((registration) => {
        // Успешная регистрация
        console.log('Service worker registred successfull');
      }, (err) => {
        // Произошла ошибка
        console.log('ServiceWorker registration failed', err);
      });
  });
}
```