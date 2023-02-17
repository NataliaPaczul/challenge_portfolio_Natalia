# TASK 6 #

## Subtask 1 ##


### 11. Popełniłam błąd wpisując nazwisko Ani Miler – wpisałam Muler. Znajdź i zastosuj funkcję, która poprawi mój karkołomny błąd 🙈

UPDATE customers SET surname='Miler' WHERE surname='MUler'

![11a](https://user-images.githubusercontent.com/122802548/219757406-5aa0e680-46ad-4ffe-b125-020fc6c844b6.jpg)


### 12. Pobrałam za dużo pieniędzy od klienta, który kupił w ostatnim czasie film o id 4. Korzystając z funkcji join sprawdź, jak ma na imię klient i jakiego ma maila. W celu napisania mu wiadomości o pomyłce fantastycznej szefowej.

SELECT customers.customer_id, customers.email, customers.name, customers.surname, sale.customer_id, sale.movie_id, sale.sale_date FROM customers INNER JOIN sale ON customers.customer_id=sale.customer_id WHERE sale.movie_id = 4;

![image](https://user-images.githubusercontent.com/122802548/219757820-9616cdf5-45a2-4ae8-a7e7-e33436d157fb.png)

 
### 13. Na pewno zauważył_ś, że sprzedawca zapomniał wpisać emaila klientce Patrycji. Uzupełnij ten brak wpisując: pati@mail.com

UPDATE customers SET email = CONCAT('pati@mail.com') WHERE email IS NULL; 

![image](https://user-images.githubusercontent.com/122802548/219758149-5480e174-b6a0-4a7d-9c5e-76a1360f8f40.png)


### 14. Dla każdego zakupu wyświetl, imię i nazwisko klienta, który dokonał wypożyczenia oraz tytuł wypożyczonego filmu. (wykorzystaj do tego funkcję inner join, zastanów się wcześniej, które tabele Ci się przydadzą do wykonania ćwiczenia).

SELECT sale.customer_id, sale.movie_id, sale.sale_date,customers.customer_id, customers.name, customers.surname, movies.movie_id,movies.title FROM customers INNER JOIN sale ON customers.customer_id=sale.customer_id INNER JOIN movies ON sale.movie_id=movies.movie_id;

![image](https://user-images.githubusercontent.com/122802548/219758427-51a87648-f5f0-4f87-b4e3-67ab1763b099.png)


### 15. W celu anonimizacji danych, chcesz stworzyć pseudonimy swoich klientów. - Dodaj kolumnę o nazwie ‘pseudonym’ do tabeli customer,- Wypełnij kolumnę w taki sposób, aby pseudonim stworzył się z dwóch pierwszych liter imienia i ostatniej litery nazwiska. Np. Natalie Pilling → Nag

 ALTER TABLE customers ADD pseudomyn VARCHAR(3); UPDATE customers SET pseudomyn= CONCAT(SUBSTRING(name,1, 2), SUBSTRING(surname, -1));
 
 ![image](https://user-images.githubusercontent.com/122802548/219758673-d72d212f-9415-4f05-959f-05275f68876b.png)


### 16. Wyświetl tytuły filmów, które zostały zakupione, wyświetl tabelę w taki sposób, aby tytuły się nie powtarzały.

SELECT ###DISTINCT movies.title FROM sale INNER JOIN movies ON sale.movie_id = movies.movie_id

![image](https://user-images.githubusercontent.com/122802548/219759002-f1fc196a-ffc1-48ab-b3d5-9c8b703a175c.png)


### 17. Wyświetl wspólną listę imion wszystkich aktorów i klientów, a wynik uporządkuj alfabetycznie. (Wykorzystaj do tego funkcji UNION)

SELECT name FROM customers UNION SELECT name FROM actors ORDER BY name ASC;

![image](https://user-images.githubusercontent.com/122802548/219760089-90a4f316-5dec-4e72-b211-2a398dcb8273.png)


### 18. Polskę opanowała inflacja i nasz sklepik z filmami również dotknął ten problem. Podnieś cenę wszystkich filmów wyprodukowanych po 2000 roku o 2,5 $ (Pamiętaj, że dolar to domyślna jednostka- nie używaj jej nigdzie).

UPDATE `movies` SET `price` = `price` + 2.5 WHERE `year_of_production` > 2000

![image](https://user-images.githubusercontent.com/122802548/219760682-35677700-2e0f-48e1-b4cb-1e7835d9ddd0.png)


### 19. Wyświetl imię i nazwisko aktora o id 4 i tytuł filmu, w którym zagrał

SELECT actors.actor_id, actors.name, actors.surname, movies.title FROM actors INNER JOIN cast ON actors.actor_id=cast.actor_id INNER JOIN movies ON cast.movie_id=movies.movie_id WHERE actors.actor_id = 4;

![image](https://user-images.githubusercontent.com/122802548/219761148-03fda02f-f04e-4a5e-8092-0bc2b2f35169.png)


### 20. A gdzie nasza HONIA!? Dodaj do tabeli customers nową krotkę, gdzie customer_id = 7, name = Honia, surname = Stuczka-Kucharska, email = honia@mail.com oraz pseudonym = Hoa

INSERT INTO customers (customer_id, name, surname, email, pseudomyn) VALUES ('7', 'Honia', 'Stuczka-Kucharska', 'honia@mail.com', 'Hoa');

![image](https://user-images.githubusercontent.com/122802548/219761608-c7854bd1-9a62-47e1-8e44-ca19c01d91aa.png)


