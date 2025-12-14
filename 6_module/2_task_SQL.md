Написать 3 SQL-запроса к этой схеме: 
1) Найти все книги автора "X".
2) Найти всех читателей, которые сейчас держат у себя книгу Y (используя LEFT JOIN и WHERE ... IS NOT NULL).
3) Найти все книги, которые ни разу не брали.
   
**1 задание:**
```sql
SELECT book.title_book
FROM book
LEFT OUTER JOIN author_name ON book.id_book = author_name.id_book
LEFT OUTER JOIN author ON author_name.id_ author = author.id_ author
WHERE author.last_name = ‘X’;
```

**2 задание:**
```sql
SELECT read.first_name_reader,
	     read.last_name_reader
FROM reader AS read
LEFT OUTER JOIN borrow AS bor ON read.id_reader = bor.id_reader
LEFT OUTER JOIN book ON bor.id_book = book.id_book
WHERE book.title_book = ‘Y’;
```

**3 задание:**
```sql
SELECT book.title_book
FROM book
LEFT OUTER JOIN borrow AS bor ON book.id_book = bor.id_book
WHERE data_borrow IS NULL;
```
