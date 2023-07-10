# HW#1: Linux terminal (GitBash) commands
![OS](https://img.shields.io/badge/выполненно%20на%20платформе%20Windows%2010-0000FF)
___
1) *Посмотреть где я* :  `pwd`  
___
2) *Создать папку* : `mkdir master_folder`
___
3) *Зайти в папку* : `cd master_folder`
___
4) *Создать 3 папки* : `mkdir fold_1 fold_2 fold_3`
___
5) *Зайти в любоую папку* : `cd fold_1`
___
6) *Создать 5 файлов (3 txt, 2 json)* : `touch 1.txt 2.txt 3.txt 1test.json 2test.json`
___
7) *Создать 3 папки* : `mkdir n_1 n_2 n_3`
___
8) *Вывести список содержимого папки* : `ls -la`
___
9) *Открыть любой txt файл* : `cat 1.txt`
___
10) *Написать туда что-нибудь, любой текст* : `vim 1.txt` => нажать на кнопку `i` => вводим `text` на клавиатуре
___
11) *Сохранить и выйти.* : `esc` затем вводим а клавиатуре `:wq` 
___
12)  *Выйти из папки на уровень выше* : `cd ..`
___
13) *Переместить любые 2 файла, которые вы создали, в любую другую папку* : `mv fold_1/{1test.json,3.txt}`
___
14) *Скопировать любые 2 файла, которые вы создали, в любую другую папку* : `cp fold_1/{2.txt,2test.json} fold_2`
___
15) *Найти файл по имени* : `find . -maxdepth 5 -type f -name "*test*"`
___
16) *Просмотреть содержимое в реальном времени (команда grep) изучите как она работает* : `tail -f fold_1/1.txt`
___
17) *Вывести несколько первых строк из текстового файла* : `head -n2 fold_1/1.txt`
___
18) *Вывести несколько последних строк из текстового файла* : `tail -n2 fold_1/1.txt`
___
19) *Просмотреть содержимое длинного файла (команда less) изучите как она работает.* : `less fold_1/1.txt` => выйти из команды клавиша `q` на клавиатуре
___
20) *Вывести дату и время* : `date`
___

####Дополнительные задание под :star:

1) *Отправить http запрос на сервер.
http://162.55.220.72:5005/terminal-hw-request* :  

`curl http://162.55.220.72:5005/terminal-hw-request` 

_Response:_

`curl "http://162.55.220.72:5005/get_method?name=Pavel&age=28"`
   _Response:_
  ```gitbash
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100    16  100    16    0     0    154      0 --:--:-- --:--:-- --:--:--   155["(6)","(279)"]
```
___

2) *Написать скрипт который выполнит автоматически пункты 3, 4, 5, 6, 7, 8, 13* :

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

