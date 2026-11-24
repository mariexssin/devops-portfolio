# Лабораторна робота №4 — Локальний запуск та налагодження WishList

## Командні репозиторії
- Backend (withlist-api): https://github.com/mariexssin/withlist-api (форк nromanen)
- Frontend (wishlist-ui): https://github.com/mariexssin/wishlist-ui (форк nromanen)

## Мій внесок
Налаштувала та запустила локальне оточення для сервісу списків бажань (FastAPI, PostgreSQL, Redis та фронтенд на Vue 3 / Vite) на macOS. Виправила підключення до локального PostgreSQL (DB_HOST=postgres, ?sslmode=disable), додала ALGORITHM=HS256 у конфігурацію, адаптувала клієнт Redis для локального redis:// без ssl_cert_reqs та налаштувала запуск фронтенду з директорії ~/wishlist-ui.

## Інструкція локального запуску (macOS)
1. cd ~ && git clone https://github.com/mariexssin/withlist-api.git && git clone https://github.com/mariexssin/wishlist-ui.git
2. cd ~/withlist-api && cp .env.example .env (DB_HOST=postgres, REDIS_URL=redis://redis:6379, ALGORITHM=HS256)
3. cd ~/withlist-api && docker compose up -d && docker compose ps
4. cd ~/wishlist-ui && npm ci && npm run dev
5. Відкрити http://localhost:5173 та http://localhost:8000/docs, увійти або зареєструватися, створити вішліст і оновити сторінку (Cmd + R).
