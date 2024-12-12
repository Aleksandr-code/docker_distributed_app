## Проект: 
Распреденная разработка vue и laravel под docker (начальная конфигурация) 

## Использование

- Склонировать репозиторий  <b>git clone</b>
- Запуск версии dev: <b>docker compose -f docker-compose.dev.yml up --build</b>
- Запуск версии prod: <b>docker compose up --build</b>

## Дополнительно:

<p> <b>Проблема:</b> Hot Module Reload не работает из WSL2 </p>

<b>Статьи</b>:
    
- [Hot Module Reload not working Windows Docker + wsl](https://github.com/vitejs/vite/issues/1153?ysclid=m4hml1km27842778662)
- [WSL2 File changes made by Windows apps on Windows filesystem don't trigger notifications for Linux apps](https://github.com/vitejs/vite/issues/1153?ysclid=m4hml1km27842778662)

<b>Решение</b>:

- Опция usePolling (<i>*высокая загрузка процессора</i>) добавлена в vite.config.js. [Ссылка](https://vite.dev/config/server-options.html#server-watch) 

<b>Recommended</b>: Use WSL2 applications to edit your files.
- It is also recommended to move the project folder outside of a Windows filesystem. Accessing Windows filesystem from WSL2 is slow. Removing that overhead will improve performance.
