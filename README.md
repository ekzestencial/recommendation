Суть задачи.
Необходимо реализовать сервис(в recommendation-api), рекомендующий пользователю на-
бор инвестиционных продуктов в соответствии с его риск-профилем и введенной суммой.
Входные параметры:
- Сумма
- Идентификатор пользователя
Результат работы сервиса:
- список рекоммендованных позиций(id продукта и количество «штук»)
Описание методики.
Каждый продукт имеет цену за одну единицу(price), риск-категорию(riskCategory),
тип(INSURANCE или INCOME).
Содержание рекомендации должно соответствовать условиям:
- Риск-категория продукта меньше или равна риск-профилю клиента;
- Суммарная стоимость всех позиций рекомендации не превышает заданной суммы;
- Соотношение продуктов разных типов равно 50/50 по суммарной стоимости.
Рис-категория и риск-профиль клиента это целое число от 1 до 5 включительно.
Сущность продукт(product-api) содержит поля
UUID id - идентификатор продукта
BigDecimal price - стоимость единицы продукта;
Integer riskCategory - риск-категория продукта;
Type type - тип продукта(INSURANCE или INCOME);
Сущность клиент(profile-api) содержит поля
UUID id - идентификатор клиент
Integer risk - риск-профиль клиента;
Содержание репозитория
В репозитории https://github.com/DeShir/test.git
Микросервис product-api предоставляет API для управления продуктами
Микросервис profile-api предоставляет API для управления профилями пользователей
В микросервис recommendation-api необходимо реализовать сервис по рекомендации.
