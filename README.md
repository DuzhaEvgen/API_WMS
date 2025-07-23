Таблиця	|	Стовпець	|	Тип даних	|	Обов’язковий	|	Коментар	|
motivation_by_tasks	|	motivation_by_tasks_id	|	varchar(72)	|	NO	|		|
motivation_by_tasks	|	motivation_by_tasks_task_title	|	varchar(255)	|	YES	|	Наименование задачи	|
motivation_by_tasks	|	motivation_by_tasks_user_id	|	varchar(72)	|	NO	|	Пользователь исполнитель	|
motivation_by_tasks	|	motivation_by_tasks_task_type_id	|	varchar(72)	|	YES	|	Тип задачи	|
motivation_by_tasks	|	motivation_by_tasks_task_amount	|	decimal(10,4)	|	YES	|	Количество единиц	|
motivation_by_tasks	|	motivation_by_tasks_task_amount_art	|	int(11)	|	YES	|	Количество артикулов	|
motivation_by_tasks	|	motivation_by_tasks_task_det_amount	|	int(11)	|	YES	|	Количество строк	|
motivation_by_tasks	|	motivation_by_tasks_task_tc	|	timestamp	|	YES	|	Время создания	|
motivation_by_tasks	|	motivation_by_tasks_task_finish	|	timestamp	|	YES	|	Время завершения	|
motivation_by_tasks	|	motivation_by_tasks_tc	|	timestamp	|	YES	|		|
motivation_by_tasks	|	motivation_by_tasks_tm	|	timestamp	|	YES	|		|
	|		|		|		|		|
Таблиця	|	Стовпець	|	Тип даних	|	Обов’язковий	|	Коментар	|
task_type	|	task_type_id	|	varchar(72)	|	NO	|		|
task_type	|	task_type_title	|	varchar(255)	|	YES	|		|
task_type	|	task_type_tc	|	timestamp	|	NO	|		|
task_type	|	task_type_tm	|	timestamp	|	YES	|		|
	|		|		|		|		|
Таблиця	|	Стовпець	|	Тип даних	|	Обов’язковий	|	Коментар	|
zkt_log	|	zkt_log_id	|	bigint(20) unsigned	|	NO	|		|
zkt_log	|	zkt_log_user_code	|	bigint(20) unsigned	|	YES	|		|
zkt_log	|	zkt_log_date	|	datetime	|	NO	|		|
zkt_log	|	zkt_log_zkt_type_id	|	int(10) unsigned	|	NO	|		|
zkt_log	|	zkt_log_zkt_state_id	|	int(10) unsigned	|	YES	|		|
zkt_log	|	zkt_log_zkt_code_id	|	int(10) unsigned	|	YES	|		|
zkt_log	|	zkt_log_tc	|	timestamp	|	NO	|		|
zkt_log	|	zkt_log_tm	|	timestamp	|	YES	|		|
	|		|		|		|		|
Таблиця	|	Стовпець	|	Тип даних	|	Обов’язковий	|	Коментар	|
cell_position	|	cell_position_id	|	varchar(72)	|	NO	|		|
cell_position	|	cell_position_rack_id	|	varchar(72)	|	YES	|		|
cell_position	|	cell_position_rack_column_id	|	varchar(72)	|	YES	|		|
cell_position	|	cell_position_rack_row_id	|	varchar(72)	|	YES	|		|
cell_position	|	cell_position_tc	|	timestamp	|	NO	|		|
cell_position	|	cell_position_tm	|	timestamp	|	YES	|		|
	|		|		|		|		|
Таблиця	|	Стовпець	|	Тип даних	|	Обов’язковий	|	Коментар	|
user_role	|	user_role_id	|	varchar(72)	|	NO	|		|
user_role	|	user_role_title	|	varchar(255)	|	YES	|		|
user_role	|	user_role_type_user_role_id	|	varchar(72)	|	YES	|		|
user_role	|	user_role_acceptance	|	tinyint(4)	|	YES	|		|
user_role	|	user_role_tc	|	timestamp	|	NO	|		|
user_role	|	user_role_tm	|	timestamp	|	YES	|		|
	|		|		|		|		|
Таблиця	|	Стовпець	|	Тип даних	|	Обов’язковий	|	Коментар	|
abc_classifiers	|	abc_classifier	|	varchar(72)	|	NO	|		|
abc_classifiers	|	abc_classifiers_tc	|	timestamp	|	NO	|		|
abc_classifiers	|	abc_classifiers_tm	|	timestamp	|	YES	|		|
billing_tariff_plan	|	billing_tariff_plan_id	|	varchar(72)	|	NO	|		|
billing_tariff_plan	|	billing_tariff_plan_title	|	varchar(255)	|	YES	|		|
billing_tariff_plan	|	billing_tariff_plan_description	|	varchar(255)	|	YES	|		|
billing_tariff_plan	|	billing_tariff_plan_tc	|	timestamp	|	NO	|		|
billing_tariff_plan	|	billing_tariff_plan_tm	|	timestamp	|	YES	|		|
	|		|		|		|		|
Таблиця	|	Стовпець	|	Тип даних	|	Обов’язковий	|	Коментар	|
user	|	user_id	|	varchar(72)	|	NO	|		|
user	|	user_login	|	varchar(255)	|	YES	|		|
user	|	user_email	|	varchar(255)	|	YES	|		|
user	|	user_password	|	varchar(255)	|	YES	|		|
user	|	user_FIO	|	varchar(255)	|	YES	|		|
user	|	user_user_role_id	|	varchar(72)	|	YES	|		|
user	|	user_warehouse_id	|	varchar(72)	|	YES	|		|
user	|	user_fp	|	varchar(255)	|	YES	|		|
user	|	user_code	|	varchar(255)	|	YES	|		|
user	|	user_tc	|	timestamp	|	NO	|		|
user	|	user_tm	|	timestamp	|	YES	|		|
user	|	user_lang_id	|	varchar(72)	|	YES	|		|
	|		|		|		|		|
Таблиця	|	Стовпець	|	Тип даних	|	Обов’язковий	|	Коментар	|
product_type	|	product_type_id	|	varchar(72)	|	NO	|		|
product_type	|	product_type_title	|	varchar(255)	|	NO	|		|
product_type	|	product_type_product_group_id	|	varchar(72)	|	YES	|		|
product_type	|	product_type_tc	|	timestamp	|	NO	|		|
product_type	|	product_type_tm	|	timestamp	|	YES	|		|
	|		|		|		|		|
Таблиця	|	Стовпець	|	Тип даних	|	Обов’язковий	|	Коментар	|
bi_settings	|	bi_settings_id	|	varchar(72)	|	NO	|	ID	|
bi_settings	|	bi_settings_title	|	varchar(255)	|	NO	|	Наименование	|
bi_settings	|	bi_settings_value	|	varchar(255)	|	NO	|	Значение	|
bi_settings	|	bi_settings_tc	|	timestamp	|	YES	|		|
bi_settings	|	bi_settings_tm	|	timestamp	|	YES	|		|
	|		|		|		|		|
Таблиця	|	Стовпець	|	Тип даних	|	Обов’язковий	|	Коментар	|
document_mail	|	document_mail_id	|	varchar(72)	|	NO	|		|
document_mail	|	document_mail_title	|	varchar(255)	|	NO	|		|
document_mail	|	document_mail_tc	|	timestamp	|	NO	|		|
document_mail	|	document_mail_tm	|	timestamp	|	YES	|		|
	|		|		|		|		|
Таблиця	|	Стовпець	|	Тип даних	|	Обов’язковий	|	Коментар	|
sys_migration_versions	|	migration_versions_version	|	varchar(255)	|	NO	|		|
sys_migration_versions	|	migration_versions_executed_at	|	datetime	|	YES	|		|
sys_migration_versions	|	migration_versions_execution_time	|	int(11)	|	YES	|		|
product_group_zone	|	product_group_zone_id	|	varchar(72)	|	NO	|		|
product_group_zone	|	product_group_zone_product_group_id	|	varchar(72)	|	NO	|		|
product_group_zone	|	product_group_zone_zone_id	|	varchar(72)	|	NO	|		|
product_group_zone	|	product_group_zone_tc	|	timestamp	|	NO	|		|
product_group_zone	|	product_group_zone_tm	|	timestamp	|	YES	|		|
content	|	content_id	|	varchar(72)	|	NO	|		|
content	|	content_cell_id	|	varchar(72)	|	YES	|		|
content	|	content_tare_id	|	varchar(72)	|	YES	|		|
content	|	content_product_id	|	varchar(72)	|	YES	|		|
content	|	content_product_barcode_id	|	varchar(72)	|	YES	|		|
content	|	content_product_status_id	|	int(11)	|	NO	|		|
content	|	content_amount	|	decimal(10,3) unsigned	|	YES	|		|
content	|	content_user_id	|	varchar(72)	|	YES	|		|
content	|	content_acceptance_date	|	datetime	|	YES	|	Дата приёмки	|
content	|	content_expiration_date	|	date	|	YES	|	Срок годности	|
content	|	content_batch_code	|	varchar(72)	|	YES	|	Партия	|
content	|	content_tc	|	timestamp	|	NO	|		|
content	|	content_tm	|	timestamp	|	YES	|		|
content	|	content_manufacturer_id	|	varchar(72)	|	YES	|		|
content	|	content_flag_defect	|	tinyint(2)	|	NO	|		|
content	|	content_seller_id	|	varchar(72)	|	YES	|		|
content	|	content_warehouse_number_erp	|	varchar(72)	|	YES	|		|
content	|	content_warehouse_title_erp	|	varchar(72)	|	YES	|		|
content	|	content_id_int	|	bigint(20) unsigned	|	NO	|		|
package	|	package_id	|	int(11)	|	NO	|		|
package	|	package_document_id	|	varchar(72)	|	YES	|		|
package	|	package_document_type_id	|	varchar(72)	|	NO	|		|
package	|	package_document_tc	|	timestamp	|	YES	|		|
package	|	package_document_status_id	|	varchar(72)	|	YES	|		|
package	|	package_json	|	mediumtext	|	YES	|		|
package	|	package_status	|	tinyint(4)	|	YES	|		|
package	|	package_tc	|	timestamp	|	YES	|		|
product_parameter_length	|	product_parameter_length_id	|	varchar(72)	|	NO	|		|
product_parameter_length	|	product_parameter_length_title	|	varchar(255)	|	YES	|		|
product_parameter_length	|	product_parameter_length_barcode	|	varchar(72)	|	YES	|		|
product_parameter_length	|	product_parameter_length_tc	|	timestamp	|	NO	|		|
product_parameter_length	|	product_parameter_length_tm	|	timestamp	|	YES	|		|
report_inventory_log	|	report_inventory_log_id	|	bigint(20)	|	NO	|		|
report_inventory_log	|	report_inventory_log_task_id	|	varchar(72)	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_title	|	varchar(255)	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_type_title	|	varchar(255)	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_start	|	timestamp	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_finish	|	timestamp	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_user_id	|	varchar(72)	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_det_id	|	varchar(72)	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_det_user_id	|	varchar(72)	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_det_cell_id	|	varchar(72)	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_det_tare_id	|	varchar(72)	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_det_amount_task	|	decimal(10,4)	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_det_amount_fact	|	decimal(10,4)	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_det_tm	|	timestamp	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_det_product_id	|	varchar(72)	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_det_product_art	|	varchar(72)	|	YES	|		|
report_inventory_log	|	report_inventory_log_task_det_product_title	|	varchar(255)	|	YES	|		|
report_inventory_log	|	report_inventory_log_content_expiration_date	|	date	|	YES	|		|
report_inventory_log	|	report_inventory_log_content_batch_code	|	varchar(72)	|	YES	|		|
report_inventory_log	|	report_inventory_log_tc	|	timestamp	|	NO	|		|
report_inventory_log	|	report_inventory_log_tm	|	timestamp	|	YES	|		|
sys_printer_driver	|	printer_driver_id	|	varchar(72)	|	NO	|		|
sys_printer_driver	|	printer_driver_title	|	varchar(192)	|	NO	|		|
sys_printer_driver	|	printer_driver_tc	|	timestamp	|	NO	|		|
sys_printer_driver	|	printer_driver_tm	|	timestamp	|	YES	|		|
billing_document_det	|	billing_document_det_id	|	varchar(72)	|	NO	|		|
billing_document_det	|	billing_document_det_document_id	|	varchar(72)	|	NO	|		|
billing_document_det	|	billing_document_det_service_id	|	varchar(72)	|	NO	|		|
billing_document_det	|	billing_document_det_warehouse_id	|	varchar(72)	|	NO	|		|
billing_document_det	|	billing_document_det_user_id	|	varchar(72)	|	NO	|		|
billing_document_det	|	billing_document_det_date	|	date	|	NO	|		|
billing_document_det	|	billing_document_det_quantity	|	decimal(20,4)	|	NO	|		|
billing_document_det	|	billing_document_det_sum	|	decimal(20,2)	|	NO	|		|
billing_document_det	|	billing_document_det_discount	|	decimal(20,2)	|	NO	|		|
billing_document_det	|	billing_document_det_tc	|	timestamp	|	NO	|		|
billing_document_det	|	billing_document_det_tm	|	timestamp	|	YES	|		|
counterparty	|	counterparty_id	|	varchar(72)	|	NO	|	Идентификатор контрагента	|
counterparty	|	counterparty_counterparty_type_id	|	varchar(72)	|	YES	|	Тип контрагента	|
counterparty	|	counterparty_document_legal_person_id	|	varchar(72)	|	YES	|		|
counterparty	|	counterparty_title	|	varchar(255)	|	YES	|	Наименование контрагента (для юр.лиц)	|
counterparty	|	counterparty_f	|	varchar(255)	|	YES	|	Фамилия контрагента	|
counterparty	|	counterparty_i	|	varchar(255)	|	YES	|	Имя контрагента	|
counterparty	|	counterparty_o	|	varchar(255)	|	YES	|	Отчество контрагента	|
counterparty	|	counterparty_phone_number	|	varchar(255)	|	YES	|	Мобильный номер контрагента	|
counterparty	|	counterparty_region	|	varchar(255)	|	YES	|	Регион контрагента	|
counterparty	|	counterparty_city	|	varchar(255)	|	YES	|	Город контрагента	|
counterparty	|	counterparty_street	|	varchar(255)	|	YES	|	Адрес контрагента	|
counterparty	|	counterparty_building	|	varchar(255)	|	YES	|	Номер дома контрагента	|
counterparty	|	counterparty_flat	|	varchar(255)	|	YES	|	Квартира контрагента	|
counterparty	|	counterparty_counterparty_warehouse_id	|	varchar(72)	|	YES	|		|
counterparty	|	counterparty_tc	|	timestamp	|	NO	|		|
counterparty	|	counterparty_tm	|	timestamp	|	YES	|		|
counterparty	|	counterparty_seller_id	|	varchar(72)	|	YES	|		|
sys_menu_ui_params_type	|	menu_ui_params_type_id	|	varchar(72)	|	NO	|		|
sys_menu_ui_params_type	|	menu_ui_params_type_title	|	varchar(100)	|	NO	|		|
sys_menu_ui_params_type	|	menu_ui_params_type_type	|	enum('string','array','bool','directory')	|	NO	|		|
sys_menu_ui_params_type	|	menu_ui_params_type_directory	|	varchar(192)	|	YES	|		|
sys_menu_ui_params_type	|	menu_ui_params_type_comment	|	varchar(192)	|	YES	|		|
sys_menu_ui_params_type	|	menu_ui_params_type_tc	|	timestamp	|	NO	|		|
sys_menu_ui_params_type	|	menu_ui_params_type_tm	|	timestamp	|	YES	|		|
sys_printer_label_size	|	printer_label_size_id	|	varchar(72)	|	NO	|		|
sys_printer_label_size	|	printer_label_size_title	|	varchar(192)	|	NO	|		|
sys_printer_label_size	|	printer_label_size_height	|	int(11)	|	NO	|		|
sys_printer_label_size	|	printer_label_size_width	|	int(11)	|	NO	|		|
sys_printer_label_size	|	printer_label_size_tc	|	timestamp	|	NO	|		|
sys_printer_label_size	|	printer_label_size_tm	|	timestamp	|	YES	|		|
sys_printer_label_size	|	printer_label_size_delete	|	tinyint(1)	|	NO	|		|
inventory_sent	|	inventory_sent_id	|	bigint(20)	|	NO	|		|
inventory_sent	|	inventory_sent_document_id	|	varchar(72)	|	YES	|		|
inventory_sent	|	inventory_sent_user_id	|	varchar(72)	|	YES	|		|
inventory_sent	|	inventory_sent_content_product_id	|	varchar(72)	|	YES	|		|
inventory_sent	|	inventory_sent_content_amount	|	decimal(10,4)	|	YES	|		|
inventory_sent	|	inventory_sent_content_expiration_date	|	date	|	YES	|		|
inventory_sent	|	inventory_sent_content_batch_code	|	varchar(72)	|	YES	|		|
inventory_sent	|	inventory_sent_content_flag_defect	|	tinyint(2)	|	NO	|		|
inventory_sent	|	inventory_sent_tc	|	timestamp	|	NO	|		|
inventory_sent	|	inventory_sent_tm	|	timestamp	|	YES	|		|
document_det	|	document_det_id	|	varchar(72)	|	NO	|		|
document_det	|	document_det_document_id	|	varchar(72)	|	YES	|		|
document_det	|	document_det_date_time	|	datetime	|	YES	|		|
document_det	|	document_det_product_id	|	varchar(72)	|	YES	|		|
document_det	|	document_det_product_status_id	|	int(11)	|	NO	|		|
document_det	|	document_det_tare_id	|	varchar(72)	|	YES	|		|
document_det	|	document_det_cell_id	|	varchar(72)	|	YES	|		|
document_det	|	document_det_amount	|	decimal(10,3) unsigned	|	YES	|		|
document_det	|	document_det_defect	|	tinyint(1)	|	NO	|		|
document_det	|	document_det_expiration_date	|	date	|	YES	|	Срок годности	|
document_det	|	document_det_batch_code	|	varchar(255)	|	YES	|	Номер партии	|
document_det	|	document_det_tc	|	timestamp	|	NO	|		|
document_det	|	document_det_tm	|	timestamp	|	YES	|		|
document_det	|	document_det_ordinal_number	|	mediumint(9)	|	YES	|		|
document_det	|	document_det_manufacturer_id	|	varchar(72)	|	YES	|	Внешний ключ на производителя товара	|
counterparty_type	|	counterparty_type_id	|	varchar(72)	|	NO	|		|
counterparty_type	|	counterparty_type_title	|	varchar(255)	|	NO	|		|
counterparty_type	|	counterparty_type_tc	|	timestamp	|	NO	|		|
counterparty_type	|	counterparty_type_tm	|	timestamp	|	YES	|		|
billing_report	|	billing_report_id	|	bigint(20)	|	NO	|		|
billing_report	|	billing_report_date	|	date	|	NO	|		|
billing_report	|	billing_report_task_id	|	varchar(72)	|	YES	|		|
billing_report	|	billing_report_seller_id	|	varchar(72)	|	YES	|		|
billing_report	|	billing_report_service_id	|	varchar(72)	|	YES	|		|
billing_report	|	billing_report_warehouse_id	|	varchar(72)	|	YES	|		|
billing_report	|	billing_report_value	|	decimal(20,4)	|	YES	|	Значение	|
billing_report	|	billing_report_sum	|	decimal(20,2)	|	YES	|	Сумма	|
billing_report	|	billing_report_discount	|	decimal(20,2)	|	YES	|	Скидка	|
billing_report	|	billing_report_tc	|	timestamp	|	NO	|		|
billing_report	|	billing_report_tm	|	timestamp	|	YES	|		|
billing_report	|	billing_report_user_id	|	varchar(72)	|	YES	|		|
scheme	|	scheme_id	|	varchar(72)	|	NO	|	Идентификатор схемы	|
scheme	|	scheme_product_id	|	varchar(72)	|	NO	|	Идентификатор продукта (итогового)	|
scheme	|	scheme_tc	|	timestamp	|	NO	|		|
scheme	|	scheme_tm	|	timestamp	|	YES	|		|
zkt_code	|	zkt_code_id	|	bigint(20) unsigned	|	NO	|		|
zkt_code	|	zkt_code_title	|	varchar(255)	|	NO	|		|
zkt_code	|	zkt_code_tc	|	timestamp	|	NO	|		|
zkt_code	|	zkt_code_tm	|	timestamp	|	YES	|		|
return_reason	|	return_reason_id	|	varchar(72)	|	NO	|	ID 1C	|
return_reason	|	return_reason_value	|	varchar(255)	|	NO	|	Значение	|
return_reason	|	return_reason_zone_id	|	varchar(72)	|	YES	|		|
return_reason	|	return_reason_tc	|	timestamp	|	YES	|		|
return_reason	|	return_reason_tm	|	timestamp	|	YES	|		|
return_reason	|	return_reason_number	|	mediumint(9)	|	YES	|		|
product_group	|	product_group_id	|	varchar(72)	|	NO	|		|
product_group	|	product_group_title	|	varchar(255)	|	YES	|		|
product_group	|	product_group_package_title	|	varchar(255)	|	YES	|		|
product_group	|	product_group_tc	|	timestamp	|	NO	|		|
product_group	|	product_group_tm	|	timestamp	|	YES	|		|
product_parameter_width	|	product_parameter_width_id	|	varchar(72)	|	NO	|		|
product_parameter_width	|	product_parameter_width_title	|	varchar(255)	|	YES	|		|
product_parameter_width	|	product_parameter_width_barcode	|	varchar(72)	|	YES	|		|
product_parameter_width	|	product_parameter_width_tc	|	timestamp	|	NO	|		|
product_parameter_width	|	product_parameter_width_tm	|	timestamp	|	YES	|		|
type_user_role	|	type_user_role_id	|	varchar(72)	|	NO	|		|
type_user_role	|	type_user_role_title	|	varchar(255)	|	YES	|		|
type_user_role	|	type_user_role_tc	|	timestamp	|	NO	|		|
type_user_role	|	type_user_role_tm	|	timestamp	|	YES	|		|
np_warehouse	|	np_warehouse_id	|	varchar(72)	|	NO	|		|
np_warehouse	|	np_warehouse_description	|	varchar(255)	|	YES	|		|
np_warehouse	|	np_warehouse_short_address	|	varchar(255)	|	YES	|		|
np_warehouse	|	np_warehouse_np_city_id	|	varchar(72)	|	YES	|		|
np_warehouse	|	np_warehouse_settlement_ref	|	varchar(255)	|	YES	|		|
np_warehouse	|	np_warehouse_tc	|	timestamp	|	NO	|		|
np_warehouse	|	np_warehouse_tm	|	timestamp	|	YES	|		|
sys_menu_ui	|	menu_ui_id	|	varchar(72)	|	NO	|		|
sys_menu_ui	|	menu_ui_parent_menu_ui_id	|	varchar(72)	|	YES	|		|
sys_menu_ui	|	menu_ui_menu_ui_type_id	|	varchar(72)	|	YES	|		|
sys_menu_ui	|	menu_ui_process_name	|	varchar(192)	|	NO	|		|
sys_menu_ui	|	menu_ui_title	|	varchar(192)	|	NO	|		|
sys_menu_ui	|	menu_ui_icon	|	varchar(192)	|	YES	|		|
sys_menu_ui	|	menu_ui_parent_query	|	varchar(192)	|	YES	|		|
sys_menu_ui	|	menu_ui_position	|	int(11)	|	NO	|		|
sys_menu_ui	|	menu_ui_enable	|	tinyint(1)	|	NO	|		|
sys_menu_ui	|	menu_ui_delete	|	tinyint(1)	|	NO	|		|
sys_menu_ui	|	menu_ui_tc	|	timestamp	|	NO	|		|
sys_menu_ui	|	menu_ui_tm	|	timestamp	|	YES	|		|
tare_type	|	tare_type_id	|	varchar(72)	|	NO	|		|
tare_type	|	tare_type_title	|	varchar(255)	|	YES	|		|
tare_type	|	tare_type_tc	|	timestamp	|	NO	|		|
tare_type	|	tare_type_tm	|	timestamp	|	YES	|		|
tare_type	|	tare_type_x	|	float(10,2)	|	NO	|	Width (Ширина) X	|
tare_type	|	tare_type_y	|	float(10,2)	|	NO	|	Height (Высота) Y (max)	|
tare_type	|	tare_type_z	|	float(10,2)	|	NO	|	Length (Довжина) Z	|
tare_type	|	tare_type_m	|	float(10,3)	|	NO	|	Weight (Вес) M (max)	|
scheme_det	|	scheme_det_id	|	varchar(72)	|	NO	|	Идентификатор детализации схемы	|
scheme_det	|	scheme_det_scheme_id	|	varchar(72)	|	NO	|	Идентификатор схемы	|
scheme_det	|	scheme_det_product_id	|	varchar(72)	|	NO	|	Идентификатор продукта (из чего состоит)	|
scheme_det	|	scheme_det_amount	|	decimal(10,4) unsigned	|	NO	|	Количество (из чего состоит)	|
scheme_det	|	scheme_det_tc	|	timestamp	|	NO	|		|
scheme_det	|	scheme_det_tm	|	timestamp	|	YES	|		|
task	|	task_id	|	varchar(72)	|	NO	|		|
task	|	task_document_id	|	varchar(72)	|	YES	|		|
task	|	task_task_status_id	|	varchar(72)	|	YES	|		|
task	|	task_task_type_id	|	varchar(72)	|	YES	|		|
task	|	task_title	|	varchar(255)	|	YES	|		|
task	|	task_barcode	|	bigint(11)	|	NO	|		|
task	|	task_tc	|	timestamp	|	NO	|		|
task	|	task_tm	|	timestamp	|	YES	|		|
task	|	task_start	|	timestamp	|	YES	|		|
task	|	task_finish	|	timestamp	|	YES	|		|
task	|	task_user_id	|	varchar(72)	|	YES	|		|
task	|	task_return_request_number	|	varchar(72)	|	YES	|		|
task	|	task_seller_id	|	varchar(72)	|	YES	|		|
task	|	task_warehouse_id	|	varchar(72)	|	YES	|		|
task	|	task_create_user_id	|	varchar(72)	|	YES	|		|
task	|	task_update_user_id	|	varchar(72)	|	YES	|		|
task	|	task_process_start_user_id	|	varchar(72)	|	YES	|		|
task	|	task_process_finish_user_id	|	varchar(72)	|	YES	|		|
task	|	task_prev_task_id	|	varchar(72)	|	YES	|		|
document_priority	|	document_priority_id	|	varchar(72)	|	NO	|		|
document_priority	|	document_priority_title	|	varchar(255)	|	YES	|		|
document_priority	|	document_priority_tc	|	timestamp	|	NO	|		|
document_priority	|	document_priority_tm	|	timestamp	|	NO	|		|
rack_class	|	rack_class_id	|	varchar(72)	|	NO	|		|
rack_class	|	rack_class_amount_row	|	bigint(20)	|	YES	|		|
rack_class	|	rack_class_amount_column	|	bigint(20)	|	YES	|		|
rack_class	|	rack_class_title	|	varchar(255)	|	YES	|		|
rack_class	|	rack_class_width	|	bigint(20)	|	YES	|		|
rack_class	|	rack_class_height	|	bigint(20)	|	YES	|		|
rack_class	|	rack_class_long	|	bigint(20)	|	YES	|		|
rack_class	|	rack_class_tc	|	timestamp	|	NO	|		|
rack_class	|	rack_class_tm	|	timestamp	|	YES	|		|
sys_menu_tsd_rights	|	menu_tsd_rights_id	|	varchar(72)	|	NO	|		|
sys_menu_tsd_rights	|	menu_tsd_rights_menu_tsd_id	|	varchar(72)	|	YES	|		|
sys_menu_tsd_rights	|	menu_tsd_rights_user_role_id	|	varchar(72)	|	NO	|		|
sys_menu_tsd_rights	|	menu_tsd_rights_tc	|	timestamp	|	NO	|		|
sys_menu_tsd_rights	|	menu_tsd_rights_tm	|	timestamp	|	YES	|		|
product_brand	|	product_brand_id	|	varchar(72)	|	NO	|		|
product_brand	|	product_brand_title	|	varchar(255)	|	NO	|		|
product_brand	|	product_brand_tc	|	timestamp	|	NO	|		|
product_brand	|	product_brand_tm	|	timestamp	|	YES	|		|
exchange_status	|	exchange_status_id	|	int(10) unsigned	|	NO	|		|
exchange_status	|	exchange_status_title	|	varchar(255)	|	NO	|		|
exchange_status	|	exchange_status_tc	|	timestamp	|	NO	|		|
exchange_status	|	exchange_status_tm	|	timestamp	|	YES	|		|
report_inventory_queue	|	report_inventory_queue_id	|	bigint(20)	|	NO	|		|
report_inventory_queue	|	report_inventory_queue_task_tm	|	timestamp	|	YES	|	Время последней выгрузки отчета	|
report_inventory_queue	|	report_inventory_queue_tc	|	timestamp	|	NO	|		|
report_inventory_queue	|	report_inventory_queue_tm	|	timestamp	|	YES	|		|
abc_cell	|	abc_cell_id	|	varchar(72)	|	NO	|		|
abc_cell	|	abc_cell_abc_classifier	|	varchar(72)	|	YES	|		|
abc_cell	|	abc_cell_tc	|	timestamp	|	NO	|		|
abc_cell	|	abc_cell_tm	|	timestamp	|	YES	|		|
warehouse_uri	|	warehouse_uri_id	|	varchar(72)	|	NO	|		|
warehouse_uri	|	warehouse_uri_warehouse_id	|	varchar(72)	|	NO	|		|
warehouse_uri	|	warehouse_uri_uri	|	varchar(255)	|	NO	|	Базовый адрес для запроса на склад	|
warehouse_uri	|	warehouse_uri_tc	|	timestamp	|	NO	|		|
warehouse_uri	|	warehouse_uri_tm	|	timestamp	|	YES	|		|
warehouse_uri	|	warehouse_uri_is_active	|	tinyint(1) unsigned	|	NO	|		|
linking_cell_and_printer	|	linking_cell_and_printer_id	|	varchar(192)	|	NO	|		|
linking_cell_and_printer	|	linking_cell_and_printer_cell_id	|	varchar(192)	|	NO	|		|
linking_cell_and_printer	|	linking_cell_and_printer_printer_id	|	varchar(192)	|	NO	|		|
linking_cell_and_printer	|	linking_cell_and_printer_tc	|	timestamp	|	NO	|		|
linking_cell_and_printer	|	linking_cell_and_printer_tm	|	timestamp	|	YES	|		|
np_ownership_type	|	np_ownership_type_id	|	varchar(72)	|	NO	|		|
np_ownership_type	|	np_ownership_type_title	|	varchar(255)	|	NO	|		|
np_ownership_type	|	np_ownership_type_tc	|	timestamp	|	NO	|		|
np_ownership_type	|	np_ownership_type_tm	|	timestamp	|	YES	|		|
rack_column	|	rack_column_id	|	varchar(72)	|	NO	|		|
rack_column	|	rack_column_level	|	bigint(20)	|	YES	|		|
rack_column	|	rack_column_tc	|	timestamp	|	NO	|		|
rack_column	|	rack_column_tm	|	timestamp	|	YES	|		|
sys_menu_ui_params	|	menu_ui_params_id	|	varchar(72)	|	NO	|		|
sys_menu_ui_params	|	menu_ui_params_menu_ui_id	|	varchar(72)	|	NO	|		|
sys_menu_ui_params	|	menu_ui_params_menu_ui_params_type_id	|	varchar(72)	|	NO	|		|
sys_menu_ui_params	|	menu_ui_params_value_string	|	varchar(192)	|	YES	|		|
sys_menu_ui_params	|	menu_ui_params_value_array	|	text	|	YES	|		|
sys_menu_ui_params	|	menu_ui_params_value_bool	|	tinyint(1)	|	NO	|		|
sys_menu_ui_params	|	menu_ui_params_tc	|	timestamp	|	YES	|		|
sys_menu_ui_params	|	menu_ui_params_tm	|	timestamp	|	YES	|		|
user_warehouse	|	user_warehouse_id	|	varchar(72)	|	NO	|		|
user_warehouse	|	user_warehouse_user_id	|	varchar(72)	|	NO	|		|
user_warehouse	|	user_warehouse_warehouse_id	|	varchar(72)	|	NO	|		|
user_warehouse	|	user_warehouse_tc	|	timestamp	|	NO	|		|
user_warehouse	|	user_warehouse_tm	|	timestamp	|	YES	|		|
billing_type	|	billing_type_id	|	varchar(72)	|	NO	|		|
billing_type	|	billing_type_title	|	varchar(255)	|	NO	|		|
exchange_log	|	exchange_log_id	|	varchar(72)	|	NO	|		|
exchange_log	|	exchange_log_tc	|	timestamp	|	NO	|		|
exchange_log	|	exchange_log_tm	|	timestamp	|	YES	|		|
exchange_log	|	exchange_log_data	|	mediumtext	|	YES	|		|
exchange_log	|	exchange_log_response	|	mediumtext	|	YES	|		|
exchange_log	|	exchange_log_user_id	|	varchar(72)	|	YES	|		|
exchange_log	|	exchange_log_request_uri	|	varchar(255)	|	YES	|		|
exchange_log	|	exchange_log_recipient	|	varchar(255)	|	YES	|	Ключ получателя в ВМС (необходимо для определения способа переотправки)	|
document_service_type	|	document_service_type_id	|	varchar(72)	|	NO	|		|
document_service_type	|	document_service_type_title	|	varchar(255)	|	NO	|		|
document_service_type	|	document_service_type_tc	|	timestamp	|	NO	|		|
document_service_type	|	document_service_type_tm	|	timestamp	|	YES	|		|
billing_report_cron	|	billing_report_cron_id	|	bigint(20)	|	NO	|		|
billing_report_cron	|	billing_report_cron_date	|	date	|	NO	|		|
billing_report_cron	|	billing_report_cron_message	|	varchar(255)	|	YES	|		|
billing_report_cron	|	billing_report_cron_tc	|	timestamp	|	NO	|		|
billing_report_cron	|	billing_report_cron_tm	|	timestamp	|	NO	|		|
repackaging_receiver	|	repackaging_receiver_id	|	varchar(72)	|	NO	|		|
repackaging_receiver	|	repackaging_receiver_product_id	|	varchar(72)	|	NO	|	Товар	|
repackaging_receiver	|	repackaging_receiver_name	|	varchar(255)	|	NO	|	Получатель	|
repackaging_receiver	|	repackaging_receiver_barcode	|	varchar(255)	|	NO	|	ШК получателя	|
repackaging_receiver	|	repackaging_receiver_tc	|	timestamp	|	YES	|		|
repackaging_receiver	|	repackaging_receiver_tm	|	timestamp	|	YES	|		|
sys_printer_journal	|	printer_journal_id	|	varchar(72)	|	NO	|		|
sys_printer_journal	|	printer_journal_printer_id	|	varchar(72)	|	NO	|		|
sys_printer_journal	|	printer_journal_printer_local_id	|	varchar(72)	|	YES	|		|
sys_printer_journal	|	printer_journal_file	|	varchar(192)	|	YES	|		|
sys_printer_journal	|	printer_journal_data	|	mediumtext	|	YES	|		|
sys_printer_journal	|	printer_journal_amount	|	int(11)	|	NO	|		|
sys_printer_journal	|	printer_journal_state	|	tinyint(1)	|	NO	|		|
sys_printer_journal	|	printer_journal_response	|	varchar(192)	|	YES	|		|
sys_printer_journal	|	printer_journal_task_id	|	varchar(72)	|	YES	|		|
sys_printer_journal	|	printer_journal_process_name	|	varchar(192)	|	YES	|		|
sys_printer_journal	|	printer_journal_stage	|	varchar(192)	|	YES	|		|
sys_printer_journal	|	printer_journal_user_id	|	varchar(72)	|	YES	|		|
sys_printer_journal	|	printer_journal_tc	|	timestamp	|	NO	|		|
sys_printer_journal	|	printer_journal_tm	|	timestamp	|	YES	|		|
sys_printer_journal	|	printer_journal_update_user_id	|	varchar(72)	|	YES	|		|
sys_printer_journal	|	printer_journal_create_user_id	|	varchar(72)	|	YES	|		|
report_not_in_stock	|	not_in_stock_id	|	bigint(20)	|	NO	|		|
report_not_in_stock	|	not_in_stock_document_id	|	varchar(72)	|	NO	|	Документ	|
report_not_in_stock	|	not_in_stock_product_id	|	varchar(72)	|	NO	|	Продукт	|
report_not_in_stock	|	not_in_stock_need	|	decimal(10,4) unsigned	|	YES	|	Кол-во по документу	|
report_not_in_stock	|	not_in_stock_exists	|	decimal(10,4) unsigned	|	YES	|	Кол-во по складу	|
report_not_in_stock	|	not_in_stock_defect	|	decimal(10,4) unsigned	|	YES	|	Кол-во с дефектом	|
report_not_in_stock	|	not_in_stock_expired	|	decimal(10,4) unsigned	|	YES	|	Кол-во с другим сроком годности	|
report_not_in_stock	|	not_in_stock_cell_block	|	decimal(10,4) unsigned	|	YES	|	Кол-во в заблокированных ячейках	|
report_not_in_stock	|	not_in_stock_not_found	|	decimal(10,4) unsigned	|	YES	|	Кол-во не найдено	|
report_not_in_stock	|	not_in_stock_tc	|	timestamp	|	YES	|		|
report_not_in_stock	|	not_in_stock_tm	|	timestamp	|	YES	|		|
sys_route_type	|	route_type_id	|	varchar(72)	|	NO	|		|
sys_route_type	|	route_type_title	|	varchar(192)	|	NO	|		|
sys_route_type	|	route_type_tc	|	timestamp	|	YES	|		|
sys_route_type	|	route_type_tm	|	timestamp	|	YES	|		|
zkt_type	|	zkt_type_id	|	bigint(20) unsigned	|	NO	|		|
zkt_type	|	zkt_type_title	|	varchar(255)	|	NO	|		|
zkt_type	|	zkt_type_tc	|	timestamp	|	NO	|		|
zkt_type	|	zkt_type_tm	|	timestamp	|	YES	|		|
sys_menu_ui_type	|	menu_ui_type_id	|	varchar(72)	|	NO	|		|
sys_menu_ui_type	|	menu_ui_type_title	|	varchar(100)	|	NO	|		|
sys_menu_ui_type	|	menu_ui_type_comment	|	varchar(192)	|	YES	|		|
sys_menu_ui_type	|	menu_ui_type_tc	|	timestamp	|	NO	|		|
sys_menu_ui_type	|	menu_ui_type_tm	|	timestamp	|	YES	|		|
np_city	|	np_city_id	|	varchar(72)	|	NO	|		|
np_city	|	np_city_title	|	varchar(255)	|	YES	|		|
np_city	|	np_city_tc	|	timestamp	|	NO	|		|
np_city	|	np_city_tm	|	timestamp	|	YES	|		|
product_kind_of	|	product_kind_of_id	|	varchar(72)	|	NO	|		|
product_kind_of	|	product_kind_of_title	|	varchar(255)	|	YES	|		|
product_kind_of	|	product_kind_of_product_type_id	|	varchar(72)	|	YES	|		|
product_kind_of	|	product_kind_of_accounting_expiration_date	|	tinyint(1) unsigned	|	YES	|	Учёт сроков годности при размещении	|
product_kind_of	|	product_kind_of_accounting_batch_code	|	tinyint(1) unsigned	|	YES	|	Учёт партий при размещении	|
product_kind_of	|	product_kind_of_tc	|	timestamp	|	NO	|		|
product_kind_of	|	product_kind_of_tm	|	timestamp	|	YES	|		|
user_employee	|	user_employee_id	|	varchar(72)	|	NO	|		|
user_employee	|	user_employee_fio	|	varchar(255)	|	NO	|		|
user_employee	|	user_employee_tc	|	timestamp	|	NO	|		|
user_employee	|	user_employee_tm	|	timestamp	|	YES	|		|
document_cargo_type	|	document_cargo_type_id	|	varchar(72)	|	NO	|		|
document_cargo_type	|	document_cargo_type_title	|	varchar(255)	|	NO	|		|
document_cargo_type	|	document_cargo_type_tc	|	timestamp	|	NO	|		|
document_cargo_type	|	document_cargo_type_tm	|	timestamp	|	YES	|		|
nk_barcode_log	|	nk_barcode_log_id	|	bigint(20) unsigned	|	NO	|		|
nk_barcode_log	|	nk_barcode_log_value	|	varchar(255)	|	NO	|		|
nk_barcode_log	|	nk_barcode_log_tc	|	timestamp	|	NO	|		|
nk_barcode_log	|	nk_barcode_log_tm	|	timestamp	|	YES	|		|
nk_barcode_log	|	nk_barcode_log_serial	|	varchar(255)	|	YES	|		|
manufacturer	|	manufacturer_id	|	varchar(72)	|	NO	|		|
manufacturer	|	manufacturer_code	|	varchar(50)	|	NO	|		|
manufacturer	|	manufacturer_title	|	varchar(255)	|	NO	|		|
manufacturer	|	manufacturer_tc	|	timestamp	|	NO	|		|
manufacturer	|	manufacturer_tm	|	timestamp	|	YES	|		|
user_zone	|	user_zone_id	|	varchar(72)	|	NO	|		|
user_zone	|	user_zone_user_id	|	varchar(72)	|	NO	|		|
user_zone	|	user_zone_zone_id	|	varchar(72)	|	NO	|		|
user_zone	|	user_zone_tc	|	timestamp	|	NO	|		|
user_zone	|	user_zone_tm	|	timestamp	|	YES	|		|
group_timesheet_log	|	group_timesheet_log_id	|	bigint(20) unsigned	|	NO	|		|
group_timesheet_log	|	group_timesheet_log_start	|	timestamp	|	NO	|		|
group_timesheet_log	|	group_timesheet_log_end	|	timestamp	|	YES	|		|
group_timesheet_log	|	group_timesheet_log_group_timesheet_id	|	varchar(72)	|	NO	|		|
group_timesheet_log	|	group_timesheet_log_tc	|	timestamp	|	NO	|		|
group_timesheet_log	|	group_timesheet_log_tm	|	timestamp	|	YES	|		|
incompatible_pko	|	incompatible_pko_id	|	varchar(72)	|	NO	|		|
incompatible_pko	|	incompatible_pko_product_kind_of_id_1	|	varchar(72)	|	NO	|		|
incompatible_pko	|	incompatible_pko_product_kind_of_id_2	|	varchar(72)	|	NO	|		|
incompatible_pko	|	incompatible_pko_tc	|	timestamp	|	NO	|		|
incompatible_pko	|	incompatible_pko_tm	|	timestamp	|	YES	|		|
route	|	route_id	|	varchar(72)	|	NO	|		|
route	|	route_title	|	varchar(255)	|	YES	|		|
route	|	route_number	|	varchar(72)	|	NO	|	Номер маршрута	|
route	|	route_driver	|	varchar(255)	|	NO	|	Наименование водителя	|
route	|	route_document_id	|	varchar(72)	|	NO	|		|
route	|	route_tc	|	timestamp	|	NO	|		|
route	|	route_tm	|	timestamp	|	YES	|		|
group_timesheet	|	group_timesheet_id	|	varchar(72)	|	NO	|		|
group_timesheet	|	group_timesheet_title	|	varchar(255)	|	NO	|		|
group_timesheet	|	group_timesheet_tc	|	timestamp	|	NO	|		|
group_timesheet	|	group_timesheet_tm	|	timestamp	|	YES	|		|
document_pdf	|	document_pdf_id	|	varchar(72)	|	NO	|		|
document_pdf	|	document_pdf_document_id	|	varchar(72)	|	NO	|		|
document_pdf	|	document_pdf_data	|	longtext	|	NO	|		|
document_pdf	|	document_pdf_amount	|	int(10) unsigned	|	YES	|		|
document_pdf	|	document_pdf_tc	|	timestamp	|	NO	|		|
document_pdf	|	document_pdf_tm	|	timestamp	|	YES	|		|
seller	|	seller_id	|	varchar(72)	|	NO	|		|
seller	|	seller_title	|	varchar(255)	|	YES	|		|
seller	|	seller_api_key	|	char(36)	|	YES	|	API-key	|
seller	|	seller_ref_sender	|	char(36)	|	YES	|	Sender	|
seller	|	seller_ref_city_sender	|	char(36)	|	YES	|	CitySender	|
seller	|	seller_ref_sender_address	|	char(36)	|	YES	|	SenderAddress	|
seller	|	seller_ref_contact_sender	|	char(36)	|	YES	|	ContactSender	|
seller	|	seller_phone	|	char(24)	|	YES	|	SendersPhone	|
seller	|	seller_agreement_number	|	varchar(255)	|	YES	|	Номер договора	|
seller	|	seller_agreement_date	|	varchar(32)	|	YES	|	Дата договора	|
seller	|	seller_agreement_date_end	|	varchar(32)	|	YES	|	Дата истечения договора	|
seller	|	seller_tariff_date_end	|	varchar(32)	|	YES	|	Дата окончания действующего тарифа	|
seller	|	seller_tc	|	timestamp	|	NO	|		|
seller	|	seller_tm	|	timestamp	|	YES	|		|
seller	|	seller_user_id	|	varchar(72)	|	YES	|		|
seller	|	seller_auto_create_task	|	tinyint(1) unsigned	|	NO	|		|
cell	|	cell_id	|	varchar(72)	|	NO	|		|
cell	|	cell_zone_id	|	varchar(72)	|	YES	|		|
cell	|	cell_cell_class_id	|	varchar(72)	|	YES	|		|
cell	|	cell_barcode	|	varchar(72)	|	YES	|		|
cell	|	cell_cell_position_id	|	varchar(72)	|	YES	|		|
cell	|	cell_block	|	tinyint(3) unsigned	|	NO	|		|
cell	|	cell_tc	|	timestamp	|	NO	|		|
cell	|	cell_tm	|	timestamp	|	YES	|		|
cell	|	cell_barcode_format	|	varchar(72)	|	YES	|		|
cell	|	cell_warehouse_id	|	varchar(72)	|	YES	|		|
cell	|	cell_title	|	varchar(192)	|	YES	|		|
minmax	|	minmax_id	|	varchar(72)	|	NO	|		|
minmax	|	minmax_product_id	|	varchar(72)	|	NO	|		|
minmax	|	minmax_cell_id	|	varchar(72)	|	NO	|		|
minmax	|	minmax_amount_min	|	int(11)	|	YES	|		|
minmax	|	minmax_amount_max	|	int(11)	|	YES	|		|
minmax	|	minmax_tc	|	timestamp	|	NO	|		|
minmax	|	minmax_tm	|	timestamp	|	YES	|		|
document_status	|	document_status_id	|	varchar(72)	|	NO	|		|
document_status	|	document_status_title	|	varchar(255)	|	YES	|		|
document_status	|	document_status_color	|	varchar(10)	|	YES	|		|
document_status	|	document_status_tc	|	timestamp	|	NO	|		|
document_status	|	document_status_tm	|	timestamp	|	YES	|		|
1c_document_type	|	1c_document_type_id	|	varchar(72)	|	NO	|	Идентификатор типа документа в 1С	|
1c_document_type	|	1c_document_type_description	|	varchar(255)	|	YES	|	Описание типа общего для понимания	|
1c_document_type	|	1c_document_type_tc	|	timestamp	|	NO	|		|
1c_document_type	|	1c_document_type_tm	|	timestamp	|	YES	|		|
cell_class	|	cell_class_id	|	varchar(72)	|	NO	|		|
cell_class	|	cell_class_title	|	varchar(255)	|	NO	|	Класс ячейки	|
cell_class	|	cell_class_x	|	float	|	NO	|	Ширина X	|
cell_class	|	cell_class_y	|	float	|	NO	|	Высота Y	|
cell_class	|	cell_class_z	|	float	|	NO	|	Глубина Z	|
cell_class	|	cell_class_m	|	float	|	NO	|	Максимальный вес M	|
cell_class	|	cell_class_limit	|	bigint(20) unsigned	|	YES	|		|
cell_class	|	cell_class_tc	|	timestamp	|	NO	|		|
cell_class	|	cell_class_tm	|	timestamp	|	YES	|		|
linking_seller_and_zone	|	linking_seller_and_zone_id	|	varchar(72)	|	NO	|		|
linking_seller_and_zone	|	linking_seller_and_zone_seller_id	|	varchar(72)	|	NO	|		|
linking_seller_and_zone	|	linking_seller_and_zone_zone_id	|	varchar(72)	|	NO	|		|
linking_seller_and_zone	|	linking_seller_and_zone_tc	|	timestamp	|	NO	|		|
linking_seller_and_zone	|	linking_seller_and_zone_tm	|	timestamp	|	YES	|		|
document_legal_person	|	document_legal_person_id	|	varchar(72)	|	NO	|		|
document_legal_person	|	document_legal_person_title	|	varchar(255)	|	YES	|		|
document_legal_person	|	document_legal_person_tc	|	timestamp	|	NO	|		|
document_legal_person	|	document_legal_person_tm	|	timestamp	|	YES	|		|
document_legal_person	|	document_legal_person_api_key	|	char(36)	|	YES	|	API-key	|
document_legal_person	|	document_legal_person_ref_sender	|	char(36)	|	YES	|	Sender	|
document_legal_person	|	document_legal_person_ref_city_sender	|	char(36)	|	YES	|	CitySender	|
document_legal_person	|	document_legal_person_ref_sender_address	|	char(36)	|	YES	|	SenderAddress	|
document_legal_person	|	document_legal_person_contact_sender	|	char(36)	|	YES	|	ContactSender	|
document_legal_person	|	document_legal_person_phone	|	char(24)	|	YES	|	SendersPhone	|
document_legal_person	|	document_legal_person_agreement_number	|	varchar(255)	|	YES	|	Номер договора	|
document_legal_person	|	document_legal_person_agreement_date	|	varchar(32)	|	YES	|	Дата договора	|
document_legal_person	|	document_legal_person_agreement_date_end	|	varchar(32)	|	YES	|	Дата истечения договора	|
document_legal_person	|	document_legal_person_tariff_date_end	|	varchar(32)	|	YES	|	Дата окончания действующего тарифа	|
document_legal_person	|	document_legal_person_document_legal_person_counterparty_id	|	varchar(72)	|	YES	|		|
zkt_state	|	zkt_state_id	|	bigint(20) unsigned	|	NO	|		|
zkt_state	|	zkt_state_title	|	varchar(255)	|	NO	|		|
zkt_state	|	zkt_state_tc	|	timestamp	|	NO	|		|
zkt_state	|	zkt_state_tm	|	timestamp	|	YES	|		|
sys_menu_tsd	|	menu_tsd_id	|	varchar(72)	|	NO	|		|
sys_menu_tsd	|	menu_tsd_parent_menu_tsd_id	|	varchar(72)	|	YES	|		|
sys_menu_tsd	|	menu_tsd_type_menu_tsd_type_id	|	int(11)	|	NO	|		|
sys_menu_tsd	|	menu_tsd_title	|	varchar(72)	|	NO	|		|
sys_menu_tsd	|	menu_tsd_to_uri	|	varchar(72)	|	YES	|		|
sys_menu_tsd	|	menu_tsd_to_page	|	varchar(72)	|	YES	|		|
sys_menu_tsd	|	menu_tsd_hot_key	|	varchar(72)	|	YES	|		|
sys_menu_tsd	|	menu_tsd_task_type_task_type_id	|	varchar(72)	|	YES	|		|
sys_menu_tsd	|	menu_tsd_counter_func	|	varchar(72)	|	YES	|		|
sys_menu_tsd	|	menu_tsd_icon	|	varchar(72)	|	YES	|		|
sys_menu_tsd	|	menu_tsd_position	|	int(11)	|	NO	|		|
sys_menu_tsd	|	menu_tsd_enable	|	tinyint(1)	|	NO	|		|
sys_menu_tsd	|	menu_tsd_visible	|	tinyint(1)	|	NO	|		|
sys_menu_tsd	|	menu_tsd_tc	|	timestamp	|	NO	|		|
sys_menu_tsd	|	menu_tsd_tm	|	timestamp	|	YES	|		|
sys_menu_tsd	|	menu_tsd_process_name	|	varchar(50)	|	YES	|		|
inventory_result	|	inventory_result_id	|	bigint(20)	|	NO	|		|
inventory_result	|	inventory_result_task_id	|	varchar(72)	|	YES	|		|
inventory_result	|	inventory_result_task_start	|	timestamp	|	YES	|		|
inventory_result	|	inventory_result_task_finish	|	timestamp	|	YES	|		|
inventory_result	|	inventory_result_task_user_id	|	varchar(72)	|	YES	|		|
inventory_result	|	inventory_result_task_det_id	|	varchar(72)	|	YES	|		|
inventory_result	|	inventory_result_task_det_user_id	|	varchar(72)	|	YES	|		|
inventory_result	|	inventory_result_task_det_cell_id	|	varchar(72)	|	YES	|		|
inventory_result	|	inventory_result_task_det_tare_id	|	varchar(72)	|	YES	|		|
inventory_result	|	inventory_result_task_det_amount_task	|	decimal(10,4)	|	YES	|		|
inventory_result	|	inventory_result_task_det_amount_fact	|	decimal(10,4)	|	YES	|		|
inventory_result	|	inventory_result_task_det_product_id	|	varchar(72)	|	YES	|		|
inventory_result	|	inventory_result_task_det_product_art	|	varchar(72)	|	YES	|		|
inventory_result	|	inventory_result_task_det_product_title	|	varchar(255)	|	YES	|		|
inventory_result	|	inventory_result_content_expiration_date	|	date	|	YES	|		|
inventory_result	|	inventory_result_content_batch_code	|	varchar(72)	|	YES	|		|
inventory_result	|	inventory_result_tc	|	timestamp	|	NO	|		|
inventory_result	|	inventory_result_tm	|	timestamp	|	YES	|		|
np_counterparty	|	np_counterparty_id	|	varchar(72)	|	NO	|		|
np_counterparty	|	np_counterparty_np_city_id	|	varchar(72)	|	NO	|		|
np_counterparty	|	np_counterparty_f	|	varchar(255)	|	YES	|		|
np_counterparty	|	np_counterparty_i	|	varchar(255)	|	YES	|		|
np_counterparty	|	np_counterparty_o	|	varchar(255)	|	YES	|		|
np_counterparty	|	np_counterparty_phone	|	varchar(16)	|	YES	|		|
np_counterparty	|	np_counterparty_np_ownership_type_id	|	varchar(72)	|	YES	|		|
np_counterparty	|	np_counterparty_edrpou	|	varchar(16)	|	YES	|		|
np_counterparty	|	np_counterparty_tc	|	timestamp	|	NO	|		|
np_counterparty	|	np_counterparty_tm	|	timestamp	|	YES	|		|
tare_limit	|	tare_limit_id	|	varchar(72)	|	NO	|		|
tare_limit	|	tare_limit_product_id	|	varchar(72)	|	YES	|		|
tare_limit	|	tare_limit_tare_type_id	|	varchar(72)	|	YES	|		|
tare_limit	|	tare_limit_amount	|	bigint(20) unsigned	|	YES	|		|
tare_limit	|	tare_limit_tc	|	timestamp	|	NO	|		|
tare_limit	|	tare_limit_tm	|	timestamp	|	YES	|		|
np_area	|	np_area_id	|	varchar(72)	|	NO	|		|
np_area	|	np_area_title	|	varchar(255)	|	YES	|		|
np_area	|	np_area_tc	|	timestamp	|	NO	|		|
np_area	|	np_area_tm	|	timestamp	|	YES	|		|
counterparty_warehouse	|	counterparty_warehouse_id	|	varchar(72)	|	NO	|	Идентификатор склада почтового оператора	|
counterparty_warehouse	|	counterparty_warehouse_title	|	varchar(255)	|	NO	|	Наименование склада почтового адреса	|
counterparty_warehouse	|	counterparty_warehouse_tc	|	timestamp	|	NO	|		|
counterparty_warehouse	|	counterparty_warehouse_tm	|	timestamp	|	YES	|		|
document_payment_method	|	document_payment_method_id	|	varchar(72)	|	NO	|		|
document_payment_method	|	document_payment_method_title	|	varchar(255)	|	NO	|		|
document_payment_method	|	document_payment_method_tc	|	timestamp	|	NO	|		|
document_payment_method	|	document_payment_method_tm	|	timestamp	|	YES	|		|
document_payer_type	|	document_payer_type_id	|	varchar(72)	|	NO	|		|
document_payer_type	|	document_payer_type_title	|	varchar(255)	|	NO	|		|
document_payer_type	|	document_payer_type_tc	|	timestamp	|	NO	|		|
document_payer_type	|	document_payer_type_tm	|	timestamp	|	YES	|		|
sys_language	|	language_id	|	varchar(72)	|	NO	|		|
sys_language	|	language_title	|	varchar(72)	|	NO	|		|
sys_language	|	language_code	|	varchar(72)	|	NO	|		|
sys_language	|	language_position	|	int(11) unsigned	|	NO	|		|
sys_language	|	language_tc	|	timestamp	|	NO	|		|
sys_language	|	language_tm	|	timestamp	|	YES	|		|
sys_language	|	language_delete	|	tinyint(1) unsigned	|	NO	|		|
rack_class_det	|	rack_class_det_id	|	varchar(72)	|	NO	|		|
rack_class_det	|	rack_class_det_column	|	bigint(20)	|	YES	|		|
rack_class_det	|	rack_class_det_row	|	bigint(20)	|	YES	|		|
rack_class_det	|	rack_class_det_cell_class_id	|	varchar(72)	|	YES	|		|
rack_class_det	|	rack_class_det_rack_class_id	|	varchar(72)	|	YES	|		|
rack_class_det	|	rack_class_det_tc	|	timestamp	|	NO	|		|
rack_class_det	|	rack_class_det_tm	|	timestamp	|	YES	|		|
nk_timesheet	|	nk_timesheet_id	|	bigint(20) unsigned	|	NO	|		|
nk_timesheet	|	nk_timesheet_user_id	|	varchar(72)	|	NO	|		|
nk_timesheet	|	nk_timesheet_start	|	timestamp	|	YES	|		|
nk_timesheet	|	nk_timesheet_stop	|	timestamp	|	YES	|		|
nk_timesheet	|	nk_timesheet_data	|	longtext	|	YES	|		|
nk_timesheet	|	nk_timesheet_tc	|	timestamp	|	NO	|		|
nk_timesheet	|	nk_timesheet_tm	|	timestamp	|	YES	|		|
rack	|	rack_id	|	varchar(72)	|	NO	|		|
rack	|	rack_title	|	varchar(255)	|	YES	|		|
rack	|	rack_position_x	|	bigint(20)	|	YES	|		|
rack	|	rack_position_z	|	bigint(20)	|	YES	|		|
rack	|	rack_zone_id	|	varchar(72)	|	YES	|		|
rack	|	rack_rack_class_id	|	varchar(72)	|	YES	|		|
rack	|	rack_tc	|	timestamp	|	NO	|		|
rack	|	rack_tm	|	timestamp	|	YES	|		|
billing_seller	|	billing_seller_id	|	varchar(72)	|	NO	|		|
billing_seller	|	billing_seller_seller_id	|	varchar(72)	|	NO	|		|
billing_seller	|	billing_seller_plan_id	|	varchar(72)	|	YES	|		|
billing_seller	|	billing_seller_tc	|	timestamp	|	NO	|		|
billing_seller	|	billing_seller_tm	|	timestamp	|	YES	|		|
product	|	product_id	|	varchar(72)	|	NO	|		|
product	|	product_product_legal_person_id	|	varchar(72)	|	YES	|		|
product	|	product_title	|	varchar(255)	|	YES	|		|
product	|	product_full_name	|	varchar(255)	|	YES	|		|
product	|	product_art	|	varchar(72)	|	YES	|		|
product	|	product_product_brand_id	|	varchar(72)	|	YES	|		|
product	|	product_product_kind_of_id	|	varchar(72)	|	YES	|		|
product	|	product_x	|	float unsigned	|	NO	|		|
product	|	product_y	|	float unsigned	|	NO	|		|
product	|	product_z	|	float unsigned	|	NO	|		|
product	|	product_m	|	float unsigned	|	NO	|		|
product	|	product_amount_in_package	|	decimal(10,4) unsigned	|	NO	|		|
product	|	product_product_unit_id	|	varchar(72)	|	YES	|		|
product	|	product_specific_amount	|	decimal(10,4)	|	NO	|	Количество на единицу товара (необходимо для подбора штучно-весового товара)	|
product	|	product_specific_weight	|	tinyint(1)	|	NO	|	Признак весового продукта (можно подбирать больше чем в задаче)	|
product	|	product_percent_leave	|	double unsigned	|	NO	|	Процент сроков годности для расходов	|
product	|	product_percent_coming	|	double unsigned	|	NO	|	Процент сроков годности для приходов	|
product	|	product_expiration_days	|	int(11) unsigned	|	NO	|	Срок хранения общий в днях	|
product	|	product_product_group_id	|	varchar(72)	|	YES	|		|
product	|	product_tc	|	timestamp	|	NO	|		|
product	|	product_tm	|	timestamp	|	YES	|		|
product	|	product_product_type_id	|	varchar(72)	|	YES	|		|
product	|	product_wms_number	|	bigint(9) unsigned	|	NO	|		|
product	|	product_wms_barcode	|	varchar(20)	|	YES	|		|
product	|	product_erp_attribute_1	|	varchar(255)	|	YES	|		|
product	|	product_erp_attribute_2	|	varchar(255)	|	YES	|		|
product	|	product_erp_attribute_3	|	varchar(255)	|	YES	|		|
product	|	product_erp_attribute_4	|	varchar(255)	|	YES	|		|
product	|	product_erp_attribute_5	|	varchar(255)	|	YES	|		|
product	|	product_erp_attribute_6	|	varchar(255)	|	YES	|		|
product	|	product_erp_attribute_7	|	varchar(255)	|	YES	|		|
product	|	product_erp_attribute_8	|	varchar(255)	|	YES	|		|
product	|	product_erp_attribute_9	|	varchar(255)	|	YES	|		|
product	|	product_erp_attribute_10	|	varchar(255)	|	YES	|		|
zone	|	zone_id	|	varchar(72)	|	NO	|	Зона склада	|
zone	|	zone_title	|	varchar(255)	|	NO	|	Зона склада	|
zone	|	zone_zone_type_id	|	varchar(72)	|	NO	|	Тип зоны	|
zone	|	zone_x	|	bigint(20)	|	YES	|		|
zone	|	zone_z	|	bigint(20)	|	YES	|		|
zone	|	zone_y	|	bigint(20)	|	YES	|		|
zone	|	zone_warehouse_id	|	varchar(72)	|	YES	|	Идентификатор склада	|
zone	|	zone_tc	|	timestamp	|	NO	|		|
zone	|	zone_tm	|	timestamp	|	YES	|		|
zone	|	zone_group	|	smallint(5) unsigned	|	YES	|		|
zone	|	zone_safekeeping	|	tinyint(1)	|	YES	|		|
zone	|	zone_row	|	varchar(255)	|	YES	|		|
product_det	|	product_det_id	|	varchar(72)	|	NO	|	Идентификатор продукта (итогового)	|
product_det	|	product_det_product_id	|	varchar(72)	|	NO	|	Идентификатор продукта (из чего состоит)	|
product_det	|	product_det_amount	|	float unsigned	|	NO	|	Количество (из чего состоит)	|
product_det	|	product_det_tc	|	timestamp	|	NO	|		|
product_det	|	product_det_tm	|	timestamp	|	YES	|		|
product_legal_person	|	product_legal_person_id	|	varchar(72)	|	NO	|		|
product_legal_person	|	product_legal_person_title	|	varchar(255)	|	YES	|		|
product_legal_person	|	product_legal_person_tc	|	timestamp	|	NO	|		|
product_legal_person	|	product_legal_person_tm	|	timestamp	|	YES	|		|
task_det	|	task_det_id	|	varchar(72)	|	NO	|		|
task_det	|	task_det_content_id	|	varchar(72)	|	YES	|		|
task_det	|	task_det_user_id	|	varchar(72)	|	YES	|		|
task_det	|	task_det_cell_id_from	|	varchar(72)	|	YES	|		|
task_det	|	task_det_comment	|	varchar(255)	|	YES	|		|
task_det	|	task_det_cell_id_to	|	varchar(72)	|	YES	|		|
task_det	|	task_det_tare_id_from	|	varchar(72)	|	YES	|		|
task_det	|	task_det_tare_id_to	|	varchar(72)	|	YES	|		|
task_det	|	task_det_amount_task	|	decimal(10,3) unsigned	|	NO	|		|
task_det	|	task_det_amount_fact	|	decimal(10,3) unsigned	|	NO	|		|
task_det	|	task_det_task_id	|	varchar(72)	|	YES	|		|
task_det	|	task_det_document_det_id	|	varchar(72)	|	YES	|		|
task_det	|	task_det_defect	|	tinyint(3) unsigned	|	NO	|		|
task_det	|	task_det_product_id	|	varchar(72)	|	YES	|		|
task_det	|	task_det_tc	|	timestamp	|	NO	|		|
task_det	|	task_det_tm	|	timestamp	|	YES	|		|
task_det	|	task_det_group_id	|	varchar(72)	|	YES	|		|
task_det	|	task_det_return_reason_id	|	varchar(72)	|	YES	|		|
task_det	|	task_det_placement_type	|	tinyint(4)	|	YES	|		|
task_det	|	task_det_scheme_det_id	|	varchar(72)	|	YES	|		|
task_det	|	task_det_ordinal_number	|	int(4)	|	YES	|		|
task_det	|	task_det_create_user_id	|	varchar(72)	|	YES	|		|
task_det	|	task_det_update_user_id	|	varchar(72)	|	YES	|		|
sys_route_user_role	|	route_user_role_id	|	varchar(72)	|	NO	|		|
sys_route_user_role	|	route_user_role_user_role_id	|	varchar(72)	|	NO	|		|
sys_route_user_role	|	route_user_role_route_id	|	varchar(72)	|	NO	|		|
sys_route_user_role	|	route_user_role_tc	|	timestamp	|	YES	|		|
sys_route_user_role	|	route_user_role_tm	|	timestamp	|	YES	|		|
product_parameter_height	|	product_parameter_height_id	|	varchar(72)	|	NO	|		|
product_parameter_height	|	product_parameter_height_title	|	varchar(255)	|	YES	|		|
product_parameter_height	|	product_parameter_height_barcode	|	varchar(72)	|	YES	|		|
product_parameter_height	|	product_parameter_height_tc	|	timestamp	|	NO	|		|
product_parameter_height	|	product_parameter_height_tm	|	timestamp	|	YES	|		|
billing_document_status	|	billing_document_status_id	|	varchar(72)	|	NO	|		|
billing_document_status	|	billing_document_status_title	|	varchar(192)	|	YES	|		|
billing_document_status	|	billing_document_status_tc	|	timestamp	|	NO	|		|
billing_document_status	|	billing_document_status_tm	|	timestamp	|	YES	|		|
document_np	|	document_np_id	|	varchar(72)	|	NO	|		|
document_np	|	document_np_tc	|	timestamp	|	NO	|		|
document_np	|	document_np_tm	|	timestamp	|	YES	|		|
document_np	|	document_np_service_type	|	varchar(50)	|	YES	|		|
document_np	|	document_np_payment_method	|	varchar(50)	|	YES	|		|
document_np	|	document_np_payer_type	|	varchar(50)	|	YES	|		|
document_np	|	document_np_cost	|	varchar(50)	|	YES	|		|
document_np	|	document_np_seats_amount	|	varchar(10)	|	YES	|		|
document_np	|	document_np_desc	|	varchar(255)	|	YES	|		|
document_np	|	document_np_cargo_type	|	varchar(50)	|	YES	|		|
document_np	|	document_np_weight	|	varchar(10)	|	YES	|		|
document_np	|	document_np_volume	|	varchar(10)	|	YES	|		|
document_np	|	document_np_sender_f	|	varchar(50)	|	YES	|		|
document_np	|	document_np_sender_i	|	varchar(50)	|	YES	|		|
document_np	|	document_np_sender_o	|	varchar(50)	|	YES	|		|
document_np	|	document_np_sender_city	|	varchar(50)	|	YES	|		|
document_np	|	document_np_sender_region	|	varchar(50)	|	YES	|		|
document_np	|	document_np_sender_phone	|	varchar(50)	|	YES	|		|
document_np	|	document_np_sender_address	|	varchar(100)	|	YES	|		|
document_np	|	document_np_sender_warehouse	|	varchar(100)	|	YES	|		|
document_np	|	document_np_receiver_f	|	varchar(50)	|	YES	|		|
document_np	|	document_np_receiver_i	|	varchar(50)	|	YES	|		|
document_np	|	document_np_receiver_o	|	varchar(50)	|	YES	|		|
document_np	|	document_np_receiver_phone	|	varchar(50)	|	YES	|		|
document_np	|	document_np_receiver_city	|	varchar(50)	|	YES	|		|
document_np	|	document_np_receiver_region	|	varchar(50)	|	YES	|		|
document_np	|	document_np_receiver_address	|	varchar(100)	|	YES	|		|
document_np	|	document_np_receiver_warehouse	|	varchar(100)	|	YES	|		|
document_np	|	document_np_ref	|	varchar(255)	|	YES	|		|
document_np	|	document_np_receiver_address_raw	|	varchar(255)	|	YES	|		|
document_np	|	document_np_receiver_lp_title	|	varchar(255)	|	YES	|		|
document_np	|	document_np_receiver_lp_edrpou	|	varchar(255)	|	YES	|		|
abc_product	|	abc_product_warehouse_id	|	varchar(72)	|	NO	|	Идентификатор склада	|
abc_product	|	abc_product_seller_id	|	varchar(72)	|	NO	|	Идентификатор контрагента (владельца) товара	|
abc_product	|	abc_product_id	|	varchar(72)	|	NO	|	Идентификатор продукта	|
abc_product	|	abc_product_abc_classifier	|	varchar(72)	|	YES	|	Категория количества проданного товара	|
abc_product	|	abc_product_previous_abc_classifier	|	varchar(72)	|	YES	|	Предыдущая категория количества проданного товара	|
abc_product	|	abc_product_tc	|	timestamp	|	NO	|		|
abc_product	|	abc_product_tm	|	timestamp	|	YES	|		|
document	|	document_id	|	varchar(72)	|	NO	|		|
document	|	document_document_type_id	|	varchar(72)	|	YES	|		|
document	|	document_document_status_id	|	varchar(72)	|	YES	|	Статус документа	|
document	|	document_title	|	varchar(255)	|	YES	|		|
document	|	document_barcode	|	varchar(72)	|	YES	|		|
document	|	document_document_legal_person_id	|	varchar(72)	|	YES	|		|
document	|	document_user_id	|	varchar(72)	|	YES	|		|
document	|	document_warehouse_id	|	varchar(72)	|	YES	|	Идентификатор склада	|
document	|	document_warehouse_id_from	|	varchar(72)	|	YES	|	Идентификатор склада откуда	|
document	|	document_warehouse_id_to	|	varchar(72)	|	YES	|	Идентификатор склада куда	|
document	|	document_zone_id_from	|	varchar(72)	|	YES	|	Идентификатор зоны склада откуда	|
document	|	document_zone_id_to	|	varchar(72)	|	YES	|	Идентификатор зоны склада куда	|
document	|	document_tc	|	timestamp	|	NO	|		|
document	|	document_tm	|	timestamp	|	YES	|		|
document	|	document_comment	|	text	|	YES	|	Комментарий к документу	|
document	|	document_counterparty_id_from	|	varchar(72)	|	YES	|	Контрагент откуда	|
document	|	document_counterparty_id_to	|	varchar(72)	|	YES	|	Контрагент куда	|
document	|	document_cost	|	varchar(255)	|	YES	|	Объявленная стоимость содержимого документа	|
document	|	document_date	|	varchar(255)	|	YES	|	Дата документа	|
document	|	document_document_service_type_id	|	varchar(72)	|	YES	|	Тип доставки в документе	|
document	|	document_document_payment_method_id	|	varchar(72)	|	YES	|	Тип оплаты в документе	|
document	|	document_document_payer_type_id	|	varchar(72)	|	YES	|	Тип плательщика в документе	|
document	|	document_seats_amount	|	int(10) unsigned	|	NO	|		|
document	|	document_document_cargo_type_id	|	varchar(72)	|	YES	|	Тип груза в документе	|
document	|	document_weight	|	float unsigned	|	YES	|		|
document	|	document_volume	|	float unsigned	|	YES	|		|
document	|	document_express_invoice	|	varchar(255)	|	YES	|	Экспресс накладная	|
document	|	document_document_mail_id	|	varchar(72)	|	YES	|		|
document	|	document_document_priority_id	|	varchar(72)	|	YES	|	Приоритетность расходного документа	|
document	|	document_incoming_priority	|	tinyint(1)	|	YES	|	Приоритетность приходного документа	|
document	|	document_priority_update_tm	|	timestamp	|	YES	|		|
document	|	document_1c_document_type_id	|	varchar(72)	|	YES	|	Идентификатор типа документа 1С	|
document	|	document_1c_document_id	|	varchar(72)	|	YES	|		|
document	|	document_car_number	|	varchar(128)	|	YES	|		|
document	|	document_control_expiration_date	|	tinyint(1)	|	YES	|		|
document	|	document_seller_id	|	varchar(72)	|	YES	|		|
document	|	document_warehouse_title_erp	|	varchar(225)	|	YES	|		|
document	|	document_warehouse_number_erp	|	varchar(72)	|	YES	|		|
document	|	document_create_user_id	|	varchar(72)	|	YES	|		|
document	|	document_car	|	varchar(255)	|	YES	|		|
document	|	document_driver	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_1	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_2	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_3	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_4	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_5	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_6	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_7	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_8	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_9	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_10	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_11	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_12	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_13	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_14	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_15	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_16	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_17	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_18	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_19	|	varchar(255)	|	YES	|		|
document	|	document_erp_attribute_20	|	varchar(255)	|	YES	|		|
sys_menu_ui_rights	|	menu_ui_rights_id	|	varchar(72)	|	NO	|		|
sys_menu_ui_rights	|	menu_ui_rights_menu_ui_id	|	varchar(72)	|	NO	|		|
sys_menu_ui_rights	|	menu_ui_rights_user_role_id	|	varchar(72)	|	NO	|		|
sys_menu_ui_rights	|	menu_ui_rights_read	|	tinyint(1)	|	NO	|		|
sys_menu_ui_rights	|	menu_ui_rights_create	|	tinyint(1)	|	NO	|		|
sys_menu_ui_rights	|	menu_ui_rights_update	|	tinyint(1)	|	NO	|		|
sys_menu_ui_rights	|	menu_ui_rights_delete	|	tinyint(1)	|	NO	|		|
sys_menu_ui_rights	|	menu_ui_rights_tc	|	timestamp	|	NO	|		|
sys_menu_ui_rights	|	menu_ui_rights_tm	|	timestamp	|	YES	|		|
minimum_stock	|	minimum_stock_id	|	varchar(72)	|	NO	|		|
minimum_stock	|	minimum_stock_product_id	|	varchar(72)	|	NO	|		|
minimum_stock	|	minimum_stock_min	|	decimal(10,4) unsigned	|	YES	|		|
minimum_stock	|	minimum_stock_max	|	decimal(10,4) unsigned	|	YES	|		|
minimum_stock	|	minimum_stock_tc	|	timestamp	|	NO	|		|
minimum_stock	|	minimum_stock_tm	|	timestamp	|	YES	|		|
product_barcode	|	product_barcode_id	|	varchar(72)	|	NO	|		|
product_barcode	|	product_barcode_title	|	varchar(72)	|	YES	|		|
product_barcode	|	product_barcode_product_id	|	varchar(72)	|	YES	|		|
product_barcode	|	product_barcode_seller_id	|	varchar(72)	|	YES	|		|
product_barcode	|	product_barcode_tc	|	timestamp	|	NO	|		|
product_barcode	|	product_barcode_tm	|	timestamp	|	YES	|		|
sys_menu_ui_params_window_type	|	menu_ui_params_window_type_id	|	varchar(72)	|	YES	|		|
sys_menu_ui_params_window_type	|	menu_ui_params_window_type_title	|	varchar(100)	|	YES	|		|
sys_menu_ui_params_window_type	|	menu_ui_params_window_type_comment	|	varchar(192)	|	YES	|		|
sys_menu_ui_params_window_type	|	menu_ui_params_window_type_tc	|	timestamp	|	YES	|		|
sys_menu_ui_params_window_type	|	menu_ui_params_window_type_tm	|	timestamp	|	YES	|		|
billing_document	|	billing_document_id	|	varchar(72)	|	NO	|		|
billing_document	|	billing_document_seller_id	|	varchar(72)	|	NO	|		|
billing_document	|	billing_document_document_status_id	|	varchar(72)	|	NO	|		|
billing_document	|	billing_document_user_id	|	varchar(72)	|	YES	|		|
billing_document	|	billing_document_number	|	int(11)	|	YES	|		|
billing_document	|	billing_document_seller_agreement	|	varchar(255)	|	YES	|		|
billing_document	|	billing_document_period	|	varchar(255)	|	YES	|		|
billing_document	|	billing_document_comment	|	varchar(255)	|	YES	|		|
billing_document	|	billing_document_tc	|	timestamp	|	YES	|		|
billing_document	|	billing_document_tm	|	timestamp	|	YES	|		|
product_cell	|	product_cell_id	|	varchar(72)	|	NO	|		|
product_cell	|	product_cell_product_id	|	varchar(72)	|	YES	|		|
product_cell	|	product_cell_cell_id	|	varchar(72)	|	YES	|		|
product_cell	|	product_cell_tc	|	timestamp	|	NO	|		|
product_cell	|	product_cell_tm	|	timestamp	|	YES	|		|
warehouse	|	warehouse_id	|	varchar(72)	|	NO	|	Идентификатор склада	|
warehouse	|	warehouse_title	|	varchar(255)	|	NO	|	Наименование склада	|
warehouse	|	warehouse_local	|	tinyint(1)	|	NO	|	Внутренний склад	|
warehouse	|	warehouse_tc	|	timestamp	|	NO	|		|
warehouse	|	warehouse_tm	|	timestamp	|	YES	|		|
warehouse	|	warehouse_delete	|	tinyint(1)	|	NO	|		|
document_type	|	document_type_id	|	varchar(72)	|	NO	|		|
document_type	|	document_type_title	|	varchar(225)	|	YES	|		|
document_type	|	document_type_tc	|	timestamp	|	NO	|		|
document_type	|	document_type_tm	|	timestamp	|	YES	|		|
sys_printer	|	printer_id	|	varchar(72)	|	NO	|		|
sys_printer	|	printer_driver_printer_driver_id	|	varchar(72)	|	NO	|		|
sys_printer	|	printer_title	|	varchar(192)	|	NO	|		|
sys_printer	|	printer_barcode	|	varchar(20)	|	YES	|		|
sys_printer	|	printer_connect	|	enum('NETWORK','LOCAL')	|	NO	|		|
sys_printer	|	printer_lan_ip	|	varchar(20)	|	YES	|		|
sys_printer	|	printer_lan_port	|	varchar(6)	|	YES	|		|
sys_printer	|	printer_uri	|	varchar(192)	|	YES	|		|
sys_printer	|	printer_port	|	varchar(100)	|	YES	|		|
sys_printer	|	printer_disable	|	tinyint(1)	|	NO	|		|
sys_printer	|	printer_printer_label_size_id	|	varchar(72)	|	YES	|		|
sys_printer	|	printer_tc	|	timestamp	|	NO	|		|
sys_printer	|	printer_tm	|	timestamp	|	YES	|		|
sys_printer	|	printer_delete	|	tinyint(1)	|	NO	|		|
rack_row	|	rack_row_id	|	varchar(72)	|	NO	|		|
rack_row	|	rack_row_level	|	bigint(20)	|	YES	|		|
rack_row	|	rack_row_tc	|	timestamp	|	NO	|		|
rack_row	|	rack_row_tm	|	timestamp	|	YES	|		|
erp_shop	|	erp_shop_id	|	varchar(72)	|	NO	|		|
erp_shop	|	erp_shop_title	|	text	|	YES	|		|
erp_shop	|	erp_shop_erp_client_id	|	varchar(72)	|	YES	|		|
erp_shop	|	erp_shop_external_number	|	varchar(255)	|	YES	|		|
erp_shop	|	erp_shop_tc	|	timestamp	|	NO	|		|
erp_shop	|	erp_shop_tm	|	timestamp	|	YES	|		|
tare	|	tare_id	|	varchar(72)	|	NO	|		|
tare	|	tare_barcode	|	varchar(72)	|	YES	|		|
tare	|	tare_tare_type_id	|	varchar(72)	|	YES	|		|
tare	|	tare_tc	|	timestamp	|	NO	|		|
tare	|	tare_tm	|	timestamp	|	YES	|		|
tare	|	tare_in_x	|	float	|	YES	|		|
tare	|	tare_in_y	|	float	|	YES	|		|
tare	|	tare_in_z	|	float	|	YES	|		|
tare	|	tare_out_x	|	float	|	YES	|		|
tare	|	tare_out_y	|	float	|	YES	|		|
tare	|	tare_out_z	|	float	|	YES	|		|
tare	|	tare_m	|	float	|	YES	|		|
linking_task_type_and_printer	|	linking_task_type_and_printer_id	|	varchar(192)	|	NO	|		|
linking_task_type_and_printer	|	linking_task_type_and_printer_task_type_id	|	varchar(192)	|	NO	|		|
linking_task_type_and_printer	|	linking_task_type_and_printer_printer_id	|	varchar(192)	|	NO	|		|
linking_task_type_and_printer	|	linking_task_type_and_printer_tc	|	timestamp	|	NO	|		|
linking_task_type_and_printer	|	linking_task_type_and_printer_tm	|	timestamp	|	YES	|		|
linking_user_role_document_type	|	linking_user_role_document_type_id	|	varchar(72)	|	NO	|		|
linking_user_role_document_type	|	linking_user_role_document_type_user_role_id	|	varchar(72)	|	NO	|		|
linking_user_role_document_type	|	linking_user_role_document_type_document_type_id	|	varchar(72)	|	NO	|		|
linking_user_role_document_type	|	linking_user_role_document_type_tc	|	timestamp	|	NO	|		|
linking_user_role_document_type	|	linking_user_role_document_type_tm	|	timestamp	|	YES	|		|
sys_printer_label	|	printer_label_id	|	varchar(72)	|	NO	|		|
sys_printer_label	|	printer_label_printer_driver_id	|	varchar(72)	|	NO	|		|
sys_printer_label	|	printer_label_title	|	varchar(192)	|	NO	|		|
sys_printer_label	|	printer_label_label	|	mediumtext	|	NO	|		|
sys_printer_label	|	printer_label_printer_label_size_id	|	varchar(72)	|	YES	|		|
sys_printer_label	|	printer_label_tc	|	timestamp	|	NO	|		|
sys_printer_label	|	printer_label_tm	|	timestamp	|	YES	|		|
product_unit	|	product_unit_id	|	varchar(72)	|	NO	|	Идентификатор из ERP	|
product_unit	|	product_unit_title	|	varchar(255)	|	NO	|		|
product_unit	|	product_unit_not_allow_fraction	|	tinyint(1) unsigned	|	NO	|	Не разрешать дробление количества в этой единице измерения	|
product_unit	|	product_unit_tc	|	timestamp	|	NO	|		|
product_unit	|	product_unit_tm	|	timestamp	|	YES	|		|
sys_printer_local	|	printer_local_id	|	varchar(72)	|	NO	|		|
sys_printer_local	|	printer_local_title	|	varchar(60)	|	NO	|		|
sys_printer_local	|	printer_local_user_id	|	varchar(72)	|	NO	|		|
sys_printer_local	|	printer_local_height	|	int(11)	|	NO	|		|
sys_printer_local	|	printer_local_width	|	int(11)	|	NO	|		|
sys_printer_local	|	printer_local_default	|	tinyint(1)	|	NO	|		|
sys_printer_local	|	printer_local_tc	|	timestamp	|	NO	|		|
sys_printer_local	|	printer_local_tm	|	timestamp	|	YES	|		|
sys_menu_tsd_type	|	menu_tsd_type_id	|	int(11)	|	NO	|		|
sys_menu_tsd_type	|	menu_tsd_type_title	|	varchar(72)	|	NO	|		|
sys_menu_tsd_type	|	menu_tsd_type_tc	|	timestamp	|	NO	|		|
sys_menu_tsd_type	|	menu_tsd_type_tm	|	timestamp	|	YES	|		|
1c_document_status	|	1c_document_status_id	|	varchar(72)	|	NO	|	Идентификатор статуса документа в 1С	|
1c_document_status	|	1c_document_status_description	|	varchar(255)	|	YES	|	Общее описание статуса для своего понимания	|
1c_document_status	|	1c_document_status_tc	|	timestamp	|	NO	|		|
1c_document_status	|	1c_document_status_tm	|	timestamp	|	YES	|		|
sys_options	|	options_id	|	varchar(72)	|	NO	|		|
sys_options	|	options_options_section_id	|	varchar(72)	|	YES	|		|
sys_options	|	options_key	|	varchar(100)	|	YES	|		|
sys_options	|	options_value	|	varchar(192)	|	YES	|		|
sys_options	|	options_type	|	varchar(16)	|	YES	|		|
sys_options	|	options_title	|	varchar(192)	|	YES	|		|
sys_options	|	options_process	|	varchar(192)	|	YES	|		|
sys_options	|	options_tc	|	timestamp	|	NO	|		|
sys_options	|	options_tm	|	timestamp	|	YES	|		|
sys_options	|	options_user_id	|	varchar(72)	|	YES	|		|
billing_tariff	|	billing_tariff_id	|	varchar(72)	|	NO	|		|
billing_tariff	|	billing_tariff_tariff_plan_id	|	varchar(72)	|	NO	|		|
billing_tariff	|	billing_tariff_seller_id	|	varchar(72)	|	NO	|		|
billing_tariff	|	billing_tariff_service_id	|	varchar(72)	|	YES	|		|
billing_tariff	|	billing_tariff_price	|	decimal(12,2)	|	NO	|		|
billing_tariff	|	billing_tariff_is_price_next	|	tinyint(4)	|	NO	|		|
billing_tariff	|	billing_tariff_discount	|	decimal(12,2)	|	NO	|		|
billing_tariff	|	billing_tariff_tc	|	timestamp	|	NO	|		|
billing_tariff	|	billing_tariff_tm	|	timestamp	|	YES	|		|
billing_service	|	billing_service_id	|	varchar(72)	|	NO	|		|
billing_service	|	billing_service_type_id	|	varchar(72)	|	NO	|		|
billing_service	|	billing_service_task_type_id	|	varchar(72)	|	YES	|		|
billing_service	|	billing_service_tare_type_id	|	varchar(72)	|	YES	|		|
billing_service	|	billing_service_cell_class_id	|	varchar(72)	|	YES	|		|
billing_service	|	billing_service_tare_weight	|	float	|	YES	|		|
billing_service	|	billing_service_title	|	varchar(255)	|	NO	|		|
billing_service	|	billing_service_code_ax	|	varchar(255)	|	NO	|		|
billing_service	|	billing_service_for_accompanying_documents	|	tinyint(1)	|	NO	|		|
billing_service	|	billing_service_tc	|	timestamp	|	NO	|		|
billing_service	|	billing_service_tm	|	timestamp	|	YES	|		|
product_status	|	product_status_id	|	int(11)	|	NO	|		|
product_status	|	product_status_title	|	varchar(255)	|	NO	|		|
report_volumetric	|	volumetric_zone_id	|	varchar(72)	|	NO	|		|
report_volumetric	|	volumetric_date	|	date	|	NO	|	Дата	|
report_volumetric	|	volumetric_busy_cells_storage	|	mediumint(8) unsigned	|	YES	|	Хранение	|
report_volumetric	|	volumetric_busy_cells_selection	|	mediumint(8) unsigned	|	YES	|	Зона подбора	|
report_volumetric	|	volumetric_acceptance_pallets	|	mediumint(8) unsigned	|	YES	|	Разгрузка / погрузка паллеты	|
report_volumetric	|	volumetric_shipment_mono_pallets	|	mediumint(8) unsigned	|	YES	|	Отгрузка целых паллет	|
report_volumetric	|	volumetric_shipment_mix_pallets	|	mediumint(8) unsigned	|	YES	|	Отгрузка паллет коробами	|
report_volumetric	|	volumetric_shipment_packages	|	mediumint(8) unsigned	|	YES	|	Отгрузка коробами	|
report_volumetric	|	volumetric_shipment_units	|	mediumint(8) unsigned	|	YES	|	Отгрузка штуками	|
report_volumetric	|	volumetric_movement_pallets	|	mediumint(8) unsigned	|	YES	|	Перемещение в паллетах ЦФО	|
report_volumetric	|	volumetric_acceptance_return_packages	|	mediumint(8) unsigned	|	YES	|	Приемка возвратов коробов	|
report_volumetric	|	volumetric_acceptance_return_units	|	mediumint(8) unsigned	|	YES	|	Приемка возвратов штук	|
report_volumetric	|	volumetric_placement_return_packages	|	mediumint(8) unsigned	|	YES	|	Размещение возвратов коробов	|
report_volumetric	|	volumetric_placement_return_units	|	mediumint(8) unsigned	|	YES	|	Размещение возвратов штук	|
report_volumetric	|	volumetric_coming_rows	|	mediumint(8) unsigned	|	YES	|	Движение строк приход	|
report_volumetric	|	volumetric_expense_rows	|	mediumint(8) unsigned	|	YES	|	Движение строк расход	|
report_volumetric	|	volumetric_shipment_total_packages	|	mediumint(8) unsigned	|	YES	|	Сборка коробов	|
report_volumetric	|	volumetric_shipment_total_units	|	mediumint(8) unsigned	|	YES	|	Сборка штук	|
sys_route	|	route_id	|	varchar(72)	|	NO	|		|
sys_route	|	route_title	|	varchar(192)	|	YES	|		|
sys_route	|	route_array	|	text	|	YES	|		|
sys_route	|	route_tc	|	timestamp	|	YES	|		|
sys_route	|	route_tm	|	timestamp	|	YES	|		|
sys_route	|	local_title_route	|	varchar(192)	|	YES	|		|
sys_route	|	route_route_type_id	|	varchar(72)	|	NO	|		|
task_status	|	task_status_id	|	varchar(72)	|	NO	|		|
task_status	|	task_status_title	|	varchar(255)	|	YES	|		|
task_status	|	task_status_color	|	varchar(10)	|	YES	|		|
task_status	|	task_status_tc	|	timestamp	|	NO	|		|
task_status	|	task_status_tm	|	timestamp	|	YES	|		|
