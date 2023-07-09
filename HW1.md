# Первое ДЗ https://img.shields.io/badge/just%20the%20message-8A2BE2
## Linux terminal (GitBash) commands
**1) Посмотреть где я** 
`=> pwd`  
___
- 2) *Создать папку* => mkdir master_folder
___
+ 3) Зайти в папку => cd master_folder
___
* 4) Создать 3 папки => mkdir fold_1 fold_2 fold_3
5) Зайти в любоую папку => cd fold_1
6) Создать 5 файлов (3 txt, 2 json) => touch 1.txt 2.txt 3.txt 1test.json 2test.json
7) Создать 3 папки => mkdir n_1 n_2 n_3
8) Вывести список содержимого папки => ls -la
9) + Открыть любой txt файл => cat 1.txt
10) + написать туда что-нибудь, любой текст. => vim 1.txt => нажать на кнопку i => вводим текст в файл
11) + сохранить и выйти. => esc => вводим а клавиатуре ":wq" 
12) Выйти из папки на уровень выше cd ..
—
13) переместить любые 2 файла, которые вы создали, в любую другую папку. => mv fold_1/{1test.json,3.txt} .
14) скопировать любые 2 файла, которые вы создали, в любую другую папку. => cp fold_1/{2.txt,2test.json} fold_2
15) Найти файл по имени => find . -maxdepth 5 -type f -name "*test*"
16) просмотреть содержимое в реальном времени (команда grep) изучите как она работает. => tail -f fold_1/1.txt
17) вывести несколько первых строк из текстового файла => head -n2 fold_1/1.txt
18) вывести несколько последних строк из текстового файла => tail -n2 fold_1/1.txt
19) просмотреть содержимое длинного файла (команда less) изучите как она работает. => less fold_1/1.txt => выйти буква q на клавиатуре
20) вывести дату и время => date
=========

Задание *
1) Отправить http запрос на сервер.
http://162.55.220.72:5005/terminal-hw-request =>  curl http://162.55.220.72:5005/terminal-hw-request => curl "http://162.55.220.72:5005/get_method?name=Pavel&age=28"
   Результат:
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100    16  100    16    0     0    154      0 --:--:-- --:--:-- --:--:--   155["(6)","(279)"]

2) Написать скрипт который выполнит автоматически пункты 3, 4, 5, 6, 7, 8, 13
```bash
#!/bin/bash

echo "Привет, это мой первый скрипт на bash, и здесь мы выполняем пункты 3,4,5,6,7,8,13"
echo "let's go"
mkdir master_folder
cd master_folder
mkdir fold_1 fold_2 fold_3
cd fold_1
touch 1.txt 2.txt 3.txt 1test.json 2test.json
mkdir n_1 n_2 n_3
ls -la
mv {1test.json,3.txt} ../..
```

