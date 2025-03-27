## Powłoki systemu
- **/bin/sh** - jest to przodek wszystkich innych powłok systemów UNIX-owych, ale brakuje jej wielu przydatnych możliwości
- **/bin/bash** - domyślna powłoka systemów linuxowych
- **/bin/csh** - składnia i konstrukcje używane w tej powłoce są bardzo podobne do znanych z języka C
- **/bin/tcsh** - Jest to bardziej rozbudowana wersja powłoki C Shell
- **/bin/ksh** - Jest to jedna z najpopularniejszych powłok UNIX-owych, ale nie jest ona zwykle używana w systemach linuxowych
## Użytkownik w Linuxie
- **/etc/passwd** - podstawowa baza użytkowników
- **/etc/shadow** - plik haseł zakodowanych
- **/etc/group**- baza danych grup
- **/etc/gshadow** -  plik haseł zakodowanych dla grup
### /etc/passwd
1. Nazwa użytkownika
2. hasło użytkownika
3. ID użytkownika
4. ID grupy w której jest użytkownik
5. Dane identyfikacyjne (komentarz)
6. Katalog domowy
7. Ścieżka do powłoki
### /etc/shadow
![image](https://github.com/user-attachments/assets/010f92d9-6239-442b-82ea-33a3c9bafde0)
### Useradd -D
- **Useradd -D** - pokazuje domyślne ustawienia przy tworzeniu użytkownika
- **Useradd -D -g nazwa_grupy** - ustawia domyślną grupę
- **Useradd -D -b ścieżka do katalogu domowego** - ustawia domyślny katalog domowy
- **Useradd -D -f ilość dni** - ustawia domyślną ilość dni do wygaśnięcia hasła
- **Useradd -D -e data** - ustawia domyślną datę wygaśnięcia konta
- **Useradd -D -s powłoka** - zmienia domyślną powłokę użytkownika
### Useradd
- **Useradd -c "komentarz" nazwa_użytkownika** - dodaje komentarz do użytkownika
- **Useradd -d katalog_główny nazwa_użytkownika** - wskazanie użytkownikowy katalogu domowego
- **Useradd -m nazwa_użytkownika** - tworzy katalog użytkownika jeśli takowy nie istnieje
- **Useradd -e data nazwa_użytkownika** - dodaje date wyłączenia konta
- **Useradd -f dni nazwa_użytkownika** - liczba dni od wygaśnięcia hasła po których konto jest blokowane
- **Useradd -g grupa nazwa_użytkownika** - dodawanie użytkownika do grupy
- **Useradd -G grupa1,grupa2... nazwa_użytkownika** - dodawanie użytkownika do kilku grup
- **Useradd -u id_użytkownika nazwa_użytkownika** - nadajesz numer ID
- **Useradd -p zakodowane_hasło nazwa_użytkownika** - koduje hasło
- **Useradd -s powłoka nazwa_użytkownika** - nadajesz domyślną powłokę użytkownikowi
## Adduser
Po wpisaniu **adduser nazwa_użytkownika nazwa_grupy** tworzy użytkownika i dodaje do grupy. Różnicą od **Useradd** jest to, że pyta o dane po kolei
## Passwd
- **Passwd -a nazwa_użytkownika** (--all) - wyświetla raporty stanu hasła
- **Passwd -d nazwa_użytkownika** (--delete) - usuwa hasło
- **Passwd -e nazwa_użytkownika** (--expire) - wymusza wygaśnięcie hasła
- **Passwd -h** (--help) - wyświetla pomoc dla komendy
- **Passwd -k nazwa_użytkownika** (--keep-tokens) - zmienia hasło o ile już wygasło
- **Passwd -l nazwa_użytkownika** (--lock) - blokuje hasło
- **Passwd -S nazwa_użytkownika** (--status) - wyświetla raport stanu hasła
- **Passwd -u nazwa_użytkownika** (--unlock) - odblokowuje hasło
- **Passwd -n ilość_dni -x ilość-dni nazwa_użytkownika** - ustawia minimalny i maksymalny dzień zmiany hasła
- **Passwd -w ilość_dni nazwa_użytkownika** - ustawia ilość dni przez które będzie się pojawiać informacja o zmianie hasła
## Chage 
- **chage -l nazwa_użytkownika** - sprawdza datę ważności hasła, jeśli je posiada
- **chage -E data nazwa_użytkownika** podajemy datę wygaśnięcia konta
- **chage -E liczba_dni nazwa_użytkownika** - dodaje liczbe dni do daty wygaśnięcia hasła (od 1 stycznia 1970)
- **chage -W liczba_dni nazwa_użytkownika** - ustawia ilość dni przez które będzie się pojawiać informacja o zmianie hasła
- **chage -I liczba_dni nazwa_użytkownika** - dodajemy liczbę dni zablokowania hasła po wygaśnięciu hasła
## Usermod
- **usermod -d nazwa_użytkownika** - zmienia katalog domowy
- **usermod -L nazwa_użytkownika** - blokuje konto
- **usermod -l nazwa_użytkownika** - zmienia nazwe użytkownika
- **usermod -g nazwa_użytkownika** - zmienia domyślną grupę użytkownika
- **usermod -U nazwa_użytkownika** - odblokowuje konto użytkownika
- **usermod -G nazwa_użytkownika** - zmiana grupy dla użytkownika
- **usermod -a nazwa_użytkownika** - dodaje użytkownika do grupy roboczej. Używamy z parametrem -G
## userdel
- **userdel nazwa_użytkownika** - usuwa konto użytkownika
- **userdel -r nazwa_użytkownika** - usuwa konto użytkownika razem z katalogiem domowych
