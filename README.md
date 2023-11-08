# Програмна реалізація алгоритму гешування SHA-1
## Завдання
### Власна реалізація алгоритму гешування на вибір
Напишіть власну реалізацію алгоритму гешування SHA-1 або SHA-3 (Keccak) на вибір. Зверніть увагу, що ці алгоритми гешування є блочними і вхідні дані слід правильно розділити на порції, кожна довжиною рівно один блок. Якщо останній блок є неповним його треба доповнити згідно зі специфікацією алгоритма.
Ваша функція повинна мати змогу загешувати будь-які дані довільної довжини. В більш розширеному варіанті можете реалізувати подачу вхідних даних порціями, тобто щоб можна було декілька разів викликати функцію гешування передаючи кожну наступну порцію даних для гешування. Ця функціональність буде доречна для гешування дуже великих обсягів даних, коли неприпустимо зберігати одразу весь аргумент функції в памʼяті.
### Тест на співпадіння гешу з бібліотечною реалізацією
Метою цього етапу є перевірка вашої реалізації на коректність. Для цього оберіть декілька повідомлень різної довжини: до одного блока, більше одного блока, декілька блоків. Далі обчислить геш-значення від цих повідомлень використовуючи вашу реалізацію і використовуючи бібліотечну реалізацію від сторонніх розробників. Результати гешування порівняйте попарно з зробіть висновок щодо коректності обчислень. У разі необхідності знайдіть і виправте помилки у вашій реалізації.
### Порівняння швидкодії власної реалізації з бібліотечною
Метою цього етапу є оптимізація вашої реалізації алгоритму гешування для зменшення обсягу памʼяті і процесорного часу, що використовуються для обчислення геш-значення від повідомлення певної довжини. Для виконання цього етапу зробіть замір часу витраченого на гешування певного повідомлення вашою функцією і замір часу гешування функцією з готової бібліотеки. Результати замірів порівняйте і зробіть висновок щодо ефективності вашої реалізації.
Обсяг використаної памʼяті можна виміряти додатковими інструментами моніторингу ПЗ або вашої ОС. Усі результати порівняння можна викласти у файлі readme.md вашого репозиторію.

## Інструкція щодо запуска коду
Код розроблено з використанням Python 3.10.7. Для запуску коду необхідно мати встановлений Python відповідної або більш нової версії та прописати наступну консольну команду у директорії файлу:
```python
python .\MySHA1_Kitsun.py
```
## Приклад визову програми та результату виконання програми
Приклад визову програми та результату виконання програми зображено на рисунку нижче. Також даний скріншот можна знайти в репозиторії.

![Code_exectuion_example](https://github.com/KKitsun/My-SHA-1/blob/master/ExecutionExample_MySHA1.PNG)

## Висновок щодо ефективності власної реалізації
За результатами вимірювань видно, що моя власна реалізація алгоритму гешування SHA-1 значно повільніша в порівнянні з бібліотечною функцією hashlib.sha1().
Це різке розходження в часі виконання свідчить про те, що моя реалізація SHA-1 не є ефективною в порівнянні з бібліотечною реалізацією. Бібліотечні функції, як правило, оптимізовані та ефективніше використовують апаратне обладнання або спеціалізовані оптимізації для обчислень геш-кодів.

Результати неефективності власної реалізації SHA-1 можуть бути пояснені кількома чинниками: низька або неспеціалізована оптимізація (В бібліотечних реалізаціях часто використовуються низькорівневі оптимізації, процесорні інструкції тощо), використання функцій та алгоритмів, що є дуже вимогливими до ресурсів (використання функцій зі struct, внутрішні цикли, велика кількість обчислень, особливості обраної мови програмування).

З цього можна зробити висновок, що для обчислення геш SHA-1 краще використовувати бібліотечні функції, оскільки вони працюють набагато швидше і зазвичай надійніше. Власні реалізації можуть бути корисні для навчання або певних досліджень, але в реальних застосуваннях важливо обирати оптимізовані та перевірені бібліотечні функції.
