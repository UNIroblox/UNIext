# UNIext — лендинг расширения UNI

Одностраничный сайт расширения **UNI — Roblox, но лучше**.
Статика без сборки: GitHub Pages отдаёт файлы прямо из ветки `main`.

## Структура

```
index.html              страница (RU по умолчанию, переключатель RU/EN)
404.html                страница ошибки
assets/                 иконка и скриншоты
downloads/              ZIP-сборка расширения
```

## Локальный просмотр

Открыть `index.html` файлом или поднять статику:

```powershell
python -m http.server 8000
# http://127.0.0.1:8000
```

## Публикация

```powershell
git add -A
git commit -m "site: update"
git push
```

GitHub Pages настроен на `main` / `/` — изменения выкатываются в течение минуты
на https://rouni.github.io/UNIext/

## Обновление сборки

1. Положить новый архив в `downloads/` и удалить старый.
2. Заменить `downloads/UNI-2.7.3-plus.zip` во всех ссылках (шапка, hero, подвал),
   версию в `.btn-note` (`v2.7.3-plus · 4.0 MB`) и в подвале `GPL-3.0 · v2.7.3-plus`.
3. Обновить номер версии в `.manual`-примечании, если он там встречается.
4. `git add -A; git commit; git push` — Pages пересоберётся сам.

## Ссылки

- Telegram проекта: `https://t.me/UNI_EXT` (шапка, hero, подвал, FAQ).
- Chrome Web Store и GitHub на странице намеренно не используются.

## Язык

Тексты лежат в атрибутах `data-ru` / `data-en`. Переключатель — `#lang`,
выбор запоминается в `localStorage`; ссылку можно зафиксировать параметром
`?lang=en`.
