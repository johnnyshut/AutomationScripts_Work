# Рекомендованное ПО и расширения

`TODO: Планируется сделать batch-файлы для установки в пакетном режиме`
> В документе описанны инструменты которые упрощают работу с GIT, Docker и другими ПО используемые в автоматизации работы

## Chocolatey

Chocolatey - менеджер пакетов в среде Windows по аналогии с apt-get в Linux Мире. Помогает сократить поиск, установку и обнволение софта до одной команды в консоли. Весь ниже перечисленый софт на Ваш выбор можно скачать и установить вручную или с помощью пакетного менеджера.

Установить можно скачав с официального сайта по [ссылке](https://chocolatey.org/) или с помощью консольных команд ниже.

### Установка через CMD

Запустить следующую команду: (Скопируйте текст команды)
`@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"`

### Установка через PowerShell

Для PowerShell есть дополнительный шаг. Вы должны убедиться, что `Get-ExecutionPolicy` не ограничен. Мы предлагаем использовать `Bypass` для обхода политики, чтобы установить вещи, или `AllSigned` для большей безопасности.

Запустите `Get-ExecutionPolicy`. Если он возвращает `Restricted`, запустите `Set-ExecutionPolicy AllSigned` или `Set-ExecutionPolicy Bypass -Scope Process`.

Запустить следующую команду: (Скопируйте текст команды)
`Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))`
или
`iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))`

### Команды для установки программ через choco etc

`choco install chocolateygui`   - установка графического интерфейса chocolateygui, доступен из пуск.
`choco install 7zip.install`    - полный инсталятор 7zip или `choco install 7zip` содержащий только скрипт начала загрузки.
`choco install vscode`          - полный дистрибутив VSCode.
`choco install sourcetree`      - Git клиент от компании atlassian с графическим интерфейсом.
`choco upgrade chocolatey`      - обновление пакет chocolatey.

`cup all`                       - обновление всех установленных пакетов приложений.
`choco uninstall chocolateygui` - удаление пакета chocolateygui.

`choco install git.install`     - полный инсталятор git или `choco install git` содержащий только скрипт начала загрузки. Для некоторых пакетов доступен список параметров установки. Разберем их на примере git:

* `/GitOnlyOnPath`            - Помещает `gitinstall\cmd` по указанному пути. Это также делается по умолчанию, если параметры пакета не установлены.
* `/GitAndUnixToolsOnPath`    - Помещает `gitinstall\bin` по указанному пути. Этот параметр переопределит `/GitOnlyOnPath`.
* `/NoAutoCrlf`               - Проверьте `Checkout as is, commit as is` . Эта настройка применяется, только при первоначальной установке, и не меняет `.gitconfig`.
* `/WindowsTerminal`          - Назначает обычный терминал Windows вместо терминала MinTTY.
* `/NoShellIntegration`       - Отключает установку стандартного Git GUI и интеграцию с оболочкой (записи "Git GUI Here" и "Git Bash Here" в контекстных меню).
* `/NoGuiHereIntegration`     - Отключает установку стандартного Git GUI и интеграцию с оболочкой (запись "Git GUI Here" в контекстных меню).
* `/NoShellHereIntegration`   - Отключает интеграцию с оболочкой (запись "Git GUI Here" в контекстных меню).
* `/NoCredentialManager`      - Отключает Git Credential Manager, добавив `$Env:GCM_VALIDATE='false'` в переменных средах пользователя.
* `/NoGitLfs`                 - Отключает установку Git LFS.
* `/SChannel`                 - Конфигурация Git для использования собственной реализации SSL/TLS (SChannel) вместо OpenSSL.

Пример: `choco install git.install --params "/GitAndUnixToolsOnPath /NoGitLfs /SChannel /NoAutoCrlf"`

`Создание собственного пакета, TODO иззучить. https://chocolatey.org/docs https://chocolatey.org/docs/create-packages`

## Visual Studio Code

VSCode - Редактор исходного кода, разработанный Microsoft для Windows, Linux и macOS. Позиционируется как «лёгкий» редактор кода для кроссплатформенной разработки веб- и облачных приложений.

Скачать можно с официального сайта по [ссылке](https://code.visualstudio.com/)

### Extensions

Для расширения встроенных возможностей VSCode предназначена возможность устанавливать расширения.  

Список имен рекомендуемых расширений:

* Bracket Pair Colorizer
* Chocolatey
* Docker
* docs-markdown
* Excel Viewer
* Git Graph
* Git History
* GitLens — Git supercharged
* indent-rainbow
* Language 1C (BSL)
* Markdown All in One
* Markdown Converter
* Markdown Navigation
* Markdown PDF
* Markdown Preview Enhanced with litvis
* Markdown Preview Github Styling
* Markdown Shortcuts
* markdownlint
* OneScript Debug
* Partial Diff
* REST Client
* Russian Language Pack for Visual Studio Code
* Tester 1C
* vscode-icons

## Git For Windows

Git - одна из самых популярных систем контроля версий, используется разработчиками, для контроля изменений в своих разработках и проектах. Изначально создан для использования на Linux-подобных операционных системах, но позднее, из-за удобства и популярности для Windows был написан специальный эмулятор, поддерживающий функционал Git’a.

Скачать можно с официального сайта по [ссылке](https://git-scm.com/downloads)

## Sourcetree

Бесплатный клиент Git для Windows и Mac. Sourcetree упрощает взаимодействие с репозиториями Git, поэтому вы можете сосредоточиться на кодировании. Визуализируйте и управляйте своими репозиториями с помощью простого графического интерфейса Git Sourcetree.

Скачать можно с официального сайта по [ссылке](https://www.sourcetreeapp.com/)