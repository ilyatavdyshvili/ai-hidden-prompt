# План тестирования

## Smoke
- сервис запускается;
- `/health` возвращает OK;
- PNG/JPEG принимаются;
- некорректный файл отклоняется.

## Functional
- создаётся job;
- job переходит по статусам;
- результат содержит regions и score;
- GUI показывает bounding boxes.

## ML
- detection: Precision/Recall/F1;
- OCR: CER/WER;
- classifier: Precision/Recall/F1/PR-AUC;
- end-to-end: Recall/F1/FPR.

## Robustness
Сформировать версии изображений с resize, blur, JPEG compression, noise, contrast, rotation и crop.

## Regression
Хранить фиксированный golden set и сравнивать метрики каждой версии.
