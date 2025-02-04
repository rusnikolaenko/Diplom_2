
# Stella Burgers API Testing | Diplom_2

Этот проект содержит API-тесты для сервиса [Stella Burgers](https://stellarburgers.nomoreparties.site/). Тестирование охватывает ключевые аспекты API, обеспечивая надежность и стабильность функционала перед релизом.

## Тестируемые сценарии

### 1. **Создание пользователя**
- ✅ Создание уникального пользователя.
- ❌ Попытка создания уже зарегистрированного пользователя.
- ⚠️ Попытка создания пользователя с пропуском одного из обязательных полей.

[Код тестов →](tests/test_create_user.py)

---

### 2. **Логин пользователя**
- ✅ Успешный логин под существующим пользователем.
- ❌ Логин с неверными данными (неверный email или пароль).

[Код тестов →](tests/test_login_user.py)

---

### 3. **Изменение данных пользователя**
- 🔓 С авторизацией: проверка изменения всех доступных полей.
- 🔒 Без авторизации: проверка, что запрос отклоняется с ошибкой.

[Код тестов →](tests/test_changing_user_data.py)

---

### 4. **Создание заказа**
- 🛒 Авторизованный/неавторизованный пользователь.
- 🍔 С ингредиентами/без ингредиентов.
- ❌ С неверным хешем ингредиентов.

[Код тестов →](tests/test_create_order.py)

---

### 5. **Получение заказов**
- 📋 Авторизованный пользователь: проверка доступности заказов.
- 🚫 Неавторизованный пользователь: проверка отказа в доступе.

[Код тестов →](tests/test_get_order_for_user.py)

---

## Установка и запуск тестов

### 1. Установка зависимостей
Перед началом работы убедитесь, что у вас установлен Python версии 3.9 или выше. Для установки зависимостей выполните команду:

```bash
pip install -r requirements.txt
```

---

### 2. Запуск тестов
Для запуска всех тестов используйте команду:

```bash
pytest tests --alluredir=allure-results
```

---

### 3. Генерация отчёта Allure
Чтобы получить интерактивный отчёт по результатам тестов, выполните команду:

```bash
allure serve allure-results
```

---

## Структура проекта

- **`data`**: Модуль содержит вспомогательные данные для тестов, такие как данные пользователей и ингредиентов.
- **`tests`**: Основные тестовые сценарии, разделённые по функциональным областям.
- **`conftest.py`**: Общие фикстуры для подготовки тестовых данных.

---

## Используемые технологии
- **Python 3.9+**
- **pytest**: Фреймворк для тестирования.
- **requests**: Для работы с HTTP-запросами.
- **Allure**: Для визуализации и анализа отчётов.

---

## Особенности
- Полностью независимые тесты: каждая проверка изолирована и не зависит от других.
- Подготовка и удаление тестовых данных через фикстуры.
- Удобные отчёты Allure, отображающие результаты в виде таблиц и графиков.

---

Если у вас есть вопросы или предложения по улучшению, создавайте `Issue` или открывайте `Pull Request`.
