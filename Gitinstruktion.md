g![logo]()
# Работа с Git

## 1. Проверка наличия установленного Git

В терминале выполнить комаеду `Git --version`

Если Git установлен, появится сообщение с информацией о версии  программы. Иначе будет сообщение об ошибке.

## 2. Установка Git
Устанавливаем последнюю версию Git с сайта https://git-scm.com/downloads.
Устанавливаем с настройками по умолчанию.

## Настройка Git
При первом использовании необходимо представиться. Для этого нужно ввести в терминале 2 команды:
```
git config--global user.name."Ваше имя английскими буквами"
git config--global user.email "Ваша почта"
```
## 4. Инициализации репозитория
 
* Для инициализации репозитория используется команда Git init которая набирается в командной строке, важно проверить что находимся именно в специально созданной локальной папке.

## 5. Команды Git используемые для работы с репозиторием

* git status- позволяет получить информацию от `git` о его текущем состоянии
* git add- добавляет файл или файлы к дальнейшей индексации
* git commit-m "message"- создает фиксацию текущих изменений (создание комита)
* git log - выводит на экран историю всех комитов(изменений)с их хеш кодами
* git log --oneline выводит на 
экран историю всех комитов в одну строку с первыми пятью символами хеш код ,имеет более удобное представление информации
* git checkout- позволяет переходить между изменениями(комитами) различными версиями проекта
* git checkout master- позволяет вернуться к последнему актуальному состоянию и продолжить работу
* git diff- позволяе увидеть разницу между текущим файлом и сохраненным(закомиченным)файлом
* git switch- позволяет вернуться к актуальному состоянию как и команда `git checkout master`
## 6. Запись изменений в репозиторий
## 7. Просмотр истории коммитов
## 8. Перемещение между сохранениями
 ## 9. Игнорирование файлов
 
 
Для того, чтобы исключить из отслеживания в репозитории определенные файлы или папки необходимо создать там файл ***.gitignore***. и записать в него их названия или шаблоны, соответствующие таким файлам или папкам.

## 10. Сoздание веток в Git

    Ветка в Git - это простой перемещаемый указатель на один из коммитов, обычно последний в цепочке коммитов.

По умолчанию имя основной ветки в  Git - **master**.

* Создание новой ветки в Git осуществляется с помощью команды :
* Git branch и имя ветки
 
* Если ввести команду Git branch без параметров на экgitран будут выведены все существующие ветки проекта

## 11.Слияние веток в Git

* На различных стадиях проекта работа осуществляется в различных ветках. Но на определенной стадии возникает необходимость объеденить ветки в одну основную или осуществить слияние веток.
Слияние веток осуществляется с помощью команды `Git merge`

## 12.Конфликты при слиянии веток в Git

* При осуществлении слияния веток могут возникать конфликты с предложением предпринять определенные дествия для разрешения конфликта.
Как правило разрешением конфликтов занимается руководитель проекта он решает добавлять изменения в основную ветку или оставить без изменений. После разрешения конфликта обязательно делается фиксация изменений с соответствующим коммитом.

## 13. Удаление веток в Git

При завершении работы в отдельных ветках и слиянии в основную ветку. Ненужные ветки можно удалить. Для етого используется команда 
`Git branch -d имя ветки`
при этом программа попросит уточнение действительно эту ветку следует удалить.
Для безусловного удаления используется параметр `-D "delete"`

## Слияние веток
При работе  в больших проектах используются различное количество веток которые могут быть слиты в основную ветку.
Слияние веток осуществляют с помощью команды   ``` merge ```

##  Разрешение конфликтов
При слиянии веток могут возникать конфликты если были допущены какие либо ошибки. Git при слиянии делает подсказки как можно поступить в таких случаях и предлагает на выбор несколько вариантов. 

## Работа с удаленными репозиториями

* Для работы с удаленным репозиторием необходимо создать аккаунт на сервисе `GitHab` и авторизоваться.
Сервис `GitHab` имеет много матепиалов с открытым исходным кодом, дающий возможность участвовать в различных проектах и предлагать свои изменения в различные проекты.

## Копирование (клонирование) публичных(открытых) репозиториев.

Для того чтобы скопировать понравивщейся репозиторий с целью предложить свои изменения необходимо в своем аккаунте на `GitHab` сделать копию этого репозитория с помощью кнопки  `Fork` после чего в своем аккаунте сделать копию ссылки на клонированный  репозиторий.
После чего переходим в (вижиал код) и создаем  папку для клонирования удаленного репозитория в нашу папку для внесения изменений с помощью команды `git clone`.
С помощью команды `cd` имя нашей папки переходим в склонированную папку и делаем свои изменения.
Все изменения необходимо делать в специально созданную для этого ветку.
После всех изменений предлагаемых к проекту с помощью команды `Git push` отправляем изменения на наш удаленный репозиторий. В виду того ,что мы для предлагаемых изменений создавали отдельную папку к которой не прописан путь по ссылке. Но Git подскажет команду `--set-upstream origin имя ветки` для отправки изменений на удаленный репозиторий.
Если на удаленном репозитории не появляется кнопка `pullRequest` то это необходимо сделать в ручную. Нажмем на кнопку `newpullrequest` после выбираем ветку которую специально создавали для изменений.
После чего появится сообщение сделать `Pullrequest`
Отправляем `pullrequest`автору проекта.






