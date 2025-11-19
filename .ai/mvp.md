Dokument Wymagań Produktowych (PRD): Kalkulator i Tracker Nadpłat Kredytu
Wersja: 1.0 (MVP) Data: 9 października 2025

1. Wprowadzenie
1.1. Problem
Kredytobiorcy w Polsce często nie mają prostego i motywującego narzędzia, które pozwoliłoby im zrozumieć realne, długoterminowe korzyści płynące z nadpłacania kredytu hipotecznego. Brak natychmiastowej gratyfikacji i wizualizacji oszczędności sprawia, że regularne nadpłaty są psychologicznie trudne, a potencjalne oszczędności rzędu dziesiątek lub setek tysięcy złotych pozostają niezrealizowane.

1.2. Rozwiązanie
Tworzymy aplikację webową, która pełni dwie kluczowe role:

Dla użytkowników anonimowych: Zaawansowany symulator "co by było, gdyby", pozwalający na obliczenie potencjalnych oszczędności przy różnych scenariuszach nadpłat.

Dla użytkowników zarejestrowanych: Prosty i motywujący tracker (narzędzie do śledzenia), który monitoruje rzeczywiste, dokonane nadpłaty i na bieżąco pokazuje osiągnięte korzyści.

1.3. Grupa Docelowa
Osoby posiadające kredyt hipoteczny na polskim rynku, oparte głównie na oprocentowaniu zmiennym (WIBOR + marża) lub stałym, które szukają sposobów na skrócenie okresu kredytowania i zmniejszenie całkowitego kosztu kredytu.

1.4. Kluczowe Wskaźniki Sukcesu (KPIs) dla MVP
Zaangażowanie: Stosunek liczby przeprowadzonych symulacji do liczby unikalnych użytkowników.

Konwersja: Procent użytkowników, którzy zakładają konto po wykonaniu symulacji.

Retencja: Miesięczny wskaźnik powracających zalogowanych użytkowników.

2. Cele Produktu
Cel Użytkownika: Dać użytkownikom jasność i motywację do nadpłacania kredytu poprzez proste wizualizowanie oszczędności w czasie i pieniądzach.

Cel Projektu: Szybkie wdrożenie funkcjonalnej wersji MVP, aby zweryfikować pomysł, zebrać opinie od pierwszych użytkowników i stworzyć fundament pod dalszy rozwój.

3. Wymagania i Funkcjonalności
Aplikacja będzie działać w dwóch odrębnych trybach:

3.1. Tryb Anonimowy (Symulator)
Cel: Pozwolić każdemu szybko i bez zobowiązań oszacować potencjalne korzyści z nadpłat. Dane nie są zapisywane po stronie serwera.

Funkcjonalności:

F.A1: Formularz Danych Kredytu: Użytkownik wprowadza podstawowe dane swojego kredytu:

Pozostała kwota kapitału (PLN)

Aktualne oprocentowanie roczne (%)

Liczba pozostałych rat (miesiące)

F.A2: Formularz Symulacji Nadpłat: Użytkownik może zasymulować przyszłe nadpłaty w różnych wariantach:

Nadpłata cykliczna co miesiąc (np. 500 PLN)

Jednorazowa nadpłata "teraz" (np. 50 000 PLN)

Dodatkowe, cykliczne nadpłaty roczne (np. 5 000 PLN co roku w grudniu)

Użytkownik wybiera cel nadpłaty: skrócenie okresu kredytowania, zmniejszenie raty lub strategia "mix".

F.A3: Wyświetlanie Wyników Symulacji: System prezentuje wynik w formie prostego podsumowania liczbowego: "Zaoszczędzisz X PLN", "Skrócisz kredyt o Y miesięcy".

3.2. Tryb Zarejestrowany (Tracker)
Cel: Pozwolić użytkownikowi na śledzenie faktycznie dokonanych nadpłat i monitorowanie realnych oszczędności w czasie.

Funkcjonalności:

F.R1: Minimalny System Rejestracji i Logowania:

Rejestracja za pomocą adresu e-mail i hasła.

Logowanie.

MVP celowo pomija funkcję "resetuj hasło".

F.R2: Onboarding Użytkownika: Po pierwszym zalogowaniu użytkownik jest kierowany do formularza (identycznego z F.A1), aby zapisać dane swojego kredytu. Jest to warunek konieczny do zobaczenia panelu głównego.

F.R3: Panel Główny (Dashboard): Główny ekran dla zalogowanego użytkownika, prezentujący jego aktualny postęp.

F.R4: Tabela Wyników i Postępów: Na panelu głównym wyświetlana jest tabela z kluczowymi danymi:

Pozostały kapitał

Skumulowane nadpłaty

Łącznie zaoszczędzone odsetki

Nowa data końca kredytu

Liczba rat skrócona o

F.R5: Funkcja Dodawania Rzeczywistej Nadpłaty:

Wyraźnie widoczny przycisk "Dodaj nadpłatę".

Prosty formularz z polami: "Kwota" i "Data".

Po zatwierdzeniu, system przelicza dane w Tabeli Wyników (F.R4) i wyświetla komunikat o sukcesie.

3.3. Funkcjonalności Wspólne
F.C1: Mechanizm Zbierania Opinii: Link tekstowy w stopce ("Zauważyłeś różnicę w obliczeniach? Daj nam znać..."), który otwiera domyślny program pocztowy użytkownika z przygotowanym tematem.

F.C2: Pomoc Kontekstowa: Ikony pomocy ("?") przy bardziej skomplikowanych polach (np. "Oprocentowanie roczne"), które po najechaniu wyświetlają dymek z podpowiedzią.

4. Założenia i Uproszczenia w Wersji MVP
Aby zapewnić szybkie wdrożenie, MVP będzie oparte na następujących uproszczeniach:

Brak wizualizacji graficznych: Wszystkie dane prezentowane są w formie liczb i tabel.

Uproszczona logika księgowania: Wszystkie nadpłaty, dla celów obliczeniowych, są uznawane za pomniejszające kapitał na początku kolejnego miesiąca/okresu rozliczeniowego.

Brak funkcji "resetuj hasło": Użytkownik musi zarządzać swoim hasłem we własnym zakresie.

Wsparcie tylko dla prostych kredytów: System nie obsługuje scenariuszy takich jak wakacje kredytowe, okresy karencji w spłacie czy zmiany oprocentowania ze stałego na zmienne w trakcie trwania kredytu.

Brak zapisu danych dla gości: Użytkownik anonimowy musi wprowadzać dane kredytu przy każdej wizycie. Aplikacja nie korzysta z pamięci lokalnej przeglądarki.

Tylko manualne wprowadzanie nadpłat: Brak integracji z systemami bankowymi.