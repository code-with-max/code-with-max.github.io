---
layout:     post
title:      "xClip. Копируем чувствительные данные из файла сразу в буфер обмена"
categories: [Linux, CLI]
tag:        [linux, cli, xclip]
---


## xclip
##### Копирует в буфер из стандартного ввода или выводит содержимое буфера в стандартный вывод. Работает в xOrg


Устанавливаем:

```bash
sudo apt install xclip
```


##### В системе используется два буфера обмена:
Буфер оболочки

```bash
xclip file_name
```

Системный буфер

```bash
xclip -sel clip file_name
```


Скопировать вывод команды в буфер:

```bash
echo 123 | xclip -i
```


Скопировать вывод команды в системный буфер:

```bash
echo 123 | xclip -sel clip
```


Скопировать вывод выполнения команды: 

```bash
top | xclip
uptime | xclip
```


Копировать файл в системный буфер:

```bash
cat myfile.txt | xclip -sel clip
```


Вставка из буфера:

```bash
clip -o > file.txt
```


##### Aliases (псевдонимы)
[CLI bash Aliases]()

Откроем файл:

```bash
nano  ~/.bash_aliases
```


Допишем строки:

```bash
alias pbcopy='xclip -sel clip'
alias pbpaste='xclip -sel clip -o'
```


Для применения изменений выполнить:

```bash
. ~/.bashrc
```


Псевдонимы pbcopy и pbpaste использованы пол аналогии с системой macosx. Использовать можно любые названия по желанию.
