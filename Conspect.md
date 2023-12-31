 # Terminal Linux

Linux-терминал – это командная строка операционной системы Linux, которая предоставляет пользователю возможность управлять системой через команды. Первые терминалы с командной строкой появились задолго до Linux и использовались в операционных системах UNIX, таких как Unix System V и BSD UNIX.
## Зачем он нужен тестировщику?
Чтобы посмотреть серверные логи, запустить скрипты (автотесты), запустить\собрать сборку. 95% серверов работают на система Linux т.к она бесплатная и очень хорошо подходит по функционалу. Серверная версия Linux не графическая, в ней отключен графический интерфейс и взаимодействие происходит только через терминал. Есть онлайн FTP-клиенты и десктоп такие как FileZilla, Total Commander, ForkLift с их помощью можно подключиться к серверу и использовать графическое отображение, но если допустим, мы просматриваем лог файл клиентов на миллион строк чтобы понять как определённый пользователь положил сервер, терминал будет работать быстрее когда нужно будет отфильтровать конкретного пользователя и положить эти данные в другой файл.
## Различия терминалов Linux и GitBash
Одно из основных отличий заключается в том, что Linux-терминал является стандартной командной оболочкой для операционной системы Linux, основанной на ядре Linux. А Git Bash - это своего рода мост между Windows и линуксоидными системами, его сделали разработчики Git. Он позволяет использовать мощные команды, которые встречаются в Linux, но при этом оставаться в Windows с привычным пользовательским интерфейсом.
## Примеры команд
`pwd` - отображение текущего рабочего каталога (где я нахожусь)
`ls` - отображение содержимого текущего каталога
+ ключ `-la` показывает скрытые папки, права доступа, дату создания
+ `-R` -рекурсивный просмотр директории
+ `-Rla` -ключ, показывающий все папки и их содержимое

`cd` - переход в указанный каталог
+ `../` - указатель на родительскую папку
+ `./` - указатель на текущую папку
+ `~` - домашний каталог
+ `cd -` -вернуться к предидущему каталогу
+  `/c/home/user/images/pic.jpg` -абсолютный путь 
+  `../images/pic.jpg` -относительный\не полный путь до файла
+ `cd ../folder1` -зайти в folder1 через родительскую папку

`start .` -открыть текущую папку в проводнике Windows
`open ./` -открыть текущую папку на Mac
`mkdir`- создание нового каталога 
+ `mkdir {d_1,d_2,d_3}` // создание 3 папок в файле
+ `mkdir -p d_4/d_5/d_6` // рекурсивное создание внутри папки внутри папки 
+ `touch` или `>` - создание новых файлов, через `.` можно указать расширение `touch file.txt` или `>file.txt`

`rm` - удаление файлов или каталогов
`cp` - копирование файлов и каталогов
+ `cp folder1/file.txt folder2/file.txt` -при указании куда можно переименовать файл `cp folder1/file.txt folder2/new_file.txt` 

`mv` - функция перемещения или переименования файлов и каталогов `mv folder2/new_file.txt folder3/new_file.txt`
`cat` - отображение содержимого файла
+ `cat > users.txt` -создание файла\перезапись текста в файле
+ `cat >> users.txt` -добавление информации в файл
+ `cat users.txt >> users2.txt` -соединение двух файлов в файл users2.txt
+ `cat n1.txt n2.txt` -вывести содержимое двух файлов
+ `cat n1.txt n2.txt > n3.txt` -записать содержимое `n1.txt n2.txt` в `n3.txt`
`vim` - редактор текстового файла
+ сочетанием клавиш `ctrl+/` можно включить поиск текста в файле
+ клавиша `i` включает режим редактирования (INSERT)
+ после завершения редактирования файла жмём `Esc`
+ во время редактирования можно откатить изменения с помощью `:u`
+ `shift+:` для сохранения и выхода пишем `wq`
`clear` или `ctrl+l` -очистить окно терминала 
`history` - отображение истории команд
+ `history >> history.txt` -для выгрузки истории команд в файл

`find` - поиск файла и директорий
+ `find d1 -type f -name "*n*"` - искать в папке _d1_ ***файлы*** `type -f` имя которых содержит букву "n" в названии `-name "*n*"` (поиск регистрозависимый), `*` -всё что угодно
+`find . -name *.png` -найти в текущей директории файл с расширением `png`

+ `find . -type d -name "*d*"` - искать в текущей директории `.` и ниже по дереву все ***папки*** `-type d` имя которых содержит букву "d" в названии (поиск регистрозависимый, используй команду `-iname` чтобы использовать независимый регистр)

`grep` - поиск текста внутри файла
+ `grep -c inna d1/n1.txt` -посмотреть сколько раз встречается текст `inna` в файле `d1/n1.txt`
###### поиск если ==знаем== какой конкретно файл нужен:
+ `grep inna d1/n1.txt` -поиск в файле `d1/n1.txt` строчки `inna` написанный в нижнем регистре.
+ `grep -ir inna d1/n1.txt` -рекурсивный поиск в файлах строчки `inna` написанный в любом регистре
+  `grep -i inna d1/n1.txt d2/n4.txt` -поиск строчек `inna` в файлах `d1/n1.txt` и `d2/n4.txt`
+ `grep Anna d1/n1.txt` - найти текст `Anna` в директории `d1/n1.txt`
+ `grep Anna d1/n1.txt d2/n4.txt` - найти текст `Anna` в директориях `d1/n1.txt` и `d2/n4.txt`
###### поиск если ==не знаем== какой конкретно файл нужен:
+ `grep -r -w inna d1` -рекурсивный поиск конкретного `-w` слова `inna` в папке `d1`
+ `grep -r -i inna . > Inna_Logs.txt` - найти рекурсивно не зависимо от регистра текст `inna` в текущей `.` директории и сохранить результат в отдельный файл `> Inna_Logs.txt`


`less` -команда для просмотра файла в отдельном окне, чтобы вернуться в терминал, используем кнопку `q`
+ `/inna` -найти текст inna в просмотрщике текста less



`curl` - передача данных по сети по различным протоколам
`kill` - отправка сигнала процессу для его остановки
`ping` - проверка доступности узла по сети
`uname` - отображение информации о системе
`echo` - отображение текста или переменной
`date` - отображение текущей даты и времени
`sudo` - выполнение команды с привилегиями суперпользователя
`clear`- очистка экрана
`exit` - выход из текущего сеанса
`head` - отображение первых строк файла
`tail` - отображение последних строк файла
`wc` - подсчет количества строк, слов и символов в файле
`sort` - сортировка строк файла
`sed` - потоковый текстовый редактор для обработки и фильтрации текста
`awk` - язык для обработки и анализа текстовых данных
`diff` - сравнение двух файлов
`file` - определяет тип файла на основе его содержимого и выводит соответствующую информацию.
`top` - отображает список текущих процессов и их ресурсов, что позволяет отслеживать производительность системы.


