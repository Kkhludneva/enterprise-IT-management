# Процесс Б «до»: Перенос доработок с Oracle на Nord


```mermaid
flowchart TD
    subgraph RND["Команда R&D"]
        A1["Инвентаризация<br/>доработок (вручную)"]
        A2["Перенос кода<br/>(кастомизация)"]
        A3["Деплой в старую версию"]
    end

    subgraph VKP["ВКП"]
        B1["Приоритизация:<br/>что переносить первым"]
    end

    subgraph ARCH["Архитектор"]
        C1["Ревью кода"]
    end

    subgraph QA["Тестировщик"]
        D1["Тестирование"]
    end

    subgraph OLD["Старая версия Oracle"]
        E1["Новые доработки<br/>продолжают поступать"]
    end

    subgraph LEGEND["Легенда"]
        L1["🟡 шаг с ожиданием"]
        L2["🔴 источник потерь"]
    end

    A1 -->|"до 2 недель"| B1
    B1 -->|"до 1 недели"| A2
    A2 -->|"до 3 дней"| C1
    C1 -->|"до 2 дней"| D1
    D1 --> A3
    E1 -->|"не останавливается"| A2

    style A1 fill:#fff3cd,stroke:#b80
    style A2 fill:#fff3cd,stroke:#b80
    style A3 fill:#fff3cd,stroke:#b80
    style B1 fill:#fff3cd,stroke:#b80
    style C1 fill:#fff3cd,stroke:#b80
    style D1 fill:#fff3cd,stroke:#b80
    style E1 fill:#f9d5d5,stroke:#c00
    style L1 fill:#fff3cd,stroke:#b80
    style L2 fill:#f9d5d5,stroke:#c00