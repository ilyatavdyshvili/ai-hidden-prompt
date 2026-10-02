# Данные

## Рекомендуемая структура

```text
data/
  raw/
  synthetic/
  annotations/
  train/
  val/
  test/
```

## Формат annotation.json

```json
{
  "image_id": "img_000001",
  "language": "ru",
  "regions": [
    {
      "bbox": [100, 200, 300, 240],
      "text": "пример инструкции",
      "label": "prompt_injection_candidate"
    }
  ]
}
```

## Правило split

Все производные изображения одного исходного изображения должны находиться только в одном split. Это предотвращает leakage между train и test.
