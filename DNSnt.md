# Konfiguracja serwera DNS (Ubuntu, BIND9)
## Zmiana nazwy serwera
Pliki do edycji:
- **/etc/hostname** – wpisujemy nową nazwę serwera.
- **/etc/hosts** – dodajemy nową nazwę serwera obok adresu IP.

## Instalacja serwera DNS BIND9
Instalujemy pakiet poleceniem:
- **sudo apt-get install bind9 bind9utils**

Pliki do edycji:
- **/etc/bind/named.conf.options** – ustawienia globalne.
- **/etc/bind/named.conf.local** – konfiguracja stref.
- **/etc/bind/db.local** – rekordy DNS.

## Konfiguracja ustawień globalnych
Plik do edycji: 
- **/etc/bind/named.conf.options**
Ustawiamy serwery nadrzędne (np. Google: 8.8.8.8, 8.8.4.4).
Sprawdzamy, czy serwer działa na właściwym adresie IP (np. 10.80.80.1).

## Konfiguracja stref DNS
Plik do edycji: 
- **/etc/bind/named.conf.local**
Dodajemy strefę przeszukiwania do przodu (egzamin.local).
Dodajemy strefę przeszukiwania wstecznego (80.80.10.in-addr.arpa).

## Konfiguracja pliku strefy przeszukiwania do przodu
Plik do edycji: 
- **/etc/bind/for.egzamin.local**
Przypisujemy adresy IP do nazw serwera i klientów.

## Konfiguracja pliku strefy przeszukiwania wstecznego
Plik do edycji: 
- **/etc/bind/rev.egzamin.local**
Tworzymy odwrotne mapowanie adresów IP na nazwy domenowe.

## Ustawienie serwera DNS w systemie
Plik do edycji: 
- **/etc/resolv.conf**
Ustawiamy nameserver na 10.80.80.1.
Blokujemy plik przed nadpisaniem: sudo chattr +i /etc/resolv.conf.

## Restart serwera DNS i testowanie
Restart serwera: 
**sudo systemctl restart bind9**

## Test działania:
- **dig egzamin.local**
- **nslookup serwer110.egzamin.local**
- **ping egzamin.local**
