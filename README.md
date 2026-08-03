# PhotoGenAI Catalog

Каталог промтов для приложения PhotoGenAI.

Приложение читает файл `catalog.json` по адресу:

```
https://raw.githubusercontent.com/serjio256/photogenai-catalog/main/catalog.json
```

## Структура

```
├── catalog.json      # список промтов
└── previews/         # превью-картинки (PNG/JPEG/WebP, ~1024px по длинной стороне)
```

## Формат catalog.json

```json
{
  "version": 1,
  "prompts": [
    {
      "id": "astro-cat",
      "title": "Кот в скафандре",
      "prompt": "Рыжий кот в скафандре на фоне Земли",
      "type": "image",
      "model": "google/gemini-2.5-flash-image",
      "aspectRatio": "1:1",
      "quality": "high",
      "tags": ["животные", "космос"],
      "preview": "previews/astro-cat.png"
    }
  ]
}
```

### Поля промта

| Поле | Обязательное | Описание |
|---|---|---|
| `id` | да | уникальный латинский идентификатор |
| `title` | да | название промта |
| `prompt` | да | текст промта |
| `type` | да | `"image"` или `"video"` |
| `model` | нет | рекомендуемая модель (`author/slug`), пусто = модель из настроек приложения |
| `aspectRatio` | нет | image: `1:1`, `16:9`, `9:16`, `4:3`, `3:4`; video: `16:9`, `9:16`, `1:1` |
| `quality` | нет | `auto`, `low`, `medium`, `high` (только image) |
| `durationSec` | нет | `5` или `10` (только video) |
| `tags` | нет | массив строк |
| `preview` | нет | относительный путь к картинке; пусто = плейсхолдер в приложении |

Обновление каталога — обычный push в ветку `main`, релиз APK не требуется.
