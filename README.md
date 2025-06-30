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

