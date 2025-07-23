|Таблиця|Стовпець|Тип даних|Обов’язковий|Коментар|
|----------------------------- |----------------------------- |----------------------------- |----------------------------- |----------------------------- |
|motivation_by_tasks|motivation_by_tasks_id|varchar(72)|NO||
|motivation_by_tasks|motivation_by_tasks_task_title|varchar(255)|YES|Наименование задачи|
|motivation_by_tasks|motivation_by_tasks_user_id|varchar(72)|NO|Пользователь исполнитель|
|motivation_by_tasks|motivation_by_tasks_task_type_id|varchar(72)|YES|Тип задачи|
|motivation_by_tasks|motivation_by_tasks_task_amount|decimal(10,4)|YES|Количество единиц|
|motivation_by_tasks|motivation_by_tasks_task_amount_art|int(11)|YES|Количество артикулов|
|motivation_by_tasks|motivation_by_tasks_task_det_amount|int(11)|YES|Количество строк|
|motivation_by_tasks|motivation_by_tasks_task_tc|timestamp|YES|Время создания|
|motivation_by_tasks|motivation_by_tasks_task_finish|timestamp|YES|Время завершения|
|motivation_by_tasks|motivation_by_tasks_tc|timestamp|YES|
|motivation_by_tasks|motivation_by_tasks_tm|timestamp|YES|
