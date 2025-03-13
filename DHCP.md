# DHCP
## Krok 1 - instalacja
**Sudo apt-get install isc-dhcp-server** - instaluje usługę DHCP
## Krok 2 - konfiguracja
1. **/etc/defaul/isc-dhcp-server** - Wpisujemy w INTERFACESv4="enp0s3"  lub "eth0" itd.
![image](https://github.com/user-attachments/assets/b5ccfc61-3f0e-4e95-bfd8-b0bdfe942127)
2. **/etc/dhcp/dhcpd.conf** - dodajemy opcjonalny adres serwera i usuwamy # od authoritative
![image](https://github.com/user-attachments/assets/633e4b17-1f0d-4103-b5ed-92166b0ec8d5)
3. **/etc/dhcp/dhcpd.conf**
![Zrzut ekranu 2025-03-13 180832](https://github.com/user-attachments/assets/7bec467c-39e5-4f18-a8a5-b87f111a9199)
4. **sudo systemctl start isc-dhcp-server** - uruchamia usługę
5. **sudo systemctl status isc-dhcp-server** - sprawdza czy usługa została uruchomiona
## Klient
1. Ustawiamy na kliencie metodę **DHCP**
2. Idziemy do terminala/CMD i wpisujemy **ip a**, aby sprawdzić jaki adres został przypisany
### Sprawdzanie użytkowników
Z poziomu serwera należy wpisać **sudo dhcp-lease-list** i powinno pokazać adres MAC, IP (przypisany), nazwę hosta i datę końcową działania
