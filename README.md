# Selenoid
[![Build Status](https://github.com/aerokube/selenoid/workflows/build/badge.svg)](https://github.com/aerokube/selenoid/actions?query=workflow%3Abuild)
[![Coverage](https://codecov.io/github/aerokube/selenoid/coverage.svg)](https://codecov.io/gh/aerokube/selenoid)
[![Go Report Card](https://goreportcard.com/badge/github.com/aerokube/selenoid)](https://goreportcard.com/report/github.com/aerokube/selenoid)
[![Release](https://img.shields.io/github/release/aerokube/selenoid.svg)](https://github.com/aerokube/selenoid/releases/latest)
[![Docker Pulls](https://img.shields.io/docker/pulls/aerokube/selenoid.svg)](https://hub.docker.com/r/aerokube/selenoid)
[![StackOverflow Tag](https://img.shields.io/badge/stackoverflow-selenoid-orange.svg?style=flat)](https://stackoverflow.com/questions/tagged/selenoid)

Selenoid is a powerful implementation of [Selenium](http://github.com/SeleniumHQ/selenium) hub using [Docker](https://docker.com/) containers to launch browsers.
![Selenoid Animation](docs/img/selenoid-animation.gif)

## Features

### One-command Installation
Start browser automation in minutes by downloading [Configuration Manager](https://github.com/aerokube/cm/releases) binary and running just **one command**:
```
$ ./cm selenoid start --vnc --tmpfs 128
```
**That's it!** You can now use Selenoid instead of Selenium server. Specify the following Selenium URL in tests:
```
http://localhost:4444/wd/hub
```

### Ready to use Browser Images
No need to manually install browsers or dive into WebDriver documentation. Available images:
![Browsers List](docs/img/browsers-list.gif)

New images are added right after official releases. You can create your custom images with browsers. 

### Live Browser Screen and Logs
New **[rich user interface]((https://github.com/aerokube/selenoid-ui))** showing browser screen and Selenium session logs:
![Selenoid UI](docs/img/selenoid-ui.png)

### Video Recording
* Any browser session can be saved to [H.264](https://en.wikipedia.org/wiki/H.264/MPEG-4_AVC) video ([example](https://www.youtube.com/watch?v=maB298oO5cI))
* An API to list, download and delete recorded video files

### Convenient Logging

* Any browser session logs are automatically saved to files - one per session
* An API to list, download and delete saved log files

### Lightweight and Lightning Fast
Suitable for personal usage and in big clusters:
* Consumes **10 times** less memory than Java-based Selenium server under the same load
* **Small 6 Mb binary** with no external dependencies (no need to install Java)
* **Browser consumption API** working out of the box
* Ability to send browser logs to **centralized log storage** (e.g. to the [ELK-stack](https://logz.io/learn/complete-guide-elk-stack/))
* Fully **isolated** and **reproducible** environment

### Detailed Documentation and Free Support
Maintained by a growing community:
* Detailed [documentation](http://aerokube.com/selenoid/latest/)
* Telegram [support channel](https://t.me/aerokube)
* Support by [email](mailto:support@aerokube.com)
* StackOverflow [tag](https://stackoverflow.com/questions/tagged/selenoid)
* YouTube [channel](https://www.youtube.com/channel/UC9HvE3FNfTvftzpvXi9c69g)

## Complete Guide & Build Instructions

Complete reference guide (including building instructions) can be found at: http://aerokube.com/selenoid/latest/

## Selenoid in Kubernetes

Selenoid was initially created to be deployed on hardware servers or virtual machines and is not suitable for Kubernetes. Detailed motivation is described [here](https://aerokube.com/selenoid/latest/#_selenoid_in_kubernetes). If you still need running Selenium tests in Kubernetes, then take a look at [Moon](https://github.com/aerokube/moon/) - our dedicated solution for Kubernetes. 

## Known Users

[![JetBrains](docs/img/logo/jetbrains.png)](http://jetbrains.com/) [![Yandex](docs/img/logo/yandex.png)](https://yandex.com/company/) [![Sberbank Technology](docs/img/logo/sbertech.png)](http://sber-tech.com/) [![ThoughtWorks](docs/img/logo/thoughtworks.png)](https://thoughtworks.com/) [![VK.com](docs/img/logo/vk.png)](https://vk.com/) [![SuperJob](docs/img/logo/superjob.png)](http://superjob.ru/) [![PropellerAds](docs/img/logo/propellerads.png)](http://propellerads.com/) [![AlfaBank](docs/img/logo/alfabank.png)](https://alfabank.com/) [![3CX](docs/img/logo/3cx.png)](https://www.3cx.com/) [![IQ Option](docs/img/logo/iq_option.png)](https://iqoption.com/) [![Mail.Ru Group](docs/img/logo/mail_ru.png)](https://corp.mail.ru/en/) [![Newegg.Com](docs/img/logo/newegg.png)](https://newegg.com/) [![Badoo](docs/img/logo/badoo.png)](https://badoo.com/team/) [![BCS](docs/img/logo/bcs.png)]
(https://bcs.ru/) [![Quality Lab](docs/img/logo/quality-lab.png)](https://quality-lab.ru) [![AT Consulting](docs/img/logo/at-consulting.png)](https://www.at-consulting.ru/) [![Royal Caribbean International](docs/img/logo/royal-caribbean.png)](https://www.royalcaribbean.com/) [![Sixt](docs/img/logo/sixt.png)](https://sixt.com/) [![Testjar](docs/img/logo/testjar.png)](http://www.testjar.com/) [![Flipdish](docs/img/logo/flipdish.png)]

15.02.26
Ось результати аналізу та стратегія трансформації для проекту **selenoid**, підготовлені у форматі для Notion.

---

# 📑 Звіт AI-консультанта: Проект "Selenoid"

## 🧬 Частина 1: "ДНК" Проекту

**Selenoid** — це сучасна реалізація Selenium Hub, яка використовує Docker-контейнери для запуску браузерів. Його логіку можна розбити на такі **атомарні функції**:

*   **Контейнеризація браузерів (Orchestration):** Запуск кожного браузера в окремому ізольованому Docker-контейнері, що забезпечує незмінність (immutability) та повну ізоляцію середовища.
*   **Управління сесіями (Session Management):** Надання Selenium-сумісного API для споживання браузерів "з коробки".
*   **Мультимедійне логування (Telemetry):** Автоматичний запис відео (H.264) будь-якої сесії браузера та збереження логів для кожного окремого вікна.
*   **Візуалізація в реальному часі (Live Stream):** Надання насиченого інтерфейсу користувача для перегляду екрана браузера в реальному часі.
*   **Високошвидкісне керування (Binary Core):** Робота через компактний бінарний файл (6 Мб), написаний на Go, що споживає в 10 разів менше пам'яті, ніж традиційний Java-сервер.

### 💎 Головна технічна цінність
Головна цінність проекту полягає в **масштабованості та відтворюваності (reproducibility)**. Selenoid дозволяє розгортати цілу інфраструктуру для автоматизації браузерів однією командою, гарантуючи, що кожен тест запускається в "чистому" середовищі без залишків попередніх сесій.

---

## 🚀 Частина 2: "Трансформація" (Інтеграція з Gemini LLM)

*Наступна інформація щодо трансформації базується на сучасних AI-трендах, оскільки джерела не описують інтеграцію з LLM:*

Інтеграція Gemini перетворює Selenoid з "ферми контейнерів" на **автономного агента тестування та моніторингу**.

### Як зміниться функціонал?
1.  **AI-відладка (Self-healing tests):** Gemini аналізуватиме відео та логи сесій, що генерує Selenoid, щоб автоматично виявляти причини збоїв тестів і пропонувати виправлення коду [За межами джерел].
2.  **Природно-мовне керування браузером:** Замість написання складних селекторів, ви зможете давати Gemini команди: *"Зайди на сайт X і знайди найдешевший квиток"*. LLM перетворюватиме це на дії всередині контейнера Selenoid [За межами джерел].
3.  **Інтелектуальний візуальний регрес:** Gemini зможе порівнювати скріншоти live-сесій з еталонними, розуміючи контекст змін (наприклад, де баг верстки, а де просто оновлений банер) [За межами джерел].

### Сценарій сервісу (Selenoid + ID_{$} + Gemini)

Уявімо створення сервісу **"Автономний моніторинг конкурентів"** на вашому сайті.

**Алгоритм роботи:**
1.  **Команда (ID_{$}):** Ваш базовий Python-скрипт отримує від користувача запит: *"Стеж за цінами на товар А у конкурентів"*.
2.  **Інфраструктура (Selenoid):** Скрипт ініціює запуск контейнера з браузером через Selenoid API.
3.  **Виконання (Gemini):** Gemini керує браузером усередині Selenoid, імітуючи поведінку людини, щоб обійти анти-фрод системи.
4.  **Аналіз:** Selenoid записує відео сесії. Gemini аналізує це відео, витягує ціни та передає їх назад у **ID_{$}**.
5.  **Результат:** Ваш сайт видає користувачу фінальний звіт з підтверджуючим відео-доказом від Selenoid.

---

## 📋 План дій для Notion
| Крок | Дія | Результат |
| :--- | :--- | :--- |
| **Setup** | Встановлення Selenoid через Configuration Manager (`./cm`) | Готова інфраструктура за 1 хвилину |
| **Integration** | Підключення Python-бібліотеки `selenium` до `http://localhost:4444/wd/hub` | Зв'язок скриптів ID_{$} з браузерами |
| **AI Layer** | Налаштування Gemini для обробки логів, зібраних Selenoid | Перехід до інтелектуального аналізу помилок |
| **Scaling** | Налаштування збереження відео сесій на S3 через вбудовані тести | Створення архіву для навчання власних моделей |

> **Технічна замітка:** Оскільки Selenoid написаний на **Go (98%)**, він надзвичайно стабільний при високих навантаженнях, що робить його ідеальним бекендом для високонавантажених AI-сервісів.

(https://www.flipdish.com/)

