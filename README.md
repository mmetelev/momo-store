# Momo Store aka Пельменная №2

<img width="900" alt="image" src="https://user-images.githubusercontent.com/9394918/167876466-2c530828-d658-4efe-9064-825626cc6db5.png">

Этот репозиторий предназначен для исходного кода дипломного проекта в Yandex Practicum.

В течение работы над дипломом проект доступен по следующему адресу: [https://momo-store-practicum.ru/](https://momo-store-practicum.ru/)

## Запуск приложения в Docker

1. **Перейти в директорию backend и собрать образ:**
   ```bash
   docker build -t momo-store-backend:latest .
   ```

2. **Перейти в директорию frontend и собрать образ:**
   ```bash
   docker build -t momo-store-frontend:latest .
   ```

3. **Запуск с использованием docker-compose:**
   - Измените путь до образа контейнера в `docker-compose.yml`, если это необходимо.
   - Выполните команду из корневой директории:
     ```bash
     docker-compose up -d
     ```

## Поднятие проекта локально

### Frontend

1. Установите зависимости:
   ```bash
   npm install
   ```

2. Запустите приложение с указанием переменных окружения:
   ```bash
   NODE_ENV=production VUE_APP_API_URL=http://localhost:8081 npm run serve
   ```

### Backend

1. Запустите сервер:
   ```bash
   go run ./cmd/api
   ```

2. Запустите тесты:
   ```bash
   go test -v ./...
   ```