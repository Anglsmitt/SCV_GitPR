![Logo](Git-Logo-2Color.png)


# Работа с Git

## 1. Проверка наличия установленного Git
В терминале набрать 
```bash
git --version

```
 если Git установлен,  появиться сообщени с версией программы. Иначе будет сообщение об ошибке

## 2. Установка GIt
Устанавливаем последнюю версию программы с [сайта](https://git-scm.com/downloads) 

устанавливаем с настройками по умолчанию

## 3. Настройка Git

Настраиваем Git, для этого в терминале надо ввести команды:

```bash
git config --global user.name "My Name"
git config --global user.email myEmail@example.com
```


## 4. Инициализация репозитория 

Выбираем **открыть папку** и находясь в нужной папке вводим команду

```bash
git init
```

## 5. Запись изменений в репозиторий

Записать изменения в репозиторий можно двумя способами

1. Командой 
```bash
git add имя файла
```
И затем закрепить командой 

```bash
git commit -m "текст коментария"
```
2. Командой

```bash
git commit -am "текст коментария"
```
Эта команда работает только для файлов закомиченных  ранее, новый файл добавить в репозиторий не получится.

## 6. Просмотр истории коммитов
Список всех сохраненных коммитов в репо0зитории доступен по команде
```bash
git log
```

## 7. Перемещение между сохранениями (коммитами)

Чтобы перерместиться между коммитами мы используем команду

```bash
git checkout первые 6 знаков в ID сохранения
```
Для перемещения на главную ветку
```bash
git checkout master
```
Либо
```bash
git switch master
```

## 8. Игнорирование файлов
Для того, чтобы исключить из отслеживания репозиторием файлов или папок нужно создать файл ***.gitignore*** и записать в него относительный путь требуемых файлов или папок.

## 9. Создание веток в Git
По умолчанию имя основной ветки в Git - **master**

Для того, чтобы создать новую ветку надо ввести команду
```bash
git branch имя ветки
```
Для просмотра списка веток в репозитории вводим команду
```bash
git branch
```

## 10. Слияние веток и разрешение конфликтов


Чтобы слить две ветки между собой, например после редактирования черновика мы вносим изменения в основной файл, переходим в основную ветку командой 
```bash
git switch имя ветки
```
или
```bash
git checkout имя ветки
```
затем выполняем команду

```bash
git merge имя ветки черновика
```

Если в обоих ветках на одних строках есть разные значения Git сообщит о конфликте и предложит его решить

## 11. Удаление веток

Перед удалением ветки надо из нее выйти. Нельзя удалить ветку находясь в ней.

Для удаления веток используется команда
```bash
git branch -d имя ветки
```

Если есть конфликт, но вы не хотите их вносить эти изменения в основную ветку исползуется команда 
```bash
git branch -D имя ветки
```

## 12. работа с удаленный репозиторием

Заходим на сервис удаленных репозиториев, например GitHub, открываем интересующий нас репозиторий и копируем его в свой с помощью кнопки `fork`. Заходим в свой аккаунт, выбираем скопированный репозиторий, копируем его адрес, который находится под зеленой кнопкой `Code`. Переходим в локальный репозиторий, открываем папку в которую будем клонировать интересующий репозиторий. Вводим команду 
```bash
git clone скопированный адрес репозитория
```
Команда `git clone` составная: она не только Загружает все изменения, но и пытается слить все ветки на локальном компьютере и в удаленном репозитории.

В папке появляется папка с клонированным репозиторием. Заходим в нее командой 
```
cd название папки
```
Создаем новую ветку, в ней совершаем необходимые изменения, коммитим.
Если мы хотим синхронизировать локальный репозиторий с удаленным, используем команду
```
git pull
```
Если наоборот
```
git push
```
На удаленном репозитории предлагаем свои изменения командой `pull request`

Владелец репозитория увидит наши предложения и будет решать, что с ними делать.