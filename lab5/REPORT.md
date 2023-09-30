# Отчёт по лабораторной работе
## Генеративные текстовые нейросети
### Студенты: 

| ФИО       | Роль в проекте                     | Оценка       |
|-----------|------------------------------------|--------------|
| Андреев А. О. | Программировал LSTM модели, писал отчет |       |
| Попов И. П. | Программировал SimpleRNN модели, писал отчет |      |
| Семин А. В.  | Программировал LSTM модели, писал отчет |          |

> *Комментарии проверяющего*

## Датасет

В качестве датасета мы решили взять текста песен. Исходные данные - текста песен, а результат - оригинальный язык песни. Данный датасет мы нашли только в формате .csv, поэтому для его обработки использована библиотека pandas. Мы делим датасет на обучающий (80%) и тестовы (20%). Для этого используем библиотеку sklearn.

## SimpleRNN

Создаём простую нейросеть с одним слоем SimpleRNN. Перед ней также создаем vectorizer, который обрабатывает массив строк ( или тензоры) и делит их на отдельные текстовые единицы через пробелы в зависимости от параметра split. 

Для сжатия используем Embedding, потому что словарь целых слов очень большой, а его использования позволяет сэкономить память.

Параметры для обучения мы старались подбирать так, чтобы нейросеть не выбирала единственный класс и не пыталась сопоставить все с ним.

## LSTM

Модель LSTM сложнее, поэтому лучше обучается и даёт большую точность.
Мы реализовали три модели:
- однослойная однонаправленная модель;
- двуслойная однонаправленная модель;
- однослойная двунаправленная модель.

Параметры слоёв регулировались вручную, исходя из результатов обучения при тех или иных параметрах.

## Трансформерная архитектура

Для создания трансформерной архитектуры мы использовали библиотеку keras_nlp. Она позволяет разбивать тензоры строк на токены из слов. После мы произвели преобразование, создали модель и обучили нейросеть.