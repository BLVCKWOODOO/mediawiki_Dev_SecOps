# 🎓 DevSecOps диплом на основе MediaWiki

![License](https://img.shields.io/badge/license-MIT-green.svg?style=flat-square)

## 📘 Описание

Этот репозиторий содержит реализацию дипломного проекта по специальности **"Информационная безопасность"** в рамках трека **DevSecOps**.  
В качестве целевой платформы выбран [MediaWiki](https://www.mediawiki.org/) — популярная система управления вики-контентом.

Форк проекта: [BLVCKWOODOO/mediawiki_DevSecOps](https://github.com/BLVCKWOODOO/mediawiki_DevSecOps)

---

## 🎯 Цель проекта

Продемонстрировать внедрение полного DevSecOps-конвейера, включающего:

- CI/CD пайплайн на GitHub Actions
- Интеграцию с инструментами безопасной разработки
- Реализацию сканеров безопасности (SAST, DAST)
- Проверку конфигураций и секретов (Security Checks)
- Security Gateway с блокировкой сборки при наличии уязвимостей

---

## 🛠 Реализованные этапы

### ✅ Этап 1. Установка MediaWiki
- Поднята виртуальная машина с Ubuntu
- Установлены необходимые зависимости: PHP, MariaDB, NGINX
- Настроена база данных и веб-сервер
- Выполнена ручная установка MediaWiki

### ✅ Этап 2. CI/CD
- Реализован CI на GitHub Actions
- Линтинг кода
- Установка зависимостей через Composer
- Интеграция с CodeQL
- Артефакты: отчёты, конфиги

### ✅ Этап 3. SAST
- Статический анализ с использованием **Psalm**
- Результаты в формате SARIF
- Интеграция с GitHub Code Scanning

### ✅ Этап 4. DAST
- Динамическое сканирование с использованием **OWASP ZAP**
- Результаты сканирования сохраняются в `zap-reports/zap-report.html`

### ✅ Этап 5. Security Checks
- Проверка зависимостей через `PHP Security Checker`
- Включена проверка секретов с помощью **GitHub Secret Scanning**

### ✅ Этап 6. Security Gateway
- Остановка сборки при наличии ошибок SAST/DAST
- Генерация рекомендаций и отчётов
- Возможность внедрения комментариев в PR/MR (опционально)

---

## 📁 Структура проекта

```
mediawiki_DevSecOps/
├── .github/workflows/        # CI/CD пайплайн (GitHub Actions)
├── zap-reports/              # Отчёты DAST-сканирования
├── psalm-report.sarif        # SARIF-отчёт SAST (Psalm)
├── composer.json             # Зависимости PHP
├── LocalSettings.php         # Конфигурация MediaWiki (локально)
└── README.md                 # Этот файл
```

---

## 🚀 Как запустить

### 1. Установите зависимости:

```bash
composer install
```

### 2. Запустите MediaWiki локально (примерный стек: NGINX + PHP + MariaDB)

### 3. Запустите Psalm для статического анализа:

```bash
vendor/bin/psalm --output-format=sarif --report=psalm-report.sarif
```

### 4. Проведите DAST-сканирование вручную через OWASP ZAP

---

## 📜 Лицензия

Этот проект доступен под лицензией [MIT](LICENSE)

---

## 📌 Автор диплома

**Кирилл Колодкин**  
Трек: DevSecOps  
Учебное заведение: Нетология  
2025 год
