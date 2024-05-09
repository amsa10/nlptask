# nlptask

Классификация текстов при помощи ключевых слов неотъемлемая часть
современных диалоговых систем, при помощи данного метода можно точно, а главное
весьма надежно определять интент и соответственно дальше вести пользователя по
схеме внутри диалоговой системы.
Task
Нужно построить алгоритм который по ключевым словам из датасета Medium
Stories умеет сопоставлять правильно Tag к тексту
Ссылка на датасет - https://www.kaggle.com/datasets/harrisonjansma/medium-stories
1) скачать датасет
2) проанализировать, обработать и извлечь тексты и теги
3) полученный датасет разбить на train/test в соотношении 80% / 20%
4) При помощи различных подходов и методов на основе корпуса текстов из train
выборки, определить набор ключевых слов к каждому тегу/label
5) Продемонстрировать точность алгоритма классификатора тегов, на
основе мэтчинга по ключевым словам на тестовой(test) выборке
6) Результат работы передать в виде проекта в гитхаб или jupyter-notebook.
Примечание 1: не обязательно брать все теги из датасета, достаточное количество -
30, но не меньше. Если весь датасет не помещается в вашу оперативную память,
нужно взять наибольший сэмпл.
Примерчаение 2:
Tag - это label,класс текста
Keywords - набор ключевых слов извлеченных из множества текстов относящихся к
определенному тегу (tag “football”, keywords: ‘Football’, ‘league of champions’, ‘cristiano’,
‘Cristiano Ronaldo’, ‘cr7’, ‘world cup’, ‘Ballon d'Or’)
Алгоритм действий(input-output):
1. input - это текст статьи(заголовок, дескрипшн не важно) в виде строки, который
мы токенизируем каким либо образом(делим по пробелу, делим на нграммы итд
на ваш выбор), тем самым строку текста - переводим во множество ключевых
слов/фраз/токенов.
2. Далее определенным алгоритмом к каждому Tag/Label - назначаем набор его
самых важных ключевых слов/фраз/токенов
3. Затем мы создаем алгоритм/правило - мэтчинг input к Tag путем пересечения
множеств их ключевых слов. Условно если пересекается на 70% - да, иначе -
нет.(threshold выбирается вами)
4. output: tag/label каждого входящего текста

![image](https://github.com/amsa10/nlptask/assets/51148660/d1da4ae9-676b-4b62-8dd4-60912c1bdb40)

Ответ: по ключевым словам матчин и классификация  не самый лудший подход и нет смысла делать 

подход трансфр ленинг  или ZSM модели лудше использовать 



Cons:

Limited Flexibility: Keyword matching relies heavily on the keywords you choose. If a keyword is missing or if the text contains variations or synonyms that are not covered by your keywords, the classification may be inaccurate.
Lack of Contextual Understanding: Keyword matching doesn't capture the context or semantic meaning of the text. It simply checks for the presence of specific words or phrases, which may lead to misclassification in cases where context is crucial.
Scalability: Managing a large number of keywords and tags can become cumbersome and difficult to maintain, especially as the dataset or the number of tags grows. It may require frequent updates and adjustments to the keyword lists.
Handling Ambiguity: Text classification often deals with ambiguous or nuanced language. Keyword matching alone may struggle to handle such cases where multiple tags could potentially apply based on the same keywords.
