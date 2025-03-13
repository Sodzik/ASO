# Apache
## Przygotowanie
- **sudo apt-get install build-essential** - instaluje dodatki niezbędne do pracy apache
- **sudo apt-get apache2** - instaluje usługę *Apache*
- **sudo systemctl start apache2** - uruchamia usługę *Apache*
- **sudo systemctl status apache2** - sprawdza działanie usługi *Apache*
- **sudo hostname -I** - sprawdza czy Apache poprawnie działa i nasłuchuje adres IP
## Tworzenie
Teraz strona Apache2 jest wyświetlana przez przeglądarke internetową pod adresem **`http://IP serwera`**, **`http://localhost`** oraz **`http://127.0.0.1`**
1. **sudo mkdir /var/www/sampledomain.com/html -p*** - tworzy folder html z brakującymi katalogami (-p)
2. **sudo nano /var/www/sampledomain.com/html/index.html** - tworzy plik index.html
3. **sudo chown -R 755 /var/ww/sampledomain.com** - przypisuje własność katalogu
## Konfiguracja
1. **sudo nano /etc/apache2/sites-available/000-default.conf** - konfigurujemy w nim ścieżkę katalogu z plikiem html<br>
![image](https://github.com/user-attachments/assets/0719146c-c176-4014-9681-aa9aa8b13f7a)
2. **sudo nano /etc/apache2/apache2.conf** - również zmieniamy ścieżkę katalogu z plikiem html<br>
![image](https://github.com/user-attachments/assets/b071c21f-0d0a-417c-96b5-0a26dbd89464)
3. **sudo systemctl restart apache2** - restartuje usługę apache2, dzięki czemu plik index.html wyświetla się gdy wpisujemy m.in. localhost<br>
![image](https://github.com/user-attachments/assets/a50f4912-dabd-416b-a0cf-acd1291ad3b7)
## Zmiana portu
1. **sudo nano /etc/apache2/ports.conf** - w tym pliku zmieniamy port wyjściowy z 80 na 8080<br>
![image](https://github.com/user-attachments/assets/2422072a-1a61-4f8d-a857-19e46272e479)
2. **sudo nano /etc/apache2/sites-available/000-default.conf** - w tym pliku również zmieniamy port wyjściowy z 80 na 8080<br>
![image](https://github.com/user-attachments/assets/017c1502-d94c-4d0f-9c5c-3288557698d4)
3. **sudo systemctl restart apache2** - restarujemy usługę, dzięki czemu teraz na localhost możemy wejść tylko z portem 8080
## Udostępnianie stron użytkownikom
1. **sudo mkdir ~/public_html** - tworzymy katalog w folderze domowym
2. **sudo nano ~/public_html/index.html** - tworzysz plik html do udostępniania w katalogu public_html
3. **sudo systemctl restart apache2**
