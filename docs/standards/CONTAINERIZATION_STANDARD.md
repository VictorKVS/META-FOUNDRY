
# Containerization Standard — META-FOUNDRY
Документ: MF-ST-06.01
Версия: 1.0.0


## Назначение
Определить единый корпоративный стандарт контейнеризации для всех подсистем META-FOUNDRY.


## Зачем это нужно
- воспроизводимость окружений
- ускорение DevOps и CI/CD
- безопасность через изоляцию
- контроль зависимостей
- минимизация «работает у меня»


## Требования
1. Использовать минимальные базовые образы (distroless, alpine).
2. Все Dockerfile проходят security scan (Trivy).
3. Все контейнеры подписываются (Cosign / Sigstore).
4. Каждый сервис имеет versioned image (semver).
5. Используется единый corporate Dockerfile template.


## Минимальный корпоративный Dockerfile
```dockerfile
FROM python:3.11-alpine
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD ["python", "main.py"]
```