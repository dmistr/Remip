[![License](https://img.shields.io/badge/license-MIT-red.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-blue.svg)]()
[![Python](https://img.shields.io/badge/Python-3.14%2B-yellow.svg)]()
[![PyQt](https://img.shields.io/badge/PyQt-6.0%2B-brightgreen.svg)]()
[![Downloads](https://img.shields.io/github/downloads/dmistr/Remip/total.svg)](https://github.com/dmistr/Remip/releases)

<h1 align="center">
  <img src="https://raw.githubusercontent.com/dmistr/Remip/main/resources/logo.png" alt="RemIP Logo" width="64" align="center">
  RemIP - Remote IP Control
</h1>

<p align="center">
  <b>Универсальный инструмент удалённого управления ПК по IP</b><br>
  <i>Universal remote PC management tool over IP</i>
</p>

<p align="center">
  👤 <b>Автор:</b> dmistr &nbsp;&nbsp;|&nbsp;&nbsp; 📧 <b>Email:</b> dmistr9999@gmail.com &nbsp;&nbsp;|&nbsp;&nbsp; 🐙 <b>GitHub:</b> <a href="https://github.com/dmistr/Remip">dmistr/Remip</a>
</p>

---

<div align="center">

[🇷🇺 Русский](#русский) &nbsp;&nbsp;|&nbsp;&nbsp; [🇬🇧 English](#english)

</div>

---

<a name="русский"></a>
## 🇷🇺 РУССКИЙ

### 📋 ОПИСАНИЕ ПРОГРАММЫ

**RemIP** — это портативный инструмент для удалённого управления компьютерами в локальной сети. Не требует установки, достаточно запустить EXE-файл. Программа состоит из трёх основных режимов, окна настроек и уникальной **Платформы Умного Агента**.

<p align="center">
  <img src="[SCREENSHOT_MAIN_MENU]" alt="Главное меню RemIP" width="800">
  <br><i>Главное меню программы</i>
</p>

---

### 🚀 ОСНОВНЫЕ ВОЗМОЖНОСТИ

#### 🤖 Платформа Умного Агента (Smart Agent Platform)

*Новейшая технология, не имеющая аналогов на рынке.*

Агент Remip — это легковесный PowerShell-сервер, который доставляется на удалённый ПК в один клик. Он самостоятельно преодолевает ограничения изолированной Session 0, перезапускаясь в активной сессии пользователя. Это открывает доступ к графической подсистеме и позволяет:

- **📸 Делать скриншоты** удалённого экрана в один клик
- **🖥️ Выполнять команды** в контексте пользователя (в разработке)
- **💬 Показывать интерактивные уведомления** (в разработке)

**Ключевые особенности:**
- **Мгновенная доставка** — без скачивания файлов и подтверждений
- **Полная невидимость** — ни окон, ни иконок в трее
- **Самовосстановление** — агент следит за правилом брандмауэра и восстанавливает его
- **Контроль версий** — автоматическое определение устаревшей версии и обновление

<p align="center">
  <img src="[SCREENSHOT_AGENT_INSTALLED]" alt="Агент RemIP в работе" width="400">
  <br><i>Кнопка агента: 🟢 установлен и работает, 🔴 не установлен</i>
</p>

---

### 🔹 Режим УПРАВЛЕНИЕ ПК (Control)

Позволяет удалённо управлять компьютерами, на которых уже настроен WinRM.

<p align="center">
  <img src="[SCREENSHOT_CONTROL_TAB]" alt="Режим Управление ПК" width="800">
</p>

#### 🔑 Учётные данные

| Элемент | Описание |
|---------|----------|
| **Поле ввода IP** | Ввод IP-адреса удалённого компьютера. |
| **Кнопка статуса** (`▶`/`⏳`/`✓`/`⛌`) | Проверяет доступность ПК. Меняет цвет: серый — не проверен, жёлтый — проверка, зелёный — онлайн, красный — офлайн. |
| **Выпадающий список IP** | Список сохранённых IP. **Зелёная галочка ✓** означает, что учётные данные проверены и работают. |
| **ВВЕСТИ И СОХРАНИТЬ** | Открывает диалог ввода логина/пароля. Проверяет их **до сохранения** и ставит ✓ при успехе. |
| **ОЧИСТИТЬ СПИСОК IP** | Удаляет все сохранённые учётные данные и очищает TrustedHosts. |

#### 🔴 Выключение компьютера

| Кнопка | Описание |
|--------|----------|
| **ВЫКЛЮЧИТЬ СЕЙЧАС** | Мгновенная команда `shutdown /s /f /t 0`. |
| **ВЫКЛЮЧИТЬ С ТАЙМЕРОМ** | Выключение через N секунд. |
| **ВЫКЛЮЧИТЬ + ТЕКСТ** | Показывает текстовое предупреждение перед выключением. |
| **ВЫКЛЮЧИТЬ + ГОЛОС** | Озвучивает сообщение через системный синтезатор речи перед выключением. |

#### 💬 Сообщения и Скриншоты

| Кнопка | Описание |
|--------|----------|
| **📸 СКРИНШОТ** | **НОВИНКА!** Мгновенно получает скриншот удалённого экрана через Агента. Поддерживает форматы PNG (без потерь) и JPEG (сжатие). Встроенный просмотрщик с зумом и полноэкранным режимом. |
| **ТЕКСТОВОЕ СООБЩЕНИЕ** | Отправляет текст через команду `msg`. Поддерживает русский и английский языки. |
| **ГОЛОСОВОЕ СООБЩЕНИЕ** | Озвучивает текст на удалённом ПК через `System.Speech.SpeechSynthesizer`. |

<p align="center">
  <img src="[SCREENSHOT_SCREENSHOT_VIEWER]" alt="Просмотр скриншота" width="800">
  <br><i>Встроенный просмотрщик скриншотов с зумом и панорамированием</i>
</p>

#### 🔧 Сервис

| Кнопка | Описание |
|--------|----------|
| **WinRM (ВКЛ/ВЫКЛ)** | Управляет службой WinRM на вашем локальном компьютере. При включении синхронизирует TrustedHosts. |
| **ДИАГНОСТИКА** | Полная проверка: ping, порт 5985, WinRM, учётные данные, права администратора, UAC, пустой пароль, создание файлов. |
| **ОЧИСТИТЬ** | Очищает окно вывода терминала. |

#### ⚙️ Режим «Анти-отмена»

| Режим | Описание |
|-------|----------|
| **Обычный** | Отправляет команду `shutdown`. Пользователь может отменить её (`shutdown /a`). |
| **Защищённый** | После отправки ждёт (задержка настраивается) и проверяет статус ПК. Если не выключился — отправляет принудительную команду повторно (до 2 попыток). |

---

### 🔹 Режим НАСТРОЙКА ПК (Install)

Готовит текущий компьютер к приёму удалённых команд.

<p align="center">
  <img src="[SCREENSHOT_INSTALL_TAB]" alt="Режим Настройка ПК" width="800">
</p>

#### 🚀 Экспресс-настройка

| Кнопка | Описание |
|--------|----------|
| **⚡ БЫСТРАЯ НАСТРОЙКА** | Всё в одном: открывает порты 445, 139, 5985, включает службы Server, RemoteRegistry, WinRM, разрешает пустой пароль, включает Remote UAC, DCOM, RDP. |
| **💡 УМНАЯ НАСТРОЙКА** | Диагностирует систему и показывает диалог с выбором: что именно исправить. Вы сами решаете, какие изменения применить. |

<p align="center">
  <img src="[SCREENSHOT_SMART_FIX]" alt="Диалог Умной настройки" width="500">
  <br><i>Диалог выбора исправлений в Умной настройке</i>
</p>

#### 🔌 Расширенная настройка (цветные переключатели)

| Группа | Кнопки | Описание |
|--------|--------|----------|
| **🌐 ПОРТЫ** | 445, 139, 5985 | Открытие/закрытие портов в брандмауэре. 🟩 — открыт, 🟥 — закрыт. |
| **🛡️ ПРОФИЛИ** | 🏠 Частная, 🌍 Общественная, 🏢 Доменная | Выбор сетевых профилей для правил. |
| **🖥️ СЛУЖБЫ** | Server, RemoteRegistry, WinRM | Включение/отключение служб и настройка автозапуска. |
| **🔐 РАЗРЕШЕНИЯ** | UAC, DCOM, RDP, Пустой пароль | Управление расширенными разрешениями системы. |

#### 🔧 Сервис

| Кнопка | Описание |
|--------|----------|
| **📊 ДИАГНОСТИКА** | Проверяет профиль сети, порты, службы, TrustedHosts, пустой пароль, разрешения. |
| **🗑️ СБРОС** | Откатывает все настройки, сделанные программой: удаляет правила, останавливает службы, очищает TrustedHosts. |
| **🧹 ОЧИСТИТЬ** | Очищает окно вывода. |

---

### 🔹 Режим КАРТА СЕТИ (Network Map)

Сканирует локальную сеть и отображает все устройства.

<p align="center">
  <img src="[SCREENSHOT_NETWORK_MAP]" alt="Карта сети" width="800">
  <br><i>Расширенный режим карты сети с групповыми действиями</i>
</p>

#### 🔍 Сканирование

| Кнопка | Описание |
|--------|----------|
| **⚡ БЫСТРОЕ** | Проверка основных портов (135, 139, 445, 5985, 3389, 80, 443). ~30 сек. |
| **🔍 ПОЛНОЕ** | Проверка расширенного списка портов. 1-5 мин. |
| **📋 ARP** | Сканирование устройств из ARP-таблицы. Самый быстрый способ. |
| **⏹ СТОП** | Остановка текущего сканирования. |

#### 📊 Таблица устройств

| Столбец | Описание |
|---------|----------|
| **☑ Чекбокс** | Для групповых действий (только для 🟢). |
| **Статус** | 🟢 — Готов к работе; 🟡 — Нет данных; 🔵 — Требуется настройка WinRM; 🔴 — Не поддерживается. |
| **WinRM** | ✅ доступен / ❌ недоступен. |
| **Данные** | ✅ сохранены / ❌ не сохранены. |

#### 👥 Групповые действия (для отмеченных 🟢 устройств)

| Кнопка | Описание |
|--------|----------|
| **🔴 ВЫКЛЮЧИТЬ** | Мгновенное выключение всех выбранных ПК. |
| **💬 СООБЩЕНИЕ** | Отправка одного текста на все выбранные ПК. |
| **🎤 ГОЛОС** | Озвучка текста на всех выбранных ПК с настраиваемой задержкой для синхронизации. |

---

### ⚙️ ОКНО НАСТРОЕК

<p align="center">
  <img src="[SCREENSHOT_SETTINGS]" alt="Окно настроек" width="600">
</p>

| Настройка | Описание |
|-----------|----------|
| **Задержка проверки выключения** | Время ожидания перед проверкой статуса ПК в защищённом режиме (15-99 сек). |
| **Синхронизация голоса** | Задержка между устройствами при групповой отправке голоса (0-3 сек). |
| **Автоматическая диагностика** | Автозапуск проверки состояния при входе в «Настройку ПК». |
| **Автопроверка обновлений** | Проверка новых версий на GitHub при запуске. |
| **Язык / Тема** | Русский/English, Светлая/Тёмная тема. |
| **Формат скриншота** | Выбор между PNG (качество) и JPEG (экономия места). |
| **Логирование** | Вкл/выкл записи логов. Кнопка «📂 ЛОГИ» открывает папку с файлами. |

---

### 🚀 АВТООБНОВЛЕНИЕ

- При запуске проверяет GitHub на наличие новой версии.
- Значок 🔔 в верхней панели сигнализирует о доступном обновлении.
- Скачивание нового EXE в фоне с отображением прогресса.
- Кнопка «Перезапустить сейчас» для быстрого обновления.

---

### 📤 ОБРАТНАЯ СВЯЗЬ

В окне «О программе» (кнопка `?`) нажмите **📤 Обратная связь**. Опишите проблему, укажите email (опционально). Программа автоматически прикрепит системную информацию и последние строки лога. Отправка происходит через защищённый канал `ntfy.sh`.

---

### 📝 Системные требования

| Компонент | Требование |
|-----------|------------|
| **ОС** | Windows 10/11, Windows Server 2019/2022 |
| **Права** | Администратор (для полной функциональности) |
| **PowerShell** | 5.1+ |
| **.NET Framework** | 4.8+ |

---

### 📞 Контакты

По всем вопросам и предложениям: **dmistr9999@gmail.com**

---

<a name="english"></a>
## 🇬🇧 ENGLISH

### 📋 PROGRAM DESCRIPTION

**RemIP** is a portable tool for remote computer management in local networks. No installation required. It features three main modes, a settings window, and the unique **Smart Agent Platform**.

<p align="center">
  <img src="[SCREENSHOT_MAIN_MENU]" alt="RemIP Main Menu" width="800">
  <br><i>Main Menu</i>
</p>

---

### 🚀 KEY FEATURES

#### 🤖 Smart Agent Platform

*A unique technology with no market analogues.*

Remip Agent is a lightweight PowerShell server delivered to a remote PC in one click. It overcomes Session 0 isolation by restarting itself in the active user session, enabling:

- **📸 Screenshots** of the remote screen in one click.
- **🖥️ Command execution** in user context (in development).
- **💬 Interactive notifications** (in development).

**Key Features:**
- **Instant delivery** — no file downloads or confirmations.
- **Complete invisibility** — no windows or tray icons.
- **Self-healing** — monitors and restores its firewall rule.
- **Version control** — automatically detects outdated versions and updates.

<p align="center">
  <img src="[SCREENSHOT_AGENT_INSTALLED]" alt="RemIP Agent in action" width="400">
  <br><i>Agent button: 🟢 installed & running, 🔴 not installed</i>
</p>

---

### 🔹 PC CONTROL Mode

Remote management of computers with WinRM already configured.

| Feature | Description |
|---------|-------------|
| **Credentials** | Save username/password. Verified credentials show a ✓ checkmark. |
| **Shutdown** | Instant, timer, text, or voice announcement. |
| **📸 Screenshot** | **NEW!** Capture remote screen via Agent. Supports PNG/JPEG. Built-in viewer with zoom. |
| **Messages** | Send text via `msg` or voice via Speech Synthesizer. |
| **Anti-cancel Mode** | Verifies shutdown and retries if necessary. |

---

### 🔹 PC SETUP Mode

Prepares the current computer for remote management.

| Feature | Description |
|---------|-------------|
| **Fast Setup** | One-click configuration: opens ports, enables services, allows blank password, enables Remote UAC, DCOM, RDP. |
| **Smart Setup** | Diagnoses and lets you choose what to fix. |
| **Manual Control** | Toggle individual ports, profiles, services, and permissions. |

---

### 🔹 NETWORK MAP Mode

Scans the local network and displays all devices.

| Feature | Description |
|---------|-------------|
| **Fast/Full/ARP Scan** | Different scan modes for speed vs. thoroughness. |
| **Device Status** | 🟢 Ready, 🟡 No credentials, 🔵 Needs setup, 🔴 Not supported. |
| **Group Actions** | Select multiple 🟢 devices to shutdown or send messages/voice. |
| **Voice Sync** | Adjustable delay for synchronized voice playback across devices. |

---

### ⚙️ SETTINGS

| Setting | Description |
|---------|-------------|
| **Shutdown check delay** | Wait time before verifying shutdown (15-99 sec). |
| **Voice sync delay** | Delay between devices for group voice (0-3 sec). |
| **Auto-diagnostic** | Run diagnostics when entering PC Setup mode. |
| **Auto-update** | Check for new versions on startup. |
| **Language / Theme** | Russian/English, Light/Dark. |
| **Screenshot format** | PNG (lossless) or JPEG (compressed). |
| **Logging** | Enable/disable log file writing. |

---

### 🚀 AUTO-UPDATE

- Checks GitHub for new versions on startup.
- 🔔 icon appears if an update is available.
- Downloads the new EXE in the background.
- «Restart now» button closes the old version and opens the new one.

---

### 📤 FEEDBACK

In the «About» window (`?` button), click **📤 Feedback**. Describe the issue, optionally enter your email. System info and the last 500 log lines are attached automatically. Sent via secure `ntfy.sh` channel.

---

### 📝 System Requirements

| Component | Requirement |
|-----------|-------------|
| **OS** | Windows 10/11, Windows Server 2019/2022 |
| **Privileges** | Administrator (for full functionality) |
| **PowerShell** | 5.1+ |
| **.NET Framework** | 4.8+ |

---

### 📞 Contact

For questions and suggestions: **dmistr9999@gmail.com**
