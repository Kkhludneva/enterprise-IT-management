# Процесс Б «после»: Перенос доработок с Oracle на Nord


```mermaid
flowchart TD
    subgraph AGENT["Агент"]
        G1["Инвентаризация:<br/>сканирование репозитория"]
        G2["Подготовка<br/>чек-листа ревью"]
        G3["Мониторинг новых<br/>доработок в старой версии"]
    end

    subgraph VKP["ВКП"]
        B1["Приоритизация<br/>по WSJF"]
    end

    subgraph RND["Команда R&D"]
        A2["Перенос кода<br/>(кастомизация)"]
        A3["Деплой в Nord"]
    end

    subgraph ARCH["Архитектор"]
        C1["Ревью по чек-листу"]
    end

    subgraph QA["Тестировщик"]
        D1["Тестирование<br/>(параллельные среды)"]
    end

    subgraph FREEZE["Заморозка"]
        H1["Новые доработки<br/>в старой версии остановлены"]
    end

    subgraph WIP["WIP-лимит"]
        W1["Не более 5 доработок<br/>в работе одновременно"]
    end

    subgraph LEGEND["Легенда"]
        L1["🟢 изменённый шаг"]
        L2["🔵 новый шаг (агент)"]
    end

    G1 --> B1
    B1 --> A2
    A2 --> G2
    G2 --> C1
    C1 --> D1
    D1 --> A3
    H1 -.->|"контроль"| G3
    G3 -.->|"сигнал"| VKP
    W1 -.->|"ограничивает"| A2

    style G1 fill:#cce5ff,stroke:#06c
    style G2 fill:#cce5ff,stroke:#06c
    style G3 fill:#cce5ff,stroke:#06c
    style B1 fill:#d4edda,stroke:#080
    style A2 fill:#d4edda,stroke:#080
    style A3 fill:#d4edda,stroke:#080
    style C1 fill:#d4edda,stroke:#080
    style D1 fill:#d4edda,stroke:#080
    style H1 fill:#d4edda,stroke:#080
    style W1 fill:#d4edda,stroke:#080
    style L1 fill:#d4edda,stroke:#080
    style L2 fill:#cce5ff,stroke:#06c