# Процесс А «до»: Принятие решения по миграции биллинга Oracle → Nord


```mermaid
flowchart TD
    subgraph VENDOR["Внешний вендор"]
        A1["Oracle объявляет<br/>о конце поддержки"]
    end

    subgraph VKP["ВКП (владелец процесса)"]
        B1["Осознание риска"]
        B2["Сбор требований<br/>от бизнеса"]
        B5["Согласование<br/>и утверждение"]
    end

    subgraph BIZ["Бизнес-заказчик"]
        C1["Формулировка<br/>коммерческих инициатив"]
    end

    subgraph ARCH["Архитектор + R&D"]
        D1["Техническая оценка<br/>вариантов"]
    end

    subgraph FD["Финансовый директор"]
        E1["Финансовая оценка"]
    end

    subgraph OLD["Старая версия Oracle"]
        F1["Доработки под<br/>коммерческие инициативы<br/>продолжаются"]
    end

    subgraph LEGEND["Легенда"]
        L1["🔴 внешний триггер"]
        L2["🟡 шаг с ожиданием"]
        L3["🟠 источник потерь"]
    end

    A1 --> B1
    B1 -->|"до 2 недель"| B2
    B2 -->|"до 1 месяца"| C1
    C1 -->|"до 2 месяцев"| D1
    D1 -->|"до 1 месяца"| E1
    E1 -->|"до 3 недель"| B5
    B5 -.->|"решение отложено"| F1
    F1 -.->|"+1 доработка к долгу переноса"| F1

    style A1 fill:#f9d5d5,stroke:#c00
    style B1 fill:#fff3cd,stroke:#b80
    style B2 fill:#fff3cd,stroke:#b80
    style B5 fill:#fff3cd,stroke:#b80
    style C1 fill:#fff3cd,stroke:#b80
    style D1 fill:#fff3cd,stroke:#b80
    style E1 fill:#fff3cd,stroke:#b80
    style F1 fill:#fce5cd,stroke:#e60
    style L1 fill:#f9d5d5,stroke:#c00
    style L2 fill:#fff3cd,stroke:#b80
    style L3 fill:#fce5cd,stroke:#e60