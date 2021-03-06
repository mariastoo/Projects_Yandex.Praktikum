# 🆎 Оценка результатов A/B-теста по внедрению улучшенной рекомендательной системы в интернет-магазине

**Посмотреть на nbviewer**: https://nbviewer.jupyter.org/github/mariastoo/Projects_Yandex.Praktikum/blob/main/recommender_system_ab_test/recommender_system_ab_test.ipynb

Исследование проводится с **целью** проведения оценки результатов A/B-теста по внедрению улучшенной рекомендательной системы в интернет-магазине. 

**Задачи исследования:**
- Оценить соответствие проведенного A/B-теста техническому заданию (пересекается ли тестовая аудитория с конкурирующим тестом, совпадает ли тест с маркетинговыми событиями, есть ли другие проблемы временных границ теста);
- Проанализировать его результаты (даже в случае несоответствия теста техническому заданию).

Данные для исследования предоставлены Яндекс.Практикумом и включают в себя **4 таблицы.**

**1.`ab_project_marketing_events`** — календарь маркетинговых событий на 2020 год с переменными:
- `name` — название маркетингового события;
- `regions` — регионы, в которых проводилась рекламная кампания;
- `start_dt` — дата начала кампании;
- `finish_dt` — дата завершения кампании.

**2.`final_ab_new_users`** — таблица всех пользователей, зарегистрировавшиеся в интернет-магазине в период с 7 по 21 декабря 2020 года, с переменными:
- `user_id` — идентификатор пользователя;
- `first_date` — дата регистрации;
- `region` — регион пользователя;
- `device` — устройство, с которого происходила регистрация.

**3.`final_ab_events`** — таблица всех событий новых пользователей в период с 7 декабря 2020 по 4 января 2021 года, с переменными:
- `user_id` — идентификатор пользователя;
- `event_dt` — дата и время события;
- `event_name` — тип события;
- `details` — дополнительные данные о событии. Например, для покупок в этом поле хранится стоимость покупки в долларах.

**4.`final_ab_participants`** — таблица участников тестов с переменными:
- `user_id` — идентификатор пользователя;
- `ab_test` — название теста;
- `group` — группа пользователя.

В исследовании использованы **библиотеки**: `pandas`, `matplotlib`, `seaborn`, `plotly`, `datetime`, `numpy`, `scipy`, `math`.

**Краткие выводы исследования:**
- A/B-тест был проведен некачественно, так как мы выявили многочисленные нарушения технического задания,
- результаты проведенного A/B-тестирования нерепрезентативны и не помогут определить, существуют ли изменения, связанные с внедрением улучшенной рекомендательной системы,
- проверка гипотез была выполнена лишь в исследовательских целях. Результаты этой проверки могут быть использованы после проведения нового (корректного) A/B-теста, исключительно для иллюстрации того, как сильно некачественно собранные данные искажают результаты эксперимента.