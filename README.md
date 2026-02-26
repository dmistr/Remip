# RemIP - Remote IP Management Suite

[![Windows](https://img.shields.io/badge/Platform-Windows-blue)](https://github.com/)
[![PowerShell](https://img.shields.io/badge/PowerShell-5.1+-green)](https://github.com/)
![License](https://img.shields.io/badge/License-Free-orange)

**RemIP** - это комплекс из двух программ для удаленного управления компьютерами в локальной сети:

1. **Install RemIP** - настройка компьютера для приема удаленных команд
2. **RemIP** - управление удаленными компьютерами с сохранением учетных данных

---

## 🌍 Language / Язык

- [English](#english)
- [Русский](#русский)

---

## English

### 📋 Overview

**RemIP Suite** consists of two complementary tools for remote PC management:

| Program | Purpose |
|---------|---------|
| **Install RemIP** | Prepare a computer to accept remote commands (run on target PC) |
| **RemIP** | Manage remote computers with saved credentials (run on management PC) |

---

## Install RemIP - Incoming PC Setup

### 🚀 Features

#### 1. Target PC Selection
| Feature | Description |
|---------|-------------|
| Management PC IP | Enter the IP address of the computer that will manage this PC |

#### 2. Setup Functions
| # | Function | Description |
|---|----------|-------------|
| 1 | **FULL SETUP** | Complete configuration (ports + services + WinRM) |
| 2 | **OPEN PORTS** | Open firewall ports 445, 139, 5985 |
| 3 | **ENABLE SERVICES** | Enable Server, RemoteRegistry, WinRM services |
| 4 | **CONFIGURE WINRM** | Configure WinRM and add management PC to TrustedHosts |
| 5 | **CHECK AND FIX** | Diagnose and automatically fix common issues |
| 6 | **DIAGNOSTICS** | Check current system state |
| 7 | **REBOOT** | Reboot the computer |
| 8 | **RESET SETTINGS** | Remove all changes and restore default security |

#### 3. Interface
| Feature | Description |
|---------|-------------|
| 🌐 Bilingual | Russian/English interface |
| 🎨 Colored output | Emoji indicators for status |
| 📊 Progress bar | Visual feedback for operations |
| 🔒 Fixed window | No resizing, clean layout |
| 📋 Manual instructions | Shows commands if automatic fix fails |

### 📖 User Guide - Install RemIP

#### 🔧 Initial Setup

1. **Run the program** as administrator (required for system changes)
2. **Select language** in the top-right corner
3. **Enter the IP address** of the computer that will manage this PC
4. Choose the desired operation from the menu

#### 🛠️ Setup Operations

**Item 1: FULL SETUP**

Performs complete configuration in one click:
- Opens ports 445, 139, 5985 in firewall
- Enables Server, RemoteRegistry, WinRM services
- Configures WinRM and adds management PC to TrustedHosts

FULL SETUP
════════════════════════════════════════
→ Port setup:
→ Starting services:
→ 4. CONFIGURE WINRM
✅ FULL SETUP COMPLETE


**Item 2: OPEN PORTS**

Opens required ports in Windows Firewall:
- **Port 445** - SMB (File Sharing)
- **Port 139** - NetBIOS
- **Port 5985** - WinRM (Windows Remote Management)

**Item 3: ENABLE SERVICES**

Starts and enables automatic startup for:
- **Server service** (LanmanServer) - required for file sharing
- **RemoteRegistry** - allows remote registry access
- **WinRM** - Windows Remote Management service

**Item 4: CONFIGURE WINRM**

Sets up WinRM for remote management:
- Runs `winrm quickconfig`
- Adds management PC IP to TrustedHosts
- Enables basic authentication

**Item 5: CHECK AND FIX**

Diagnoses and automatically fixes common issues:
- Checks if services are running
- Verifies firewall rules
- Updates TrustedHosts
- Restarts firewall if needed

If automatic fix fails, displays manual instructions:

📋 MANUAL FIREWALL COMMANDS
══════════════════════════════════════════════════
Some rules could not be created automatically.

Delete old rules:
→ netsh advfirewall firewall delete rule name="SMB 445"
→ netsh advfirewall firewall delete rule name="WinRM 5985"
→ netsh advfirewall firewall delete rule name="NetBIOS 139"

Create new rules:
→ netsh advfirewall firewall add rule name="SMB 445" dir=in action=allow protocol=TCP localport=445
→ netsh advfirewall firewall add rule name="WinRM 5985" dir=in action=allow protocol=TCP localport=5985
→ netsh advfirewall firewall add rule name="NetBIOS 139" dir=in action=allow protocol=TCP localport=139

⚠️ Run these commands as administrator!


**Item 6: DIAGNOSTICS**

Checks current system state:
- Port status (445, 139, 5985)
- Service status (Server, RemoteRegistry, WinRM)
- Firewall rules presence
- TrustedHosts configuration

Example output:

SYSTEM DIAGNOSTICS
════════════════════════════════════════

PORT STATUS:
✅ Port 445 (SMB): ACTIVE
✅ Port 139 (NetBIOS): ACTIVE
✅ Port 5985 (WinRM): ACTIVE

SERVICE STATUS:
✅ Server Service: RUNNING
✅ RemoteRegistry Service: RUNNING
✅ WinRM Service: RUNNING

FIREWALL RULES:
✅ SMB 445 Rule: PRESENT
✅ WinRM 5985 Rule: PRESENT
✅ NetBIOS 139 Rule: PRESENT

WINRM SETTINGS:
TrustedHosts = 192.168.1.2

✅ DIAGNOSTICS COMPLETE


**Item 7: REBOOT**

- Safely reboots the computer
- Shows confirmation dialog
- 30-second countdown before restart

**Item 8: RESET SETTINGS**

Removes all changes and restores default security:
- Deletes all created firewall rules
- Stops and disables RemoteRegistry and WinRM services
- Clears TrustedHosts
- Restarts firewall

⚠️ **Warning:** This reverts all changes made by the program!

---

## RemIP - Remote PC Management

### 🚀 Features

#### 1. Target PC Selection
| Feature | Description |
|---------|-------------|
| Manual IP input | Enter any IP address in the local network |
| IP history | Automatically saves used IPs |
| Availability check | Ping test before executing commands |

#### 2. Power Management
| # | Function | Description |
|---|----------|-------------|
| 1 | **SHUTDOWN NOW** | Instant remote PC shutdown |
| 2 | **SHUTDOWN WITH TIMER** | Shutdown after specified seconds |
| 3 | **SHUTDOWN + TEXT** | Shutdown with text notification |
| 4 | **SHUTDOWN + VOICE** | Shutdown with voice warning |

#### 3. Message Sending
| # | Function | Description |
|---|----------|-------------|
| 5 | **TEXT MESSAGE** | Pop-up windows on remote PC |
| 6 | **VOICE MESSAGE** | Speech synthesis via System.Speech |

#### 4. Credential Management
| # | Function | Description |
|---|----------|-------------|
| 7 | **SAVE CREDENTIALS** | Secure encrypted storage of logins and passwords |
| 8 | **SHOW SAVED IPs** | View all saved addresses |
| 9 | **DELETE CREDENTIALS** | Clear saved data for selected IP |

#### 5. Diagnostics
| # | Function | Description |
|---|----------|-------------|
| 10 | **DIAGNOSTICS** | Check PC availability, WinRM, port 5985 |

### 📖 User Guide - RemIP

#### 🔧 Initial Setup

1. **Run the program** as administrator (required for WinRM)
2. **Select language** in the top-right corner
3. **Enter IP address** of target computer
4. **Save credentials** (item 7) - enter login and password for remote PC

#### 💻 Power Management

**Item 1: Shutdown Now**
- Click "1. SHUTDOWN NOW" button
- Command executes immediately

**Item 2: Shutdown with Timer**
- Enter seconds until shutdown (e.g., 30, 60, 120)
- Click OK
- Command executes after specified time

**Item 3: Shutdown + Text**
- Enter time in seconds
- Enter warning text
- Message window appears on remote PC
- PC shuts down after specified time

**Item 4: Shutdown + Voice**
- Enter time in seconds
- Enter text for voice
- Voice message plays on remote PC
- PC shuts down after specified time

#### 💬 Sending Messages

**Item 5: Text Message**
- Enter message text
- Pop-up window appears on remote PC for 30 seconds

**Item 6: Voice Message**
- Enter text for voice
- Voice message plays on remote PC using text-to-speech

#### 🔐 Credential Management

**Item 7: Save Credentials**
- Enter login and password for remote PC
- Data is encrypted and saved in `C:\temp\`
- Format: `remote_cred_192_168_1_100.xml`

**Item 8: Show Saved IPs**
- Displays all IPs with saved credentials
- Shows list of files in `C:\temp\`

**Item 9: Delete Credentials**
- Deletes saved data for current IP
- Requires confirmation before deletion

#### 🔍 Diagnostics

**Item 10: Diagnostics**

Performs three checks:
1. **Ping test** - basic network availability
2. **WinRM test** - remote management service
3. **Port 5985 test** - WinRM default port

Output example:

CONNECTION DIAGNOSTICS
════════════════════════════════════════

PING TEST:
✅ Computer 192.168.1.166 is online

WINRM TEST:
✅ WinRM is available

PORT 5985 TEST:
✅ Port 5985 is open

✅ DIAGNOSTICS COMPLETE


#### 🧹 Clear Output

| Button | Function |
|--------|----------|
| **CLEAR OUTPUT** | Clears the output window |

---

## 🔄 Workflow Example

### Step 1: Prepare target PC (run Install RemIP)
1. Run **Install RemIP** as administrator on the computer to be managed
2. Enter management PC IP
3. Select **1. FULL SETUP**
4. Verify with **6. DIAGNOSTICS**

### Step 2: Manage remote PC (run RemIP)
1. Run **RemIP** as administrator on management PC
2. Enter target PC IP
3. Select **7. SAVE CREDENTIALS** and enter login/password
4. Now you can shutdown, send messages, etc.

---

## ⚠️ Important Notes (Both Programs)

1. **Administrator Rights** - both programs require administrator privileges
2. **WinRM** - target PC must have WinRM configured (port 5985)
3. **Firewall** - port 5985 must be open on target PC's firewall
4. **Credentials** - stored encrypted, accessible only to current user
5. **Availability** - programs check PC availability before executing commands

### 📁 File Structure

C:\temp

├── remote_cred_192.168.1.100.xml # Encrypted credentials for IP

├── remote_cred_192.168.1.120.xml # Encrypted credentials for IP

└── ...


### 🔧 Troubleshooting

| Error | Solution |
|-------|----------|
| ❌ Computer is offline | Check if target PC is turned on and network connection |
| ❌ WinRM is unavailable | Run Install RemIP on target PC, item 1 or 4 |
| ❌ Port 5985 is closed | Run Install RemIP on target PC, item 2 |
| ⚠️ Credentials not found | Save credentials via RemIP item 7 first |
| ❌ Administrator rights required | Run program as administrator |
| ❌ Firewall start error | Wait a few seconds and try again |

---

## Русский

### 📋 Обзор

**RemIP Suite** состоит из двух взаимодополняющих программ для удаленного управления ПК:

| Программа | Назначение |
|-----------|------------|
| **Install RemIP** | Подготовка компьютера к приему удаленных команд (запускать на целевом ПК) |
| **RemIP** | Управление удаленными компьютерами с сохранением данных (запускать на управляющем ПК) |

---

## Install RemIP - Настройка входящего ПК

### 🚀 Функции

#### 1. Выбор целевого ПК
| Функция | Описание |
|---------|----------|
| IP управляющего ПК | IP-адрес компьютера, который будет управлять этим ПК |

#### 2. Функции настройки
| # | Функция | Описание |
|---|---------|----------|
| 1 | **ПОЛНАЯ НАСТРОЙКА** | Полная конфигурация (порты + службы + WinRM) |
| 2 | **ОТКРЫТЬ ПОРТЫ** | Открыть порты 445, 139, 5985 в брандмауэре |
| 3 | **ВКЛЮЧИТЬ СЛУЖБЫ** | Включить службы Server, RemoteRegistry, WinRM |
| 4 | **НАСТРОИТЬ WINRM** | Настроить WinRM и добавить управляющий ПК в TrustedHosts |
| 5 | **ПРОВЕРИТЬ И ИСПРАВИТЬ** | Диагностика и автоматическое исправление проблем |
| 6 | **ДИАГНОСТИКА** | Проверка текущего состояния системы |
| 7 | **ПЕРЕЗАГРУЗИТЬ** | Перезагрузка компьютера |
| 8 | **СБРОС НАСТРОЕК** | Удаление всех изменений и восстановление безопасности |

### 📖 Инструкция - Install RemIP

#### 🔧 Первоначальная настройка

1. **Запустите программу** от имени администратора
2. **Выберите язык** в правом верхнем углу
3. **Введите IP-адрес** управляющего компьютера
4. Выберите нужную операцию

#### 🛠️ Операции настройки

**Пункт 1: ПОЛНАЯ НАСТРОЙКА**
- Открывает порты 445, 139, 5985
- Включает службы Server, RemoteRegistry, WinRM
- Настраивает WinRM и TrustedHosts

**Пункт 2: ОТКРЫТЬ ПОРТЫ**
- **Порт 445** - SMB (общий доступ)
- **Порт 139** - NetBIOS
- **Порт 5985** - WinRM

**Пункт 3: ВКЛЮЧИТЬ СЛУЖБЫ**
- Служба Сервер (LanmanServer)
- RemoteRegistry
- WinRM

**Пункт 4: НАСТРОИТЬ WINRM**
- `winrm quickconfig`
- Добавление IP в TrustedHosts
- Базовая аутентификация

**Пункт 5: ПРОВЕРИТЬ И ИСПРАВИТЬ**
- Проверка служб и правил
- Автоматическое исправление
- Ручные инструкции при ошибках

**Пункт 6: ДИАГНОСТИКА**
- Статус портов
- Состояние служб
- Правила брандмауэра
- TrustedHosts

**Пункт 7: ПЕРЕЗАГРУЗИТЬ**
- Подтверждение
- 30 секунд до перезагрузки

**Пункт 8: СБРОС НАСТРОЕК**
- Удаление всех правил
- Остановка служб
- Очистка TrustedHosts

---

## RemIP - Управление удаленными ПК

### 🚀 Функции

#### 1. Выбор целевого ПК
| Функция | Описание |
|---------|----------|
| Ручной ввод IP | Любой IP-адрес в сети |
| История IP | Автосохранение использованных адресов |
| Проверка связи | Ping перед командами |

#### 2. Управление питанием
| # | Функция | Описание |
|---|---------|----------|
| 1 | **ВЫКЛЮЧИТЬ СЕЙЧАС** | Мгновенное выключение |
| 2 | **ВЫКЛЮЧИТЬ С ТАЙМЕРОМ** | Выключение через N секунд |
| 3 | **ВЫКЛЮЧИТЬ + ТЕКСТ** | Выключение с уведомлением |
| 4 | **ВЫКЛЮЧИТЬ + ГОЛОС** | Выключение с голосом |

#### 3. Отправка сообщений
| # | Функция | Описание |
|---|---------|----------|
| 5 | **ТЕКСТОВОЕ СООБЩЕНИЕ** | Всплывающие окна |
| 6 | **ГОЛОСОВОЕ СООБЩЕНИЕ** | Синтез речи |

#### 4. Управление данными
| # | Функция | Описание |
|---|---------|----------|
| 7 | **СОХРАНИТЬ ДАННЫЕ** | Шифрованное хранение логинов/паролей |
| 8 | **СПИСОК IP** | Все сохраненные адреса |
| 9 | **УДАЛИТЬ ДАННЫЕ** | Очистка для выбранного IP |

#### 5. Диагностика
| # | Функция | Описание |
|---|---------|----------|
| 10 | **ДИАГНОСТИКА** | Проверка связи, WinRM, порта 5985 |

### 📖 Инструкция - RemIP

#### 🔧 Начало работы

1. **Запустите** от имени администратора
2. **Выберите язык**
3. **Введите IP** целевого ПК
4. **Сохраните данные** (пункт 7)

#### 💻 Управление

**Пункт 1-4:** Выключение с разными опциями
**Пункт 5-6:** Отправка сообщений
**Пункт 7-9:** Управление учетными данными
**Пункт 10:** Диагностика подключения

---

## 🔄 Пример работы

### Шаг 1: Подготовка целевого ПК (Install RemIP)
1. Запустите **Install RemIP** на целевом ПК (администратор)
2. Введите IP управляющего ПК
3. Выберите **1. ПОЛНАЯ НАСТРОЙКА**
4. Проверьте **6. ДИАГНОСТИКА**

### Шаг 2: Управление (RemIP)
1. Запустите **RemIP** на управляющем ПК (администратор)
2. Введите IP целевого ПК
3. Выберите **7. СОХРАНИТЬ ДАННЫЕ**, введите логин/пароль
4. Теперь можно выключать, отправлять сообщения и т.д.

---

## ⚠️ Важные замечания

1. **Права администратора** - требуются для обеих программ
2. **WinRM** - должен быть настроен на целевом ПК
3. **Брандмауэр** - порт 5985 должен быть открыт
4. **Данные** - хранятся в зашифрованном виде в `C:\temp\`
5. **Проверка связи** - выполняется перед командами

### 📁 Структура файлов

C:\temp

├── remote_cred_192.168.1.100.xml

├── remote_cred_192.168.1.120.xml

└── ...


### 🔧 Устранение неполадок

| Ошибка | Решение |
|--------|---------|
| ❌ ПК не отвечает | Проверьте сеть, включен ли ПК |
| ❌ WinRM недоступен | Запустите Install RemIP, пункт 1 |
| ❌ Порт 5985 закрыт | Запустите Install RemIP, пункт 2 |
| ⚠️ Данные не найдены | Сохраните через RemIP, пункт 7 |
| ❌ Нет прав администратора | Запустите от имени администратора |

---

## 📝 Version History / История версий

### 2026
- Initial release of RemIP Suite / Первый релиз RemIP Suite
- Complete remote management solution / Полное решение для удаленного управления
- Bilingual interface / Двуязычный интерфейс
- Automatic setup and diagnostics / Автоматическая настройка и диагностика

---

## 👨‍💻 Author / Автор

Created for remote PC management in local networks.  
Создано для удаленного управления ПК в локальных сетях.

---

## 📄 License / Лицензия

Free for personal and educational use.  
Бесплатно для личного и образовательного использования.
