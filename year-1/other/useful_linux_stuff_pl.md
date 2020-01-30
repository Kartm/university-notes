## Spis treści

- [Ścieżki](#Ścieżki)
  - [Ścieżki bezwzględne](#Ścieżki-bezwzględne)
  - [Ścieżki względne](#Ścieżki-względne)
- [Uprawnienia](#uprawnienia)
  - [Oznaczenia](#oznaczenia)
  - [Przykład](#przykład)
  - [Chmod - nadawanie uprawnień](#chmod---nadawanie-uprawnień)
  - [Chmod - nadawanie uprawnień ósemkowo](#chmod---nadawanie-uprawnień-ósemkowo)
- [Przydatne komendy](#przydatne-komendy)
    - [**pwd** - wyświetlenie ścieżki dostępu do bieżącego katalogu](#pwd---wyświetlenie-ścieżki-dostępu-do-bieżącego-katalogu)
    - [**touch** - tworzenie nowego pliku lub zmiana daty modyfikacji](#touch---tworzenie-nowego-pliku-lub-zmiana-daty-modyfikacji)
    - [**mkdir** - tworzenie katalogu](#mkdir---tworzenie-katalogu)
    - [**sort** - sortuje zawartość pliku tekstowego](#sort---sortuje-zawartość-pliku-tekstowego)
      - [Przydatne opcje:](#przydatne-opcje)
      - [Przykłady użycia](#przykłady-użycia)
    - [**grep** - przeszukiwanie tekstu linijka po linijce](#grep---przeszukiwanie-tekstu-linijka-po-linijce)
    - [**wc** - liczy ilość znaków, słów i linii w pliku](#wc---liczy-ilość-znaków-słów-i-linii-w-pliku)
    - [**less** - wyświetla zawartość pliku strona po stronie](#less---wyświetla-zawartość-pliku-strona-po-stronie)
    - [**cat** - wyświetla zawartość pliku](#cat---wyświetla-zawartość-pliku)
    - [**passwd** - zmienia hasło użytkownika](#passwd---zmienia-hasło-użytkownika)
    - [**ps** - wyświetla listę procesów](#ps---wyświetla-listę-procesów)
    - [**kill** - wysyła podany sygnał do danego procesu](#kill---wysyła-podany-sygnał-do-danego-procesu)
    - [**finger** - sprawdzanie informacji o użytkowniku i wypisywanie wszystkich użytkowników](#finger---sprawdzanie-informacji-o-użytkowniku-i-wypisywanie-wszystkich-użytkowników)
- [Vim](#vim)

# Ścieżki

## Ścieżki bezwzględne

Bezwzględna ścieżka dostępu rozpoczyna się od folderu głównego. Folder główny jest pojedynczym folderem, od którego rozpoczyna się cała hierarchia. Pierwszym znakiem ścieżki bezwzględnej jest ukośnik (/). Przykład bezwzględnej ścieżki dostępu do pliku "list":

> /home/s/prow/p-k1g2/chaos

## Ścieżki względne

Jeśli ścieżka dostępu nie rozpoczyna się ukośnikiem, jest ścieżką względną.

Względna ścieżka dostępu przedstawia lokalizację pliku lub folderu względem folderu bieżącego. Aby z folderu bieżącego przejść niżej w strukturze drzewa, nie trzeba podawać pełnej ścieżki dostępu. Wystarczy wpisać ścieżkę rozpoczynając od nazwy następnego folderu. Na przykład, jeżeli bieżącym folderem jest /usr/dt, a użytkownik zamierza przejść do folderu /usr/dt/config/listy, wystarczy wprowadzić względną ścieżkę dostępu:

> config/listy

# Uprawnienia

## Oznaczenia

- **u** - użytkownik
- **g** - group (grupa)
- **o** - other (inni)
- **a** - all (wszyscy)
- **r** - uprawnienie do odczytu pliku
- **w** - uprawnienie do modyfikacji pliku
- **x** - uprawnienie do wykonywania/uruchamiania pliku

## Przykład

Użyjemy komendy `ls -lga` w folderze "linuks":

> drwxr-xr-x 2 root root 512 May 3 00:37 linuks

Oto opis uprawnień:
| d | rwx | r-x | r-x |
| ---------------------- | --- | --- | --- |
| d = directory (folder) | u | g | o |

## Chmod - nadawanie uprawnień

- Nadanie użytkownikowi wszystkich uprawnień
  > chmod u+rxw nazwa_pliku
- Zabranie użytkownikowi wszystkich uprawnień
  > chmod u-rxw nazwa_pliku

## Chmod - nadawanie uprawnień ósemkowo

Nadawac uprawnienia można również wpisując odpowiednią liczbę. Trzeba ją policzyć w następujący sposób:

- **r** = 4 -odczyt
- **w** = 2 modyfikacja
- **x** = 1 wykonywanie

| d      | rwx       | r-x       | r-x       |
| ------ | --------- | --------- | --------- |
| &nbsp; | u         | g         | o         |
| &nbsp; | 4 + 2 + 1 | 4 + 0 + 1 | 4 + 0 + 1 |
| &nbsp; | =7        | =5        | =5        |

Aby je nadać, wystarczy użyć komendy:

> chmod 755 nazwa_pliku

# Przydatne komendy

### **pwd** - wyświetlenie ścieżki dostępu do bieżącego katalogu

Przykładowe użycie: `pwd`

> /tmp/KATALOG_ROBOCZY

---

### **touch** - tworzenie nowego pliku lub zmiana daty modyfikacji

Polecenie zmienia datę modyfikacji lub ostatniego dostępu pliku. Wywołane z argumentem tworzy (jeżeli jeszcze nie istnieje) nowy plik o takiej jak argument nazwie i ustala jego daty modyfikacji i ostatniego dostępu na aktualną datę.

Wywołanie `touch plik2` tworzy nowy plik `plik2`.

---

### **mkdir** - tworzenie katalogu

Polecenie to bez żadnych dodatkowych opcji tworzy katalog podany jako argument. Jeśli argumentów będzie więcej, to odpowiednia liczba katalogów zostanie utworzona.

- Wywołanie `mkdir katalog_1` stworzy katalog o nazwie `katalog_1`.
- Wywołanie `mkdir -m 600 katalog_1 katalog_2` stworzy dwa katalogi `katalog_1` oraz `katalog_2` o ósemkowych prawach dostępu `600` (właściciel ma prawa do odczytu i zapisu, nikt inny nie ma dostępu do pliku).

---

### **sort** - sortuje zawartość pliku tekstowego

#### Przydatne opcje:

- -r sortowanie w odwrotnej kolejności
- -u usuwanie duplikatów
- -f nie rozróżnianie małych i dużych liter
- -n sortowanie liczb (domyślnie dane sortowane traktowane są jako ciągi znaków)

#### Przykłady użycia

- posortowanie linii zawartych w pliku dane.txt i przesłanie wyniku do pliku posortowane.txt
  > sort dane.txt > posortowane.txt
- sortowanie kolumnami<br>
  Opcja **+liczba** pozwala pominąć przy sortowaniu określoną liczbę pól (pola standardowo są rozdzielone białymi znakami tj. spacjami, tabami etc.).<br><br>Wyświetlenie posortowanej listy plików według piątej kolumny otrzymanej za pomocą polecenia ls -l:
  > ls -l | sort +4 -n

---

### **grep** - przeszukiwanie tekstu linijka po linijce

Wyświetla pasujące linijki.

- `grep 'slowo1\|slowo2'` wyszuka linie zawierające 'slowo1' lub 'slowo2'.
- grep można łączyć za pomocą pipe: `cat plik | grep 'abc'` wyświetli wszystkie linijki z pliku `plik` zawierające `abc`.

---

### **wc** - liczy ilość znaków, słów i linii w pliku

Przykład:

- wywołanie `wc dane.txt` wyświetli ilość znaków, słów i linii w pliku `dane.txt`
  >
- wywołanie `wc -l *.txt` wyświetli liczbę linii we wszystkich plikach o rozszerzeniu .txt znajdujących się w bieżącym katalogu.

---

### **less** - wyświetla zawartość pliku strona po stronie

Pozwala poruszać się po pliku zarówno w przód jak i w tył.

Przykładowe użycie: `less plik.txt`.

---

### **cat** - wyświetla zawartość pliku

Przykład:

- wyświetlenie zawartości pliku `passwd`
  > cat /etc/passwd
- łączenie plików `plik1`, `plik2`, `plik3` w jedną całość o nazwie `plik4`
  > cat plik1 plik2 plik3 > plik4

---

### **passwd** - zmienia hasło użytkownika

Wywołanie `passwd` pozwala zmienić hasło aktualnie zalogowanego użytkownika.

Najpierw użytkownik musi wpisać swoje aktualne hasło, po czym dwukrotnie wpisać nowe. Jeśli wpisane hasło w pierwszej oraz w drugiej próbie są identyczne, hasło użytkownika zostało zmienione.

---

### **ps** - wyświetla listę procesów

Bez podania dodatkowych opcji pokazuje wszystkie procesy, związane z bieżącym użytkownikiem i aktywną sesją naszego terminalu.

- `ps aux` pokazuje procesy wszystkich użytkowników
- `ps -ef` również pokazuje wszystkie procesy, lecz w mniej przyjaznej dla użytkownika formie<br>
  - -e - wyświetla wszystkie uruchomione procesy
  - -f - wyświetla szczegółowe informacje o uruchomionych procesach
  - -u - wyświetla uruchomione procesy danego użytkownika

---

### **kill** - wysyła podany sygnał do danego procesu

PID_procesu
Każdy sygnał posiada odpowiedni numer, który można przekazać zamiast jego nazwy. Na przykład, można skorzystać z:

- „-15” zamiast „-TERM”
- „-9” zamiast „-KILL”.

- Poniższe polecenie wysyła sygnał TERM do wykonywanego procesu. TERM prosi u procesu grzecznie zakończyć pracę. To pozwoli dokonać czyszczenie działających procesów i wyjść bez dodatkowych problemów.

  > kill PID_procesu

- Jeśli program zachowuje się nie tak, jak oczekiwaliśmy, i nie chce zakończyć swojej pracę, możemy to wymusić:
  > kill -9 PID_procesu

---

### **finger** - sprawdzanie informacji o użytkowniku i wypisywanie wszystkich użytkowników

- `finger` wypisuje wszystkich zalogowanych użytkowników
- `finger @komputer` – użytkownicy zalogowani na komputerze o nazwie 'komputer;
- `finger username` – wypisuje informacje o użytkowniku 'username' i wszystkie terminale na których jest zalogowany
- `finger Marek` – wypisuje informacje o wszystkich użytkownikach o imieniu 'marek'

# Vim

Źródła:

- http://info.ee.pw.edu.pl/
- http://www.cybertech.net.pl/
- https://hostovita.pl/
- https://www.arturpyszczuk.pl/
- http://www.is.umk.pl/
- https://www.astrouw.edu.pl/
