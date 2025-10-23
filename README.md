# Gitea Server Runner

Docker-контейнер для запуска CI/CD раннера Gitea Actions.

## Настройка

1. Скопируйте `env.example` в `.env`
2. Заполните переменные в `.env`:
   - `GITEA_RUNNER_REGISTRATION_TOKEN` - токен из админ-панели Gitea
   - `GITEA_INSTANCE_URL` - URL вашего Gitea сервера
   - `GITEA_RUNNER_NAME` - уникальное имя раннера

## Запуск

```bash
docker-compose up -d
```

Раннер автоматически зарегистрируется в Gitea при первом запуске.

## actions/cache в Docker ранере
Для работы actions/cache требуется настроить config.yaml согласно документации.  
https://docs.gitea.com/usage/actions/act-runner#advanced-configurations

host: - должна быть локальная сеть (пример: 192.168.0.35 ip текущего сервера). 127.0.0.1 не прокатит так-как у каждого контейнера свой изолированный 127.0.0.1.