Обмін даними

-Глосарій

    • WMS - Система управління складом
    • ERP - Система планування ресурсів підприємства
    • Імпорт - процес передачі даних у систему WMS
    • Експорт - процес передачі даних із системи WMS
    • Довідник - таблиця в БД WMS
    • RabbitMQ - брокер повідомлень на основі стандарту AMQP
    • Request - запит до системи
    • Response - відповідь від системи

-Вступ
      Помилки та інформаційні повідомлення
      Додаток у будь-який момент може відповісти повідомленням із ключем error і описом всередині.
      Помилки, яким не присвоєно описового тексту, зазвичай повертаються з текстом за замовчуванням Server critical exception
Приклад помилки:
{
  "error": "In the content so much free quantity does not exist."
}

Приклад помилки з параметрами:
{
  "error": {
    "text": "Path not found (:var)",
    "prepare": {
      "var": "/dsada"
    }
  }
}
Також можлива відповідь інформаційним повідомленням із ключем message, яке всередині містить опис і інформує про успішну обробку запиту:
{
  "message": "You have successfully updated"
}

-Автентифікація
    • METHOD: POST 
    • HOST APP: https://wms-ik-test.srv.mhp.com.ua

    • PATH: /login/
    • BODY: auth-body
    • Приклад - https://wms-ik-test.srv.mhp.com.ua/login/
{
"login": "User",
"password": "PASSW",
"api": true
}
RESPONSE: auth-success
{"login":"EXT-LOGIN-01","session":"n2fol9cm5vdgbk57f8jnka1n8i"}
Сесійний ідентифікатор застосовується в REQUEST->RESPONSE запитах для наділення користувача належними правами.
Для подальших запитів необхідно вказувати в параметрах заголовка /?session_key =’’RESPONSE.session’’
-Оновлення довідників (CUD)
Загальний маршрут для оновлення довідників виглядає так: /unit/@TABLE/@METHOD/
    • @TABLE - Таблиця/довідник, який необхідний
        ◦ product - Товар
        ◦ product_brand - Бренд товару
        ◦ product_group - Група товару
        ◦ product_kind_of - Вид товару
        ◦ product_type - Тип товару
        ◦ product_barcode - ШК товару
        ◦ product_category - Категорії товару
    • 
    • @METHOD - Дія над цим довідником
        ◦ cu - Операція створення або зміни
        ◦ d - Операція видалення

Наприклад, для того щоб оновити або додати дані, потрібно вказати маршрут:
    • у довідник продуктів  -  /unit/product/cu/
    • у довідник брендів  -  /unit/product_brand/cu/
    • у довідник груп  - /unit/product_group/cu/
    • у довідник видів  - /unit/product_kind_of/cu/
    • у довідник типів  - /unit/product_type/cu/
    • у довідник ШК  -  /unit/product_barcode/cu/
    • у довідник категорій  -  /unit/product_category/cu/
    • у довідник упаковок  -   /unit/product_pack/cu/
Загальний підхід до операцій оновлення або створення
У тілі повідомлення вказуються допустимі ключі та їхні нові значення для оновлюваної таблиці.

1.Десктоп  процеси
Приклад створення запису в довіднику Товарів:
    • METHOD: POST
    • PATH: /unit/product/cu/
    • BODY: unit-product-body
{
  "product_id": "0011405b-6787-44d3-807f-19d2dbfd071a",
  "product_title": "Шоколад чорний Nut з мигдалем пакет пластиковий 90г Roshen",
  "product_full_name": "Шоколад чорний Nut з мигдалем пакет пластиковий 90г Roshen",
  "product_art": "ПМ36441",
  "product_product_brand_id": "511a89bf-e23d-11ef-8b7d-005056acf860",
  "product_product_kind_of_id": "e583b727-be76-11ed-988b-00505691a3b3",
  "product_product_group_id": "2",
  "product_product_category_id": "2",
  "product_product_type_id": "1",
  "product_product_unit_id": "222",
  "product_x": "10",
  "product_y": "8",
  "product_z": "8.7",
  "product_m": "0.095",
  "product_amount_in_package":"1.0000",
  "product_percent_leave": "36",
  "product_percent_coming": "56",
  "product_expiration_days": "365"
}
    • RESPONSE: unit-success
{
  "message": "Your operation was successful."
}




Таблиця product
|Стовпець|Тип даних|Обов’язковий|Коментар|
|----------------------------- |----------------------------- |----------------------------- |----------------------------- |
|product_id|varchar(72)|NO|Індентифікатор товару|
|product_product_legal_person_id|varchar(72)|YES|Індентифікатор постачальника|
|product_title|varchar(255)|YES|Назва товару|
|product_full_name|varchar(255)|YES|Повна назва товару|
|product_art|varchar(72)|YES|Номер артикулу товару|
|product_product_brand_id|varchar(72)|YES|Номер Бренду товару|
|product_product_kind_of_id|varchar(72)|YES|Номер Класу товару|
|product_x|float unsigned|NO|Ширина товару в сантиметрах|
|product_y|float unsigned|NO|Висота товару в сантиметрах|
|product_z|float unsigned|NO|Довжина товару в сантиметрах|
|product_m|float unsigned|NO|Вага товару  в кілограмах|
|product_amount_in_package|decimal(10,4) unsigned|NO|Кількість товару в ящику|
|product_product_unit_id|varchar(72)|YES||
|product_specific_amount|decimal(10,4)|NO|Кількість на одиницю товару(потрібно для підбору товару ), кратність товару 1 ціле або дробне число|
|product_specific_weight|tinyint(1)|NO|Признак вагового товару(можливо підбирати аніж в завданні)|
|product_percent_leave|double unsigned|NO|Відсоток строку придатності при комплектації|
|product_percent_coming|double unsigned|NO|Відсоток строку приадності при постачанні|
|product_expiration_days|int(11) unsigned|NO|Строк зберігання в днях|
|product_product_group_id|varchar(72)|YES|Номер Групи товару|
|product_tc|timestamp|НІ|Встановлюється автоматично|
|product_tm|timestamp|НІ|Встановлюється автоматично|
|product_product_type_id|varchar(72)|YES|Номер типу продукту|

Стовбець product_product_brand_id пов’язаний з таблицею :
product_brand
|Стовпець|Тип даних|Обов’язковий|Коментар|
|----------------------------- |----------------------------- |----------------------------- |----------------------------- |
|product_brand_id|varchar(72)|NO|Індентифікатор Бренду товару|
|product_brand_title|varchar(255)|NO|Найменування бренду|
|product_brand_tc|timestamp|NO|Встановлюється автоматично|
|product_brand_tm|timestamp|YES|Встановлюється автоматично|


Стовбець product_product_kind_of_id  пов’язаний з таблицею
product_kind_of 
|Стовпець|Тип даних|Обов’язковий|Коментар|
|----------------------------- |----------------------------- |----------------------------- |----------------------------- |
|product_kind_of_id|varchar(72)|Так|Індентифікатор Класу товару|
|product_kind_of_title|varchar(255)|Так|Назва класу товару|
|product_kind_of_product_type_id|varchar(72)|Так|Індентифікатор Типу товару|
|product_kind_of_accounting_expiration_date|tinyint(1) unsigned|Так|Облік строку придатності|
|product_kind_of_accounting_batch_code|tinyint(1) unsigned|Так|Облік партійності товару|
|product_kind_of_tc|timestamp|Ні|Встановлюється автоматично|
|product_kind_of_tm|timestamp|Ні|Встановлюється автоматично|


Стовбець product_product_product_type_id  пов’язаний з таблицею
product_type
|Стовпець|Тип даних|Обов’язковий|Коментар|
|----------------------------- |----------------------------- |----------------------------- |----------------------------- |
|product_type_id|varchar(72)|Так|Індентифікатор Типу товару|
|product_type_title|varchar(255)|Так|Назва типу товару|
|product_type_product_group_id|varchar(72)|Так|Індентифікатор Групи товару|
|product_type_tc|timestamp|Ні|Встановлюється автоматично|
|product_type_tm|timestamp|Ні|Встановлюється автоматично|

Стовбець product_product_product_group_id пов’язаний з таблицею
product_group
|Стовпець|Тип даних|Обов’язковий|Коментар|
|----------------------------- |----------------------------- |----------------------------- |----------------------------- |
|product_group_id|varchar(72)|NO|Індентифікатор Групи товару|
|product_group_title|varchar(255)|YES||
|product_group_package_title|varchar(255)|YES||
|product_group_tc|timestamp|NO|Встановлюється автоматично|
|product_group_tm|timestamp|YES|Встановлюється автоматично|


Також можлива множинна обробка даних у контексті одного запиту.
Уся операція виконується в одній транзакції і в разі помилки скасовується повністю.
Приклад відправлення колекції для створення записів у довіднику ШК:
METHOD: POST  
PATH: /unit/product_barcode/cu/  
BODY: unit-product_barcode-body  
[
  {
    "product_barcode_id": " 2374154020503_ЦБ74312772",
    "product_barcode_title": "2374154020503",
    "product_barcode_product_id": "15c11458-a7fd-48c3-80fa-6be997bd4528"
  },
  {
    "product_barcode_id": " 4006402301451_ЦБ74324697",
    "product_barcode_title": "4006402301451",
    "product_barcode_product_id": "416a5fd9-104f-454a-b7d9-7954cfba4d61"
  }
]
RESPONSE: unit-success  
{
  "message": "Your operation was successful."
}

Таблиця product_barcode_id
|Стовпець|Тип даних|Обов’язковий|Коментар|
|----------------------------- |----------------------------- |----------------------------- |----------------------------- |
|product_barcode_id|varchar(72)|Так|Індентифікатор запису штрихкоду |
|product_barcode_title|varchar(72)|Так|Назва штрихкоду|
|product_barcode_product_id|varchar(72)|Так|Індентифікатор товару|
|product_barcode_seller_id|varchar(72)|Ні|Індентифікатор власника|
|product_barcode_tc|timestamp|Ні|Встановлюється автоматично|
|product_barcode_tm|timestamp|Ні|Встановлюється автоматично|



-Приклад відправлення колекції для створення записів у довіднику Товари:
METHOD: POST  
PATH: /unit/product/cu/  
BODY: unit-product-body  
[
  {
{ 2374154020503_ЦБ74312772
  "product_id": "0011405b-6787-44d3-807f-19d2dbfd071a",
  "product_title": "Шоколад чорний Nut з мигдалем пакет пластиковий 90г Roshen",
  "product_full_name": "Шоколад чорний Nut з мигдалем пакет пластиковий 90г Roshen",
  "product_art": "ПМ36441",
  "product_product_brand_id": "511a89bf-e23d-11ef-8b7d-005056acf860",
  "product_product_kind_of_id": "e583b727-be76-11ed-988b-00505691a3b3",
  "product_product_group_id": "2",
  "product_product_category_id": "2",
  "product_product_type_id": "1",
  "product_product_unit_id": "222",
  "product_x": "10",
  "product_y": "8",
  "product_z": "8.7",
  "product_m": "0.095", 4006402301451_ЦБ74324697
  "product_amount_in_package":"1.0000",
  "product_coeff_leave": "36",
  "product_coeff_coming": "56",
  "product_expiration_days": "365"
}
  },

{
  "product_id": "0006d014-ee04-4ff9-a703-b49821c64bda",
  "product_title": "Етикетка термо топ лоток "Курчати-бройлера напівфабрикат кулінарний охолоджений" ТМ "Наша Ряба" 58х60",
  "product_full_name": "Ет. термо топ лоток "Кур-бр н/ф кулінарний охол." ТМ "Наша Ряба" 58х60",
  "product_art": "39023",
  "product_product_brand_id": "511a89bf-e23d-11ef-8b7d-005056acf860",
  "product_product_kind_of_id": "0a54ebd7-e86e-11ef-b82a-005056acf860",
  "product_product_group_id": "2",
  "product_product_category_id": "2",
  "product_product_type_id": "1",
  "product_product_unit_id": "222",
  "product_x": "10",
  "product_y": "8",
  "product_z": "8.7",
  "product_m": "0.095",
  "product_amount_in_package":"1.0000",
  "product_percent_leave": "36",
  "product_percent_coming": "56",
  "product_expiration_days": "365"
}
]

Відповідь при правильній передачі даних
RESPONSE: unit-success  
{
  "message": "Your operation was successful."
}


-Загальний підхід для операцій видалення

У тілі повідомлення зазначаються ідентифікатори, які вже завантажені в систему.
Приклад відправлення колекції для видалення записів у довіднику ШК: 
METHOD: POST  
PATH: /unit/product_barcode/d/  
BODY: unit-d-product_barcode-body  
[
  "4006402301451_ЦБ74324697",
  "2374154020503_ЦБ74312772"
]
RESPONSE: unit-success  
{
  "message": "Your operation was successful."
}

Приклад відправлення колекції для видалення записів у довіднику Товари:
METHOD: POST  
PATH: /unit/product/d/  
BODY: unit-d-product-body  
[
  "4",
  "5",
  "6"
]
RESPONSE: unit-success  
{
  "message": "Your operation was successful."
}

