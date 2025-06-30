
Tocan.WMS
Формат обміну даними

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
    • HOST APP: https://wms-server.com

    • PATH: /login/
    • BODY: auth-body
    • Приклад - https://wms-server.com/login/
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
  "product_id": "4",
  "product_title": "Product 4",
  "product_full_name": "Товар 4",
  "product_art": "art4",
  "product_product_brand_id": "1",
  "product_product_kind_of_id": "2",
  "product_product_group_id": "2",
  "product_product_category_id": "2",
  "product_product_type_id": "1",
  "product_product_unit_id": "222",
  "product_x": "10",
  "product_y": "8",
  "product_z": "8.7",
  "product_m": "2.5",
  "product_specific_amount": "1",
  "product_coeff_leave": "0.85",
  "product_coeff_coming": "0.85",
  "product_expiration_days": "305"
}
    • RESPONSE: unit-success
{
  "message": "Your operation was successful."
}
product :
Стовбець	Тип даних	Обов'язкове поле	Коментар
product_id	varchar(72)	Так	Індентифікатор товару
product_product_legal_person_id	varchar(72)	Ні	Індентифікатор контрагента
product_title	varchar(255)	Ні	Назва тотвару
product_full_name	varchar(255)	Ні	Повна назва товару
product_art	varchar(72)	Ні	Артикул товару
product_product_brand_id	varchar(72)	Ні	Індентифікатор бренду
product_product_kind_of_id	varchar(72)	Ні	Індентифікатор виду товару
product_x	float unsigned	Так	Ширина X
product_y	float unsigned	Так	Висота Y
product_z	float unsigned	Так	Глибина Z
product_m	float unsigned	Так	Вага товару
product_amount_in_package	decimal(10,4) unsigned	Ні	Кількість товару в ящику
product_product_unit_id	varchar(72)	Ні	Індентифікатор одиниці виміру товару
product_specific_amount	decimal(10,4)	Ні	Кількість на одиницю товару (необхідно для підбору штучно-вагового товару)
product_specific_weight	tinyint(1)	Ні	Ознака вагового продукту (можна підбирати більше ніж у завданні)
product_percent_leave	double unsigned	Ні	Відсоток терміну придатності для витрат
product_percent_coming	double unsigned	Ні	Відсоток терміну придатності для приходу
product_expiration_days	int(11) unsigned	Ні	Термін зберігання загальний в днях
product_product_group_id	varchar(72)	Ні	Індентифікатор групи товару
product_tc	timestamp	Так	Час стоврення (автоматичне заповнення системою)
product_tm	timestamp	Ні	Час зміни (автоматичне заповнення системою)
product_product_type_id	varchar(72)	Ні	Індентифікатор типу товару

Стовбець product_product_legal_person_id пов’язаний з таблицею :
product_legal_person()
Стовбець	Тип даних	Обов'язкове поле	Коментар
product_legal_person_id	varchar(72)	Так	Індентифікатор контрагента
product_legal_person_title	varchar(255)	Ні	Назва контрагента
product_legal_person_tc	timestamp	Так	
product_legal_person_tm	timestamp	Ні	

Стовбець product_product_brand_id пов’язаний з таблицею :
product_brand
Стовбець	Тип даних	Обов'язкове поле	Коментар
product_brand_id	varchar(72)	Так	Індентифікатор бренду
product_brand_title	varchar(255)	Так	Найменування бренду
product_brand_tc	timestamp	Так	
product_brand_tm	timestamp	Ні	

Стовбець product_product_kind_of_id  пов’язаний з таблицею
product_kind_of 
Стовбець	Тип даних	Обов'язкове поле	Коментар
product_kind_of_id	varchar(72)	Так	Індентифікатор виду товару
product_kind_of_title	varchar(255)	Ні	Найменування воду товару

product_type
Стовбець	Тип даних	Обов'язкове поле	Коментар
product_type_id	varchar(72)	Так	Ідентифікатор типів продукту
product_type_title	varchar(255)	Так	Найменування типів продукту

product_group
Стовбець	Тип даних	Обов'язкове поле	Коментар
product_group_id	varchar(72)	Так	Індентифікатор групи товару
product_group_title	varchar(255)	Ні	Найменування групи товару

product_group_zone
Стовбець	Тип даних	Обов'язкове поле	Коментар
product_group_zone_id	varchar(72)	Так	Ідентифікатор прив'язки групи до зони
product_group_zone_product_group_id	varchar(72)	Так	Ідентифікатор групи
product_group_zone_zone_id	varchar(72)	Так	Ідентифікатор зони
product_group_zone_tc	timestamp	Так	Заповнюється автоматично системою
product_group_zone_tm	timestamp	Ні	Заповнюється автоматично системою


-Приклад створення запису в довіднику Упаковка:
METHOD: POST  
PATH: /unit/product_pack/cu/  
BODY: unit-product_pack-body  
{
    "product_pack_id": "p000001-6",
    "product_pack_product_id": "p000001",
    "product_pack_title": "Ящик - 6 шт",
    "product_pack_barcode": "8512545632546",
    "product_pack_amount": "6"
}
RESPONSE: unit-success  
{
"message": "Your operation was successful."
}
product_pack(додаткова вкладка)
Назва	Тип	R	Залежність	Опис
product_pack_id	varchar(72)	+		Ідентифікатор упаковки
product_pack_product_id	varchar(72)	+	product_id	Ідентифікатор продукту
product_pack_title	varchar(192)	+		Назва упаковки
product_pack_amount	int	+		Кількість одиниць в упаковці
product_pack_barcode	varchar(72)	-		Штрих-код упаковки

Також можлива множинна обробка даних у контексті одного запиту.
Уся операція виконується в одній транзакції і в разі помилки скасовується повністю.
Приклад відправлення колекції для створення записів у довіднику ШК:
METHOD: POST  
PATH: /unit/product_barcode/cu/  
BODY: unit-product_barcode-body  
[
  {
    "product_barcode_id": "PB-P01-01",
    "product_barcode_title": "012345678912",
    "product_barcode_product_id": "P01"
  },
  {
    "product_barcode_id": "PB-P01-02",
    "product_barcode_title": "X12345678912",
    "product_barcode_product_id": "P01"
  }
]
RESPONSE: unit-success  
{
  "message": "Your operation was successful."
}
product_barcode
Стовбець	Тип даних	Обов'язкове поле	Коментар
product_barcode_id	varchar(72)	Так	Індентифікатор штрихкоду товару
product_barcode_title	varchar(72)	Ні	Штрихкод товару
product_barcode_product_id	varchar(72)	Ні	Індентифікатор товару
product_barcode_tc	timestamp	Так	Заповнюється системою (не вносити дані)
product_barcode_tm	timestamp	Ні	Заповнюється системою (не вносити дані)

-Приклад відправлення колекції для створення записів у довіднику Товари:
METHOD: POST  
PATH: /unit/product/cu/  
BODY: unit-product-body  
[
  {
    "product_id": "5",
    "product_title": "Product 5",
    "product_full_name": "Товар 5",
    "product_art": "art5",
    "product_product_brand_id": "1",
    "product_product_kind_of_id": "2",
    "product_product_unit_id": "222",
    "product_x": "10",
    "product_y": "8",
    "product_z": "8.7",
    "product_m": "2.5",
    "product_specific_amount": "1",
    "product_coeff_leave": "0.85",
    "product_coeff_coming": "0.85",
    "product_expiration_days": "305"
  },

{
    "product_id": "6",
    "product_title": "Product 6",
    "product_full_name": "Товар 6",
    "product_art": "art6",
    "product_product_brand_id": "1",
    "product_product_kind_of_id": "2",
    "product_product_unit_id": "222",
    "product_x": "10",
    "product_y": "8",
    "product_z": "8.7",
    "product_m": "2.5",
    "product_specific_amount": "1",
    "product_coeff_leave": "0.85",
    "product_coeff_coming": "0.85",
    "product_expiration_days": "305"
  }
]
RESPONSE: unit-success  
{
  "message": "Your operation was successful."
}
product
Стовбець	Тип даних	Обов'язкове поле	Коментар
product_id	varchar(72)	Так	Індентифікатор товару
product_product_legal_person_id	varchar(72)	Ні	Індентифікатор контрагента
product_title	varchar(255)	Ні	Назва тотвару
product_full_name	varchar(255)	Ні	Повна назва товару
product_art	varchar(72)	Ні	Артикул товару
product_product_brand_id	varchar(72)	Ні	Індентифікатор бренду
product_product_kind_of_id	varchar(72)	Ні	Індентифікатор виду товару
product_x	float unsigned	Так	Ширина X
product_y	float unsigned	Так	Висота Y
product_z	float unsigned	Так	Глибина Z
product_m	float unsigned	Так	Вага товару
product_amount_in_package	decimal(10,4) unsigned	Ні	Кількість товару в ящику
product_product_unit_id	varchar(72)	Ні	Індентифікатор одиниці виміру товару
product_specific_amount	decimal(10,4)	Ні	Кількість на одиницю товару (необхідно для підбору штучно-вагового товару)
product_specific_weight	tinyint(1)	Ні	Ознака вагового продукту (можна підбирати більше ніж у завданні)
product_percent_leave	double unsigned	Ні	Відсоток терміну придатності для витрат
product_percent_coming	double unsigned	Ні	Відсоток терміну придатності для приходу
product_expiration_days	int(11) unsigned	Ні	Термін зберігання загальний в днях
product_product_group_id	varchar(72)	Ні	Індентифікатор групи товару
product_tc	timestamp	Так	Час стоврення (автоматичне заповнення системою,значення на встановлюється)
product_tm	timestamp	Ні	Час зміни (автоматичне заповнення системою,значення на встановлюється)
product_product_type_id	varchar(72)	Ні	Індентифікатор типу товару


-Загальний підхід для операцій видалення
У тілі повідомлення зазначаються ідентифікатори, які вже завантажені в систему.
Приклад відправлення колекції для видалення записів у довіднику ШК: 
METHOD: POST  
PATH: /unit/product_barcode/d/  
BODY: unit-d-product_barcode-body  
[
  "PB-P01-01",
  "PB-P01-02"
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

-Документообіг

Загальне
Для всіх типів документів застосовується загальна структура даних.
document
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документу
document_document_type_id	varchar(72)	Ні	Тип документу
document_document_status_id	varchar(72)	Ні	Статус документа
document_title	varchar(255)	Ні	Назва документу
document_barcode	varchar(72)	Ні	Штрихкод документу
document_document_legal_person_id	varchar(72)	Ні	Котнрагент документу
document_user_id	varchar(72)	Ні	14
document_warehouse_id	varchar(72)	Ні	Ідентифікатор складу
document_warehouse_id_from	varchar(72)	Ні	Ідентифікатор складу звідки
document_warehouse_id_to	varchar(72)	Ні	Ідентифікатор складу куди
document_zone_id_from	varchar(72)	Ні	Ідентифікатор зони складу звідки
document_zone_id_to	varchar(72)	Ні	Ідентифікатор зони складу куди
document_tc	timestamp	Так	
document_tm	timestamp	Ні	
document_comment	text	Ні	Коментар до документа
document_counterparty_id_from	varchar(72)	Ні	Контрагент звідки
document_counterparty_id_to	varchar(72)	Ні	Контрагент куди
document_cost	varchar(255)	Ні	Оголошена вартість вмісту документа
document_date	varchar(255)	Ні	Дата документа
document_document_service_type_id	varchar(72)	Ні	Тип доставки в документі
document_document_payment_method_id	varchar(72)	Ні	Тип оплати в документі
document_document_payer_type_id	varchar(72)	Ні	Тип платника в документі
document_seats_amount	int(10) unsigned	Ні	
document_document_cargo_type_id	varchar(72)	Ні	Тип вантажу в документі
document_weight	float unsigned	Ні	Вага
document_volume	float unsigned	Ні	Об’єм
document_express_invoice	varchar(255)	Ні	Експрес накладна
document_document_mail_id	varchar(72)	Ні	
document_document_priority_id	varchar(72)	Ні	Пріоритетність витратного документа
document_incoming_priority	tinyint(1)	Ні	Пріоритетність вхідного документа
document_priority_update_tm	timestamp	Ні	
document_1c_document_type_id	varchar(72)	Ні	Ідентифікатор типу документа 1С
document_1c_document_id	varchar(72)	Ні	
document_car_number	varchar(128)	Ні	
document_control_expiration_date	tinyint(1)	Ні	
document_seller_id	varchar(72)	Ні	
document_create_user_id	varchar(72)	Ні	





-Прихідна
На основі цього типу документів виконуються процеси (Приймання-Розміщення).
document_document_type_id = 1  
Приклад:
METHOD: POST  
PATH: /document/coming/  
BODY: doc-acceptance-body  
  METHOD: POST
    PATH: /document/coming/
    BODY: doc-acceptance-body

{
  "document_id": "DOC_AC_01",
  "document_document_type_id": "1",
  "document_comment": "Without commentary",
  "document_document_legal_person_id": "DLP_01",
  "document_title": "Acceptance 01",

  "document_warehouse_id": "MAIN",

  "items": [
    {
      "document_det_product_id": "P01",
      "document_det_amount": 10
    },
    {
      "document_det_product_id": "P02",
      "document_det_amount": 12.5
    }
  ]
}

    RESPONSE: doc-success
{
  "message": "Your operation was successful."}

document(Основне вкладення)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документу
document_document_type_id	varchar(72)	Ні	Тип документу
document_title	varchar(255)	Ні	Назва документу
document_warehouse_id_to	varchar(72)	Ні	Ідентифікатор складу куди
document_comment	text	Ні	Коментар до документа

document_det( Вкладення деталізація документа)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_det_id	varchar(72)	Так	Ідентифікатор деталізації документа
document_det_document_id	varchar(72)	Ні	Ідентифікатор документа
document_det_date_time	datetime	Ні	Дата та час деталізації документа
document_det_product_id	varchar(72)	Ні	Ідентифікатор продукту
document_det_tare_id	varchar(72)	Ні	Ідентифікатор контейнера
document_det_amount	decimal(10,4) unsigned	Ні	Кількість продукту деталізації документа
document_det_defect	tinyint(1)	Так	Признак браку деталізації документа

Warehouse(створення складів для прив`язки до документів (прихід та замовлення )  та комірок
Path : unit/warehouse/cu
Стовбець	Тип даних	Обов'язкове поле	Коментар
warehouse_id	varchar(72)	Так	Ідентифікатор складу
warehouse_title	varchar(255)	Так	Назва складу
warehouse_local	tinyint(1)	Так	Внутрішній склад
warehouse_tc	timestamp	Так	
warehouse_tm	timestamp	Ні	
warehouse_delete	tinyint(1)	Ні	

-Видаткова
На основі цього типу документів виконуються процеси (Підбір-Відвантаження).
document_document_type_id = 2  

Цей тип документа не рекомендується до використання.  
Приклад:
 METHOD: POST
    PATH: /document/leave/
    BODY: doc-selection-body
{
  "document_id": "DOC_SE_01",
  "document_document_type_id": "2",
  "document_comment": "Without commentary",
  "document_counterparty_id_to": "WH_TO_01",
  "document_title": "Selection 01",
  "document_cost": "1000.04",
  "document_date": "2020-03-01",
  "document_document_service_type_id": "WarehouseWarehouse",
  "document_document_payment_method_id": "NonCash",
  "document_document_payer_type_id": "Sender",
  "document_warehouse_id": "MAIN",
  "items": [
    {
      "document_det_product_id": "P01",
      "document_det_amount": 5
    },
    {
      "document_det_product_id": "P02",
      "document_det_amount": 10
    }
  ]
}

  
  RESPONSE: doc-success

{
  "message": "Your operation was successful."
}

document(Основне вкладення)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документа
document_document_type_id	varchar(72)	Ні	Ідентифікатор типу документа
document_title	varchar(255)	Ні	Назва документа
document_warehouse_id	varchar(72)	Ні	Ідентифікатор складу
document_comment	text	Ні	Коментар до документа
document_counterparty_id_to	varchar(72)	Ні	Контрагент куди
document_cost	varchar(255)	Ні	Оголошена вартість вмісту документа
document_date	varchar(255)	Ні	Дата документа
document_document_service_type_id	varchar(72)	Ні	Тип доставки в документі
document_document_payment_method_id	varchar(72)	Ні	Тип оплати в документі
document_document_payer_type_id	varchar(72)	Ні	Тип платника в документі

document_det( Вкладення деталізація документа)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_det_id	varchar(72)	Так	Ідентифікатор деталізації документа
document_det_document_id	varchar(72)	Ні	Ідентифікатор документа
document_det_date_time	datetime	Ні	Дата та час деталізації документа
document_det_product_id	varchar(72)	Ні	Ідентифікатор продукту
document_det_tare_id	varchar(72)	Ні	Ідентифікатор контейнера
document_det_amount	decimal(10,4) unsigned	Ні	Кількість продукту деталізації документа
document_det_defect	tinyint(1)	Так	Признак браку деталізації документа

-Видаткова накладна (Самовивіз)
document_document_type_id = LEAVE_SELF  
Приклад:
METHOD: POST  
PATH: /document/leave/  
BODY: doc-selection-body  
{
  "document_id": "DOC_SE_01",
  "document_document_type_id": "LEAVE_SELF",
  "document_comment": "Without commentary",
  "document_title": "Selection 01",
  "document_warehouse_id": "MAIN",

  "items": [
    {
      "document_det_product_id": "P01",
      "document_det_amount": 5
    },
    {
      "document_det_product_id": "P02",
      "document_det_amount": 10
    }
  ]
}

document(Основне вкладення)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документа
document_document_type_id	varchar(72)	Ні	Ідентифікатор типу документа
document_title	varchar(255)	Ні	Назва документа
document_warehouse_id	varchar(72)	Ні	Ідентифікатор складу
document_comment	text	Ні	Коментар до документа

document_det( Вкладення деталізація документа)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_det_id	varchar(72)	Так	Ідентифікатор деталізації документа
document_det_document_id	varchar(72)	Ні	Ідентифікатор документа
document_det_date_time	datetime	Ні	Дата та час деталізації документа
document_det_product_id	varchar(72)	Ні	Ідентифікатор продукту
document_det_tare_id	varchar(72)	Ні	Ідентифікатор контейнера
document_det_amount	decimal(10,4) unsigned	Ні	Кількість продукту деталізації документа
document_det_defect	tinyint(1)	Так	Признак браку деталізації документа

-Видаткова накладна (Доставка)
document_document_type_id = LEAVE_DELIVERY  
Приклад:
METHOD: POST  
PATH: /document/leave/  
BODY: doc-selection-body  
{
  "document_id": "DOC_SE_01",
  "document_document_type_id": "LEAVE_DELIVERY",
  "document_comment": "Без коментарів",
  "document_title": "Підбір 01",
  "document_warehouse_id": "MAIN",
  
  "items": [
    {
      "document_det_product_id": "P01",
      "document_det_amount": 5
    },
    {
      "document_det_product_id": "P02",
      "document_det_amount": 10
    }
  ]
}
RESPONSE: doc-success  
{
  "message": "Your operation was successful."
}

document(Основне вкладення)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документа
document_document_type_id	varchar(72)	Ні	Ідентифікатор типу документа
document_title	varchar(255)	Ні	Назва документа
document_warehouse_id	varchar(72)	Ні	Ідентифікатор складу
document_comment	text	Ні	Коментар до документа

document_det( Вкладення деталізація документа)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_det_id	varchar(72)	Так	Ідентифікатор деталізації документа
document_det_document_id	varchar(72)	Ні	Ідентифікатор документа
document_det_date_time	datetime	Ні	Дата та час деталізації документа
document_det_product_id	varchar(72)	Ні	Ідентифікатор продукту
document_det_tare_id	varchar(72)	Ні	Ідентифікатор контейнера
document_det_amount	decimal(10,4) unsigned	Ні	Кількість продукту деталізації документа
document_det_defect	tinyint(1)	Так	Признак браку деталізації документа

-Видаткова накладна (Повернення постачальнику)
document_document_type_id = 3  
Приклад:
METHOD: POST  
PATH: /document/leave/  
BODY: doc-selection-body  
{
  "document_id": "DOC_SE_01",
  "document_document_type_id": "LEAVE_DELIVERY",
  "document_comment": "Without commentary",
  "document_title": "Selection 01",
  "document_warehouse_id": "MAIN",
  
  "items": [
    {
      "document_det_product_id": "P01",
      "document_det_amount": 5
    },
    {
      "document_det_product_id": "P02",
      "document_det_amount": 10
    }
  ]
}

RESPONSE: doc-success  
{
  "message": "Your operation was successful."
}

document(Основне вкладення)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документа
document_document_type_id	varchar(72)	Ні	Ідентифікатор типу документа
document_title	varchar(255)	Ні	Назва документа
document_warehouse_id	varchar(72)	Ні	Ідентифікатор складу
document_comment	text	Ні	Коментар до документа

document_det( Вкладення деталізація документа)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_det_id	varchar(72)	Так	Ідентифікатор деталізації документа
document_det_document_id	varchar(72)	Ні	Ідентифікатор документа
document_det_date_time	datetime	Ні	Дата та час деталізації документа
document_det_product_id	varchar(72)	Ні	Ідентифікатор продукту
document_det_tare_id	varchar(72)	Ні	Ідентифікатор контейнера
document_det_amount	decimal(10,4) unsigned	Ні	Кількість продукту деталізації документа
document_det_defect	tinyint(1)	Так	Признак браку деталізації документа

-Документ переміщення між філіалами
document_document_type_id = MOVEMENT_WAREHOUSE  
На даний момент доступні лише прописані тестові склади  
Приклад:
METHOD: POST  
PATH: /document/MovementWarehouse/  
BODY: doc-movement-zn-body  
{
  "document_id": "DOC_MV_01",
  "document_document_type_id": "MOVEMENT_WAREHOUSE",
  "document_title": "Movement 01",
  "document_comment": "Without commentary",
  "document_warehouse_id_from": "MAIN",
  "document_warehouse_id_to": "WHOUSE2432",
  "items": [
    {
      "document_det_product_id": "P01",
      "document_det_amount": 5
    },
    {
      "document_det_product_id": "P02",
      "document_det_amount": 10
    }
  ]
}
document(Основне вкладення)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документа
document_document_type_id	varchar(72)	Ні	Ідентифікатор типу документа
document_title	varchar(255)	Ні	Назва документа
document_warehouse_id	varchar(72)	Ні	Ідентифікатор складу
document_comment	text	Ні	Коментар до документа

document_det( Вкладення деталізація документа)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_det_id	varchar(72)	Так	Ідентифікатор деталізації документа
document_det_document_id	varchar(72)	Ні	Ідентифікатор документа
document_det_date_time	datetime	Ні	Дата та час деталізації документа
document_det_product_id	varchar(72)	Ні	Ідентифікатор продукту
document_det_tare_id	varchar(72)	Ні	Ідентифікатор контейнера
document_det_amount	decimal(10,4) unsigned	Ні	Кількість продукту деталізації документа
document_det_defect	tinyint(1)	Так	Признак браку деталізації документа

-Документ відвантаження документів доставки
document_document_type_id = 'SHIPMENT_DELIVERY'  
Приклад:
METHOD: POST  
PATH: /document/shipmentDelivery/  
BODY: doc-selection-body  
{
  "document_id": "DOC_SH_01",
  "document_document_type_id": "SHIPMENT_DELIVERY",
  "document_comment": "Without commentary",
  "document_title": "Shipment 01",
  "document_warehouse_id": "12345",
  "v_document_1c_document_type_id": "SHIPMENT_DELIVERY",
  
  "route": {
    "route_id": "R01",
    "route_number": "R1234",
    "route_title": "Route 01",
    "route_driver": "Ivanov Ivan Ivanovich"
  },

  "items": [
    {
      "document_id": "D01"
    },
    {
      "document_id": "D02"
    }
  ]
}

document(Основне вкладення)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документа
document_document_type_id	varchar(72)	Ні	Ідентифікатор типу документа
document_title	varchar(255)	Ні	Назва документа
document_warehouse_id	varchar(72)	Ні	Ідентифікатор складу
document_comment	text	Ні	Коментар до документа

document_det( Вкладення деталізація документа)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_det_id	varchar(72)	Так	Ідентифікатор деталізації документа
document_det_document_id	varchar(72)	Ні	Ідентифікатор документа
document_det_date_time	datetime	Ні	Дата та час деталізації документа
document_det_product_id	varchar(72)	Ні	Ідентифікатор продукту
document_det_tare_id	varchar(72)	Ні	Ідентифікатор контейнера
document_det_amount	decimal(10,4) unsigned	Ні	Кількість продукту деталізації документа
document_det_defect	tinyint(1)	Так	Признак браку деталізації документа

-Видаткова. Зміни типу документа
Можливі типи документів:  

    LEAVE_SELF  
    LEAVE_MAIL  
    LEAVE_DELIVERY  
Приклад:
METHOD: POST  
PATH: /document/leave/changeType/  
BODY: doc-leave-change-type-body  
{
  "document_id": "DOC_SE_01",
  "document_document_type_id": "LEAVE_SELF"
}
RESPONSE: doc-success  
{
  "message": "Your operation was successful."
}

Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документу
document_document_type_id	varchar(72)	Ні	Тип документу

-Документообіг (додатково)
Контрагенти Нова Пошта (Одержувачі)
Контрагенти є частиною документообігу, але працюють за принципом звичайних довідників (CUD).
Приклад:
METHOD: POST  
PATH: /unit/counterparty/cu/  
BODY: unit-counterparty-body 
[
  {
    "counterparty_id": "WH_TO_01",
    "counterparty_counterparty_type_id": "INDIVIDUAL_PERSON",
    "counterparty_title": "Клиент 01",
    "counterparty_f": "Иванов",
    "counterparty_i": "Иван",
    "counterparty_o": "Иванович",
    "counterparty_phone_number": "380661234561",
    "counterparty_region": "Київська",
    "counterparty_city": "Київ",
    "counterparty_counterparty_warehouse_id": "39931b80-e1c2-11e3-8c4a-0050568002cf",
    "counterparty_street": "вул. Автозаводська",
    "counterparty_building": "5",
    "counterparty_flat": "66"
  }
]

RESPONSE: doc-success  
{
  "message": "Your operation was successful."
}
counterparty
Стовбець	Тип даних	Обов'язкове поле	Коментар
counterparty_id	varchar(72)	Так	Ідентифікатор контрагента
counterparty_counterparty_type_id	varchar(72)	Ні	Тип контрагента
counterparty_title	varchar(255)	Ні	Найменування контрагента (для юридичних осіб)
counterparty_f	varchar(255)	Ні	Прізвище контрагента
counterparty_i	varchar(255)	Ні	Ім'я контрагента
counterparty_o	varchar(255)	Ні	По батькові контрагента
counterparty_phone_number	varchar(255)	Ні	Мобільний номер контрагента
counterparty_region	varchar(255)	Ні	Регіон контрагента
counterparty_city	varchar(255)	Ні	Місто контрагента
counterparty_street	varchar(255)	Ні	Адреса контрагента
counterparty_building	varchar(255)	Ні	Номер будинку контрагента
counterparty_flat	varchar(255)	Ні	Квартира контрагента
counterparty_counterparty_warehouse_id	varchar(72)	Ні	Ідентифікатор складу поштового оператора
counterparty_tc	timestamp	Так	
counterparty_tm	timestamp	Ні	
counterparty_seller_id	varchar(72)	Ні	
Вказузання отримувача можлива в додатковій вкладці при створенні Заявок для клієнтів:
np_counterparty
Стовбець	Тип даних	Обов'язкове поле	Коментар
np_counterparty_id	varchar(72)	Так	
np_counterparty_np_city_id	varchar(72)	Так	
np_counterparty_f	varchar(255)	Ні	
np_counterparty_i	varchar(255)	Ні	
np_counterparty_o	varchar(255)	Ні	
np_counterparty_phone	varchar(16)	Ні	
np_counterparty_np_ownership_type_id	varchar(72)	Ні	
np_counterparty_edrpou	varchar(16)	Ні	
np_counterparty_tc	timestamp	Так	
np_counterparty_tm	timestamp	Ні	

-Список доступних складів Нової Пошти
Список доступних складів Нової Пошти є частиною документообігу, але працює за принципом звичайних довідників (CRUD/PSC).
Приклад:
METHOD: POST  
PATH: /reference/counterparty_warehouse/page/  
RESPONSE: counterparty_warehouse-success  
[
  {
    "counterparty_warehouse_id": "3",
    "counterparty_warehouse_title": "Киев, ул. АБС, Склад №3"
  },
  {
    "counterparty_warehouse_id": "4",
    "counterparty_warehouse_title": "Киев, ул. АБС, Склад №4"
  }
]

counterparty_warehouse
Стовбець	Тип даних	Обов'язкове поле	Коментар
counterparty_warehouse_id	varchar(72)	Так	Ідентифікатор складу поштового оператора
counterparty_warehouse_title	varchar(255)	Так	Назва складу поштової адреси


Приклад Rabbit:
Запит:
{
  "request_id": "SOME-GUID-01",
  "path": "/reference/counterparty_warehouse/page/",
  "body": null
}

Відповідь:
{
  "response": true,
  "request_id": "SOME-GUID-01",
  "path": "/reference/counterparty_warehouse/page/",
  "body": [
    {
      "counterparty_warehouse_id": "3",
      "counterparty_warehouse_title": "Киев, ул. АБС, Склад №3"
    },
    {
      "counterparty_warehouse_id": "4",
      "counterparty_warehouse_title": "Киев, ул. АБС, Склад №4"
    }
  ]
}
counterparty_warehouse
Стовбець	Тип даних	Обов'язкове поле	Коментар
counterparty_warehouse_id	varchar(72)	Так	Ідентифікатор складу поштового оператора
counterparty_warehouse_title	varchar(255)	Так	Назва складу поштової адреси

-Статуси поштових операторів. Експорт
Приклад:
METHOD: POST  
PATH: /document/deliveryStatus/  
RESPONSE: doc-deliveryStatus  
{
  "document_id": "DOC_SE_01",
  "v_status_id": "В обработке (Склад №4)"
}
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документу

-Видаткова. Зміна заголовка документа
Можливі типи документів:  

    LEAVE_SELF  
    LEAVE_MAIL  
    LEAVE_DELIVERY  
Приклад:
METHOD: POST  
PATH: /document/leave/updateHeader/  
BODY: doc-leave-update-header-body  
{
  "document_id": "DOC_SE_01",
  "document_document_type_id": "LEAVE_MAIL",
  "document_comment": "Without commentary",
  "document_counterparty_id_to": "WH_TO_01",
  "document_title": "Selection 01",
  "document_cost": "1000.04",
  "document_date": "2020-03-01",
  "document_document_service_type_id": "WarehouseWarehouse",
  "document_document_payment_method_id": "NonCash",
  "document_document_payer_type_id": "Sender"
} 
RESPONSE: doc-success  
{
  "message": "Your operation was successful."
}


document
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документа
document_document_type_id	varchar(72)	Ні	Ідентифікатор типу документа
document_title	varchar(255)	Ні	Назва документа
document_comment	text	Ні	Коментар до документа
document_counterparty_id_to	varchar(72)	Ні	Контрагент куди
document_cost	varchar(255)	Ні	Оголошена вартість вмісту документа
document_date	varchar(255)	Ні	Дата документа
document_document_service_type_id	varchar(72)	Ні	Тип доставки в документі
document_document_payment_method_id	varchar(72)	Ні	Тип оплати в документі
document_document_payer_type_id	varchar(72)	Ні	Тип платника в документі


-Видаткова. Супровідні друковані форми з ERP
Загальна структура запиту:
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документу
v_document_base64	array(v_document_base64)	Так	Дані PDF  документів

Структура масиву v_document_base64:
Стовбець	Тип даних	Обов'язкове поле	Коментар
v_base64	BASE64(PDF)	Так	Закодований PDF-документ
v_amount	integer unsigned	Так	Кількість копій для друку

Приклад:
METHOD: POST  
PATH: /document/leave/printDoc/  
BODY: doc-leave-print-doc-body  
{
  "document_id": "8f547118-8f65-11ea-bb15-00155d080527",
  "v_document_base64": [
    {
      "v_base64": "<BASE64>",
      "v_amount": "3"
    },
    {
      "v_base64": "<BASE64>",
      "v_amount": "2"
    }
  ]
}
RESPONSE: doc-success  
{
  "message": "Your operation was successful."}
-Інвентаризація товару
Приклад:
METHOD: POST  
PATH: /document/inventoryProduct/  
BODY: doc-inventory-product  
{
  "document_id": "IN_P_01",
  "document_document_type_id": "INVENTORY_PRODUCT",
  "document_comment": "Without commentary",
  "document_title": "Inventory product 01",
  "document_warehouse_id": "MAIN",

  "items": [
    {
      "document_det_product_id": "P01"
    },
    {
      "document_det_product_id": "P02"
    }
  ]
}

RESPONSE: doc-success  {
  "message": "Your operation was successful."
}
document(Основне вкладення)
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	Так	Ідентифікатор документа
document_document_type_id	varchar(72)	Ні	Ідентифікатор типу документа
document_title	varchar(255)	Ні	Назва документа
document_warehouse_id	varchar(72)	Ні	Ідентифікатор складу
document_comment	text	Ні	Коментар до документа

-Залишки на складі
Приклад:
METHOD: POST  
PATH: /product/stockBalances/  
BODY: product-stock-balances  
{
  "warehouse_id": "00000000-0000-0000-0000-000000000000"
}
RESPONSE:
[
  {
    "v_product_id": "P01",
    "v_amount": "58.0000",
    "v_defect": "0",
    "v_expiration_date": "2022-12-31",
    "v_batch_code": null
  },
  {
    "v_product_id": "P01",
    "v_amount": "1.5000",
    "v_defect": "1",
    "v_expiration_date": "2022-12-31",
    "v_batch_code": null
  },
  {
    "v_product_id": "P02",
    "v_amount": "42.0000",
    "v_defect": "0",
    "v_expiration_date": null,
    "v_batch_code": "54.50"
  }
]

-Юридичні особи. Видаткова накладна
Тип документа: document_document_type_id = LEAVE_MAIL
Нові поля:
    • "v_title": "ТОВ Агромаш" — Назва юридичної особи 
    • "v_edrpou": "35912126" — Код ЄДРПОУ юридичної особи 
Приклад:
METHOD: POST  
PATH: /document/leave/  
BODY: doc-selection-body  
{
  "document_id": "DOC_SE_01",
  "document_document_type_id": "LEAVE_MAIL",
  "document_document_mail_id": "MAIL_NP",
  "document_comment": "Without commentary",
  "document_counterparty_id_to": "WH_TO_01",
  "document_title": "Selection 01",

  "document_cost": "1000.04",
  "document_date": "2020-03-01",
  "document_document_service_type_id": "WarehouseWarehouse",
  "document_document_payment_method_id": "NonCash",
  "document_document_payer_type_id": "Sender",

  "v_document_counterparty": {
      "v_title": "ООО Агромаш",
      "v_edrpou": "35912126",
      "counterparty_f": "Иванов",
      "counterparty_i": "Иван",
      "counterparty_o": "Иванович",
      "counterparty_phone_number": "380661234561",
      "counterparty_counterparty_warehouse_id": "39931b80-e1c2-11e3-8c4a-0050568002cf"
  },

  "document_warehouse_id": "MAIN",
  "items": [
    {
      "document_det_product_id": "P01",
      "document_det_amount": 5
    },
    {
      "document_det_product_id": "P02",
      "document_det_amount": 10
    }
  ]
}
document
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_id	varchar(72)	-	Ідентифікатор документа
document_document_type_id	varchar(72)	-	Ідентифікатор типу документа
document_title	varchar(255)	-	Назва документа
document_warehouse_id	varchar(72)	-	Ідентифікатор складу
document_warehouse_id_from	varchar(72)	-	Ідентифікатор складу звідки
document_warehouse_id_to	varchar(72)	-	Ідентифікатор складу куди
document_zone_id_from	varchar(72)	-	Ідентифікатор зони складу звідки
document_zone_id_to	varchar(72)	-	Ідентифікатор зони складу куди
document_barcode	varchar(72)	-	ШК документа
document_comment	text	-	Коментар до документа
document_counterparty_id_from	varchar(72)	-	Контрагент звідки
document_counterparty_id_to	varchar(72)	-	Контрагент куди
document_cost	varchar(255)	-	Оголошена вартість вмісту документа
document_date	varchar(255)	-	Дата документа
document_document_service_type_id	varchar(72)	-	Тип доставки в документі
document_document_payment_method_id	varchar(72)	-	Тип оплати в документі
document_document_payer_type_id	varchar(72)	-	Тип платника в документі
document_document_cargo_type_id	varchar(72)	-	Тип вантажу в документі


counterparty(Контрагент)
Стовбець	Тип даних	Обов'язкове поле	Коментар
counterparty_id	varchar(72)	Так	Ідентифікатор контрагента
counterparty_counterparty_type_id	varchar(72)	Ні	Тип контрагента
counterparty_title	varchar(255)	Ні	Назва контрагента (для юридичних осіб)
counterparty_f	varchar(255)	Ні	Прізвище контрагента
counterparty_i	varchar(255)	Ні	Ім’я контрагента
counterparty_o	varchar(255)	Ні	По батькові контрагента
counterparty_phone_number	varchar(255)	Ні	Мобільний номер контрагента
counterparty_counterparty_warehouse_id	varchar(72)	Ні	Ідентифікатор складу поштового оператора







2.Мобільні процеси (приклади)
Опис способів взаємодії з мобільними процесами
Загальне:
Для всіх типів задач використовується загальна структура даних.
Використовується для отримання даних з WMS системи
Структура v:
Назва	Тип	R	Обмеження
v_task_id	varchar(72)	-	task
v_document_id	varchar(72)	+	document
v_document_1c_document_type_id	varchar(72)	+	1c_document_type
v_document_type_id	varchar(72)	+	document_type
v_warehouse_id	varchar(72)	+	warehouse
items	array(v_det)	+	

Структура v_det:
Назва	Тип	R	Обмеження
v_product_id	varchar(72)	+	product
v_amount_task	FLOAT UNSIGNED	+	
v_amount_fact	FLOAT UNSIGNED	+	
v_defect	boolean	+	
v_batch_code	varchar(72)	+	
v_expiration_date	varchar(72)	+	формат YYYY-MM-DD

-Прийомка експорт
METHOD: POST  
PATH: /api/mobile/Acceptance/  
BODY: mob-acceptance-body
{
  "v_task_id": "T_DOC_AC_01",
  "v_document_id": "DOC_AC_01",
  "v_document_1c_document_type_id": "COMING_DELIVERY",
  "v_document_type_id": "1",
  "v_warehouse_id": "00000000-0000-0000-0000-000000000000",
  "items": [
    {
      "v_product_id": "P01",
      "v_amount_task": "34",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": "34.50",
      "v_expiration_date": null
    },
    {
      "v_product_id": "P02",
      "v_amount_task": "38",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": null,
      "v_expiration_date": "2022-02-22"
    }
  ]
}
-Розміщення експорт
METHOD: POST
PATH: /api/mobile/Placement/
BODY: mob-placement-body
{
  "v_task_id": "T_DOC_AC_01",
  "v_document_id": "DOC_AC_01",
  "v_document_1c_document_type_id": "COMING_DELIVERY",
  "v_document_type_id": "1",
  "v_warehouse_id": "00000000-0000-0000-0000-000000000000",
  "items": [
    {
      "v_product_id": "P01",
      "v_amount_task": "34",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": "34.50",
      "v_expiration_date": null
    },
    {
      "v_product_id": "P02",
      "v_amount_task": "38",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": null,
      "v_expiration_date": "2022-02-22"
    }
  ]
}



-Розміщення частинами експорт
METHOD: POST
PATH: /api/mobile/PlacementPart/
BODY: mob-placement-body
{
  "v_task_id": "T_DOC_AC_01",
  "v_document_id": "DOC_AC_01",
  "v_document_1c_document_type_id": "COMING_DELIVERY",
  "v_document_type_id": "1",
  "v_warehouse_id": "00000000-0000-0000-0000-000000000000",
  "items": [
    {
      "v_product_id": "P01",
      "v_amount_task": "34",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": "34.50",
      "v_expiration_date": null
    },
    {
      "v_product_id": "P02",
      "v_amount_task": "38",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": null,
      "v_expiration_date": "2022-02-22"
    }
  ]
}
-Підбір експорт
Приклад:
METHOD: POST
PATH: /api/mobile/Selection/
BODY: mob-selection-body
{
  "v_task_id": "T_DOC_AC_01",
  "v_document_id": "DOC_AC_01",
  "v_document_1c_document_type_id": "LEAVE_DELIVERY",
  "v_document_type_id": "LEAVE_DELIVERY",
  "v_warehouse_id": "00000000-0000-0000-0000-000000000000",
  "items": [
    {
      "v_product_id": "P01",
      "v_amount_task": "34",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": "34.50",
      "v_expiration_date": null
    },
    {
      "v_product_id": "P02",
      "v_amount_task": "38",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": null,
      "v_expiration_date": "2022-02-22"
    }
  ]
}
-Контроль експорт
Результат надсилається тільки після завершення всіх завдань контролю (по документу). Цей результат можна використовувати для синхронізації зі статусами ERP (документ відібрано, є різниця під час підбору).
Надсилається тільки для документів з document_type_id: LEAVE_DELIVERY
Приклад:
METHOD: POST
PATH: /api/mobile/Control/
BODY: mob-control-body
{
  "v_task_id": "T_DOC_AC_01",
  "v_document_id": "DOC_AC_01",
  "v_document_1c_document_type_id": "LEAVE_DELIVERY",
  "v_document_type_id": "LEAVE_DELIVERY",
  "v_warehouse_id": "00000000-0000-0000-0000-000000000000",
  "items": [
    {
      "v_product_id": "P01",
      "v_amount_task": "56",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": "34.50",
      "v_expiration_date": null
    },
    {
      "v_product_id": "P02",
      "v_amount_task": "56",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": null,
      "v_expiration_date": "2022-02-22"
    }
  ]
}
-Відвантаження
Відправляється для витратних документів із document_type_id: 2, LEAVE_MAIL, LEAVE_SELF.
Приклад:
METHOD: POST  
PATH: /api/mobile/Shipment/  
BODY: mob-shipment-body  
{
  "v_task_id": "T_DOC_AC_01",
  "v_document_id": "DOC_AC_01",
  "v_document_1c_document_type_id":"MOVEMENT_WAREHOUSE_OUT",
  "v_document_type_id": "2",
  "v_warehouse_id": "00000000-0000-0000-0000-000000000000",
  "items": [
    {
      "v_product_id": "P01",
      "v_amount_task": "56",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": "34.50",
      "v_expiration_date": null
    },
    {
      "v_product_id": "P02",
      "v_amount_task": "56",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": null,
      "v_expiration_date": "2022-02-22"
    }
  ]
}

-Інвентаризація експорт
Приклад:
METHOD: POST  
PATH: /api/mobile/Inventory/  
BODY: mob-inventory-body  
{
  "v_task_id": "T_DOC_AC_01",
  "v_document_type_id": "INVENTORY",
  "v_document_1c_document_type_id": "INVENTORY",
  "v_warehouse_id": "00000000-0000-0000-0000-000000000000",
  "items": [
    {
      "v_product_id": "P01",
      "v_amount_task": "56",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": "34.50",
      "v_expiration_date": null
    },
    {
      "v_product_id": "P02",
      "v_amount_task": "56",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": null,
      "v_expiration_date": "2022-02-22"
    }
  ]
}
-Повна інвентаризація. Експорт
Приклад:
METHOD: POST  
PATH: /api/mobile/InventoryAll/  
BODY: mob-inventory-all-body  
{
  "v_task_id": "T_DOC_AC_01",
  "v_document_type_id": "INVENTORY_ALL",
  "v_document_1c_document_type_id": "INVENTORY_ALL",
  "v_warehouse_id": "00000000-0000-0000-0000-000000000000",
  "items": [
    {
      "v_product_id": "P01",
      "v_amount_task": "56",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": "34.50",
      "v_expiration_date": null
    },
    {
      "v_product_id": "P02",
      "v_amount_task": "56",
      "v_amount_fact": "56",
      "v_defect": "0",
      "v_batch_code": null,
      "v_expiration_date": "2022-02-22"
    }
  ]
}
-Комплектація
Не використовується
Обмін даними через брокер повідомлень RabbitMQ
Загальна інформація
Структура запиту:
Назва	Тип	R
request_id	varchar(255)	+
path	varchar(255)	+
body	Array/Object/null	+
    • request_id - унікальний ідентифікатор запиту, застосовується для отримання відповіді на конкретний запит із потоку. 
    • path - маршрут для звернення до певного обробника. 
    • body - тіло запиту. 

Приклад структури запиту:
{
  "request_id": "<Ідентифікатор запиту>",
  "path": "<Викликаний маршрут>",
  "body": {
    "<Тіло запиту>": null
  }
}
Структура відповіді:
Назва	Тип	R
response	boolean (true)	+
request_id	varchar(255)	+
path	varchar(255)	+
body	Array/Object/null	+

    • request_id - унікальний ідентифікатор запиту. 
    • body - тіло відповіді, приходить завжди. 
Приклад структури відповіді:
{
  "response": true,
  "request_id": "<Ідентифікатор запиту>",
  "path": "<Викликаний маршрут>",
  "body": {
    "<Тіло відповіді>": null
  }
}


-Довідники (CUD) для передачі через Rabbit MQ
Приклад запиту на запис:
{
  "request_id": "SOME-GUID-01",
  "path": "/unit/product_barcode/cu/",
  "body": [
    {
      "product_barcode_id": "PB-P01-01",
      "product_barcode_title": "012345678912",
      "product_barcode_product_id": "P01"
    },
    {
      "product_barcode_id": "PB-P01-02",
      "product_barcode_title": "X12345678912",
      "product_barcode_product_id": "P01"
    }
  ]
}
Приклад відповіді на запис:
{
  "response": true,
  "request_id": "SOME-GUID-01",
  "path": "/unit/product_barcode/cu/",
  "body": {
    "message": "Your operation was successful."
  }
}




-Довідники v2 (CRUD/PSC)
Усі довідники використовують модель CRUD/PS.
Детальна інформація про методи:
    • Create - створення запису у довіднику. 
    • Read - читання конкретного запису з довідника. 
    • Update - зміна конкретного запису у довіднику. 
    • Delete - видалення конкретного запису у довіднику. 
    • Page - посторінковий вивід даних із довідника. 
    • Search - пошук за конкретними параметрами довідника із подальшим посторінковим виводом. 
    • Count - загальна кількість записів, із можливістю пошуку, як у Search. 
Загальна схема звернення:
/reference/@NAME/@METHOD/@PARAM/
    • @NAME - назва таблиці/довідника в системі. 
    • @METHOD - один із перелічених методів CRUD/PS. 
    • @PARAM - ідентифікатор запису або номер сторінки (не застосовується в методі Create). 
Перед початком роботи з API необхідно пройти авторизацію та використовувати сесійний ключ для ідентифікації користувача.

Приклад запиту на читання:
{
  "request_id": "SOME-GUID-01",
  "path": "/reference/product/read/1/",
  "body": null
}
Приклад відповіді на читання:
{
  "response": true,
  "request_id": "SOME-GUID-01",
  "path": "/reference/product/read/1/",
  "body": {
    "product_id": "1",
    "product_product_legal_person_id": "1",
    "product_title": "TITLE",
    "product_full_name": "FULL-NAME",
    "product_art": "art1",
    "product_product_brand_id": "1",
    "product_product_kind_of_id": "1",
    "product_product_unit_id": "1",
    "product_x": "10",
    "product_y": "8",
    "product_z": "8.7",
    "product_m": "2.5",
    "product_specific_amount": "1",
    "product_percent_leave": "0.85",
    "product_percent_coming": "0.85",
    "product_expiration_days": "305"
  }
}
-Приклади
Приклад імпорту продукту (артикула)
Відправка на запис:
{
  "response": true,
  "request_id": "SOME-GUID-01",
  "path": "/reference/product/create/",
  "body": {
    "product_id": "1",
    "product_product_legal_person_id": "1",
    "product_title": "TITLE",
    "product_full_name": "FULL-NAME",
    "product_art": "art1",
    "product_product_brand_id": "1",
    "product_product_kind_of_id": "1",
    "product_product_unit_id": "1",
    "product_x": "10",
    "product_y": "8",
    "product_z": "8.7",
    "product_m": "2.5",
    "product_specific_amount": "1",
    "product_percent_leave": "0.85",
    "product_percent_coming": "0.85",
    "product_expiration_days": "305"
  }
}
Позитивна відповідь:
{
  "response": true,
  "request_id": "SOME-GUID-01",
  "path": "/reference/product/create/",
  "body": {
    "message": {
      "text": "Some msg(:var)",
      "prepare": {
        "var": "ABC-01"  
      }   
    }
  }
}

Негативна відповідь:
{
  "response": true,
  "request_id": "SOME-GUID-01",
  "path": "/reference/product/create/",
  "body": {
    "error": "<Some msg or Object>"
  }
}
-Приклад імпорту документів
Структура document:
Назва	Тип	Обов'язковість	Залежність
document_id	varchar(72)	Так	Ідентифікатор документу
document_title	varchar(255)	Ні	Назва документу
document_barcode	varchar(72)	Ні	Штрихкод документу
document_document_type_id	varchar(72)	Ні	Тип документу
Структура document_det:
Стовбець	Тип даних	Обов'язкове поле	Коментар
document_det_id	varchar(72)	Так	Ідентифікатор
document_det_document_id	varchar(72)	Ні	Ідентифікатор документу
document_det_amount	decimal(10,4) unsigned	Ні	
document_det_defect	tinyint(1)	Так	

Відправка на запис:
{
  "request_id": "SOME-GUID-01",
  "path": "/document/coming/",
  "body": {
    "document_id": "DOC_AC_01",
    "document_document_type_id": "1",
    "document_comment": "Без коментарів",
    "document_document_legal_person_id": "DLP_01",
    "document_title": "Прийом 01",
    "items": [
      {
        "document_det_product_id": "P01",
        "document_det_amount": 10
      },
      {
        "document_det_product_id": "P02",
        "document_det_amount": 12.5
      }
    ]
  }
}
Позитивна відповідь:
{
  "request_id": "SOME-GUID-01",
  "body": {
    "message": "<Some msg or Object>"
  }
}
Негативна відповідь:
{
  "request_id": "SOME-GUID-01",
  "body": {
    "error": "<Some msg or Object>"
  }
}
-Додатки
RabbitMQ
Черги для обміну даними:
    • F_ERP — ERP → WMS 
    • F_WMS — WMS → ERP 
Хост:
    • 0.0.0.0 
    • 9100 
Віртуальний хост:
    • qa1 
Користувач:
    • Логін: admin 
    • Пароль: password (для логування на стороні WMS) 
Для запуску слухача на стороні WMS:
sudo -u www-data php /var/www/html/wms-api/rabbitmq.php


-RabbitMQ (Тестування механізму):
    • Запуск емулятора WMS (прийом/передача): 
php /var/www/html/am-test/receive.php
    • Запуск емулятора ERP (прийом): 
php /var/www/html/am-test/receive_erp.php
    • Запуск процедури емуляції відправлення на WMS: 
php /var/www/html/am-test/send.php

3.Структури всіх довідників (загальний перелік усіх таблиць та їх даних)
Cell  (комірки)
Назва	Тип	Обов'язкове поле	Залежність	Опис
cell_id	varchar(72)	Так		Ідентифікатор осередку
cell_zone_id	varchar(72)	Ні	zone	Ідентифікатор зони
cell_cell_class_id	varchar(72)	Ні	cell_class	Ідентифікатор класу осередку
cell_barcode	varchar(72)	Ні		ШК осередку
cell_cell_position_id	varchar(72)	Ні	cell_position	Ідентифікатор позиції осередку
cell_block	tinyint(3) unsigned	Так		Блокування осередку
cell_tc	timestamp	Так		(заповнюється автоматично)

cell_class (клас комірок)
Стовбець	Тип даних	Обов'язкове поле	Коментар
cell_class_id	varchar(72)	Так	Індентифікатор класу коміркаи
cell_class_title	varchar(255)	Так	Назва Класу комірки
cell_class_x	float	Так	Ширина X
cell_class_y	float	Так	Висота Y
cell_class_z	float	Так	Глибина Z
cell_class_m	float	Так	Максимальна вага M
cell_class_limit	bigint(20) unsigned	Ні	
cell_class_tc	timestamp	Так	Час створення (заповнюється автоматично)
cell_class_tm	timestamp	Ні	Час модефікації (заповнюється автоматично)




Counterparty (Контрагенти)
Стовбець	Тип даних	Обов'язкове поле	Коментар
counterparty_id	varchar(72)	Так	Ідентифікатор контрагента
counterparty_counterparty_type_id	varchar(72)	Ні	Тип контрагента
counterparty_title	varchar(255)	Ні	Найменування контрагента (для юридичних осіб)
counterparty_f	varchar(255)	Ні	Прізвище контрагента
counterparty_i	varchar(255)	Ні	Ім'я контрагента
counterparty_o	varchar(255)	Ні	По батькові контрагента
counterparty_phone_number	varchar(255)	Ні	Мобільний номер контрагента
counterparty_region	varchar(255)	Ні	Регіон контрагента
counterparty_city	varchar(255)	Ні	Місто контрагента
counterparty_street	varchar(255)	Ні	Адреса контрагента
counterparty_building	varchar(255)	Ні	Номер будинку контрагента
counterparty_flat	varchar(255)	Ні	Квартира контрагента
counterparty_counterparty_warehouse_id	varchar(72)	Ні	Ідентифікатор складу поштового оператора
counterparty_tc	timestamp	Так	Час створення (заповнюється автоматично)
counterparty_tm	timestamp	Ні	Час модефікації (заповнюється автоматично)
counterparty_seller_id	varchar(72)	Ні	

counterparty_warehouse(склади контрагентів)
Стовбець	Тип даних	Обов'язкове поле	Коментар
counterparty_warehouse_id	varchar(72)	Так	Ідентифікатор складу поштового оператора
counterparty_warehouse_title	varchar(255)	Так	Назва складу поштової адреси
counterparty_warehouse_tc	timestamp	Так	
counterparty_warehouse_tm	timestamp	Ні	






4.Зміст довідників (ENUM)(назви описів довідників)
counterparty_type
Значення	Опис
INDIVIDUAL_PERSON	Фізична особа
LEGAL_PERSON	Юридична особа
WAREHOUSE	Склад
WH_ZONE	Зона складу
document_cargo_type
Значення	Опис
Cargo	Вантаж
Documents	Документи
Pallet	Палети
Parcel	Посилка
TiresWheels	Шини або диски
document_payer_type
Значення	Опис
Recipient	Одержувач
Sender	Відправник
ThirdPerson	Третя особа
document_payment_method
Значення	Опис
Cash	Готівковий розрахунок
NonCash	Безготівковий розрахунок
document_mail
Значення	Опис
MAIL_NP	Нова пошта
MAIL_TMM	TMM Express
MAIL_GUNSEL	Gunsel group
document_service_type
Значення	Опис
DoorsDoors	Адрес > Адреса
DoorsWarehouse	Адреса > Склад
WarehouseDoors	Склад > Адреса
WarehouseWarehouse	Склад > Склад
Warehouse
Path : unit/warehouse/cu	
Значення	Опис
MAIN	Основний (/wms-desktop/)
WHOUSE2432	Тестовий 2432 (/whouse2432/wms-desktop/)

product_category
Стовбець	Тип даних	Обов'язкове поле	Коментар
product_category_id	varchar(72)	Так	Ідентифікатор групи продукту
product_category_title	varchar(255)	Так	Назва групи продукту

product_unit
Стовбець	Тип даних	Обов'язкове поле	Коментар
product_unit_id	varchar(72)	Так	Ідентифікатор одиниці вимірювання
product_unit_title	varchar(255)	Так	Назва одиниці вимірювання
product_unit_not_allow_fraction	tinyint(1)	Ні	Не дозволяти дробове значення (за замовчуванням 0)

product_pack
Стовбець	Тип даних	Обов'язкове поле	Коментар
product_pack_id	varchar(72)	Так	Ідентифікатор упаковки
product_pack_product_id	varchar(72)	Так	Ідентифікатор продукту
product_pack_title	varchar(192)	Так	Назва упаковки
product_pack_amount	int	Так	Кількість одиниць в упаковці
product_pack_barcode	varchar(72)	Ні	Штрих-код упаковки

scheme
Стовбець	Тип даних	Обов'язкове поле	Коментар
scheme_id	varchar(72)	Ні	Ідентифікатор схеми
scheme_product_id	varchar(72)	Ні	Ідентифікатор продукту (остаточного)




scheme_det
Стовбець	Тип даних	Обов'язкове поле	Коментар
scheme_det_id	varchar(72)	Ні-	Ідентифікатор деталізації схеми
scheme_det_scheme_id	varchar(72)	Ні	Ідентифікатор схеми
scheme_det_product_id	varchar(72)	Ні	Ідентифікатор продукту (з чого складається)
scheme_det_amount	float unsigned	Ні	Кількість (з чого складається)

Warehouse
Path : unit/warehouse/cu	
Стовбець	Тип даних	Обов'язкове поле	Коментар
warehouse_id	varchar(72)	Так	Ідентифікатор складу
warehouse_title	varchar(255)	Так	Назва складу
warehouse_local	tinyint(1)	Так	Внутрішній склад
warehouse_tc	timestamp	Так	
warehouse_tm	timestamp	Ні	
warehouse_delete	tinyint(1)	Так	

zone
Стовбець	Тип даних	Обов'язкове поле	Коментар
zone_id	varchar(72)	Так	Ідентифікатор зони складу
zone_title	varchar(255)	Ні	Назва зони складу
zone_zone_type_id	varchar(72)	Так	Ідентифікатор типу зони
zone_x	bigint(20)	Ні	Ширина зони
zone_y	bigint(20)	Ні	Висота зони
zone_z	bigint(20)	Ні	Глибина зони
zone_warehouse_id	varchar(72)	Ні	Ідентифікатор складу

Warehouse
Path : unit/warehouse/cu	
Значення	Опис
MAIN	Основний (/wms-desktop/)
WHOUSE2432	Тестовий 2432 (/whouse2432/wms-desktop/)

