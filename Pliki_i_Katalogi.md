# Powłoka Bash
## Tworzenie i edycja plików
 - **touch** *nazwa_pliku/ów* - tworzenie pliku bez zawartości
 - **nano** *nazwa_pliku/ów* - edycja pliku w konsolowym edytorze tekstu
 - **gedit** *nazwa_pliku.ów* - edycja pliku w graficznym edytorze tekstu (środowisko GUI)
### Zarządzanie plikami
 - **cat** [opcje] *nazwa_pliku/ów*
   - -b - numeruje wiersze z tekstem
   - -n - numeruje wszystkie wiersze
   - -s - usuwa nadmierne spacje
   - -T - usuwa nadmierne tabulacje (TAB)
 - **cp** [opcje] *źródło* *cel*
   - -r - dla katalogów
 - **mv** *źródło* *cel*
 - **rm** [opcje] *nazwa_pliku/katalogu*
   - -f - bez ostrzeżenia
   - -i - potwierdzenie przy usuwaniu każdego pliku
   - -r - usuwa katalog z jego zawartością
   - -v - terminal informuje o tym co robi
### Zarządzanie katalogami
 - **mkdir** [opcje] *nazwa_katalogu* - tworzenie katalogu
    - -p - tworzy brakujące elementy
    - -m - tworzy katalog z określonymi prawami
 - **rmdir** [opcje] *nazwa_katalogu* - usuwanie katalogu
    - -q - usuwa po cichu (quiet mode)
    - -s - usuwa wraz z podkatalogami i plikami
 - **pwd** - wyświetla aktualną ścieżkę do katalogu
 - **cd** - zmienia katalog, w którym się znajdujemy
   - **..** - wyjście o poziom wyżej
   - **.** - bieżący katalog
   - **-** - przejście do katalogu, w którym byliśmy ostatnio
 - **ls** [opcje] *katalog/plik*
   - -l - rozszerzona zawartość pliku
   - -a/A - pokazuje ukryte pliki
   - -t - sortuje według czasu
   - Wynik to pokolei: <br>
<img src="![image](https://github.com/user-attachments/assets/eca35059-9907-41d5-aba1-bb058172f78a)"
1. **Uprawnienia pliku**
2. **Liczba łączy**
3. **ID użytkownika**
4. **ID grupy**
5. **Liczba bajtów**
6. **Data ostatniej modyfikacji**
7. **Nazwa pliku**
 - **Man** *nazwa_komendy* - wyświetla pomoc dla danej komendy
### Head, Tail, Sort, Find, CMP
 - **Head** [opcje] *nazwa_pliku* [opcje2]
   - -n [liczba] - wyświetla pierwsze [liczba] linie pliku
   - -c [liczba] - wyświetla pierwsze [liczba] bajtów pliku
   - -v - wyświetla nazwe pliku przed zawartością
   - -q - nie wyświetla nazw plików
 - **Tail** [opcje] *nazwa_pliku*
   - -n [liczba] - wyświetla ostatnie [liczba] linie pliku
   - -c [liczba] - wyświetla ostatnie [liczba] bajtów pliku
   - -v - wyświetla nazwe pliku przed zawartością
   - -q - nie wyświetla nazw plików
 - **Sort** [opcje] *nazwa_pliku*
   - -k [numer] - sortowanie według podanej kolumny znaków
   - -n - porównuje zgodnie z liczbową wartością
   - -f - traktuje małe litery jak wielkie
   - -r - odwraca kolejność (reverse)
   - -o - wypisuje wynik do pliku np. sort -o plik.txt wynik.txt
- **Find** *ścieżka_w_której_szukasz* [opcje]
   - -name - wyszukuje po określonej nazwie
   - -type - wyszukuje pliki o okreslonym typie
     - d - katalog
     - f - plik normalny
     - b - plik blokowy
     - c - plik znakowy
     - l - dowiązanie symboliczne
   - -path *wzór* - wyszukuje pliki z pasującą ścieżką
   - -size [liczba] - wyszukuje pliki o określonej wielkości
   - -atime [liczba] - wyszukuje pliki otwierane w [liczba] dniach
   - -mtime [liczba] - wyszukuje pliki modyfikowane w [liczba] dniach
   - -print - przekazuje na standardowe wyjście nazwę odnalezionego pliku oraz jego pełną ścieżkę dostępu
   - -exec polecenie {}\; → uruchamia polecenie dla odnalezionego pliku
   - -ok polecenie {} \; - potwierdza uruchomienie polecenia dla odnalezionego pliku
- **Cmp** [opcje] *plik1 plik2* - porównuje znak po znaku 2 pliki (compare)
   - -c/-b - wyświetla specyfikacje znaków w ASCII
   - -l - powowduje że polecenie nie zatrzymuje się przy pierwszej różnicy
- **Diff** [opcje] *plik1 plik2*- porównuje pliki wiersz po wierszu
   - -q - informuje tylko czy pliki są różne
   - -s - wypisuje informacje czy plki są identyczne
   - -r - porównuje katalogi
   - Wyniki: np. 3c3 oznacza, że w 3 wierszu pierwszego pliku masz zamienić na tekst w drugim pliku
     - c - oznacza zamień
     - d - oznacza usuń
     - a - oznacza dodaj tekst
