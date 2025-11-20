# Secure Build Standard — META-FOUNDRY
Документ: MF-ST-08.01
Версия: 1.0.0


## Назначение
Обеспечить безопасную сборку всех программных продуктов META-FOUNDRY.


## Цели
- защита от supply-chain атак
- контроль зависимостей
- проверка целостности
- безопасные артефакты


## Основные требования
### 1. Dependency Security
- Только версии из lock-файлов
- Проверка через `pip-audit` и `safety`


### 2. Build Environment Security
- Сборка только в контейнерах
- Полная изоляция от хоста
- Подпись build logs


### 3. Artifact Integrity
- Все артефакты подписываются (Sigstore)
- Хранятся в корпоративном registry
- Каждая сборка имеет SBOM


### 4. Reproducible Builds
- Один и тот же commit → один и тот же build
- Зафиксированные версии зависимостей


## Secure Build Pipeline (корпоративная схема)
1. Code checkout
2. Dependency scan
3. Static analysis
4. Build container
5. Run tests
6. Generate SBOM
7. Sign artifacts
8. Push to registry
9. Publish build metadata