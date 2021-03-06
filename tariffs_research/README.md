# 🤳 Определение перспективного тарифа для оператора сотовой связи

**Посмотреть на nbviewer**: https://nbviewer.jupyter.org/github/mariastoo/Projects_Yandex.Praktikum/blob/main/tariffs_research/tariffs_research.ipynb

**Цель** исследования: понять, какой из двух тарифных планов приносит больше денег, чтобы телеком-компания смогла скорректировать рекламный бюджет.

**Задача** исследования: сделать предварительный анализ тарифов на небольшой выборке клиентов (500 пользователей).

Яндекс.Практикумом предоставлены 5 таблиц, которые содержат следующие **переменные**:

Таблица `users` (информация о пользователях):
- `user_id` — уникальный идентификатор пользователя,
- `first_name` — имя пользователя,
- `last_name` — фамилия пользователя,
- `age` — возраст пользователя (годы),
- `reg_date` — дата подключения тарифа (день, месяц, год),
- `churn_date` — дата прекращения пользования тарифом (если значение пропущено, то тариф еще действовал на момент выгрузки данных),
- `city` — город проживания пользователя,
- `tariff` — название тарифного плана.

Таблица `calls` (информация о звонках):
- `id` — уникальный номер звонка,
- `call_date` — дата звонка,
- `duration` — длительность звонка в минутах,
- `user_id` — идентификатор пользователя, сделавшего звонок.

Таблица `messages` (информация о сообщениях):
- `id` — уникальный номер сообщения,
- `message_date` — дата сообщения,
- `user_id` — идентификатор пользователя, отправившего сообщение.

Таблица `internet` (информация об интернет-сессиях):
- `id` — уникальный номер сессии,
- `mb_used` — объем потраченного за сессию интернет-трафика (в мегабайтах),
- `session_date` — дата интернет-сессии,
- `user_id` — идентификатор пользователя.

Таблица `tariffs` (информация о тарифах):
- `tariff_name` — название тарифа,
- `rub_monthly_fee` — ежемесячная абонентская плата в рублях,
- `minutes_included` — количество минут разговора в месяц, включённых в абонентскую плату,
- `messages_included` — количество сообщений в месяц, включённых в абонентскую плату,
- `mb_per_month_included` — объем интернет-трафика, включённого в абонентскую плату (в мегабайтах),
- `rub_per_minute` — стоимость минуты разговора сверх тарифного пакета (например, если в тарифе 100 минут разговора в месяц, то со 101 минуты будет взиматься плата),
- `rub_per_message` — стоимость отправки сообщения сверх тарифного пакета,
- `rub_per_gb` — стоимость дополнительного гигабайта интернет-трафика сверх тарифного пакета (1 гигабайт = 1024 мегабайта).

В исследовании использованы **библиотеки**: `pandas`, `math`, `matplotlib`, `numpy`, `scipy`. 

**Краткие выводы исследования**:
- пользователи тарифа «Ультра» используют в среднем больше минут разговора, сообщений и интернет-трафика в месяц. Таким образом, они платят за то, что не используют, что выгодно оператору связи, но не выгодно клиентам,
- пользователи «Смарт» используют предоставляемый им лимит до конца и даже иногда выходят за рамки своего тарифного плана, превышая лимиты (и внося дополнительную плату за превышение),
- хотя пользователи «Смарт» вносят дополнительную плату за частое превышение лимитов, это не равно той сумме, которую и так каждый месяц платят пользователи «Ультра»,
- средние выручки пользователей из Москвы и других регионов не отличаются.