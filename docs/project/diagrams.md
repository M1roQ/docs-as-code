# Диаграммы

## Диаграмма последовательности

```mermaid
sequenceDiagram
    actor User as Пользователь
    participant System as Система анализа отзывов
    participant Model as ML-модель

    User->>System: Ввести и отправить текст отзыва
    System->>Model: Передать текст отзыва
    Model-->>System: Вернуть тональность и уровень уверенности
    System-->>User: Показать результат классификации
```

## Диаграмма классов

```mermaid
classDiagram
    class User {
        +int id
        +string name
    }

    class Review {
        +int id
        +string text
        +datetime createdAt
    }

    class SentimentResult {
        +int id
        +string sentiment
        +float confidence
        +datetime createdAt
    }

    class MLModel {
        +string name
        +string version
        +predict(text) SentimentResult
    }

    User "1" --> "*" Review
    Review "1" --> "1" SentimentResult
    MLModel "1" --> "*" SentimentResult
```