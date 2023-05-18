# Извлечение фрагмента текста

## Инструменты и библиотеки:
![Python](https://img.shields.io/badge/-Python-white?style=flat&logo=python)
![Pandas](https://img.shields.io/badge/-Pandas-white?style=flat&logo=pandas&logoColor=130754)
![NumPy](https://img.shields.io/badge/-NumPy-white?style=flat&logo=NumPy&logoColor=3366C5)
![scikit-learn](https://img.shields.io/badge/-scikit-white?style=flat&logo=scikit-learn)
![seaborn](https://img.shields.io/badge/-seaborn-white?style=flat&logo=seaborn)
![matplotlib](https://img.shields.io/badge/-matplotlib-white?style=flat&logo=matplotlib)
![transformers](https://img.shields.io/badge/-LightGBM-white?style=flat&logo=LightGBM)
![HuggingFace](https://img.shields.io/badge/-%F0%9F%A4%97-white?style=flat&logo=%F0%9F%A4%97)
![BERT](https://img.shields.io/badge/-BERT-white?style=flat&logo=BERT)
![PyTorch](https://img.shields.io/badge/-PyTorch-white?style=flat&logo=PyTorch)

## Описание проекта:
В компании X работают с различными документами, такими как: арбитражные иски, госзакупки, исполнительные производства.

**Цель** — построить модель, которая поможет отделу госзакупок извлекать нужный кусок текста из документа для того, чтобы сформировать анкету заявки.

**Задача исследования** — разработать модель, которая будет способна по паре текст документа и пункт анкеты извлекать из текста документа нужный фрагмент текста.

### Описание данных:
**Данные для обучения в формате json имеют следующие поля:**
- `id`: int - id документа
-  `text`: str - текст документа, в котором может содержаться фрагмент текста, соответствующий пункту анкеты из поля `label`
- `label`: str - название пункта анкеты. Может принимать одно из двух значений: `обеспечение исполнения контракта` или `обеспечение гарантийных обязательств`
- `extracted_part`: dict следующего формата:
    ```
    {
        'text': [фрагмент текста из поля `text`, соответствующий пункту анкеты], 
        'answer_start': [индекс символа начала фрагмента текста в тексте документа],
        'answer_end': [индекс символа конца фрагмента текста в тексте документа]
    }
   ```

## Выводы:
В ходе работы было выполнено:

* Загружены данные;
* Проведен исследовательский анализ данных;
* Выполнен Fine-tuning модели из DeepPavlov/rubert-base-cased и проведена преварительная оценка модели на валидационных данных;
* Дообучение модели на полном датасете;
* Прогнозирование на тестовых данных и формирование результатов;
* Проведена оценка модели: точность модели (Accuracy) на тестовых данных составила 0.8270.

**Таким образом, была разработана модель, которая способна по паре текст документа и пункт анкеты извлекать из текста документа нужный фрагмент.**
