# Руководство по выполнению практики
В рамках практики задачей каждого студента становится дополнение существующей главы из монографии. Т.е. у нас есть монография, у нас есть в ней главы на определённые темы, а в этих главах есть описываемые понятия (определения/термины).

Теперь всё просто, нам необходимо взять какую-то главу (её тему) и найти в интернете статьи с такой же тематикой и прочитать её (опционально).

Далее нам следует обратить внимания на те определения в найденной статье, которые послужат (как нам кажется) хорошим дополнение для монографии или стандарта.

После чего мы записываем найденные понятия на SCn-коде в наш отчёт, записываем библиографические ссылки на них (т.е указатель на источник, откуда было взято понятие), делаем вывод и идём на вайбе сдавать работу нашему преподавателю.

## Начало работы
Перед началом работы необходимо определиться какую главу вы будете "дополнять", сделать это необходимо в [таблице](https://docs.google.com/spreadsheets/d/1xcR9IC5qsCP4gtq0eL4nDYyJ7BdNZp_Fi16MQDGd4e4/edit#gid=2081981130).

(ВНИМАНИЕ! Выбираете клетку и оставляете в ней комметарий с вашей фамилией и группой, ибо просто отредактировать таблицу уже не разрешают. Ваши комметарии видны всем, не переживайте)

![](https://github.com/sourist/guide/blob/main/assets/table.gif)

## Поиск понятий

Поиск статей на выбранную тему можно осуществлять любыми способами, но 9/10 стоматологов рекомендуют [Google Академию](https://scholar.google.com/), так что будем использовать её.

Вставляем в строку поиска тему и ищем что-то интересное.

![](https://github.com/sourist/guide/blob/main/assets/finding.gif)

(Рекомендую зарегистрироваться на сайте [elibrary](https://www.elibrary.ru/defaultx.asp?), так как там лежит много полезных статей).

Находим статью, находим понятие, формулируем или копируем его определение.

## Добавление понятий в отчёт
### Настройка отчёта
Для начала необходимо создать сам отчёт, пример можно найти [здесь](https://www.overleaf.com/read/cjtjbmnbgqrh#6a9cb3).

Далее алгоритм следующий:

1. Присоединяемся к проекту отчёта на overleaf по [ссылке](https://www.overleaf.com/read/cjtjbmnbgqrh#6a9cb3).
2. Переходим на главную страницу и делаем личную копию примера отчёта.
3. Заходим в скопированный проект и начинаем редактировать его под себя.

![](https://github.com/sourist/guide/blob/main/assets/copy%20project.gif)

Тут лучше создать свой собственный файл с вашими определениями, чтобы не возникало путаницы с тем, что было в примере отчёта.

(Примеры из отчёта лучше не удалять, так как по ним можно в будущем подсматривать команды, а удалить их уже после окончания работы с вашей частью)

Создадим файл *practice*.

![](https://github.com/sourist/guide/blob/main/assets/added%20file.gif)

Важно, в начале и конце файла для корректной работы команд SCn-кода необходимо прописать следующее:
```LaTex
\begin{SCn}
\begin{small}

%Основной блок текста с формализацией

\end{small}
\end{SCn}
```

После его создания, его необходимо подключить к нашему основному проекту, делается это в файле *content.tex* следующим образом:

```LaTex
\newpage
\section{Формализованные фрагменты теории интеллектуальных компьтерных систем и технологий их разработки}
\input{practice}
```

![](https://github.com/sourist/guide/blob/main/assets/added.gif)

(похоже на подключение библиотек на C++)

Теперь всё готово для непосредственной работы с найденными определениями.

### Добавление понятий

Примечание: если вы не знаете, как изобразить какую-то структуру SCn-кода на LaTex, то вам стоит попытаться найти примеры с похожей записью в скопированном отчёте и затем просмотреть их код, изучить (опционально) и скопировать в свой файл, изменив необходимый текст на свой.

Базовые команды:

* `\scnheader{понятие}` - наименование самого понятия
* `\scnidtf{определение понятия}` - здесь, в скобочках записывается определение понятия или любой текст ракрывающий его. Может записываться несколько раз, если есть несколько определения этого понятия, например, из разных источников.
  Так же в подобной конструкции записывается английский термин для понятий.
* `\scntext{примечание}{текст}` - используется для дополнения информации о понятии каким-нибудь текстом, необязательно определением. Чаще всего используется для создания примечаний к понятиям. В первых фигурных скобках укзаыается какое отношение имеет текст к понятию, а во вторых сам текст.
* `\scnsubdividing{компонет 1; компонент 2; ...}` - используется для разбиения понятия на несколько, т.е если существует какое-то количество более узких терминов, которые объединяются нашим понятием. Компоненты разбиения записываются
  в фигурных скобках, разделяясь точкой с запятой.
* Следующая структура кода используется для указания библиографических источников вашего понятия:
  
  ```LaTex
  \begin{scnrelfromlist}{библиографическая ссылка}
      \scnitem{Источник 1}
      \scnitem{Источник 2}
      \scnitem{...}
  \end{scnrelfromlist}
  ```

С этими знаниями уже можно выполнить 90% работы.

![](https://github.com/sourist/guide/blob/main/assets/%D0%A1%D0%9C%D0%90%D0%99%D0%9B%D0%98%D0%9A%20%D0%A1%D0%98%D0%94%D0%98%D0%A2%20%D0%97%D0%90%20%D0%9A%D0%9E%D0%9C%D0%9F%D0%AC%D0%AE%D0%A2%D0%95%D0%A0%D0%9E%D0%9C.gif)

### Пример формализации понятия

1. Читаем статью, находим понятие. Как пример возьмём "вопросно-ответная система". Оно является одним из ключевых в данной статье, его более-менее подробно описали и привели несколько конкретных примеров этой системы.

![](https://github.com/sourist/guide/blob/main/assets/%D0%BF%D0%BE%D0%BD%D1%8F%D1%82%D0%B8%D0%B5.png)

2. Сразу можем добавить найденное понятие в наш отчёт. И тут же добавляем в качестве определения его перевод на английский. Начало положено.
   
(Обратите внимание, что понятие записывается с маленькой буквы, так как это не конкретная сущность, а что-то более общее)

![](https://github.com/sourist/guide/blob/main/assets/1.jpg)

3. Возвращаемся к статье. Перечитаваем абзац с понятием, формулируем для него определение и записываем определение в отчёт. Мы уже получили основу нашего понятия.

![](https://github.com/sourist/guide/blob/main/assets/2.jpg)

Можем ещё добавить примечание для подробного раскрытия определения.

![](https://github.com/sourist/guide/blob/main/assets/2.1.jpg)

4. Снова возвращаемся к статье, опускаемся ниже, здесь нам представляют несколько конкретных примеров вопросно-ответных систем.

![](https://github.com/sourist/guide/blob/main/assets/4.1.png)
![](https://github.com/sourist/guide/blob/main/assets/4.2.png)
![](https://github.com/sourist/guide/blob/main/assets/4.3.png)
![](https://github.com/sourist/guide/blob/main/assets/4.4.png)
![](https://github.com/sourist/guide/blob/main/assets/4.5.png)

Нам следует добавить их в отчёт.

(Добавим в конце нашего списка "...", чтобы дать понять, что есть и другие вопросно-ответные системы)

![](https://github.com/sourist/guide/blob/main/assets/3.jpg)

5. Наконец, укажем библиографический источник для понятия. Для этого вернёмся на страницу со статьёй, возьмём её название, автора и добавим в отчёт.

![](https://github.com/sourist/guide/blob/main/assets/4.jpg)

Так как статья лежит в интернете, то можем добавить ещё и её URL. Финальный штрих.

![](https://github.com/sourist/guide/blob/main/assets/5.jpg)

Таким образом мы формализовали понятие "вопросно-ответная система" из [этой статьи](https://www.elibrary.ru/item.asp?id=34887564).

![](https://github.com/sourist/guide/blob/main/assets/result.png)

Код:

```LaTex
\scnheader{вопросно-ответная система}
\scnidtf{question-answering system}
\scnidtf{система, предназначенная для автоматического ответа на вопросы, заданные на естественном языке}
\scntext{примечание}{В вопросно-ответных системах ответ генерируется на языке запроса, в то время как в системах общения с базами данных ответ может формироваться из обычного набора данных, хранящихся в базе.}
\begin{scnrelfromvector}{вопросно-ответные системы}
    \scnitem{Система START}
    \scnitem{Женя Густман}
    \scnitem{Простая вопросно-ответная система на основе семантического анализатора русского языка}
    \scnitem{RAZOOM}
    \scnitem{ITFRU}
    \scnitem{...}
\end{scnrelfromvector}
\begin{scnrelfromlist}{библиографическая ссылка}
    \scnitem{Бородин, Д.С. \it{Системы искуственного интеллекта в задачах обработки естественного языка}}
    \begin{scnindent}
    \scntext{URL}{https://www.elibrary.ru/item.asp?id=34887564}
    \end{scnindent}
\end{scnrelfromlist}
```

Одно понятие есть, осталось всего девять, алгоритм такой же. Удачи.

![](https://github.com/sourist/guide/blob/main/assets/scweb.gif)
