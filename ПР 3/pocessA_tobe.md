
# Процесс А «после»: Принятие решения по миграции биллинга Oracle → Nord


```mermaid
flowchart TD
    subgraph VENDOR["Внешний вендор"]
        A1["Oracle объявляет<br/>о конце поддержки"]
    end

    subgraph VKP["ВКП (владелец процесса)"]
        B1["Осознание риска<br/>+ эскалация ФД"]
        B2["Сбор требований<br/>по чек-листу"]
        B5["Утверждение<br/>по дедлайну"]
    end

    subgraph ARCH["Архитектор + R&D"]
        D1["Техническая оценка<br/>в рамках A/B/C"]
    end

    subgraph FD["Финансовый директор"]
        E1["Финансовая оценка<br/>параллельно с технической"]
        E2["Черновик сравнения A/B/C<br/>(агент)"]
    end

    subgraph AGENT["Агент"]
        G1["Мониторинг новых<br/>доработок в старой версии"]
    end

    subgraph FREEZE["Заморозка"]
        H1["Приказ о заморозке<br/>некритичных доработок"]
    end

    subgraph LEGEND["Легенда"]
        L1["🔴 внешний триггер"]
        L2["🟢 изменённый шаг"]
        L3["🔵 новый шаг (агент)"]
    end

    A1 -->|"1 день"| B1
    B1 --> B2
    B2 -->|"3 дня"| D1
    B2 --> E2
    D1 -->|"2 недели"| E1
    E2 --> E1
    E1 -->|"1 неделя"| B5
    B5 --> H1
    G1 -.->|"сигнал о нарушении"| B5

    style A1 fill:#f9d5d5,stroke:#c00
    style B1 fill:#d4edda,stroke:#080
    style B2 fill:#d4edda,stroke:#080
    style B5 fill:#d4edda,stroke:#080
    style D1 fill:#d4edda,stroke:#080
    style E1 fill:#d4edda,stroke:#080
    style E2 fill:#cce5ff,stroke:#06c
    style G1 fill:#cce5ff,stroke:#06c
    style H1 fill:#d4edda,stroke:#080
    style L1 fill:#f9d5d5,stroke:#c00
    style L2 fill:#d4edda,stroke:#080
    style L3 fill:#cce5ff,stroke:#06c