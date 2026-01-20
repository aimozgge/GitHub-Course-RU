# Шаблоны схем для Git проектов

## Схема 1: Процесс работы с Git

```
Локальный компьютер          GitHub
┌─────────────┐            ┌─────────────┐
│  Working    │            │   Remote    │
│  Directory  │            │ Repository  │
│             │            │             │
│  file.py    │   push     │  file.py    │
│  (изменен)  │ ────────>  │  (обновлен) │
│             │            │             │
│  git add    │   pull     │             │
│  git commit │ <────────  │             │
└─────────────┘            └─────────────┘
```

## Схема 2: Ветвление и слияние

```
main:              A---B---C
                        \
feature-branch:          D---E
                            \
main (после merge):      A---B---C---F
                                    (F = merge D+E)
```

## Схема 3: Конфигурация Git (приоритет)

```
Локальная (проект) > Глобальная (компьютер) > Системная
```

## Схема 4: Workflow с двумя аккаунтами

```
Проект 1 (личный)              Проект 2 (рабочий)
┌─────────────────┐            ┌─────────────────┐
│ user: aimozgge  │            │ user: ivan-max  │
│ local config    │            │ local config    │
│                 │            │                 │
│ git push        │            │ git push        │
│      ↓          │            │      ↓          │
│ github.com/     │            │ github.com/     │
│   aimozgge/     │            │   ivan-max/     │
└─────────────────┘            └─────────────────┘
         ↑                              ↑
         └──────────────┬───────────────┘
                        │
                Global config (default)
                user: aimozgge
```

## Схема 5: Fork и синхронизация

```
Original (upstream)
github.com/user1/repo
        ↓ fork
Your fork (origin)
github.com/user2/repo
        ↓ clone
Local repository
        ↓ git push
Your fork (origin)
        ↓ Pull Request
Original (upstream)
```

## Как использовать эти схемы

1. Копируйте схему в документацию вашего проекта
2. Адаптируйте под свои нужды
3. Добавляйте в README.md для объяснения workflow
4. Используйте в презентациях и обучающих материалах

## Инструменты для создания схем

- **ASCII диаграммы** (как в этом файле) — простые, работают везде
- **Mermaid** — для GitHub и Markdown
- **Draw.io** — визуальный редактор
- **PlantUML** — программный подход

## Пример Mermaid схемы (для GitHub)

\`\`\`mermaid
graph LR
    A[Working Directory] -->|git add| B[Staging Area]
    B -->|git commit| C[Local Repository]
    C -->|git push| D[Remote Repository]
    D -->|git pull| A
\`\`\`

---

**Совет:** Храните схемы в папке `templates/` или `docs/` для быстрого доступа!
