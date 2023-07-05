# Инструкция для работы с Git и удалёнными репозиториями

## Что такое Git?
Git - это одна из реализаций распределённых систем контроля версий, имеющая как и локальные, так и удалённые репозитории. Является самой популярной реализацией систем контроля версий в мире.
## Подготовка репозитория
Для создание репозитория необходимо выполнить команду *git init*  в папке с репозиторием и у Вас создаться репозиторий (появится скрытая папка .git)

## Создание коммитов

### Git add
Для добавления измений в коммит используется команда *git add*. Чтобы использовать команду *git add* напишите *git add <имя файла>*

### Просмотр состояния репозитория
Для того, чтобы посмотреть состояние репозитория используется команда *git status*. Для этого необходимо в папке с репозиторием написать *git status*, и Вы увидите были ли измения в файлах, или их не было.

### Создание коммитов
Для того, чтобы создать коммит(сохранение) необходимо выполнить команду *git commit*. Выполняется она так: *git commit -m "<сообщение к коммиту>*. Все файлы для коммита должны быть ***ДОБАВЛЕНЫ*** и сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.

## Перемещение между сохранениями
Для того, чтобы перемещаться между коммитами, используется команда *git checkout*. Используется она в папке с пепозиторием следующим образом: *git checkout <номер коммита>*

## Журнал изменений
Для того, чтобы посмтреть все сделанные изменения в репозитории, используется команда *git log*. Для этого достаточно выполнить команду *git log* в папке с репозиторием

## Ветки в Git

### Создание ветки

Для того, чтобы создать ветку, используется команда *git branch*. Делается это следующим образом в папке с репозиторием: *git branch <название новой ветки>*

## Слияние веток

Для того чтобы дабавить ветку в текущую ветку используется команда *git merge <name branch>*

## Удаление веток
Для удаления ветки ввести команду "git branch -d 'name branch'"

# Отмена коммитов и изменений

Один из лучших инструментов для просмотра истории репозитория Git — команда git log

 Для просмотра всех коммитов во всех ветках используется команда git log --branches=*.

 При каждом возвращении в ветку main можно использовать команду git revert или git reset для отмены нежелательных изменений.

  git commit --amend - Отмена последнего коммита

  Команда reset с параметром --mixed перемещает все ожидающие изменения из раздела проиндексированных файлов обратно в рабочий каталог.

  Команда git reset, как правило, считается методом локальной отмены. Ее следует использовать для отмены изменений в частной ветке. Она безопасно изолирует удаление коммитов от других веток, которые могут использоваться другими разработчиками. Проблемы возникают, когда команда reset выполняется в общей ветке и затем эта ветка удаленно публикуется с помощью команды git push. В этом случае Git блокирует выполнение команды push и сообщает, что публикуемая ветка устарела, поскольку в ней отсутствуют коммиты, которые есть в удаленной ветке. Предпочтительная команда для отмены общей истории коммитов — git revert. Команда revert безопаснее, чем reset, так как она не удаляет коммиты из общей истории. Команда revert сохраняет отменяемые вами коммиты и создает новый коммит с операцией, обратной последнему коммиту. 