# TASK 5 #

## Subtask 3 ##


### 1. Wyświetl tabelę actors w kolejności alfabetycznej sortując po kolumnie surname. ###
 
SELECT * FROM actors ORDER BY `surname`

![1](https://user-images.githubusercontent.com/122802548/218280761-d58a0590-09c4-4195-8549-90c23ad958a0.jpg)


### 2. Wyświetl film, który powstał w 2019 roku. ###

SELECT * FROM movies WHERE year_of_production = 2019;

![2](https://user-images.githubusercontent.com/122802548/218280789-a8a7b938-3c95-4bd8-b644-f35d862af9e4.jpg)


### 3. Wyświetl wszystkie filmy, które powstały między 1900, a 1999 rokiem. ###

SELECT * FROM movies WHERE year_of_production BETWEEN '1900' AND '1990'

![3](https://user-images.githubusercontent.com/122802548/218280802-37457bf5-5eeb-412b-998d-53af54f1b11e.jpg)


### 4. Wyświetl JEDYNIE tytuł i cenę filmów, które kosztują poniżej 7$ ###

SELECT title, price FROM movies WHERE price < 7;

![4](https://user-images.githubusercontent.com/122802548/218280817-c4b9bc88-3279-44e3-b3b4-7dc22e0697a2.jpg)


### 5. Użyj operatora logicznego AND, aby wyświetlić aktorów o actor_id pomiędzy 4-7 (4 i 7 powinny się wyświetlać). NIE UŻYWAJ operatora BETWEEN. ###

SELECT * FROM actors WHERE actor_id >= 4 AND actor_id <= 7;

![5](https://user-images.githubusercontent.com/122802548/218280828-345953d2-3e2a-4c3f-89b6-afd3bd47d0f8.jpg)


### 6. Wyświetl klientów o id 2,4,6 wykorzystaj do tego warunek logiczny. ###

SELECT * FROM customers WHERE customer_id=2 OR customer_id=4 OR customer_id=6;

![6](https://user-images.githubusercontent.com/122802548/218280836-0fbd9b5d-04c0-462e-b032-e39a1737c978.jpg)


### 7. Wyświetl klientów o id 1,3,5 wykorzystaj do tego operator IN. ###

SELECT * FROM customers WHERE customer_id IN (1, 3, 5);

![7](https://user-images.githubusercontent.com/122802548/218280845-8a61f4b7-0831-4110-bf21-e3567ce53c53.jpg)


### 8. Wyświetl dane wszystkich osób z tabeli ‘actors’, których imię zaczyna się od ciągu “An”.###

SELECT * FROM actors WHERE name LIKE 'An%';

![8](https://user-images.githubusercontent.com/122802548/218280894-b8540eac-68bf-4046-8167-c7c0c8f77db7.jpg)


### 9. Wyświetl dane klienta, który nie ma podanego adresu email. ###

SELECT * FROM customers WHERE email IS NULL;

![9](https://user-images.githubusercontent.com/122802548/218280917-fef58ab1-3056-43a0-b0a0-b0d5532db082.jpg)


### 10. Wyświetl wszystkie filmy, których cena wynosi powyżej 9$ oraz ich ID mieści się pomiędzy 2 i 8 movie_id. ###

SELECT * FROM movies WHERE price > 9 AND movie_id BETWEEN 2 AND 8;

![10](https://user-images.githubusercontent.com/122802548/218280935-aca93e8a-6d81-479c-9116-83e17c1da971.jpg)

