# Архитектура

## Слои

1. Presentation: Web GUI, REST API, CLI.
2. Application: Job Manager, orchestration.
3. ML pipeline: preprocessing, multi-scale, detection, OCR, classification.
4. Data: result storage, optional object storage and DB.

## Контракты

Каждый модуль должен принимать/возвращать типизированные структуры, а не произвольные словари.

Пример:

```text
ImageInput
  -> ImageVariant[]
  -> TextRegion[]
  -> OCRResult[]
  -> ClassificationResult[]
  -> AggregatedFinding[]
  -> AnalysisResult
```

## Принцип

ML-модули не должны напрямую зависеть от HTTP или UI. API-слой вызывает application service, который запускает pipeline.
