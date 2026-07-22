[![License](https://img.shields.io/badge/license-MIT-red.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-blue.svg)]()
[![Python](https://img.shields.io/badge/Python-3.14%2B-yellow.svg)]()
[![PyQt](https://img.shields.io/badge/PyQt-6.0%2B-brightgreen.svg)]()
[![Downloads](https://img.shields.io/github/downloads/dmistr/Remip/total.svg)](https://github.com/dmistr/Remip/releases)
[![VirusTotal](https://img.shields.io/badge/VirusTotal-2%2F69-brightgreen?logo=virustotal&logoColor=white)](https://www.virustotal.com/gui/file/4ba0556fe18100f3959f0147e3145122331834f04024d36387a7597236bc9672)

<h1 align="center">
  <img src="https://raw.githubusercontent.com/dmistr/Remip/refs/heads/main/screenshots/logo_512x512.png" alt="RemIP Logo" width="64" align="center">
  RemIP — Remote IP Control
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

[Русский](#русский) &nbsp;&nbsp;|&nbsp;&nbsp; [English](#english)

</div>

---

<a name="русский"></a>
## 🇷🇺 РУССКИЙ

---

### 📋 ОГЛАВЛЕНИЕ

1. [Общее описание](#общее-описание)
2. [Быстрый старт](#быстрый-старт)
3. [Системные требования](#системные-требования)
4. [Главное меню](#главное-меню)
5. [Режим «Управление ПК»](#режим-управление-пк)
   - [IP и учётные данные](#ip-и-учётные-данные)
   - [Управление питанием](#управление-питанием)
   - [Агент Remip](#агент-remip)
   - [Скриншоты и стриминг](#скриншоты-и-стриминг)
   - [Терминал PowerShell](#терминал-powershell)
   - [Удалённое управление (Phantom Input)](#удалённое-управление-phantom-input)
   - [Контекстный помощник](#контекстный-помощник)
   - [Сообщения](#сообщения)
   - [Инструменты](#инструменты)
6. [Режим «Настройка ПК»](#режим-настройка-пк)
   - [Экспресс-настройка](#экспресс-настройка)
   - [Расширенная настройка](#расширенная-настройка)
   - [Локальный агент](#локальный-агент)
   - [Диагностика и сервис](#диагностика-и-сервис)
7. [Режим «Карта сети»](#режим-карта-сети)
   - [Сканирование](#сканирование)
   - [Таблица устройств](#таблица-устройств)
   - [Контекстное меню](#контекстное-меню)
   - [Групповые действия](#групповые-действия)
   - [Фоновый мониторинг](#фоновый-мониторинг)
8. [Окно настроек](#окно-настроек)
9. [Платформа Умного Агента](#платформа-умного-агента)
   - [Архитектура](#архитектура)
   - [Протокол управления](#протокол-управления)
   - [Автономные подсистемы](#автономные-подсистемы)
   - [Watchdog и самовосстановление](#watchdog-и-самовосстановление)
10. [Phantom Input — протокол и реализация](#phantom-input--протокол-и-реализация)
11. [Автообновление](#автообновление)
12. [Обратная связь](#обратная-связь)
13. [Лицензия и контакты](#лицензия-и-контакты)
---

### ОБЩЕЕ ОПИСАНИЕ

**RemIP** — портативный инструмент для удалённого управления компьютерами в локальной сети. Программа не требует установки — достаточно запустить EXE-файл от имени администратора. Весь функционал доступен «из коробки», без установки дополнительных библиотек, драйверов или виртуальных устройств.

**Три режима работы:**
- **Управление ПК** — удалённое управление компьютерами с настроенным WinRM
- **Настройка ПК** — подготовка текущего компьютера к приёму удалённых команд
- **Карта сети** — сканирование локальной сети с групповыми действиями

**Платформа Умного Агента** — легковесный PowerShell-сервер, доставляемый на удалённый ПК в один клик. Обеспечивает скриншоты, стриминг экрана, терминал, удалённое управление, заморозку процессов и многое другое.

---

### БЫСТРЫЙ СТАРТ

1. **Запустите RemIP** от имени администратора
2. **Управляющий ПК:** перейдите в «Настройка ПК» → нажмите «Быстрая настройка»
3. **Целевой ПК:** повторите шаг 2 на удалённом компьютере
4. **Сохраните учётные данные:** в «Управление ПК» введите IP, нажмите «ВВЕСТИ И СОХРАНИТЬ»
5. **Установите агент:** нажмите на кнопку «АГЕНТ» → «Установить»
6. **Готово!** Теперь доступны скриншоты, терминал, стриминг и управление

---

### СИСТЕМНЫЕ ТРЕБОВАНИЯ

| Компонент | Минимальные | Рекомендуемые |
|-----------|------------|---------------|
| **ОС** | Windows 10 | Windows 11 24H2 |
| **Серверные ОС** | Windows Server 2019 | Windows Server 2022 |
| **Права** | Администратор | Администратор |
| **PowerShell** | 5.1 | 5.1+ |
| **.NET Framework** | 4.8 | 4.8+ |
| **GPU (для стрима)** | DirectX 11 | NVIDIA GTX 10xx+ / AMD RX 5xx+ |
| **Сеть** | 10 Мбит/с | 100 Мбит/с |

---

### ГЛАВНОЕ МЕНЮ

При запуске программы открывается главное меню с тремя кнопками:

- **🖥️ Управление ПК** — удалённое управление компьютером по IP
- **🛠️ Настройка ПК** — подготовка текущего ПК к приёму команд
- **🌐 Карта сети** — сканирование локальной сети

В верхней панели отображается ваш IP-адрес. Кнопки:
- **?** — окно «О программе»
- **⚙️** — настройки
- **✕** — выход

Смена языка и темы доступна в настройках (шестерёнка) и применяется мгновенно.

---

### РЕЖИМ «УПРАВЛЕНИЕ ПК»

#### IP и учётные данные

**Поле ввода IP** — введите IPv4-адрес удалённого компьютера. Поле автоматически нормализует адрес (убирает ведущие нули в октетах).

**Кнопка статуса** — проверяет доступность ПК по ping и запускает проверку агента:
- ▶ Серый — адрес введён, проверка не выполнялась
- ⏳ Жёлтый — идёт проверка
- ✓ Зелёный — ПК онлайн
- ✗ Красный — ПК офлайн

**Фоновый мониторинг** — при вводе IP автоматически запускается проверка статуса. Пока вы работаете с этим IP, программа проверяет его доступность каждые 10 секунд (только ping, без лишних сообщений).

**Выпадающий список IP** — все сохранённые адреса с именами. Зелёная галочка ✓ означает, что учётные данные были проверены и успешно работают. ПКМ по адресу открывает контекстное меню для удаления записи.

**ВВЕСТИ И СОХРАНИТЬ** — открывает диалог ввода логина и пароля. Программа проверяет учётные данные **до сохранения**:
- Проверяет доступность ПК (ping)
- Проверяет порт 5985 (WinRM)
- Создаёт временный Clixml и выполняет тестовую команду
- При успехе ставит ✓ в списке IP
- При ошибке показывает причину и предлагает сохранить без проверки
- Поддерживает **пустые пароли** (создаёт специальный Clixml с пустым SecureString)

**ОЧИСТИТЬ СПИСОК IP** — удаляет все сохранённые учётные данные, Clixml-файлы и очищает TrustedHosts.

#### Управление питанием

Все команды выполняются через WinRM на удалённом ПК.

**ВЫКЛЮЧИТЬ ▼** — выпадающее меню:
- **Сейчас** — мгновенное выключение (`shutdown /s /f /t 0`)
- **С таймером** — запрос времени в секундах, отправка `shutdown /s /f /t N`
- **С текстом** — таймер + текстовое сообщение (до 460 символов), которое показывается пользователю перед выключением
- **С голосом** — таймер + текст (до 512 символов), озвучивается через SpeechSynthesizer, затем выключение

**ПЕРЕЗАГРУЗИТЬ ▼** — выпадающее меню:
- **Сейчас** — мгновенная перезагрузка (`shutdown /r /f /t 0`)
- **С таймером** — перезагрузка через N секунд
- **С голосом** — озвучка + перезагрузка

**ОТМЕНИТЬ** — выполняет `shutdown /a` на удалённом ПК. Если использовался защищённый режим — останавливает локальную проверку выключения.

**Режим «Анти-отмена»** (переключатель в верхней панели):
- **Выключен** — обычная команда shutdown, пользователь может отменить
- **Включен** — после отправки команды программа ждёт (задержка настраивается) и проверяет статус ПК. Если не выключился — отправляет команду принудительно повторно. Использует ShutdownChecker — фоновый поток, который пингует ПК до истечения таймаута.

#### Агент Remip

Центральный элемент управления. Кнопка «АГЕНТ» показывает текущее состояние цветом:

| Цвет | Состояние | ПКМ |
|------|-----------|-----|
| ⚫ Серый | Статус не проверен | Нажмите для проверки |
| 🔴 Красный | Агент не установлен / не запущен | Меню: Установить, Тест, Логи, Восстановить |
| 🟢 Зелёный | Агент установлен и работает | Меню: Удалить, Тест, Логи, Обновить, Перезагрузить |

**Пункты зелёного меню:**
- **Удалить** — полная очистка: остановка процессов на порту 8080, удаление задачи планировщика, очистка папки `%APPDATA%\Remip\Agent`, удаление правила брандмауэра
- **Тест агента** — 13-шаговая диагностика: ping → порт 8080 → проверка файла агента → права доступа → брандмауэр → лог-файл → автозагрузка (реестр + задача) → версия → сессия → Shell → Stream → Phantom. При отсутствии токена предлагает добавить его через диалог
- **Логи** — получает файл `agent.log` с удалённого ПК через агента, при недоступности — fallback на WinRM. Отображает в диалоге LogViewerDialog
- **Обновить** — проверяет версию агента. Если устарела — переустанавливает. При выключенном WinRM включает его через самого агента командой `ENABLE_WINRM`
- **Перезагрузить** — останавливает процессы агента и запускает заново без переустановки файлов

**Пункты красного меню:**
- **Установить** — 11 шагов с индикацией прогресса:
  1. Очистка (служба, задача, процессы) — 3 подшага
  2. Создание файлов с проверкой синтаксиса PowerShell
  3. Распаковка инструментов (RemipCE.dll)
  4. Разблокировка файла (Unblock-File)
  5. Запись PSK-токена
  6. Сброс счётчиков производительности
  7. Инициализация счётчиков
  8. Брандмауэр + запуск через Scheduled Task
  9. Ожидание запуска (6 секунд)
  10. Проверка порта 8080
  11. Синхронизация статистики и очистка кэша CPU
- **Тест** — та же диагностика, что и в зелёном меню
- **Логи** — получение логов через WinRM (агент не запущен)
- **Восстановить** — появляется только если файл `agent.ps1` существует на удалённом ПК. Запускает агента заново

#### Скриншоты и стриминг

**📸 СКРИНШОТ** — делает снимок экрана удалённого ПК через агента. Поддерживает PNG (без потерь) и JPEG (сжатие). Формат настраивается в настройках.

**Просмотрщик скриншотов (ScreenshotViewer):**
- **Зум:** колёсико мыши (25%-500% для статики, 25%-200% при LIVE)
- **Панорамирование:** зажать левую кнопку и тянуть
- **Fit-to-Screen:** автоматически при открытии, двойной клик для сброса
- **Кнопка 100%:** сброс зума к Fit-to-Screen
- **Сохранить:** выбор пути и формата (PNG/JPEG), по умолчанию на рабочий стол
- **LIVE-режим:** переключатель запускает непрерывный стрим экрана
- **🎮 Управление:** запускает полноэкранный режим с Phantom Input

**Полноэкранный режим:**
- Анимация разворачивания из текущего окна на весь экран
- Панель с FPS и трафиком в реальном времени
- **Горячие клавиши:**
  - `Esc` — выход
  - `F` или `0` — Fit-to-Screen
  - `Пробел` — 100% зум
  - `+/-` — зум
  - `F12` — выход из Phantom Input
  - `F1` — свернуть сеанс (стрим продолжается в фоне)
  - `Pause` — переключение Game Mode
- **Сворачивание (F1):** диалог скрывается, главное окно сворачивается. Стрим и управление продолжают работать. Клик по иконке Remip на панели задач восстанавливает сеанс

**Аппаратный H.264 стриминг:**
- **Захват:** DXGI Desktop Duplication (прямой доступ к видеопамяти)
- **Кодирование:** аппаратное через Media Foundation (NVENC/QuickSync/AMF)
- **Декодирование:** аппаратное через NVDEC/QuickSync + D3D11 Video API
- **Автоматический GDI-fallback** при недоступности DXGI
- **Система «Светофор»** — адаптивное управление качеством:
  - 🟢 Зелёный — сеть свободна, повышение качества и битрейта
  - 🟡 Жёлтый — стабилизация параметров
  - 🔴 Красный — снижение битрейта, качества и FPS
- **Fallback на MJPEG:** при невозможности H.264 стрима автоматически переключается на MJPEG (Временно отключено)

#### Терминал PowerShell

Интерактивный терминал с потоковым выводом. Запускается кнопкой «ТЕРМИНАЛ» в группе агента.

**Архитектура:** агент запускает процесс PowerShell с перенаправленными потоками, вывод передаётся через выделенный порт 8081.

**Возможности:**
- **Автодополнение** — более 2000 команд PowerShell и их параметров. Две фазы: ввод команды → список подходящих; после пробела → список параметров.
- **Валидатор многострочного ввода** — автоматически преобразует многострочные скрипты в однострочный формат: сжимает here-strings, вырезает комментарии, заменяет переносы строк на `;`
- **Умный декодер кодировок** — автоопределение cp1251/cp866/UTF-8 по наличию псевдографики и подсчёту кириллических символов
- **История команд** — ↑↓ для навигации
- **Анимация загрузки** — индикатор выполнения команды (│╱─╲)
- **Масштабирование** — Ctrl+колесо
- **Расширяемое поле ввода** — до 5 строк, Shift+Enter для переноса
- **Таймаут ожидания** — если команда зависла, через 8 секунд возвращается приглашение

#### Удалённое управление (Phantom Input)

Полноценное управление мышью и клавиатурой удалённого ПК через собственный бинарный протокол. Не требует RDP, драйверов или виртуальных устройств.

**Запуск:** кнопка «🎮 Управление» в просмотрщике скриншотов → запускает H.264 стрим + Phantom Input одновременно.

**Два режима:**
- **🔵 Прямой (Direct):** полный захват мыши и клавиатуры. Курсор видим, все действия передаются на целевой ПК. При выходе (Esc/F12) управление возвращается локальной машине
- **🟢 Фантом (Hidden):** скрытый режим. Вы можете двигать курсор — это не мешает пользователю на целевом ПК. Активные действия (клики, ввод) применяются моментально

**Протокол v2.0 (бинарный, 19 байт приветствие + пакеты команд):**
- Абсолютное позиционирование мыши (0x01, 8 байт)
- Относительное для игр (0x0E, 4 байта) с настраиваемой чувствительностью
- Дельта-кодирование (0x0D, 2 байта) — экономия трафика в 4 раза
- Мультимонитор (0x0F) — абсолютные координаты по виртуальному столу
- Все кнопки мыши + колесо (0x02-0x04)
- Атомарные клики (0x0C) — move+down+up в одном пакете
- Virtual-Key коды (0x05-0x06)
- Скан-коды (0x0B) для DirectInput-совместимости
- Unicode-ввод (0x07)
- Пакетная отправка клавиш (0x0A, до 16 за раз)
- Keep-alive пинг (0x09) с измерением RTT
- Статистика сервера (0x10)

**Game Mode (Pause):**
- Рецентрирование курсора в центр экрана для бесконечного вращения
- Относительные перемещения мыши
- Настраиваемая чувствительность (0.1-2.0)

**Безопасность:**
- Автоотключение UAC на время сеанса
- Автовосстановление UAC при выходе, обрыве связи или падении сервера
- Сброс всех зажатых клавиш при отключении

**Синхронизация буфера обмена:**
- При входе в управление: локальный буфер → целевой ПК
- При сворачивании (F1): целевой ПК → локальный буфер
- При разворачивании: локальный → целевой

#### Контекстный помощник

Независимое окно мониторинга удалённого ПК. Открывается кнопкой «КОНТЕКСТ».

**Карточка «Сейчас»:**
- Активное окно (заголовок + процесс)
- Статус пользователя (активен/отошёл) с временем простоя
- Автоопределение иконки приложения по имени процесса (🕹️ игры, 🌐 браузеры, 📝 офис, 💬 мессенджеры, 🎨 медиа, ⚙️ система)

**Карточка «Ресурсы»:**
- **CPU:** прогресс-бар с цветовой индикацией (зелёный→жёлтый→красный)
- **RAM:** использовано/всего GB
- **Диск C:** свободное место
- **Топ-12 процессов** по потреблению RAM с контекстным меню (ПКМ):
  - ❄️ Заморозить / 🧊 Разморозить
  - 🛑 Завершить процесс
  - Подсветка строки при наведении
  - Анимация затухания при завершении
  - Оранжевая подсветка замороженных процессов

**Заморозка процессов:**
- Приостановка всех потоков процесса на уровне Windows API
- Сворачивание видимых окон перед заморозкой
- Сохранение состояния в `frozen.json` (PID + handles окон)
- Автономный watchdog: перезаморозка при перезапуске процесса
- Защита от множественных заморозок
- Блокировка разморозки в течение 15 секунд после заморозки
- Восстановление окон при разморозке

**Лента событий (Timeline):**
- История действий на удалённом ПК: запуски агента, подключения администраторов, скриншоты, заморозки, смена окон
- Автопрокрутка при нахождении внизу
- Сохранение позиции скролла при обновлении

**Экспорт отчёта:**
- **HTML с вкладками:** Обзор, Ресурсы, Статистика, Лента, Система
- **SVG-графики** CPU и RAM за 24 часа (минутные точки)
- **Таблица статистики** с цветовыми полосами
- **Системная информация:** OS, CPU, RAM, диски, сетевые адаптеры
- Сохранение в текстовый файл (только лента)

**Дополнительно:**
- Закрепление окна поверх всех (📌)
- Настраиваемый интервал обновления (3-30 секунд)
- Ручное обновление (↻)
- Перетаскивание окна за заголовок

#### Сообщения

- **ТЕКСТОВОЕ** — отправка через `msg *` (до 240 символов). Поддерживает русский и английский. Работает даже без агента
- **ГОЛОСОВОЕ** — озвучка через System.Speech.SpeechSynthesizer (до 512 символов). Требуется WinRM

#### Инструменты

- **WinRM (ВКЛ/ВЫКЛ)** — управляет службой WinRM на вашем ПК. При включении синхронизирует TrustedHosts со всеми сохранёнными IP
- **ДИАГНОСТИКА** — 11 этапов полной проверки подключения к удалённому ПК
- **ОЧИСТИТЬ** — очищает окно вывода

---

### РЕЖИМ «НАСТРОЙКА ПК»

Готовит текущий компьютер к приёму удалённых команд. Все изменения применяются локально.

#### Экспресс-настройка

**⚡ БЫСТРАЯ НАСТРОЙКА** — 7 шагов в фоновом потоке (не блокирует UI):
1. Удаление блокирующих правил для порта 5985
2. Открытие порта 5985 для всех профилей
3. Проверка порта
4. Настройка службы WinRM (автозапуск + запуск)
5. Установка TrustedHosts
6. Включение Remote UAC + пустого пароля
7. Настройка SMB-клиента

**💡 УМНАЯ НАСТРОЙКА** — диагностика системы → диалог выбора исправлений → применение только того, что нужно:
- Автоматическая настройка SMB-клиента при открытии порта 445
- Автовозврат SMB в безопасное состояние при закрытии порта 445
- Принудительная перезагрузка при необходимости

#### Расширенная настройка

Цветные переключатели с автоматической проверкой статуса при входе:

**🌐 ПОРТЫ (445, 139, 5985):**
- 🟩 — правило включено и активно
- 🟥 — правило отключено/отсутствует
- Каждый порт управляется независимо
- При открытии 445: автонастройка SMB-клиента + службы Server
- При открытии 5985: автозапуск WinRM + настройка TrustedHosts
- При закрытии: автоостановка связанных служб, создание блокирующего правила

**🛡️ ПРОФИЛИ (🏠 Частная, 🌍 Общественная, 🏢 Доменная):**
- Показывают текущий активный профиль
- При переключении обновляют правила для всех открытых портов

**🖥️ СЛУЖБЫ (Server, RemoteRegistry, WinRM):**
- Включение/отключение с автонастройкой автозапуска
- При включении WinRM: автонастройка TrustedHosts для IP из поля ввода

**🔐 РАЗРЕШЕНИЯ (Remote UAC, DCOM, RDP, Пустой пароль):**
- Независимое управление каждым параметром
- Кнопка «Пустой пароль» показывает текстовое описание состояния

#### Локальный агент

Кнопка «АГЕНТ» в группе «Сервис» управляет агентом на локальном ПК. 8 шагов установки (сокращённая версия удалённой):
1. Очистка старых процессов
2. Создание файлов агента
3. Распаковка RemipCE.zip
4. Разблокировка
5. Создание файла токенов
6. Сброс счётчиков
7. Брандмауэр + запуск
8. Ожидание и проверка

#### Диагностика и сервис

- **📊 ДИАГНОСТИКА** — многоэтапная проверка всех компонентов
- **🗑️ СБРОС** — полный откат всех настроек с принудительной блокировкой портов и предложением перезагрузки

---

### РЕЖИМ «КАРТА СЕТИ»

Сканирует локальную сеть и отображает все устройства.

#### Сканирование

- **⚡ БЫСТРОЕ** — 7 портов (135, 139, 445, 5985, 3389, 80, 443), ~30 секунд
- **🔍 ПОЛНОЕ** — 17 портов + определение ОС по TTL и hostname, 1-5 минут
- **🔄 ОБНОВИТЬ** — перепроверка ping/WinRM/creds/агента для найденных устройств
- **⏹ СТОП** — остановка с принудительной очисткой через 3 секунды

#### Таблица устройств

Два режима: компактный (▶) и расширенный (◀) с анимацией переключения.

**Столбцы расширенной таблицы:**
| Столбец | Значения |
|---------|----------|
| ☑ | Чекбокс выбора (только для 🟢) |
| Онлайн | ✅ / ❌ / ⏳ (обновляется фоном) |
| Статус | 🟢 Готов / 🟡 Нет данных / 🔵 Нужен WinRM / 🔴 Не поддерживается / ⚫ Офлайн |
| IP | IPv4-адрес |
| Имя | Hostname или тип ОС |
| WinRM | ✅ / ❌ |
| Данные | ✅ / ❌ |
| Агент | ✅ Проверен / ⚠️ Порт открыт / ❌ Не отвечает / — Не проверен |

**Сортировка:** клик по заголовку столбца (кроме чекбокса и агента).

#### Контекстное меню

ПКМ по строке таблицы:
- **Использовать IP** — переключение в «Управление ПК» с этим IP
- **Сохранить учётные данные** — открыть диалог сохранения
- **Диагностика** — запуск полной диагностики
- **Проверить агента** — проверка порта 8080 + PSK-токен
- **Контекстный помощник** — открыть окно мониторинга (только при активном агенте)
- **Wake-on-LAN** — отправка Magic Packet (если известен MAC)
- **Подробнее ▼** — IP, hostname, MAC, ОС, порты, WinRM, учётные данные

#### Групповые действия

Панель появляется при выборе устройств чекбоксами (только 🟢).

| Кнопка | Описание |
|--------|----------|
| **🔴 ВЫКЛЮЧИТЬ** | Последовательное выключение с задержкой 0.5с |
| **💬 СООБЩЕНИЕ** | Один текст на все выбранные ПК |
| **🎤 ГОЛОС** | Синхронизированная озвучка с компенсацией пинга. Два режима: WinRM (прямой) и Agent (быстрый). Параллельная отправка с задержкой внутри скрипта |
| **🤖 УСТАНОВИТЬ АГЕНТЫ** | Массовая параллельная установка (до 10 ПК одновременно). Проверка версии, пропуск актуальных, авто-WinRM |

#### Фоновый мониторинг

Каждые 30 секунд проверяет онлайн-статус всех устройств. Обновляет иконки ✅/❌ и цветной статус. Работает только когда вкладка активна.

---

### ОКНО НАСТРОЕК

Вызывается кнопкой ⚙️ в верхней панели.

| Группа | Настройка | Значения | Описание |
|--------|-----------|----------|----------|
| **Выключение** | Задержка проверки | 15-99 сек | Время до проверки статуса ПК в режиме «Анти-отмена» |
| **Голос** | Режим отправки | 🔗 WinRM / 🤖 Агент | Способ отправки голоса при групповой рассылке |
| | Задержка синхронизации | 0.00-5.00 сек | Базовая пауза между ПК |
| | Компенсация пинга | ⚫ Выкл / 🟢 Авто / 🔵 Макс | Автоподстройка под сетевую задержку |
| **Общие** | Автодиагностика | Вкл/Выкл | Запуск проверки при входе в «Настройку ПК» |
| | Автообновление | Вкл/Выкл | Проверка GitHub при запуске |
| | Язык | Русский / English | Мгновенное применение |
| | Тема | 🌙 Тёмная / ☀️ Светлая | Перезагрузка UI |
| **Скриншот** | Формат | PNG / JPEG | Без потерь или сжатие |
| **Управление** | Режим фантома | 🔵 Прямой / 🟢 Скрытый | Режим Phantom Input по умолчанию |
| | Чувствительность | 0.1-2.0 | Множитель мыши в Game Mode |
| **Стрим** | Адаптивный битрейт | 🔵 Вкл / ⚫ Выкл | Система «Светофор» |
| | Качество | 10-100 | Только при выключенном адаптивном |
| | Макс. FPS | 10-60 | Целевая частота кадров |
| **Логи** | Режим | ⚫ Выкл / 🟢 INFO / 🔵 DEBUG | Уровень детализации |
| | Хранение | Навсегда / 1 / 7 / 30 дней | Автоудаление старых логов |
| | 📂 ЛОГИ | Кнопка | Открыть папку `%APPDATA%\RemIP\Logs` |
| **Агент** | Статистика | Вкл/Выкл | Сбор CPU/RAM/диска раз в минуту |

---

### ПЛАТФОРМА УМНОГО АГЕНТА

#### Архитектура

Агент — это единый PowerShell-скрипт (`agent.ps1`), который работает как TCP-сервер на порту 8080. При запуске он:
1. Проверяет, не запущен ли уже (глобальный мьютекс)
2. Определяет сессию — если Session 0, перезапускается в пользовательской сессии
3. Настраивает брандмауэр (правило "Remip Agent" на порт 8080)
4. Создаёт задачу в планировщике для автозапуска при входе пользователя
5. Компилирует встроенные C# типы (ProcessFreezer, NativeStreamServer, PhantomInputServer)
6. Запускает основной цикл обработки подключений

#### Протокол управления

Агент принимает текстовые команды по TCP через `TOKEN:<sha256>\n`. После аутентификации доступны команды:

| Команда | Ответ | Описание |
|---------|-------|----------|
| `VERSION` | версия | Текущая версия агента |
| `PING` | `PONG` | Проверка соединения |
| `SESSION` | ID сессии | Номер пользовательской сессии |
| `SCREENSHOT` | base64 JPEG | Скриншот экрана |
| `SCREENSHOT_PNG` | base64 PNG | Скриншот в PNG |
| `WHATSNOW` | base64 JSON | Данные контекстного помощника |
| `TIMELINE` | base64 JSON | Лента событий |
| `LOG` | base64 текст | Лог-файл агента |
| `SPEAK:<base64>` | `SPEAK_OK` | Озвучить текст |
| `FREEZE:<имя>` | `FREEZE_OK` | Заморозить процесс |
| `UNFREEZE:<имя>` | `UNFREEZE_OK` | Разморозить процесс |
| `CHECK_FROZEN:<имя>` | `FROZEN:PID` | Проверить статус заморозки |
| `SYNC` | base64 JSON | Синхронизация состояния заморозки |
| `CLEAR_CACHE` | `CACHE_CLEARED` | Очистить кэш CPU |
| `ENABLE_WINRM` | `WINRM_ENABLED` | Включить WinRM на хосте |
| `SHELL:START` | `SHELL:STARTED:8081` | Запустить PowerShell-терминал |
| `SHELL:INPUT:<b64>` | `SHELL:INPUT_OK` | Отправить команду в терминал |
| `SHELL:STOP` | `SHELL:STOPPED` | Остановить терминал |
| `NATIVE_STREAM:START:fps:q:det` | `STREAM_STARTED:...` | Запустить H.264 стрим |
| `NATIVE_STREAM:STOP` | `STREAM_STOPPED` | Остановить стрим |
| `NATIVE_STREAM:QUALITY:N` | `QUALITY_OK` | Изменить качество |
| `NATIVE_STREAM:CONFIG:d:q:f` | `STREAM_CONFIG_OK` | Полная реконфигурация |
| `PHANTOM:START` | `PHANTOM_STARTED:...` | Запустить Phantom Input |
| `PHANTOM:STOP` | `PHANTOM_STOPPED` | Остановить Phantom Input |
| `STATS:ON/OFF/CLEAR/GET` | ответ | Управление статистикой |
| `HEALTH` | JSON | Состояние всех подсистем |
| `METRICS` | JSON | Метрики стрима |
| `SIGNAL:GREEN/YELLOW/RED` | `SIGNAL_OK` | Сигнал светофора |
| `CLIPBOARD:SET:<b64>` | `CLIPBOARD_OK` | Установить буфер обмена |
| `CLIPBOARD:GET` | base64 текст | Получить буфер обмена |

#### Автономные подсистемы

Агент работает автономно и не требует постоянного подключения Remip:

- **Watchdog (агент):** проверяет PID-файл, перезапускает упавший процесс
- **Watchdog (заморозка):** каждые 5 секунд проверяет замороженные процессы, перезамораживает при перезапуске с новым PID
- **Статистика:** раз в минуту собирает CPU/RAM/диск, хранит до 1440 записей (24 часа)
- **Файл конфигурации:** `stats_config.json` — управление сбором статистики
- **Лог-файл:** `agent.log` с автоочисткой при превышении 1 МБ

---

### PHANTOM INPUT — ПРОТОКОЛ И РЕАЛИЗАЦИЯ

Собственный бинарный протокол для минимальных задержек.

**Сервер (PhantomInputServer):**
- Порт 8083, C# класс, скомпилированный через `Add-Type`
- Принимает подключения, обрабатывает бинарные пакеты
- Использует Win32 API `SendInput` для эмуляции ввода
- В режиме Direct: `SetCursorPos` для перемещения системного курсора
- В режиме Hidden: только `SendInput` без визуального отклика
- При запуске временно отключает UAC
- При остановке или обрыве соединения восстанавливает UAC
- Keep-alive: пинг каждые 5 секунд, таймаут отключения 15 секунд

**Клиент (PhantomInputSender):**
- TCP-сокет с TCP_NODELAY (отключение буферизации)
- Троттлинг мыши: ~60 FPS в обычном режиме, ~120 FPS в игровом
- Дельта-кодирование: экономия 6 байт на каждом перемещении (8→2)
- Атомарные клики: move+down+up в одном TCP-пакете
- Пакетная отправка клавиш: до 16 клавиш в одном пакете

**Статистика сервера (GetStats):**
- Всего отправлено событий ввода
- Всего передано байт
- Экономия от дельта-кодирования
- Событий/сек, байт/сек
- Текущий режим, активных клавиш

---

### АВТООБНОВЛЕНИЕ

- Проверка GitHub при запуске (настраивается)
- Значок 🔔 в верхней панели при доступности новой версии
- Скачивание в фоне с прогрессом
- Кнопка «Перезапустить сейчас» для быстрого обновления
- Проверка цифровой подписи скачанного файла

---

### ОБРАТНАЯ СВЯЗЬ


В окне «О программе» (кнопка `?`) нажмите **📤 Обратная связь**. Опишите проблему, укажите email (опционально). Программа автоматически прикрепит системную информацию и последние строки лога. Отправка через защищённый канал.

---

### ЛИЦЕНЗИЯ И КОНТАКТЫ

MIT License. По всем вопросам: **dmistr9999@gmail.com**

---

<a name="english"></a>
## 🇬🇧 ENGLISH

[![License](https://img.shields.io/badge/license-MIT-red.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-blue.svg)]()
[![Python](https://img.shields.io/badge/Python-3.14%2B-yellow.svg)]()
[![PyQt](https://img.shields.io/badge/PyQt-6.0%2B-brightgreen.svg)]()
[![Downloads](https://img.shields.io/github/downloads/dmistr/Remip/total.svg)](https://github.com/dmistr/Remip/releases)
[![VirusTotal](https://img.shields.io/badge/VirusTotal-2%2F69-brightgreen?logo=virustotal&logoColor=white)](https://www.virustotal.com/gui/file/4ba0556fe18100f3959f0147e3145122331834f04024d36387a7597236bc9672)

<h1 align="center">
  <img src="https://raw.githubusercontent.com/dmistr/Remip/refs/heads/main/screenshots/logo_512x512.png" alt="RemIP Logo" width="64" align="center">
  RemIP — Remote IP Control
</h1>

<p align="center">
  <b>Universal remote PC management tool over IP</b><br>
  <i>Универсальный инструмент удалённого управления ПК по IP</i>
</p>

<p align="center">
  👤 <b>Author:</b> dmistr &nbsp;&nbsp;|&nbsp;&nbsp; 📧 <b>Email:</b> dmistr9999@gmail.com &nbsp;&nbsp;|&nbsp;&nbsp; 🐙 <b>GitHub:</b> <a href="https://github.com/dmistr/Remip">dmistr/Remip</a>
</p>

---

### 📋 TABLE OF CONTENTS

1. [Overview](#overview)
2. [Quick Start](#quick-start)
3. [System Requirements](#system-requirements)
4. [Main Menu](#main-menu)
5. [PC Control Mode](#pc-control-mode)
   - [IP & Credentials](#ip--credentials)
   - [Power Management](#power-management)
   - [Remip Agent](#remip-agent)
   - [Screenshots & Streaming](#screenshots--streaming)
   - [PowerShell Terminal](#powershell-terminal)
   - [Remote Control (Phantom Input)](#remote-control-phantom-input)
   - [Context Assistant](#context-assistant)
   - [Messages](#messages)
   - [Tools](#tools)
6. [PC Setup Mode](#pc-setup-mode)
   - [Express Setup](#express-setup)
   - [Advanced Setup](#advanced-setup)
   - [Local Agent](#local-agent)
   - [Diagnostics & Service](#diagnostics--service)
7. [Network Map Mode](#network-map-mode)
   - [Scanning](#scanning)
   - [Device Table](#device-table)
   - [Context Menu](#context-menu)
   - [Group Actions](#group-actions)
   - [Background Monitor](#background-monitor)
8. [Settings Window](#settings-window)
9. [Smart Agent Platform](#smart-agent-platform)
   - [Architecture](#architecture)
   - [Control Protocol](#control-protocol)
   - [Autonomous Subsystems](#autonomous-subsystems)
   - [Watchdog & Self-Healing](#watchdog--self-healing)
10. [Phantom Input — Protocol & Implementation](#phantom-input--protocol--implementation)
11. [Auto-Update](#auto-update)
12. [Feedback](#feedback)
13. [License & Contacts](#license--contacts)

---

### OVERVIEW

**RemIP** is a portable tool for remote computer management in local networks. No installation required — just run the EXE as Administrator. All functionality works out of the box without additional libraries, drivers, or virtual devices.

**Three operating modes:**
- **PC Control** — remote management of computers with WinRM configured
- **PC Setup** — prepare the current computer for receiving remote commands
- **Network Map** — scan the local network with group actions

**Smart Agent Platform** — a lightweight PowerShell server delivered to a remote PC in one click. Provides screenshots, screen streaming, terminal, remote control, process freezing, and more.

---

### QUICK START

1. **Run RemIP** as Administrator
2. **Controlling PC:** go to "PC Setup" → click "Fast Setup"
3. **Target PC:** repeat step 2 on the remote computer
4. **Save credentials:** in "PC Control" enter the IP, click "SAVE CREDENTIALS"
5. **Install the agent:** click the "AGENT" button → "Install"
6. **Done!** Screenshots, terminal, streaming, and control are now available

---

### SYSTEM REQUIREMENTS

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| **OS** | Windows 10 | Windows 11 24H2 |
| **Server OS** | Windows Server 2019 | Windows Server 2022 |
| **Privileges** | Administrator | Administrator |
| **PowerShell** | 5.1 | 5.1+ |
| **.NET Framework** | 4.8 | 4.8+ |
| **GPU (for streaming)** | DirectX 11 | NVIDIA GTX 10xx+ / AMD RX 5xx+ |
| **Network** | 10 Mbps | 100 Mbps |

---

### MAIN MENU

When the program starts, the main menu opens with three buttons:

- **🖥️ PC Control** — remote PC management by IP
- **🛠️ PC Setup** — prepare this PC to receive commands
- **🌐 Network Map** — scan the local network

The top panel shows your IP address. Buttons:
- **?** — About window
- **⚙️** — Settings
- **✕** — Exit

Language and theme can be changed in Settings (gear icon) and are applied instantly.

---

### PC CONTROL MODE

#### IP & Credentials

**IP Input Field** — enter the remote computer's IPv4 address. The field automatically normalizes the address (removes leading zeros in octets).

**Status Button** — checks PC availability via ping and starts agent check:
- ▶ Gray — address entered, check not performed
- ⏳ Yellow — checking
- ✓ Green — PC online
- ✗ Red — PC offline

**Background Monitoring** — when an IP is entered, status checking starts automatically. While you work with this IP, the program checks its availability every 10 seconds (ping only, no extra messages).

**IP Dropdown List** — all saved addresses with names. A green checkmark ✓ means the credentials have been verified and work. Right-click on an address opens a context menu to delete the entry.

**SAVE CREDENTIALS** — opens a login/password dialog. The program verifies credentials **before saving**:
- Checks PC availability (ping)
- Checks port 5985 (WinRM)
- Creates a temporary Clixml and runs a test command
- On success, marks ✓ in the IP list
- On error, shows the reason and offers to save without verification
- Supports **blank passwords** (creates a special Clixml with an empty SecureString)

**CLEAR IP LIST** — removes all saved credentials, Clixml files, and clears TrustedHosts.

#### Power Management

All commands are executed via WinRM on the remote PC.

**SHUTDOWN ▼** — dropdown menu:
- **Now** — instant shutdown (`shutdown /s /f /t 0`)
- **Timer** — prompt for seconds, sends `shutdown /s /f /t N`
- **With Text** — timer + text message (up to 460 chars) shown to the user before shutdown
- **With Voice** — timer + text (up to 512 chars), spoken via SpeechSynthesizer, then shutdown

**REBOOT ▼** — dropdown menu:
- **Now** — instant reboot (`shutdown /r /f /t 0`)
- **Timer** — reboot after N seconds
- **With Voice** — speech + reboot

**CANCEL** — runs `shutdown /a` on the remote PC. If protected mode was used, stops the local shutdown check.

**Anti-Cancel Mode** (toggle in the top panel):
- **Off** — normal shutdown command, user can cancel
- **On** — after sending the command, the program waits (configurable delay) and checks PC status. If not shut down, retries the command. Uses ShutdownChecker — a background thread that pings the PC until the timeout expires.

#### Remip Agent

The central control element. The "AGENT" button shows current state by color:

| Color | State | Right-Click |
|-------|-------|-------------|
| ⚫ Gray | Status unchecked | Click to check |
| 🔴 Red | Agent not installed / not running | Menu: Install, Test, Logs, Recover |
| 🟢 Green | Agent installed and running | Menu: Remove, Test, Logs, Update, Restart |

**Green menu items:**
- **Remove** — full cleanup: stop processes on port 8080, remove scheduled task, delete `%APPDATA%\Remip\Agent` folder, remove firewall rule
- **Test Agent** — 13-step diagnostics: ping → port 8080 → agent file check → permissions → firewall → log file → autostart (registry + task) → version → session → Shell → Stream → Phantom. If token is missing, offers to add it via dialog
- **Logs** — fetches `agent.log` from the remote PC via agent; if unavailable, falls back to WinRM. Displays in LogViewerDialog
- **Update** — checks agent version. If outdated, reinstalls. If WinRM is disabled, enables it via the agent using the `ENABLE_WINRM` command
- **Restart** — stops agent processes and restarts without reinstalling files

**Red menu items:**
- **Install** — 11 steps with progress indication:
  1. Cleanup (service, task, processes) — 3 sub-steps
  2. File creation with PowerShell syntax check
  3. Tool extraction (RemipCE.dll)
  4. File unblock (Unblock-File)
  5. PSK token write
  6. Performance counter reset
  7. Counter initialization
  8. Firewall + launch via Scheduled Task
  9. Startup wait (6 seconds)
  10. Port 8080 check
  11. Statistics sync and CPU cache clear
- **Test** — same diagnostics as green menu
- **Logs** — fetch logs via WinRM (agent not running)
- **Recover** — appears only if `agent.ps1` file exists on the remote PC. Restarts the agent

#### Screenshots & Streaming

**📸 SCREENSHOT** — captures the remote PC screen via the agent. Supports PNG (lossless) and JPEG (compressed). Format is set in Settings.

**Screenshot Viewer (ScreenshotViewer):**
- **Zoom:** mouse wheel (25%-500% for static, 25%-200% during LIVE)
- **Pan:** hold left button and drag
- **Fit-to-Screen:** automatic on open, double-click to reset
- **100% Button:** reset zoom to Fit-to-Screen
- **Save:** choose path and format (PNG/JPEG), defaults to Desktop
- **LIVE Mode:** toggle starts continuous screen streaming
- **🎮 Control:** launches fullscreen mode with Phantom Input

**Fullscreen Mode:**
- Expand animation from current window to full screen
- FPS and traffic panel in real time
- **Hotkeys:**
  - `Esc` — exit (with collapse animation)
  - `F` or `0` — Fit-to-Screen
  - `Space` — 100% zoom
  - `+/-` — zoom
  - `F12` — exit Phantom Input
  - `F1` — minimize session (stream continues in background)
  - `Pause` — toggle Game Mode
- **Minimize (F1):** dialog hides, main window minimizes. Stream and control continue working. Click the Remip icon on the taskbar to restore

**Hardware H.264 Streaming:**
- **Capture:** DXGI Desktop Duplication (direct video memory access)
- **Encoding:** hardware via Media Foundation (NVENC/QuickSync/AMF)
- **Decoding:** hardware via NVDEC/QuickSync + D3D11 Video API
- **Automatic GDI fallback** when DXGI is unavailable
- **"Traffic Light" System** — adaptive quality management:
  - 🟢 Green — network free, increasing quality and bitrate
  - 🟡 Yellow — parameter stabilization
  - 🔴 Red — reducing bitrate, quality, and FPS
- **Screenshot fallback:** when H.264 streaming is impossible, automatically switches to MJPEG (temporarily unavailable)

#### PowerShell Terminal

Interactive terminal with streaming output. Launched via the "TERMINAL" button in the agent group.

**Architecture:** the agent starts a PowerShell process with redirected streams; output is transmitted via dedicated port 8081.

**Features:**
- **Autocomplete** — 2000+ PowerShell commands and their parameters. Two phases: typing a command → list of matches; after space → parameter list.
- **Multiline Input Validator** — automatically converts multiline scripts to single-line format: compresses here-strings, removes comments, replaces line breaks with `;`
- **Smart Encoding Decoder** — auto-detection of cp1251/cp866/UTF-8 by box-drawing characters and Cyrillic character count
- **Command History** — ↑↓ for navigation
- **Loading Animation** — command execution indicator (│╱─╲)
- **Scaling** — Ctrl+wheel
- **Expandable Input Field** — up to 5 lines, Shift+Enter for newline
- **Loading Timeout** — if a command hangs, the prompt returns after 8 seconds

#### Remote Control (Phantom Input)

Full mouse and keyboard control of the remote PC via a custom binary protocol. No RDP, drivers, or virtual devices required.

**Launch:** "🎮 Control" button in screenshot viewer → starts H.264 stream + Phantom Input simultaneously.

**Two modes:**
- **🔵 Direct:** full mouse and keyboard capture. Cursor is visible, all actions are transmitted to the target PC. On exit (Esc/F12), control returns to the local machine
- **🟢 Phantom (Hidden):** hidden mode. You can move the cursor — it doesn't interfere with the user on the target PC. Active actions (clicks, typing) are applied instantly

**Protocol v2.0 (binary, 19-byte greeting + command packets):**
- Absolute mouse positioning (0x01, 8 bytes)
- Relative for games (0x0E, 4 bytes) with adjustable sensitivity
- Delta encoding (0x0D, 2 bytes) — 4x traffic savings
- Multi-monitor (0x0F) — absolute coordinates across virtual desktop
- All mouse buttons + wheel (0x02-0x04)
- Atomic clicks (0x0C) — move+down+up in one packet
- Virtual-Key codes (0x05-0x06)
- Scan codes (0x0B) for DirectInput compatibility
- Unicode input (0x07)
- Batch key sending (0x0A, up to 16 at once)
- Keep-alive ping (0x09) with RTT measurement
- Server statistics (0x10)

**Game Mode (Pause):**
- Cursor recentering to screen center for infinite rotation
- Relative mouse movements
- Adjustable sensitivity (0.1-2.0)

**Security:**
- Auto-disable UAC for the session duration
- Auto-restore UAC on exit, connection loss, or server crash
- Release all pressed keys on disconnect

**Clipboard Sync:**
- On control entry: local clipboard → target PC
- On minimize (F1): target PC → local clipboard
- On restore: local → target

#### Context Assistant

Independent remote PC monitoring window. Opens via the "CONTEXT" button.

**"Now" Card:**
- Active window (title + process)
- User status (active/away) with idle time
- Auto-detection of app icon by process name (🕹️ games, 🌐 browsers, 📝 office, 💬 messengers, 🎨 media, ⚙️ system)

**"Resources" Card:**
- **CPU:** progress bar with color indication (green→yellow→red)
- **RAM:** used/total GB
- **Disk C:** free space
- **Top 12 processes** by RAM usage with context menu (right-click):
  - ❄️ Freeze / 🧊 Unfreeze
  - 🛑 Kill process
  - Row highlight on hover
  - Fade-out animation on kill
  - Orange highlight for frozen processes

**Process Freezing:**
- Suspend all threads of a process at the Windows API level
- Minimize visible windows before freezing
- Save state to `frozen.json` (PID + window handles)
- Autonomous watchdog: re-freeze on process restart
- Multiple freeze protection
- Unfreeze block for 15 seconds after freezing
- Window restoration on unfreeze

**Timeline:**
- History of actions on the remote PC: agent starts, admin connections, screenshots, freezes, window changes
- Auto-scroll when at the bottom
- Scroll position preservation on update

**Report Export:**
- **HTML with tabs:** Overview, Resources, Statistics, Timeline, System
- **SVG charts** for CPU and RAM over 24 hours (minute data points)
- **Statistics table** with color bars
- **System info:** OS, CPU, RAM, disks, network adapters
- Save to text file (timeline only)

**Additional:**
- Pin window on top (📌)
- Adjustable refresh interval (3-30 seconds)
- Manual refresh (↻)
- Drag window by title bar

#### Messages

- **TEXT** — send via `msg *` (up to 240 chars). Supports Russian and English. Works even without the agent
- **VOICE** — text-to-speech via System.Speech.SpeechSynthesizer (up to 512 chars). Requires WinRM

#### Tools

- **WinRM (ON/OFF)** — manages the WinRM service on your PC. When enabled, syncs TrustedHosts with all saved IPs
- **DIAGNOSTICS** — 11-step full connection check to the remote PC
- **CLEAR** — clears the output window

---

### PC SETUP MODE

Prepares the current computer to receive remote commands. All changes are applied locally.

#### Express Setup

**⚡ FAST SETUP** — 7 steps in a background thread (non-blocking UI):
1. Remove blocking rules for port 5985
2. Open port 5985 for all profiles
3. Port check
4. Configure WinRM service (auto-start + start)
5. Set TrustedHosts
6. Enable Remote UAC + blank password
7. Configure SMB client

**💡 SMART SETUP** — system diagnostic → fix selection dialog → apply only what's needed:
- Automatic SMB client configuration when opening port 445
- Automatic SMB restoration to safe state when closing port 445
- Forced reboot when necessary

#### Advanced Setup

Color toggles with automatic status check on entry:

**🌐 PORTS (445, 139, 5985):**
- 🟩 — rule enabled and active
- 🟥 — rule disabled/absent
- Each port is managed independently
- Opening 445: auto-configure SMB client + Server service
- Opening 5985: auto-start WinRM + configure TrustedHosts
- Closing: auto-stop related services, create blocking rule

**🛡️ PROFILES (🏠 Private, 🌍 Public, 🏢 Domain):**
- Show current active profile
- On toggle, update rules for all open ports

**🖥️ SERVICES (Server, RemoteRegistry, WinRM):**
- Enable/disable with auto-startup configuration
- Enabling WinRM: auto-configure TrustedHosts for IP from input field

**🔐 PERMISSIONS (Remote UAC, DCOM, RDP, Blank Password):**
- Independent control of each parameter
- "Blank Password" button shows text description of state

#### Local Agent

The "AGENT" button in the "Service" group manages the agent on the local PC. 8 installation steps (shortened remote version):
1. Clean up old processes
2. Create agent files
3. Extract RemipCE.zip
4. Unblock file
5. Create token file
6. Reset performance counters
7. Firewall + launch
8. Wait and verify

#### Diagnostics & Service

- **📊 DIAGNOSTICS** — multi-stage check of all components
- **🗑️ RESET** — full rollback of all settings with forced port blocking and reboot offer

---

### NETWORK MAP MODE

Scans the local network and displays all devices.

#### Scanning

- **⚡ FAST** — 7 ports (135, 139, 445, 5985, 3389, 80, 443), ~30 seconds
- **🔍 FULL** — 17 ports + OS detection by TTL and hostname, 1-5 minutes
- **🔄 REFRESH** — re-check ping/WinRM/creds/agent for found devices
- **⏹ STOP** — stop with forced cleanup after 3 seconds

#### Device Table

Two modes: compact (▶) and expanded (◀) with switch animation.

**Expanded table columns:**
| Column | Values |
|--------|--------|
| ☑ | Selection checkbox (🟢 only) |
| Online | ✅ / ❌ / ⏳ (background updated) |
| Status | 🟢 Ready / 🟡 No creds / 🔵 Needs WinRM / 🔴 Not supported / ⚫ Offline |
| IP | IPv4 address |
| Name | Hostname or OS type |
| WinRM | ✅ / ❌ |
| Creds | ✅ / ❌ |
| Agent | ✅ Verified / ⚠️ Port open / ❌ Not responding / — Not checked |

**Sorting:** click column header (except checkbox and agent).

#### Context Menu

Right-click on a table row:
- **Use IP** — switch to "PC Control" with this IP
- **Save Credentials** — open save dialog
- **Diagnostics** — run full diagnostics
- **Verify Agent** — check port 8080 + PSK token
- **Context Assistant** — open monitoring window (only if agent is active)
- **Wake-on-LAN** — send Magic Packet (if MAC is known)
- **Details ▼** — IP, hostname, MAC, OS, ports, WinRM, credentials

#### Group Actions

Panel appears when devices are selected via checkboxes (🟢 only).

| Button | Description |
|--------|-------------|
| **🔴 SHUTDOWN** | Sequential shutdown with 0.5s delay |
| **💬 MESSAGE** | One text to all selected PCs |
| **🎤 VOICE** | Synchronized speech with ping compensation. Two modes: WinRM (direct) and Agent (fast). Parallel sending with script-embedded delay |
| **🤖 INSTALL AGENTS** | Mass parallel installation (up to 10 PCs simultaneously). Version check, skip up-to-date, auto-WinRM |

#### Background Monitor

Every 30 seconds, checks the online status of all devices. Updates ✅/❌ icons and color status. Works only when the tab is active.

---

### SETTINGS WINDOW

Opened via the ⚙️ button in the top panel.

| Group | Setting | Values | Description |
|-------|---------|--------|-------------|
| **Shutdown** | Check delay | 15-99 sec | Wait time before checking PC status in Anti-Cancel mode |
| **Voice** | Send mode | 🔗 WinRM / 🤖 Agent | Voice delivery method for group messages |
| | Sync delay | 0.00-5.00 sec | Base pause between PCs |
| | Ping compensation | ⚫ Off / 🟢 Auto / 🔵 Max | Auto-adjust for network latency |
| **General** | Auto-diagnostic | On/Off | Run check on entering PC Setup mode |
| | Auto-update | On/Off | Check GitHub on startup |
| | Language | Russian / English | Instant apply |
| | Theme | 🌙 Dark / ☀️ Light | UI reload |
| **Screenshot** | Format | PNG / JPEG | Lossless or compressed |
| **Control** | Phantom mode | 🔵 Direct / 🟢 Hidden | Default Phantom Input mode |
| | Sensitivity | 0.1-2.0 | Mouse multiplier in Game Mode |
| **Stream** | Adaptive bitrate | 🔵 On / ⚫ Off | Traffic Light system |
| | Quality | 10-100 | Only when adaptive is off |
| | Max FPS | 10-60 | Target frame rate |
| **Logging** | Mode | ⚫ Off / 🟢 INFO / 🔵 DEBUG | Detail level |
| | Retention | Forever / 1 / 7 / 30 days | Auto-delete old logs |
| | 📂 LOGS | Button | Open `%APPDATA%\RemIP\Logs` folder |
| **Agent** | Statistics | On/Off | Collect CPU/RAM/disk every minute |

---

### SMART AGENT PLATFORM

#### Architecture

The agent is a single PowerShell script (`agent.ps1`) that acts as a TCP server on port 8080. On startup, it:
1. Checks if already running (global mutex)
2. Determines session — if Session 0, restarts in user session
3. Configures firewall ("Remip Agent" rule on port 8080)
4. Creates a scheduled task for autostart on user logon
5. Compiles embedded C# types (ProcessFreezer, NativeStreamServer, PhantomInputServer)
6. Starts the main connection handling loop

#### Control Protocol

The agent accepts text commands via TCP after `TOKEN:<sha256>\n`. After authentication, the following commands are available:

| Command | Response | Description |
|---------|----------|-------------|
| `VERSION` | version | Current agent version |
| `PING` | `PONG` | Connection check |
| `SESSION` | session ID | User session number |
| `SCREENSHOT` | base64 JPEG | Screen capture |
| `SCREENSHOT_PNG` | base64 PNG | PNG screenshot |
| `WHATSNOW` | base64 JSON | Context assistant data |
| `TIMELINE` | base64 JSON | Event timeline |
| `LOG` | base64 text | Agent log file |
| `SPEAK:<base64>` | `SPEAK_OK` | Speak text |
| `FREEZE:<name>` | `FREEZE_OK` | Freeze process |
| `UNFREEZE:<name>` | `UNFREEZE_OK` | Unfreeze process |
| `CHECK_FROZEN:<name>` | `FROZEN:PID` | Check freeze status |
| `SYNC` | base64 JSON | Sync freeze state |
| `CLEAR_CACHE` | `CACHE_CLEARED` | Clear CPU cache |
| `ENABLE_WINRM` | `WINRM_ENABLED` | Enable WinRM on host |
| `SHELL:START` | `SHELL:STARTED:8081` | Start PowerShell terminal |
| `SHELL:INPUT:<b64>` | `SHELL:INPUT_OK` | Send command to terminal |
| `SHELL:STOP` | `SHELL:STOPPED` | Stop terminal |
| `NATIVE_STREAM:START:fps:q:det` | `STREAM_STARTED:...` | Start H.264 stream |
| `NATIVE_STREAM:STOP` | `STREAM_STOPPED` | Stop stream |
| `NATIVE_STREAM:QUALITY:N` | `QUALITY_OK` | Change quality |
| `NATIVE_STREAM:CONFIG:d:q:f` | `STREAM_CONFIG_OK` | Full reconfiguration |
| `PHANTOM:START` | `PHANTOM_STARTED:...` | Start Phantom Input |
| `PHANTOM:STOP` | `PHANTOM_STOPPED` | Stop Phantom Input |
| `STATS:ON/OFF/CLEAR/GET` | response | Statistics management |
| `HEALTH` | JSON | All subsystem statuses |
| `METRICS` | JSON | Stream metrics |
| `SIGNAL:GREEN/YELLOW/RED` | `SIGNAL_OK` | Traffic light signal |
| `CLIPBOARD:SET:<b64>` | `CLIPBOARD_OK` | Set clipboard |
| `CLIPBOARD:GET` | base64 text | Get clipboard |

#### Autonomous Subsystems

The agent works autonomously and doesn't require a constant Remip connection:

- **Watchdog (agent):** checks the PID file, restarts a crashed process
- **Watchdog (freeze):** every 5 seconds checks frozen processes, re-freezes on restart with new PID
- **Statistics:** every minute collects CPU/RAM/disk, stores up to 1440 records (24 hours)
- **Config file:** `stats_config.json` — statistics collection control
- **Log file:** `agent.log` with auto-cleanup when exceeding 1 MB

---

### PHANTOM INPUT — PROTOCOL & IMPLEMENTATION

Custom binary protocol for minimal latency.

**Server (PhantomInputServer):**
- Port 8083, C# class compiled via `Add-Type`
- Accepts connections, processes binary packets
- Uses Win32 API `SendInput` for input emulation
- In Direct mode: `SetCursorPos` to move the system cursor
- In Hidden mode: only `SendInput` without visual feedback
- On start: temporarily disables UAC (ConsentPromptBehaviorAdmin=0, PromptOnSecureDesktop=0)
- On stop or connection loss: restores UAC
- Keep-alive: ping every 5 seconds, disconnect timeout 15 seconds

**Client (PhantomInputSender):**
- TCP socket with TCP_NODELAY (no buffering)
- Mouse throttling: ~60 FPS normal, ~120 FPS game mode
- Delta encoding: saves 6 bytes per move (8→2)
- Atomic clicks: move+down+up in one TCP packet
- Batch key sending: up to 16 keys in one packet

**Server Statistics (GetStats):**
- Total input events sent
- Total bytes transmitted
- Delta encoding savings
- Events/sec, bytes/sec
- Current mode, active keys

---

### AUTO-UPDATE

- Checks GitHub on startup (configurable)
- 🔔 icon appears in the top panel when a new version is available
- Background download with progress
- "Restart Now" button for quick update
- Digital signature verification of downloaded file

---

### FEEDBACK

In the "About" window (`?` button), click **📤 Feedback**. Describe the issue, optionally enter your email. The program automatically attaches system information and the last log lines. Sent via secure `ntfy.sh` channel.

---

### LICENSE & CONTACTS

MIT License. For all questions: **dmistr9999@gmail.com**
