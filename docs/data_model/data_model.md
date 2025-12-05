Назва сутності (Entity),Атрибути (Attributes),Тип даних,Опис
Category (Категорія),id (PK),Integer,Унікальний ідентифікатор
,name,String,"Назва (напр. ""Сукні"", ""Джинси"")"
,parent_id,Integer,Для вкладеності (напр. Жінки -> Сукні)
,image_url,String,Фото для плитки категорії
Product (Товар),id (PK),Integer,Унікальний ідентифікатор
,category_id (FK),Integer,Зв'язок з категорією
,name,String,Назва товару
,description,Text,Детальний опис тканини/фасону
,price,Decimal,Ціна (для відображення)
,material,String,"Склад (напр. ""100% бавовна"")"
ProductVariant (Варіант),id (PK),Integer,Унікальний ідентифікатор
,product_id (FK),Integer,До якого товару належить
,size,String,"Розмір (S, M, L, XL, 42)"
,color,String,"Колір (Red, Navy Blue)"
,stock_status,Boolean,Чи є в наявності (true/false)
ProductImage (Фото),id (PK),Integer,Унікальний ідентифікатор
,product_id (FK),Integer,До якого товару належить фото
,image_url,String,Посилання на зображення
,is_main,Boolean,Чи є це головним фото в списку
