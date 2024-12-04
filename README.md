> DEMO: https://makkons.github.io/rich-raul/

## Структура папок и файлов

```                      # Исходники
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
│   ├── order.html                # Оформление заказа
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

## Корзина

Работа корзины осуществляется через javascript и синхронизацию с localStorage.getItem('cart')