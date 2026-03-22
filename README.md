![Windows](https://img.shields.io/badge/Platform-Windows-blue)
![PowerShell](https://img.shields.io/badge/PowerShell-5.1+-green)
![Python](https://img.shields.io/badge/Python-3.14-green)
![License](https://img.shields.io/badge/License-Free-orange)

# RemIP - Remote IP Control

**Универсальный инструмент удалённого управления ПК по IP**

👤 **Автор:** dmistr  
📧 **Email:** dmistr9999@gmail.com  
🐙 **GitHub:** https://github.com/dmistr/Remip

---

## 🌐 Языки / Languages
- [Русский](#russian)
- [English](#english)

---

<a name="russian"></a>
## 📋 ОПИСАНИЕ ПРОГРАММЫ

RemIP — это мощный инструмент для удалённого управления компьютерами в локальной сети. Программа состоит из трех основных режимов:

### 🔹 Режим УПРАВЛЕНИЕ ПК (Control)
Позволяет удалённо управлять компьютерами, на которых уже настроен удалённый доступ:
- Выключение/перезагрузка (мгновенно, с таймером, с сообщением, с голосом)
- Отправка текстовых и голосовых сообщений
- Диагностика подключения (ping, порты, WinRM, права)
- Сохранение учётных данных для быстрого доступа

### 🔹 Режим НАСТРОЙКА ПК (Install)
Позволяет подготовить компьютер к удалённому управлению:
- Открытие необходимых портов (445, 139, 5985)
- Настройка сетевых профилей
- Включение/отключение служб (Server, RemoteRegistry, WinRM)
- Разрешение пустого пароля для учётных записей
- Полная диагностика системы

### 🔹 Режим КАРТА СЕТИ (Network Map)
Автоматическое сканирование локальной сети:
- Обнаружение всех активных устройств
- Определение открытых портов
- Проверка доступности WinRM
- Сохранение результатов между сессиями
- Быстрое переключение в режим управления

---

## 🚀 ИНСТРУКЦИЯ ДЛЯ ПОЛЬЗОВАТЕЛЯ

### ⚡ Быстрый старт
1. Запустите программу (рекомендуется от имени администратора)
2. Выберите нужный режим:
   - 🖥️ **УПРАВЛЕНИЕ ПК** — для управления уже настроенными ПК
   - 🛠️ **НАСТРОЙКА ПК** — для подготовки компьютера к удалённому управлению
   - 🗺️ **КАРТА СЕТИ** — для поиска устройств в сети

---

## 🖥️ РЕЖИМ УПРАВЛЕНИЯ ПК

### 🔑 Учётные данные
1. Введите IP удалённого компьютера
2. Нажмите 💾 **ВВЕСТИ И СОХРАНИТЬ**
3. Введите имя пользователя и пароль (можно оставить имя по умолчанию)
4. IP автоматически добавится в список сохранённых и в TrustedHosts

### 📋 Список сохранённых IP
- Выберите IP из выпадающего списка
- Правый клик на IP — удалить из списка
- Кнопка 🗑️ **ОЧИСТИТЬ СПИСОК IP** — удалить все сохранённые записи

### 🔴 Выключение компьютера
- ⚡ **ВЫКЛЮЧИТЬ СЕЙЧАС** — мгновенное завершение работы
- ⏱️ **ВЫКЛЮЧИТЬ С ТАЙМЕРОМ** — выключение через N секунд
- 💬 **ВЫКЛЮЧИТЬ + ТЕКСТ** — показать сообщение и выключить
- 🎤 **ВЫКЛЮЧИТЬ + ГОЛОС** — озвучить сообщение и выключить

### 💬 Сообщения
- 📝 **ТЕКСТОВОЕ СООБЩЕНИЕ** — отправить текст на удалённый ПК
- 🗣️ **ГОЛОСОВОЕ СООБЩЕНИЕ** — озвучить текст на удалённом ПК

### 🔧 Сервис
- 🔄 **ВКЛ/ВЫКЛ WINRM** — управление службой WinRM на вашем ПК
- 📊 **ДИАГНОСТИКА** — полная проверка подключения
- 🧹 **ОЧИСТИТЬ** — очистить окно вывода

### ⚙️ Режимы выключения
- ⚡ **Обычный** — просто отправляет команду
- 🛡️ **Защищённый** — проверяет результат и принудительно выключает при необходимости

---

## 🛠️ РЕЖИМ НАСТРОЙКИ ПК

### 🚀 Экспресс
- ⚡ **БЫСТРАЯ НАСТРОЙКА** — одним нажатием открывает все порты, включает службы и настраивает WinRM
- 💡 **УМНАЯ НАСТРОЙКА** — диагностирует состояние и предлагает выбрать, что исправить

### 🔌 Расширенная настройка (🟩 — открыт, 🟥 — закрыт)
- 🌐 **ПОРТЫ** — кнопки-переключатели для портов 445, 139, 5985
- 🛡️ **ПРОФИЛИ** — выбор сетевых профилей (🏠 Частная, 🌍 Общественная, 🏢 Доменная)
- 🔑 **ПУСТОЙ ПАРОЛЬ** — разрешение/запрет входа без пароля
- 🖥️ **СЛУЖБЫ** — управление службами Server, RemoteRegistry, WinRM

### 🔧 Сервис
- 📊 **ДИАГНОСТИКА** — полная проверка портов, служб и правил брандмауэра
- 🗑️ **СБРОС** — сброс всех настроек (закрытие портов, отключение служб)
- 🧹 **ОЧИСТИТЬ** — очистить окно вывода

---

## 🗺️ РЕЖИМ КАРТЫ СЕТИ

### 🔍 Сканирование
- ⚡ **БЫСТРОЕ** — проверка основных портов (< 1 минуты)
- 🔍 **ПОЛНОЕ** — проверка всех портов (1-5 минут)
- 📋 **ИЗ ARP-ТАБЛИЦЫ** — просмотр активных устройств (< 1 минуты)

### 📊 Обозначения
- 🟢 — WinRM доступен и есть учётные данные
- 🟡 — WinRM доступен, но нет учётных данных
- ⚪ — WinRM отсутствует

### 🖱️ Действия
- Двойной клик — перейти в режим управления
- Правый клик — контекстное меню с действиями
- ▶/◀ — развернуть/свернуть подробную информацию

### 💾 Сохранение результатов
- Результаты автоматически сохраняются во временный файл
- При повторном открытии карты сети данные восстанавливаются
- Кнопка 🗑️ **ОЧИСТИТЬ РЕЗУЛЬТАТЫ** — удаляет все сохранённые данные

---

## ❓ FAQ (Часто задаваемые вопросы)

### 1. Почему программа требует права администратора?
Для изменения правил брандмауэра, управления службами и настройки WinRM необходимы права администратора. Без них большинство функций в режиме настройки работать не будут.

### 2. Какие порты нужны для удалённого управления?
- **5985** — WinRM (обязателен)
- **445** — SMB (для доступа к файлам, необязателен)
- **139** — NetBIOS (для старых систем, необязателен)

### 3. Почему не получается подключиться к удалённому ПК?
Проверьте по порядку:
1. ✅ ПК включён и в сети (ping)
2. ✅ Порт 5985 открыт (диагностика)
3. ✅ WinRM доступен (диагностика)
4. ✅ Учётные данные сохранены
5. ✅ На удалённом ПК настроен WinRM (режим НАСТРОЙКА ПК)

### 4. Как настроить новый ПК для удалённого управления?
Запустите RemIP на целевом ПК, перейдите в режим **НАСТРОЙКА ПК** и нажмите ⚡ **ЭКСПРЕСС НАСТРОЙКА**.

### 5. Безопасно ли использовать пустой пароль?
Пустой пароль — это потенциальная угроза безопасности. Используйте эту опцию только в изолированной локальной сети. Рекомендуется всегда устанавливать пароль для учётных записей.

### 6. Почему карта сети не видит некоторые устройства?
- Устройство может отключать ping (ICMP)
- Брандмауэр может блокировать порты
- Устройство может быть в другой подсети
- Попробуйте полное сканирование или сканирование из ARP-таблицы

### 7. Как удалить сохранённый IP?
**Способ 1:** В режиме УПРАВЛЕНИЕ выберите IP в списке, нажмите правой кнопкой и выберите "Удалить".  
**Способ 2:** Нажмите 🗑️ **ОЧИСТИТЬ СПИСОК IP** для удаления всех записей.

### 8. Почему после перезагрузки ПК не виден в карте сети?
IP-адрес мог измениться (если используется DHCP). Используйте сканирование из ARP-таблицы или задайте статический IP.

### 9. Как обновить программу?
1. Нажмите на "?" рядом с кнопкой закрыть и проверьте обновление.
2. Скачайте новую версию напрямую с GitHub. Все сохранённые данные останутся в папке `%APPDATA%\RemIP\`.

### 10. Куда сохраняются учётные данные?
Все данные хранятся в зашифрованном виде в папке:  
`%APPDATA%\RemIP\credentials\`

---

## 📝 Системные требования
- **ОС:** Windows 10/11, Windows Server 2019/2022
- **Права:** Администратор (для режима настройки)

---

## 🐛 Известные проблемы и решения

| Проблема | Решение |
|----------|--------|
| Не открываются диалоги | Проверьте, что программа не запущена несколько раз |
| Не работают PowerShell команды | Выполните в PowerShell: `Set-ExecutionPolicy RemoteSigned` |
| Карта сети не видит устройства | Проверьте брандмауэр, попробуйте сканирование из ARP |
| Не удаётся сохранить учётные данные | Проверьте права на запись в папку `%APPDATA%\RemIP\` |

---

## 📞 Контакты
По всем вопросам и предложениям:
- 📧 **Email:** dmistr9999@gmail.com
- 🐙 **GitHub:** https://github.com/dmistr/RemIP

---

<a name="english"></a>
# RemIP - Remote IP Control

**Universal PC remote management tool over IP**

👤 **Author:** dmistr  
📧 **Email:** dmistr9999@gmail.com  
🐙 **GitHub:** https://github.com/dmistr/Remip

---

## 📋 PROGRAM DESCRIPTION

RemIP is a powerful tool for remote computer management in local networks. The program consists of three main modes:

### 🔹 PC CONTROL Mode
Allows remote management of computers that already have remote access configured:
- Shutdown/restart (instant, with timer, with message, with voice)
- Send text and voice messages
- Connection diagnostics (ping, ports, WinRM, permissions)
- Save credentials for quick access

### 🔹 PC SETUP Mode
Prepares a computer for remote management:
- Open required ports (445, 139, 5985)
- Configure network profiles
- Enable/disable services (Server, RemoteRegistry, WinRM)
- Allow blank passwords for accounts
- Full system diagnostics

### 🔹 NETWORK MAP Mode
Automatic local network scanning:
- Discover all active devices
- Detect open ports
- Check WinRM availability
- Save results between sessions
- Quick switch to control mode

---

## 🚀 USER GUIDE

### ⚡ Quick Start
1. Run the program (recommended as administrator)
2. Select the desired mode:
   - 🖥️ **PC CONTROL** — for managing already configured PCs
   - 🛠️ **PC SETUP** — for preparing a computer for remote management
   - 🗺️ **NETWORK MAP** — for discovering devices on the network

---

## 🖥️ PC CONTROL MODE

### 🔑 Credentials
1. Enter the remote computer's IP
2. Click 💾 **SAVE CREDENTIALS**
3. Enter username and password (default name can be left)
4. IP is automatically added to the saved list and TrustedHosts

### 📋 Saved IP List
- Select IP from the dropdown list
- Right-click on IP — delete from list
- 🗑️ **CLEAR IP LIST** button — delete all saved entries

### 🔴 Computer Shutdown
- ⚡ **SHUTDOWN NOW** — immediate shutdown
- ⏱️ **SHUTDOWN TIMER** — shutdown after N seconds
- 💬 **SHUTDOWN + TEXT** — show message and shutdown
- 🎤 **SHUTDOWN + VOICE** — speak message and shutdown

### 💬 Messages
- 📝 **TEXT MESSAGE** — send text to remote PC
- 🗣️ **VOICE MESSAGE** — speak text on remote PC

### 🔧 Service
- 🔄 **ENABLE/DISABLE WINRM** — manage WinRM service on your PC
- 📊 **DIAGNOSTICS** — full connection check
- 🧹 **CLEAR** — clear output window

### ⚙️ Shutdown Modes
- ⚡ **Simple** — just sends the command
- 🛡️ **Protected** — checks result and forces shutdown if needed

---

## 🛠️ PC SETUP MODE

### 🚀 Express
- ⚡ **FAST SETUP** — one-click setup: opens all ports, enables services, configures WinRM
- 💡 **SMART SETUP** — diagnoses status and suggests what to fix

### 🔌 Advanced Setup (🟩 — open, 🟥 — closed)
- 🌐 **PORTS** — toggle buttons for ports 445, 139, 5985
- 🛡️ **PROFILES** — select network profiles (🏠 Private, 🌍 Public, 🏢 Domain)
- 🔑 **BLANK PASSWORD** — allow/deny password-less login
- 🖥️ **SERVICES** — manage Server, RemoteRegistry, WinRM services

### 🔧 Service
- 📊 **DIAGNOSTICS** — full check of ports, services and firewall rules
- 🗑️ **RESET** — reset all settings (close ports, disable services)
- 🧹 **CLEAR** — clear output window

---

## 🗺️ NETWORK MAP MODE

### 🔍 Scanning
- ⚡ **FAST** — check main ports (< 1 minute)
- 🔍 **FULL** — check all ports (1-5 minutes)
- 📋 **FROM ARP** — view active devices (< 1 minute)

### 📊 Legend
- 🟢 — WinRM available and credentials saved
- 🟡 — WinRM available but no credentials
- ⚪ — WinRM not available

### 🖱️ Actions
- Double-click — switch to control mode
- Right-click — context menu with actions
- ▶/◀ — expand/collapse detailed information

### 💾 Saving Results
- Results are automatically saved to a temporary file
- Data is restored when reopening network map
- 🗑️ **CLEAR RESULTS** button — deletes all saved data

---

## ❓ FAQ

### 1. Why does the program require administrator rights?
Administrator rights are required to modify firewall rules, manage services, and configure WinRM. Without them, most setup mode functions won't work.

### 2. Which ports are needed for remote management?
- **5985** — WinRM (required)
- **445** — SMB (for file access, optional)
- **139** — NetBIOS (for legacy systems, optional)

### 3. Why can't I connect to a remote PC?
Check in order:
1. ✅ PC is on and on the network (ping)
2. ✅ Port 5985 is open (diagnostics)
3. ✅ WinRM is available (diagnostics)
4. ✅ Credentials are saved
5. ✅ WinRM is configured on the remote PC (PC SETUP mode)

### 4. How to set up a new PC for remote management?
Run RemIP on the target PC, go to **PC SETUP** mode and click ⚡ **FAST SETUP**.

### 5. Is it safe to use a blank password?
Blank passwords are a potential security threat. Use this option only in isolated local networks. It's recommended to always set a password for accounts.

### 6. Why doesn't the network map see some devices?
- Device may block ping (ICMP)
- Firewall may block ports
- Device may be on a different subnet
- Try full scan or ARP table scan

### 7. How to delete a saved IP?
**Method 1:** In CONTROL mode, select the IP from the list, right-click and choose "Delete".  
**Method 2:** Click 🗑️ **CLEAR IP LIST** to delete all entries.

### 8. Why is the PC not visible in the network map after reboot?
The IP address may have changed (if using DHCP). Use ARP table scan or set a static IP.

### 9. How to update the program?
1. Click the "?" next to the close button and check for the update.
2. Download the new version from GitHub. All saved data will remain in `%APPDATA%\RemIP\`.

### 10. Where are credentials stored?
All data is stored encrypted in the folder:  
`%APPDATA%\RemIP\credentials\`

---

## 📝 System Requirements
- **OS:** Windows 10/11, Windows Server 2019/2022
- **Privileges:** Administrator (for setup mode)

---

## 🐛 Known Issues and Solutions

| Problem | Solution |
|---------|----------|
| Dialogs don't open | Check that the program isn't running multiple times |
| PowerShell commands don't work | Run in PowerShell: `Set-ExecutionPolicy RemoteSigned` |
| Network map doesn't see devices | Check firewall, try ARP scan |
| Can't save credentials | Check write permissions to `%APPDATA%\RemIP\` folder |

---

## 📞 Contact
For questions and suggestions:
- 📧 **Email:** dmistr9999@gmail.com
- 🐙 **GitHub:** https://github.com/dmistr/RemIP
