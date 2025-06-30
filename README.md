Зрозуміло, ви хочете привести всі таблиці до єдиного формату, аналогічного першому прикладу з `product_legal_person`. Нижче наведено уніфіковану таблицю для `product`, а також пов’язаних таблиць `product_brand` і `product_legal_person`, з урахуванням ваших вказівок:

---

### **product**

| Стовбець                            | Тип даних              | Обов'язкове поле | Коментар                                                             |
| ----------------------------------- | ---------------------- | ---------------- | -------------------------------------------------------------------- |
| product\_id                         | varchar(72)            | Так              | Ідентифікатор товару                                                 |
| product\_product\_legal\_person\_id | varchar(72)            | Ні               | Ідентифікатор контрагента (зовнішній ключ на `product_legal_person`) |
| product\_title                      | varchar(255)           | Ні               | Назва товару                                                         |
| product\_full\_name                 | varchar(255)           | Ні               | Повна назва товару                                                   |
| product\_art                        | varchar(72)            | Ні               | Артикул товару                                                       |
| product\_product\_brand\_id         | varchar(72)            | Ні               | Ідентифікатор бренду (зовнішній ключ на `product_brand`)             |
| product\_product\_kind\_of\_id      | varchar(72)            | Ні               | Ідентифікатор виду товару                                            |
| product\_x                          | float unsigned         | Так              | Ширина X                                                             |
| product\_y                          | float unsigned         | Так              | Висота Y                                                             |
| product\_z                          | float unsigned         | Так              | Глибина Z                                                            |
| product\_m                          | float unsigned         | Так              | Вага товару                                                          |
| product\_amount\_in\_package        | decimal(10,4) unsigned | Ні               | Кількість товару в ящику                                             |
| product\_product\_unit\_id          | varchar(72)            | Ні               | Ідентифікатор одиниці виміру товару                                  |
| product\_specific\_amount           | decimal(10,4)          | Ні               | Кількість на одиницю товару                                          |
| product\_specific\_weight           | tinyint(1)             | Ні               | Ознака вагового продукту                                             |
| product\_percent\_leave             | double unsigned        | Ні               | Відсоток терміну придатності для витрат                              |
| product\_percent\_coming            | double unsigned        | Ні               | Відсоток терміну придатності для приходу                             |
| product\_expiration\_days           | int(11) unsigned       | Ні               | Термін зберігання (в днях)                                           |
| product\_product\_group\_id         | varchar(72)            | Ні               | Ідентифікатор групи товару                                           |
| product\_tc                         | timestamp              | Так              | Час створення (заповнюється системою)                                |
| product\_tm                         | timestamp              | Ні               | Час зміни (заповнюється системою)                                    |
| product\_product\_type\_id          | varchar(72)            | Ні               | Ідентифікатор типу товару                                            |

---

### **product\_legal\_person**

| Стовбець                      | Тип даних    | Обов'язкове поле | Коментар                  |
| ----------------------------- | ------------ | ---------------- | ------------------------- |
| product\_legal\_person\_id    | varchar(72)  | Так              | Ідентифікатор контрагента |
| product\_legal\_person\_title | varchar(255) | Ні               | Назва контрагента         |
| product\_legal\_person\_tc    | timestamp    | Так              | Час створення             |
| product\_legal\_person\_tm    | timestamp    | Ні               | Час зміни                 |

---

### **product\_brand**

| Стовбець              | Тип даних    | Обов'язкове поле | Коментар             |
| --------------------- | ------------ | ---------------- | -------------------- |
| product\_brand\_id    | varchar(72)  | Так              | Ідентифікатор бренду |
| product\_brand\_title | varchar(255) | Так              | Найменування бренду  |
| product\_brand\_tc    | timestamp    | Так              | Час створення        |
| product\_brand\_tm    | timestamp    | Ні               | Час зміни            |

---

Якщо потрібно — можу також уніфікувати інші таблиці (`product_unit`, `product_kind_of`, `product_group`, `product_type` тощо), якщо ви надасте їх структури.
