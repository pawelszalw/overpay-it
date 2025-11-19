\# Dokument wymagań produktu (PRD) - Kalkulator i Tracker Nadpłat Kredytu



\## 1. Przegląd produktu

Aplikacja webowa "Kalkulator i Tracker Nadpłat Kredytu" to narzędzie wspierające kredytobiorców w procesie spłacania zobowiązań, głównie hipotecznych. Produkt działa w dwóch trybach: jako publicznie dostępny symulator "co by było, gdyby" dla użytkowników anonimowych oraz jako osobisty tracker postępów dla użytkowników zarejestrowanych. Celem aplikacji jest uświadamianie realnych korzyści finansowych płynących z nadpłacania kredytu, motywowanie do regularnych nadpłat poprzez wizualizację oszczędności oraz dostarczanie prostego narzędzia do śledzenia historii dokonanych nadpłat i ich wpływu na harmonogram spłaty.



\## 2. Problem użytkownika

Kredytobiorcy w Polsce często nie mają prostego i motywującego narzędzia, które pozwoliłoby im zrozumieć realne, długoterminowe korzyści płynące z nadpłacania kredytu hipotecznego. Złożoność obliczeń, brak natychmiastowej gratyfikacji i wizualizacji oszczędności sprawiają, że regularne nadpłaty są psychologicznie trudne. W efekcie, potencjalne oszczędności rzędu dziesiątek, a nawet setek tysięcy złotych pozostają niezrealizowane, a użytkownicy spłacają kredyt dłużej i drożej, niż jest to konieczne.



\## 3. Wymagania funkcjonalne

\### 3.1. Użytkownik Anonimowy (Symulator)

\- F.A1: Możliwość wprowadzenia kluczowych danych kredytu (pozostała kwota, oprocentowanie, liczba rat).

\- F.A2: Możliwość symulacji różnych scenariuszy nadpłat: jednorazowych, cyklicznych miesięcznych, cyklicznych rocznych.

\- F.A3: Wybór strategii nadpłaty: skrócenie okresu kredytowania, zmniejszenie raty lub strategia mieszana ("kula śnieżna").

\- F.A4: Prezentacja wyników symulacji w formie liczbowej, pokazującej łączną kwotę zaoszczędzonych odsetek i liczbę skróconych miesięcy.



\### 3.2. Użytkownik Zarejestrowany (Tracker)

\- F.R1: Możliwość założenia konta za pomocą adresu e-mail i hasła oraz logowania.

\- F.R2: Proces onboardingu polegający na zapisaniu danych swojego kredytu w systemie.

\- F.R3: Dostęp do panelu głównego (dashboard) z podsumowaniem postępów.

\- F.R4: Możliwość ręcznego dodawania historycznych i bieżących nadpłat (kwota i data).

\- F.R5: Automatyczne przeliczanie i wizualizacja kluczowych danych na dashboardzie po każdej dodanej nadpłacie: pozostały kapitał, suma nadpłat, zaoszczędzone odsetki, nowa data końca kredytu, liczba skróconych rat.



\### 3.3. Funkcjonalności Wspólne

\- F.C1: Dostęp do pomocy kontekstowej (dymki z podpowiedziami) przy bardziej skomplikowanych polach formularzy.

\- F.C2: Możliwość przesłania opinii lub zgłoszenia błędu w obliczeniach za pomocą linku `mailto` w stopce strony.



\## 4. Granice produktu

Wersja 1.0 (MVP) celowo pomija następujące funkcjonalności, aby umożliwić szybkie wdrożenie i weryfikację rynkową:

\- Brak wizualizacji graficznych (wykresów, diagramów); wszystkie dane prezentowane są w formie liczbowej i tabelarycznej.

\- Brak integracji z systemami bankowymi; wszystkie dane i nadpłaty są wprowadzane manualnie przez użytkownika.

\- Brak funkcji "resetuj hasło".

\- Brak zapisu danych (np. w `localStorage`) dla użytkowników anonimowych; każda sesja wymaga ponownego wprowadzenia danych.

\- System obsługuje jedynie proste scenariusze kredytowe; nie uwzględnia wakacji kredytowych, karencji w spłacie, zmiany oprocentowania w trakcie trwania kredytu (np. ze stałego na zmienne).

\- Logika obliczeniowa zakłada, że nadpłata jest księgowana i pomniejsza kapitał na początku kolejnego miesiąca rozliczeniowego.



\## 5. Historyjki użytkowników

\### Uwierzytelnianie i Zarządzanie Kontem

\- ID: US-001

\- Tytuł: Rejestracja nowego użytkownika

\- Opis: Jako nowy użytkownik, chcę móc założyć konto w aplikacji przy użyciu mojego adresu e-mail i hasła, aby móc zapisywać dane mojego kredytu i śledzić postępy w nadpłatach.

\- Kryteria akceptacji:

&nbsp; 1. Formularz rejestracji zawiera pola: adres e-mail, hasło, powtórz hasło.

&nbsp; 2. System waliduje, czy podany e-mail ma poprawny format.

&nbsp; 3. System waliduje, czy hasła w obu polach są identyczne.

&nbsp; 4. Po pomyślnej rejestracji, użytkownik jest automatycznie zalogowany i przekierowany do strony onboardingu (wprowadzenia danych kredytu).

&nbsp; 5. System uniemożliwia rejestrację na adres e-mail, który już istnieje w bazie danych.



\- ID: US-002

\- Tytuł: Logowanie do aplikacji

\- Opis: Jako zarejestrowany użytkownik, chcę móc zalogować się do aplikacji przy użyciu mojego adresu e-mail i hasła, aby uzyskać dostęp do mojego panelu z danymi o kredycie.

\- Kryteria akceptacji:

&nbsp; 1. Formularz logowania zawiera pola: adres e-mail, hasło.

&nbsp; 2. Po poprawnym podaniu danych, użytkownik jest przekierowywany do swojego panelu głównego.

&nbsp; 3. W przypadku podania błędnych danych, wyświetlany jest stosowny komunikat o błędzie.



\### Użytkownik Anonimowy (Symulator)

\- ID: US-003

\- Tytuł: Wprowadzanie danych kredytu do symulacji

\- Opis: Jako użytkownik anonimowy, chcę móc wprowadzić podstawowe dane mojego kredytu (pozostała kwota, oprocentowanie, liczba pozostałych rat), aby przygotować symulator do obliczeń.

\- Kryteria akceptacji:

&nbsp; 1. Na stronie głównej widoczny jest formularz z polami: "Pozostała kwota kapitału (PLN)", "Aktualne oprocentowanie roczne (%)", "Liczba pozostałych rat (miesiące)".

&nbsp; 2. Pola akceptują tylko wartości liczbowe.

&nbsp; 3. Po wypełnieniu formularza i jego zatwierdzeniu, przechodzę do ekranu symulacji.



\- ID: US-004

\- Tytuł: Symulacja nadpłat kredytu

\- Opis: Jako użytkownik anonimowy, chcę móc zdefiniować scenariusz nadpłat (jednorazowa, cykliczna miesięczna, cykliczna roczna) oraz wybrać cel nadpłaty (skrócenie okresu, obniżenie raty, strategia "mix"), aby zobaczyć potencjalne korzyści.

\- Kryteria akceptacji:

&nbsp; 1. Mogę wprowadzić kwotę dla nadpłaty jednorazowej "teraz".

&nbsp; 2. Mogę wprowadzić kwotę dla cyklicznej nadpłaty miesięcznej.

&nbsp; 3. Mogę wprowadzić kwotę dla cyklicznej nadpłaty rocznej.

&nbsp; 4. Mogę wybrać jedną z trzech opcji celu nadpłaty: "Skróć okres kredytowania", "Zmniejsz ratę" lub "Strategia mieszana (kula śnieżna)".

&nbsp; 5. Po kliknięciu przycisku "Oblicz", system wykonuje symulację.



\- ID: US-005

\- Tytuł: Przeglądanie wyników symulacji

\- Opis: Jako użytkownik anonimowy, po przeprowadzeniu symulacji chcę zobaczyć jasne i zrozumiałe podsumowanie, które pokaże mi, ile pieniędzy i czasu mogę zaoszczędzić.

\- Kryteria akceptacji:

&nbsp; 1. Wynik jest prezentowany w formie liczbowej.

&nbsp; 2. Wyświetlana jest informacja "Zaoszczędzisz X PLN na odsetkach".

&nbsp; 3. Wyświetlana jest informacja "Skrócisz kredyt o Y miesięcy".

&nbsp; 4. Pod wynikami symulacji znajduje się wezwanie do akcji (CTA) zachęcające do założenia konta.



\### Użytkownik Zarejestrowany (Tracker)

\- ID: US-006

\- Tytuł: Onboarding - zapisanie danych kredytu

\- Opis: Jako nowo zarejestrowany użytkownik, po pierwszym zalogowaniu chcę zostać poprowadzony przez proces wprowadzenia i zapisania danych mojego kredytu, aby system mógł śledzić moje postępy.

\- Kryteria akceptacji:

&nbsp; 1. Po pierwszym logowaniu jestem przekierowany do formularza identycznego jak w US-003.

&nbsp; 2. Wprowadzone dane są zapisywane na moim koncie.

&nbsp; 3. Po zapisaniu danych jestem przekierowywany do panelu głównego.

&nbsp; 4. Panel główny nie jest dostępny, dopóki dane kredytu nie zostaną zapisane.



\- ID: US-007

\- Tytuł: Przeglądanie panelu głównego (dashboardu)

\- Opis: Jako zalogowany użytkownik, chcę widzieć na jednym ekranie podsumowanie mojego postępu w spłacie kredytu, aby być zmotywowanym do dalszych działań.

\- Kryteria akceptacji:

&nbsp; 1. Panel wyświetla tabelę z następującymi danymi: "Pozostały kapitał", "Skumulowane nadpłaty", "Łącznie zaoszczędzone odsetki", "Nowa data końca kredytu", "Liczba skróconych rat".

&nbsp; 2. Dane są aktualne i odzwierciedlają stan po ostatniej dodanej nadpłacie.



\- ID: US-008

\- Tytuł: Dodawanie rzeczywistej nadpłaty

\- Opis: Jako zalogowany użytkownik, chcę móc w prosty sposób dodać informację o dokonanej przeze mnie nadpłacie, podając jej kwotę i datę.

\- Kryteria akceptacji:

&nbsp; 1. Na panelu głównym znajduje się wyraźnie widoczny przycisk "Dodaj nadpłatę".

&nbsp; 2. Po kliknięciu przycisku pojawia się prosty formularz z polami: "Kwota" i "Data".

&nbsp; 3. Po zatwierdzeniu formularza dane są zapisywane w systemie.



\- ID: US-009

\- Tytuł: Aktualizacja danych po dodaniu nadpłaty

\- Opis: Jako zalogowany użytkownik, po dodaniu nowej nadpłaty chcę natychmiast zobaczyć zaktualizowane dane w moim panelu głównym.

\- Kryteria akceptacji:

&nbsp; 1. Po pomyślnym dodaniu nadpłaty wyświetlany jest komunikat o sukcesie.

&nbsp; 2. Wartości w tabeli wyników (US-007) są automatycznie przeliczane i odświeżane.

&nbsp; 3. Zaktualizowane dane odzwierciedlają wpływ nowej nadpłaty na harmonogram spłaty.



\### Funkcjonalności Wspólne

\- ID: US-010

\- Tytuł: Uzyskiwanie pomocy kontekstowej

\- Opis: Jako użytkownik, podczas wypełniania formularzy chcę mieć możliwość uzyskania wyjaśnienia dla bardziej skomplikowanych pól (np. "oprocentowanie"), aby upewnić się, że wprowadzam poprawne dane.

\- Kryteria akceptacji:

&nbsp; 1. Przy wybranych polach formularzy znajduje się ikona znaku zapytania ("?").

&nbsp; 2. Po najechaniu kursorem myszy na ikonę, wyświetla się dymek z krótkim, pomocnym tekstem wyjaśniającym.



\- ID: US-011

\- Tytuł: Zgłaszanie opinii lub błędów

\- Opis: Jako użytkownik, jeśli zauważę błąd w obliczeniach lub mam sugestię dotyczącą aplikacji, chcę mieć łatwy sposób na skontaktowanie się z twórcami.

\- Kryteria akceptacji:

&nbsp; 1. W stopce aplikacji znajduje się link tekstowy "Zauważyłeś różnicę w obliczeniach? Daj nam znać...".

&nbsp; 2. Kliknięcie w link otwiera domyślny program pocztowy użytkownika.

&nbsp; 3. Nowa wiadomość ma wstępnie wypełniony adres odbiorcy oraz temat (np. "Opinia - Kalkulator Nadpłat").



\## 6. Metryki sukcesu

Sukces wersji MVP będzie mierzony za pomocą następujących kluczowych wskaźników (KPIs):

\- Zaangażowanie: Stosunek liczby przeprowadzonych symulacji do liczby unikalnych użytkowników anonimowych. Wysoki wskaźnik będzie oznaczał, że narzędzie jest postrzegane jako użyteczne i angażujące.

\- Konwersja: Procent użytkowników anonimowych, którzy zakładają konto po wykonaniu co najmniej jednej symulacji. Będzie to miara skuteczności propozycji wartości, jaką oferuje tryb trackera.

\- Retencja: Miesięczny wskaźnik powracających zalogowanych użytkowników (użytkownicy, którzy logują się co najmniej drugi raz w ciągu miesiąca). Wskaźnik ten pokaże, czy użytkownicy widzą wartość w regularnym śledzeniu swoich postępów.

