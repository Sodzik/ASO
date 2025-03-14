# Telnet
### Krok 1
- Zaloguj się na użytkownika z systemem Linux
### Krok 2
- **sudo apt install telnetd** - instalacja usługi telnet
### Krok 3
- **sudo apt install openbsd-inetd** - instalowanie demona jakby nie był już zainstalowany
- **sudo /etc/init.d/openbsd-inetd restart** - uruchamianie demona *xinetd* na serwerze
### Krok 4
- **sudo apt install nmap** - instalacja usługi nmap 
- **nmap 1-sn  *IP serwera*** - sprawdza czy port 23 (inaczej telnet) został otwarty
### Krok 5
- **telnet *IP serwera*** - klient sprawdza czy mamy połączenie z serwerem
### Krok 6
- **ls -l** - sprawdzamy z klienta czy w katalogu bieżącym są pliki z serwera
### Krok 7
- Zakończ sesje telnet za pomocą komendy **exit**

# SSH
### Krok 1
- Zaloguj się na użytkownika z systemem Linux
### Krok 2
- **sudo apt install ssh** - instalacja usługi ssh
### Krok 3
- **sudo apt install openssh-server** - instalujemy demona **SSH**
- **sudo /etc/init.d/ssh restart** - uruchamiamy demona **SSH**
### Krok 4
- **sudo ssh *nazwa użytkownika*@*IP serwera* -p 22** - klient sprawdza połączenie połączenie z serwerem
### Krok 5
- Zakończ sesje SSH za pomocą komendy **exit**
