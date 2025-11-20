# Product Creation Chain Standard — META-FOUNDRY
Документ: MF-ST-07.01
Версия: 1.0.0


## Назначение
Создать прозрачную, воспроизводимую и автоматизированную цепочку создания продукта.


## Зачем это нужно
- единая модель прохождения задач
- предсказуемость релизов
- прозрачность инженерной фабрики
- контроль качества
- связка MSDLC ↔ Git ↔ AutoDoc ↔ CI/CD


## Общий Pipeline
1. Idea (MF-0)
2. Analysis (MF-1)
3. Architecture (MF-2)
4. Build (MF-3)
5. Verification (MF-4)
6. Release (MF-5)
7. Documentation Sync (MF-6)


## Feature Flow
- feature branch → PR → develop → test → release → main


## Documentation Flow
- docs branch → AutoDoc → mkdocs build → publish


## Release Flow
- release branch → gates → tests → security → main → tag