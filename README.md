Predict-Grant-Applications
==========================

## Описание задачи

Проект решает задачу бинарной классификации из соревнования **“Predict Grant Applications”** на Kaggle.  

Цель — по табличным данным о заявке (характеристики проекта, исследователей, финансирования и т.п.) предсказать, будет ли грант **одобрен** (`Grant.Status = 1`) или **отклонён** (`Grant.Status = 0`).

Ссылка на соревнование Kaggle: https://www.kaggle.com/competitions/unimelb/overview

## Структура проекта

- **`data/`**: данные соревнования.
  - `unimelb_training.csv` — обучающая выборка с целевой переменной `Grant.Status`.
  - `unimelb_test.csv` — тестовая выборка без целевой переменной (для сабмита на Kaggle).
  - `unimelb_training.csv.zip` — исходный архив с Kaggle.
- **`notebooks/`**:
  - `main.ipynb` — основной ноутбук с:
    - загрузкой данных;
    - разведочным анализом (EDA), в том числе анализом `Grant.Status`;
    - постановкой задачи классификации;
    - обучением моделей с помощью **LightAutoML**;
    - оценкой качества (например, `roc_auc`, `accuracy`).
- **`pyproject.toml`** — конфигурация Poetry с зависимостями (Python 3.10.10).

## Данные: где лежат и откуда скачать

Локально данные ожидаются в папке:

- `/home/darinka/projects/Predict-Grant-Applications/data/unimelb_training.csv`
- `/home/darinka/projects/Predict-Grant-Applications/data/unimelb_test.csv`

Их можно скачать со страницы соревнования Kaggle (раздел **Data**): https://www.kaggle.com/competitions/unimelb/data

После скачивания:

1. Разархивировать архив Kaggle
2. Положить файлы `unimelb_training.csv` и `unimelb_test.csv` в папку `data/` проекта.

## Установка зависимостей

Проект использует **Poetry**.

1. Установить Poetry
2. В корне проекта `/home/darinka/projects/Predict-Grant-Applications` выполнить:

```bash
poetry install
```

Будет создано виртуальное окружение с необходимыми зависимостями (`lightautoml`, `fasttext-numpy2`, `nltk` и т.д.).

## Порядок запуска анализа и моделей

1. Перейти в корень проекта:

```bash
cd /home/darinka/projects/Predict-Grant-Applications
```

2. Активировать окружение Poetry:

```bash
poetry shell
```

3. Запустить Jupyter (Notebook или Lab), например:

```bash
jupyter notebook
```

или

```bash
jupyter lab
```

4. В интерфейсе Jupyter открыть ноутбук `notebooks/main.ipynb`
5. Выполнить ячейки ноутбука по порядку.