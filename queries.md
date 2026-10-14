# DQL Запити

## Завдання 1

### 1.1. Вибрати всі стовпчики з таблиці `products`:

```sql
SELECT * 
FROM products;
```

### 1.2. Вибрати тільки стовпчики `name`, `phone` з таблиці `shippers`:

```sql
SELECT name, phone 
FROM shippers;
```

---

## Завдання 2

### Знайти середнє, максимальне та мінімальне значення стовпчика `price` таблички `products`:

```sql
SELECT 
    AVG(price) AS avg_price,
    MAX(price) AS max_price,
    MIN(price) AS min_price
FROM products;
```

---

## Завдання 3

### Обрати унікальні значення колонок `category_id` та `price` таблиці `products`. Порядок виведення за спаданням `price`, топ-10 рядків:

```sql
SELECT DISTINCT 
    category_id, 
    price
FROM products
ORDER BY price DESC
LIMIT 10;
```

---

## Завдання 4

### Знайти кількість продуктів (рядків), які знаходяться в цінових межах від 20 до 100:

```sql
SELECT COUNT(*) AS product_count
FROM products
WHERE price BETWEEN 20 AND 100;
```

---

## Завдання 5

### Знайти кількість продуктів (рядків) та середню ціну (`price`) у кожного постачальника (`supplier_id`):

```sql
SELECT 
    supplier_id,
    COUNT(*) AS product_count,
    AVG(price) AS avg_price
FROM products
GROUP BY supplier_id;
```
