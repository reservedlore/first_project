any command!!
!!! = new lesson
!!!lesson 1)
{
   # вызов краткой справки / проверка установки Git
    git
    git -h
    git --help
    
    # установка глобального пользователя Git (для всех проектов)
    git config --global user.name "Pragmatic Programmer"

    # установка глобального email пользователя Git (для всех проектов)
    git config --global user.email "prag_prog@gmail.com"

    # включение цветного вывода информации (в ряде случаев включено по умолчанию)
    git config --global color.ui true

    # вывод списка настроек
    git config --list

    # вывод имени пользователя/email из настроек
    git config user.name
    git config user.email

    #    вывод истории команд
    history

    # установка локальной настройки Git (для конкретного репозитория)
    git config user.name "Pragmatic Programmer"
    git config user.email "prag_prog@gmail.com"
}

!!!lesson 2)
{
   # создать каталог для проекта с именем 'first_project'
mkdir first_project

# вывести содержимое текущего каталога
ls

# перейти в созданный каталог
cd first_project/

# вывести путь к текущей локации
pwd

# вывести содержимое каталога в подробном (табличном виде), включая скрытые файлы и папки
ls -la

# (основная команда урока!) создать Git-репозиторий в текущей папке
git init

# перейти в папку '.git'
cd .git/

# вывести содержимое файла config
cat config

# задать локально (для текущего репозитория) имя пользователя Git
git config user.name "user22"

# вывести глобальное значение имени пользователя Git
git config --global user.name

# вывести локальное значение имени пользователя Git
git config user.name

# вывести список всех настроек Git
git config --list

# вывести список глобальных настроек Git
git config list --global

# вывести список локальных настроек Git
git config list --local

# переместиться в предыдущую локацию
cd -

# переместиться в домашний каталог пользователя
cd c:/Users/Pragmatic_Programmer

# вывести содержимое файла '.gitconfig'
cat .gitconfig

# вывести список ВСЕХ текущих настроек Git вместе с информацией о том, из какого файла конфигурации каждая настройка взята.
git config --show-origin --list

}

!!!lesson 3)
{
    # посмотреть состояние файлов в индексе
git status

# посмотреть историю коммитов
git log

# вывести на экран содержимое указанного файла
cat page1.html

# добавить в индекс указанный файл
git add page1.html

# сделать коммит (требует ввода текстового сообщения)
git commit

# вывод списка настроек
git config list

# установить редактор по умолчанию для Git
git config core.editor nano

# добавить в индекс все файлы в текущей папке
git add .

# добавить в индекс указанный файл
git add page1.html

# посмотреть историю коммитов в компактном виде
git log --oneline
}

!!!leson 4)
{
    # отменить все изменения после последнего коммита
# (подробнее будет рассмотрена далее в курсе)
git reset --hard

}

!!!leson 5)
{
    # "ленивый коммит" (без команды 'git add')
git commit -a

# добавить изменения в индексе в предыдущий коммит
git commit --amend

# показать детальную информацию о последнем коммите
git show

# показать детальную информацию об указанном коммите
git show <commit_id>

# вывести только имена файлов, участвовавших в коммите
git show --name-only <commit_id>

# переместить "голову" репозитория на 1 коммит назад
# (команда будет подробно рассмотрена в следующих уроках)
git reset HEAD~1

# выполнить коммит с указанным сообщением (после ключа -m)
git commit -m "add some new features"

# совместить ключи -a -m в коммите
# тем самым избавиться от отдельной команды git add и задать сообщение для коммита
git commit -am "add some new features"

!!!!!!!Рекомендации по оформлению сообщений для коммита:
Пустая строка между темой сообщения и его телом
Тема сообщения должна быть короче 50 символов
Тема сообщения должна быть написана в верхнем регистре (Caps Lock) - опционально
Точка не ставится в конце темы
Тело сообщения должно быть короче 80 символов
Тело сообщения должно объяснять: что изменено, а не почему были сделаны изменения
Тема сообщения должна отвечать на вопрос: "Что делает коммит?"

}

!!!lesson 4)
{
    # сбросить весь индекс\stage (сохраняя изменения в папке)
git reset

# убрать файл из индекса
git reset <file_name>

# вернуть к состоянию последнего коммита (если поломали код, например)
git reset --hard

# отменить последний коммит (сохраняя сами изменения)
git reset HEAD~1
git reset HEAD^

# отменить последние 2 коммита
git reset HEAD~2
git reset HEAD^^

# отменить последние 3 коммита
git reset HEAD~3
git reset HEAD^^^

# отменить последние 2 коммита (удаляя изменения)
git reset HEAD~2 --hard

# вывести предыдущее значение HEAD
cat .git/ORIG_HEAD

# вернуться к коммиту, на который указывает ORIG_HEAD
git reset ORIG_HEAD --hard

# вернуться к состоянию после указанного коммита
git reset --hard <commit_id>

# история коммитов в кратком виде
git log --oneline

# краткая справка по команде revert
git revert

# подробная справка по команде revert
git revert --help

# детали последнего коммита
git show

# откатить последний коммит (создавая новый `обратный коммит`)
git revert HEAD

# вывод содержимого файла styles.css на экран
cat styles.css

# откатить последний коммит без ввода сообщения для коммита
git revert HEAD --no-edit

# откатить коммит по его идентификатору (хэш-коду)
git revert 8ab14c

# откатить третий коммит с конца
git revert HEAD~3

# отменить незавершенный откат коммита
git revert --abort

# откатить серию коммитов
git revert 9e59768..4b2413e

# откатить коммит без создания нового коммита (изменения попадают в индекс)
git revert 9e59768 --no-commit

}

!!!leson5)
{
        # вызов справки
git rm --help

# удаление файла из каталога (команда терминала)
rm page2.html

# удаление файла из Git-репозитория
git rm page2.html

# форсированное удаление файла (если есть изменения в индексе)
git rm page2.html -f
git rm page2.html --force

# удаление каталога
git rm my_folder -r
git rm my_folder --recursive

# вызов справки
git clean --help

# сценарий 1
# создадим ненужные файлы
touch some_binary_file{1..9}.bin
ls

# посмотрим их статус
git status

# очистим Git от этих файлов
git clean -f
ls
git status

# сценарий 2
# создадим пустые папки
mkdir bin
mkdir tmp
ls

# посмотрим их статус
git status

# очистим Git от этих пустых каталогов
git clean -d -f
ls
git status

# ключ -n -- 'холостой прогон команды'
# покажет, что будет происходить при выполнении команды
git clean -f -n
git clean -f -d -n

# ключ -q -- тихое выполнение команды
# не выводит комментарии о ходе своего выполнения
git clean -f -d -q
}

lesson 6)
{
    # переименование файла в терминале
mv page1.html index.html

# набор команд для корректного переименования в Git
mv page1.html index.html
git add index.html
git rm page1.html

# переименование/перемещение файла в Git одной командой
git mv page1.html index.html

# вызов справки
git mv --help

# создаем папку styles
mkdir styles

# перемещаем файл с CSS-стилями в новую папку
git mv styles.css styles

# делаем коммит
git commit -m "create folder for css styles"

# переименование папки в Git
git mv styles css

# создаем папку web_pages
mkdir web_pages

# перемещение набора файлов
git mv *.html web_pages


}
