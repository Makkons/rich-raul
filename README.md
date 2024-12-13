> DEMO: https://makkons.github.io/rich-raul/

## Структура папок и файлов

```# Исходники
│   ├── js                        # Скрипты
│   │   └── main.js               # Главный скрипт
│   ├── css                       # Стили сайта
│   │   └── main.scss             # Главный файл стилей
│   │   └── vendor.scss           # Файл стилей библиотек
│   ├── partials                  # папка для хранения html-частей страницы
│   ├── img                       # папка для хранения картинок
│   ├── fonts                     # папка для хранения шрифтов в формате woff2
│   ├── index.html                # Главный html-файл
│   ├── auth-reg.html             # Регистрация
│   ├── auth-email.html           # Авторизация по email
│   ├── auth-tel.html             # Вход по номеру телефона
│   ├── auth-reset.html           # Забыли пароль
│   ├── auth-send.html            # Код подтверждения отправлен
│   ├── account-subscribe.html    # Главный html-файл
│   ├── account-paid.html         # Главный html-файл
│   ├── account-order.html        # Главный html-файл
│   ├── account-info.html         # Главный html-файл
│   ├── 404.html                  # 404
│   ├── about.html                # О нас
│   ├── atelier.html              # Ателье
│   ├── boutiques.html            # Бутики
│   ├── brands.html               # Бренды
│   ├── cart.html                 # Корзина
│   ├── catalog.html              # Каталог
│   ├── сheckout.html                # Оформление заказа
│   ├── product-clothes.html      # Страница товара - одежда
│   ├── product-bag.html          # Страница товара - сумка
│   ├── confirmation.html         # Страница подтверждения оплаты
│   ├── favourites.html           # Избранное
│   ├── news.html                 # Список новостей
│   ├── news-details.html         # Открытая страница новости
│   ├── partners.html             # Страница для партнеров
│   └── search-details.html       # Результаты поиска
```

## Шапка

У шапки несколько ключевых состояний по дизайну:

> Class `header` - стандарная прозрачная шапка как на главной

> Дополнительный Class `header--light` - прозрачная шапка как на главной, но с инвертированными цветами для темной темы

> Дополнительный Class `header--slim` - шапка меньше по высоте с серым фоном, как например на странице каталога

## Шторка в шапке (marquee)

Активируется бегущая строка когда ширина элементов больше ширины окна. 
На крестик шторка удаляется и об этом сохраняются данные в localStorage.setItem('isHiddenMarque') на 7 дней, чтобы не надоедать пользователю, затем удаляются.

## Корзина

Работа корзины осуществляется через `javascript` и синхронизацию с `localStorage.getItem('cart')`
На странице checkout также все рендерится из localStorage, только купон нужно докрутить, что бы при вводе купона и успешном ответе с сервера редактировалась итоговая цена, а также отобразилась информация со скидками

## Адаптив изображений

Адаптив изображений осуществляется через тег `picture` и `media` запросы в нем, например:

```html
<picture>
   <source srcset="./img/atelier/hero-01-mobile.webp" media="(max-width: 768px)" type="image/webp" />
   <source srcset="./img/atelier/hero-01-mobile.png" media="(max-width: 768px)" />
   <source srcset="./img/atelier/hero-01.webp" type="image/webp" />
   <img class="swiper__image img" width="1920" height="900" src="./img/atelier/hero-01.png" alt="hero" />
</picture>
```

т.е достаточно указать просто разные ссылки на обычное изображение и сжатое, если имеется. Также поддерживается `webp` формат изображений. При желании лишние `source `можно просто убрать из `picture`.

## Адаптив видео

Адаптив видео осуществляется через тег `data-desktop-src` для больших видео и `data-mobile-src` для видео для мобильных:

```HTML
<video class="play__video" preload="false" width="280" height="185" poster="./img/showroom/video-poster.png" playsinline="playsinline" loop="loop" muted="muted">
   <source data-desktop-src="./video-desktop.webm" data-mobile-src="./video-mobile.webm" type="video/webm" />
   <source data-desktop-src="./video-desktop.mp4" data-mobile-src="./video-mobile.mp4" type="video/mp4" />
</video>
```

В момент скроллинга `javascript` определяет размер экрана, а также нахождение видео в области просмотра и подставляет необходимую ссылку в `src` видео, а замет подгружает его, что экономит трафик на старте загрузки страницы. Есть поддержка `webp` через `source`, при желании строку можно удалить.
