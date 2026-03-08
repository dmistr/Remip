# RemIP - Remote IP Management

![Windows](https://img.shields.io/badge/Platform-Windows-blue)
![PowerShell](https://img.shields.io/badge/PowerShell-5.1+-green)
![Python](https://img.shields.io/badge/PowerShell-5.1+-green)
![License](https://img.shields.io/badge/License-Free-orange)

**RemIP** – A Universal Assistant for Remote Computer Management

**RemIP** is a program that solves two important tasks: it helps configure a computer for remote access and allows you to manage other computers on the network.

What is it for?
Imagine you have several computers on a local network (at home or in the office). RemIP allows you to:

Manage Remote Computers:
  - Shut them down directly from your workstation
  - Send text messages to other users' screens.
  - Play voice messages on remote PCs.
  - Check if a computer is available on the network.

Configure Computers for Remote Management:
  - Automatically open the necessary ports in the firewall.
  - Enable required system services.
  - Set up a secure connection.
  - Reset settings if something goes wrong.

The program features a simple and intuitive interface with support for two languages (Russian/English) and is suitable for both home use and small offices.

---

**RemIP** - Универсальный помощник для удаленного управления компьютерами

**RemIP** — это программа, которая решает две важные задачи: помогает настроить компьютер для удаленного доступа и позволяет управлять другими компьютерами в сети.

Для чего это нужно?
Представьте, что у вас есть несколько компьютеров в локальной сети (дома или в офисе). RemIP позволяет:

1. Управлять удаленными компьютерами:
  - Выключать их прямо со своего рабочего места
  = Отправлять текстовые сообщения на экраны других пользователей
  - Озвучивать голосовые сообщения на удаленных ПК
  - Проверять, доступен ли компьютер в сети

2. Настраивать компьютеры для удаленного управления:
  - Автоматически открывать нужные порты в брандмауэре
  - Включать необходимые системные службы
  - Настраивать безопасное подключение
  - Сбрасывать настройки, если что-то пошло не так

Программа имеет простой и понятный интерфейс с поддержкой двух языков (русский/английский) и подходит как для домашнего использования, так и для небольших офисов.

---

## **Инструкция пользователя / User manual**

[English](#english) | [Русский](#russian)

---

## English

### Overview
RemIP is a powerful portable tool for remote computer management and setup. It combines two utilities in one application:
- **PC Control Mode** - Remotely manage computers (shutdown, messages, diagnostics)
- **PC Setup Mode** - Configure a computer for remote access (ports, services, WinRM)

The program is distributed as a single executable file - no installation required!

### System Requirements
- Windows 7/8/10/11
- Administrator rights (for setup mode and some control functions)
- No additional software or frameworks required

### Installation
**No installation needed!** Just download the `RemIP.exe` file and run it.

**Important**: On first run, Windows SmartScreen might show a warning. Click "More info" and then "Run anyway" - the program is safe to use.

### First Launch
When you start RemIP, you'll see the main menu with two options:
- **PC CONTROL** (blue button) - For remote management
- **PC SETUP** (green button) - For preparing a computer for remote access

### Interface Elements

#### Top Panel (visible in all modes)
- **IP Address Field** - Enter the target computer's IP
- **Status Indicator** - Shows connection status:
  - 🟡 Yellow - Checking
  - 🟢 Green - Online
  - 🔴 Red - Offline
- **Language Selector** - Switch between Russian/English
- **? Button** - About information
- **◀ BACK Button** - Return to main menu (visible in Control/Setup modes)
- **✕ Button** - Exit application

#### Progress Bar (visible in Control/Setup modes)
Shows operation progress (0-100%)

#### Output Window
Displays all operation results, diagnostics, and status messages with color coding:
- Cyan - Headers
- Yellow - Commands
- Green - Success messages
- Red - Errors
- Orange - Warnings
- White - Regular info

### PC CONTROL Mode

This mode allows you to remotely manage computers.

#### Features:

1. **Shutdown Now** - Immediate computer shutdown
2. **Shutdown with Timer** - Set shutdown delay in seconds
3. **Shutdown + Text** - Send a text message before shutdown
4. **Shutdown + Voice** - Send a voice message before shutdown
5. **Text Message** - Send a text message to all users
6. **Voice Message** - Send a voice message to all users
7. **Save Credentials** - Save login credentials for the current IP
8. **Show Saved IPs** - Display all IPs with saved credentials
9. **Delete Credentials** - Remove saved credentials for current IP
10. **Diagnostics** - Check connection, WinRM availability, and port 5985
11. **Clear** - Clear the output window

#### How to Use Control Mode:

1. Enter the target computer's IP address
2. Wait for status indicator to turn green (online)
3. Save credentials if this is the first time connecting
4. Select desired action from the buttons
5. Follow any dialog prompts
6. Check results in the output window

#### Credentials Storage
Credentials are saved securely using Windows encryption to:
`C:\temp\remote_cred_IP.xml` (where IP uses underscores instead of dots)

### PC SETUP Mode

This mode configures the local computer for incoming remote connections.

#### Features:

1. **Full Setup** - Complete configuration (ports + services + WinRM)
2. **Open Ports** - Configure firewall rules for ports 445, 139, 5985
3. **Enable Services** - Start and configure Server, RemoteRegistry, WinRM services
4. **Configure WinRM** - Setup WinRM and add current IP to TrustedHosts
5. **Check and Fix** - Diagnose and repair configuration issues
6. **Diagnostics** - Comprehensive system diagnostic
7. **Reboot** - Restart computer with 30-second delay
8. **Reset Settings** - Remove all configurations (close ports, disable services, clear TrustedHosts)
9. **Clear** - Clear the output window

#### Ports Configured:
- **445** - SMB (file sharing)
- **139** - NetBIOS
- **5985** - WinRM (Windows Remote Management)

#### Services Configured:
- **LanmanServer** - Server service
- **RemoteRegistry** - Remote registry access
- **WinRM** - Windows Remote Management

#### How to Use Setup Mode:

1. **Run as Administrator** - Most functions require admin rights (right-click the .exe and select "Run as administrator")
2. Enter the IP that will connect to this computer
3. Select desired setup option
4. Monitor progress in the output window
5. Use Diagnostics to verify configuration

#### Reset Function
The reset option completely removes all configurations:
- Deletes firewall rules
- Stops and disables services
- Clears TrustedHosts
- May offer to create blocking rules for stubborn open ports

### Language Switching
You can switch between Russian and English at any time:
- Use the language selector in the top panel
- Interface text updates immediately
- Output window content updates with current language

### Troubleshooting

#### Connection Issues:
1. Check if target computer is online (status indicator)
2. Run Diagnostics in Control mode
3. Ensure WinRM is configured (use Setup mode on target)
4. Verify firewall allows port 5985
5. Check TrustedHosts configuration

#### Setup Issues:
1. **Always run as Administrator** for setup functions
2. Use "Check and Fix" to diagnose problems
3. Check Windows Firewall settings
4. Verify services are running
5. Try Full Setup if individual steps fail

#### Common Error Messages:
- **"Administrator rights required!"** - Right-click RemIP.exe and select "Run as administrator"
- **"Credentials not found"** - Save credentials first
- **"WinRM is unavailable"** - Configure WinRM in Setup mode
- **"Port 5985 is closed"** - Check firewall rules

### Security Notes
- Credentials are stored encrypted using Windows Data Protection API
- TrustedHosts should only contain trusted IP addresses
- Opening ports increases attack surface - use only in trusted networks
- Reset settings when remote access is no longer needed

### Author
**dmistr**
- Email: dmistr9999@gmail.com
- GitHub: https://github.com/dmistr/RemIP

### Distribution
The program is distributed as a single executable file: `RemIP.exe`
- No installation required
- No dependencies
- Portable - can be run from USB drive
- No registry changes
- No background processes

### License
Free for personal and commercial use. Use at your own risk.

**IMPORTANT LICENSE TERMS:**
- The software is free to use and distribute
- **When using or distributing any part of the source code, attribution to the original author (dmistr) and a link to the GitHub repository (https://github.com/dmistr/RemIP) are mandatory**
- This applies to both complete code and any portions thereof
- Modifications are allowed but must maintain original attribution

### Download
Get the latest version from the official GitHub repository:
https://github.com/dmistr/RemIP

---

## Russian

### Обзор
RemIP - это мощный портативный инструмент для удаленного управления и настройки компьютеров. Объединяет две утилиты в одном приложении:
- **Режим УПРАВЛЕНИЕ ПК** - Удаленное управление компьютерами (выключение, сообщения, диагностика)
- **Режим НАСТРОЙКА ПК** - Подготовка компьютера к удаленному доступу (порты, службы, WinRM)

Программа распространяется в виде одного исполняемого файла - установка не требуется!

### Системные требования
- Windows 7/8/10/11
- Права администратора (для режима настройки и некоторых функций управления)
- Не требует дополнительного ПО или фреймворков

### Установка
**Установка не нужна!** Просто скачайте файл `RemIP.exe` и запустите его.

**Важно**: При первом запуске Windows SmartScreen может показать предупреждение. Нажмите "Подробнее" и затем "Выполнить в любом случае" - программа безопасна.

### Первый запуск
При запуске RemIP вы увидите главное меню с двумя опциями:
- **УПРАВЛЕНИЕ ПК** (синяя кнопка) - Для удаленного управления
- **НАСТРОЙКА ПК** (зеленая кнопка) - Для подготовки компьютера к удаленному доступу

### Элементы интерфейса

#### Верхняя панель (видна во всех режимах)
- **Поле IP адреса** - Введите IP целевого компьютера
- **Индикатор статуса** - Показывает состояние подключения:
  - 🟡 Желтый - Проверка
  - 🟢 Зеленый - В сети
  - 🔴 Красный - Не доступен
- **Выбор языка** - Переключение между русским/английским
- **Кнопка ?** - Информация о программе
- **Кнопка ◀ НАЗАД** - Возврат в главное меню (видна в режимах Управление/Настройка)
- **Кнопка ✕** - Выход из программы

#### Прогресс-бар (виден в режимах Управление/Настройка)
Показывает ход выполнения операций (0-100%)

#### Окно вывода
Отображает все результаты операций, диагностику и статусные сообщения с цветовой кодировкой:
- Голубой - Заголовки
- Желтый - Команды
- Зеленый - Успешные сообщения
- Красный - Ошибки
- Оранжевый - Предупреждения
- Белый - Обычная информация

### Режим УПРАВЛЕНИЕ ПК

Этот режим позволяет удаленно управлять компьютерами.

#### Функции:

1. **ВЫКЛЮЧИТЬ СЕЙЧАС** - Немедленное выключение компьютера
2. **ВЫКЛЮЧИТЬ С ТАЙМЕРОМ** - Установка задержки выключения в секундах
3. **ВЫКЛЮЧИТЬ + ТЕКСТ** - Отправка текстового сообщения перед выключением
4. **ВЫКЛЮЧИТЬ + ГОЛОС** - Отправка голосового сообщения перед выключением
5. **ТЕКСТОВОЕ СООБЩЕНИЕ** - Отправка текста всем пользователям
6. **ГОЛОСОВОЕ СООБЩЕНИЕ** - Отправка голосового сообщения всем пользователям
7. **СОХРАНИТЬ УЧЁТНЫЕ ДАННЫЕ** - Сохранение логина/пароля для текущего IP
8. **СПИСОК IP** - Показать все IP с сохраненными данными
9. **УДАЛИТЬ ДАННЫЕ** - Удалить сохраненные данные для текущего IP
10. **ДИАГНОСТИКА** - Проверка подключения, доступности WinRM и порта 5985
11. **ОЧИСТИТЬ** - Очистка окна вывода

#### Как использовать режим Управление:

1. Введите IP целевого компьютера
2. Дождитесь зеленого индикатора (в сети)
3. Сохраните учетные данные при первом подключении
4. Выберите нужное действие из кнопок
5. Следуйте диалоговым подсказкам
6. Проверьте результаты в окне вывода

#### Хранение учетных данных
Учетные данные сохраняются с шифрованием Windows в:
`C:\temp\remote_cred_IP.xml` (где IP использует подчеркивания вместо точек)

### Режим НАСТРОЙКА ПК

Этот режим настраивает локальный компьютер для входящих удаленных подключений.

#### Функции:

1. **ПОЛНАЯ НАСТРОЙКА** - Полная конфигурация (порты + службы + WinRM)
2. **ОТКРЫТЬ ПОРТЫ** - Настройка правил брандмауэра для портов 445, 139, 5985
3. **ВКЛЮЧИТЬ СЛУЖБЫ** - Запуск и настройка служб Server, RemoteRegistry, WinRM
4. **НАСТРОИТЬ WINRM** - Настройка WinRM и добавление текущего IP в TrustedHosts
5. **ПРОВЕРИТЬ И ИСПРАВИТЬ** - Диагностика и исправление проблем конфигурации
6. **ДИАГНОСТИКА** - Полная диагностика системы
7. **ПЕРЕЗАГРУЗИТЬ** - Перезагрузка компьютера с задержкой 30 секунд
8. **СБРОС НАСТРОЕК** - Удаление всех конфигураций (закрытие портов, отключение служб, очистка TrustedHosts)
9. **ОЧИСТИТЬ** - Очистка окна вывода

#### Настраиваемые порты:
- **445** - SMB (общий доступ к файлам)
- **139** - NetBIOS
- **5985** - WinRM (удаленное управление Windows)

#### Настраиваемые службы:
- **LanmanServer** - Служба Сервер
- **RemoteRegistry** - Удаленный доступ к реестру
- **WinRM** - Удаленное управление Windows

#### Как использовать режим Настройка:

1. **Запустите от администратора** - Большинство функций требуют прав администратора (нажмите правой кнопкой на .exe и выберите "Запуск от имени администратора")
2. Введите IP компьютера, который будет подключаться к этому ПК
3. Выберите нужную опцию настройки
4. Следите за прогрессом в окне вывода
5. Используйте Диагностику для проверки конфигурации

#### Функция Сброс
Опция сброса полностью удаляет все конфигурации:
- Удаляет правила брандмауэра
- Останавливает и отключает службы
- Очищает TrustedHosts
- Может предложить создать блокирующие правила для "упрямых" открытых портов

### Переключение языка
Вы можете переключаться между русским и английским в любое время:
- Используйте селектор языка на верхней панели
- Текст интерфейса обновляется мгновенно
- Содержимое окна вывода обновляется на текущем языке

### Устранение неполадок

#### Проблемы подключения:
1. Проверьте, доступен ли целевой компьютер (индикатор статуса)
2. Запустите Диагностику в режиме Управление
3. Убедитесь, что WinRM настроен (используйте режим Настройка на целевом ПК)
4. Проверьте, разрешает ли брандмауэр порт 5985
5. Проверьте конфигурацию TrustedHosts

#### Проблемы настройки:
1. **Всегда запускайте от имени администратора** для функций настройки
2. Используйте "ПРОВЕРИТЬ И ИСПРАВИТЬ" для диагностики проблем
3. Проверьте настройки брандмауэра Windows
4. Убедитесь, что службы запущены
5. Попробуйте ПОЛНУЮ НАСТРОЙКУ, если отдельные шаги не работают

#### Частые сообщения об ошибках:
- **"Нужны права администратора!"** - Нажмите правой кнопкой на RemIP.exe и выберите "Запуск от имени администратора"
- **"Учётные данные не найдены"** - Сначала сохраните учетные данные
- **"WinRM недоступен"** - Настройте WinRM в режиме Настройка
- **"Порт 5985 закрыт"** - Проверьте правила брандмауэра

### Замечания по безопасности
- Учетные данные хранятся зашифрованными с использованием Windows Data Protection API
- TrustedHosts должен содержать только доверенные IP-адреса
- Открытие портов увеличивает поверхность атаки - используйте только в доверенных сетях
- Выполняйте сброс настроек, когда удаленный доступ больше не нужен

### Автор
**dmistr**
- Почта: dmistr9999@gmail.com
- GitHub: https://github.com/dmistr/RemIP

### Распространение
Программа распространяется в виде одного исполняемого файла: `RemIP.exe`
- Не требует установки
- Не имеет зависимостей
- Портативная - можно запускать с USB-накопителя
- Не вносит изменения в реестр
- Не оставляет фоновых процессов

### Лицензия
Бесплатно для личного и коммерческого использования. Используйте на свой страх и риск.

**ВАЖНЫЕ УСЛОВИЯ ЛИЦЕНЗИИ:**
- Программу можно свободно использовать и распространять
- **При использовании или распространении любой части исходного кода обязательно указание автора (dmistr) и ссылки на репозиторий GitHub (https://github.com/dmistr/RemIP)**
- Это относится как к полному коду, так и к любым его фрагментам
- Разрешено модифицировать код при сохранении указания авторства

### Скачивание
Последнюю версию можно получить в официальном репозитории GitHub:
https://github.com/dmistr/RemIP
