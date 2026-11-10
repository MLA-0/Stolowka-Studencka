Klient
1. Przeglądanie menu i składanie zamówienia [M] Jako klient, chcę przeglądać menu i dodać wybrane dania do koszyka, aby złożyć zamówienie przed przyjściem do stołówki i uniknąć stania w kolejce.
      1: Klient może dodać do koszyka tylko dania ze statusem „Dostępne”.
      2: Przycisk dodawania jest nieaktywny dla dań oznaczonych jako „Wyprzedane”.
      3: Przed przejściem do płatności system wyświetla podsumowanie: listę dań, ilość oraz łączną kwotę.
      4: Jeśli w trakcie finalizacji zamówienia wybrane danie zostanie wyprzedane, system blokuje transakcję i prosi o jego usunięcie z koszyka.
2. Płatność online [M] Jako klient, chcę opłacić moje zamówienie online natychmiast po jego złożeniu, aby proces odbioru był bezgotówkowy.
      1: Po zatwierdzeniu koszyka klient jest przekierowywany do zewnętrznej bramki płatności.
      2: Zamówienie trafia do kuchni (zmienia status) dopiero po odnotowaniu pozytywnej autoryzacji płatności.
3. Śledzenie statusu i odbiór [M] Jako klient, chcę na bieżąco sprawdzać status zamówienia i wiedzieć kiedy mogę odebrać danie.
      1: Po opłaceniu zamówienia klient otrzymuje unikalny numer (lub kod).
      2: Widok klienta prezentuje aktualny status: Opłacone -> W przygotowaniu -> Gotowe do odbioru -> Wydane.
      3: Kiedy zamówienie osiągnie status „Gotowe do odbioru”, system wyraźnie to sygnalizuje na ekranie urządzenia.
4. Obsługa błędu płatności [M] Jako klient, chcę otrzymać jasny komunikat o statusie płatności a w przypadku odrzuceniu móc ją ponowić.
      1: Zamówienie z odrzuconą płatnością otrzymuje status „Oczekuje na płatność”.
      2: Klient widzi przycisk „Spróbuj ponownie” pozwalający wznowić proces bez ponownego kompletowania koszyka.
 Pracownik stołówki
5. Obsługa aktywnych zamówień [M] Jako pracownik stołówki, chcę widzieć listę opłaconych zamówień i móc zmieniać ich status, aby organizować wydawanie posiłków.
      1: Panel wyświetla wyłącznie zamówienia ze statusem „Opłacone”, „W przygotowaniu” i „Gotowe do odbioru”.
      2: Zamówienia są posortowane chronologicznie (najstarsze opłacone na górze).
      3: Każde zamówienie ma widoczne przyciski akcji do ręcznej zmiany statusu.
6. Zarządzanie dostępnością [M] Jako pracownik stołówki, chcę w dowolnej chwili przełączyć dostępność danego dania, aby zablokować możliwość jego dalszego zamawiania lub umożliwić jego zamówienie.
      1: Pracownik ma dostęp do listy dzisiejszego menu z przełącznikiem „Dostępne / Wyprzedane” przy każdej pozycji.
      2: Zmiana statusu na „Wyprzedane” natychmiast blokuje możliwość zamawiania tego dania po stronie klienta.
7. Monitorowanie premii [S] Jako pracownik stołówki, chcę widzieć licznik wydanych przeze mnie posiłków w trakcie bieżącej zmiany, aby móc na bieżąco śledzić realizację mojego dziennego celu.
      1: Każdorazowe kliknięcie przycisku „Wydaj zamówienie” powoduje powiązanie ID tego zamówienia z ID aktualnie zalogowanego pracownika w bazie danych.
      2: Pracownik widzi w panelu sumę zamówień wydanych w podziale na dni, tygodnie i miesiące.
      3: W przypadku, gdy inny pracownik przejmie zamówienie (np. zmiana zmiany w trakcie gotowania), punkt trafia do osoby, która sfinalizowała akcję „Wydaj zamówienie”. 

8.Ochrona dostępu [M] Jako pracownik stołówki, chcę mieć możliwość logowania się do systemu za pomocą unikalnego loginu i hasła, aby chronić dostęp do panelu zamówień przed osobami nieuprawnionymi i pracować na własnym profilu.
      1: Pracownik musi podać poprawny login i hasło, aby uzyskać dostęp do panelu.
      2: W panelu znajduje się przycisk „Wyloguj”, który natychmiastowo przerywa sesję użytkownika.
      3: System nie pozwala na zalogowanie się na to samo konto z dwóch różnych urządzeń jednocześnie.

Administrator 
9. Zarządzanie menu i cenami [M] Jako administrator, chcę dodawać, edytować i usuwać dania z menu, aby oferta w systemie była spójna z rzeczywistym jadłospisem.
      1: Dodawanie dania wymaga podania: Nazwy, Ceny i Kategorii.
      2: Zmiana ceny lub usunięcie dania nie modyfikuje danych na opłaconych już zamówieniach.
10. Automatyczne anulowanie [S] Jako administrator, chcę automatycznie anulować zamówienia, aby zwalniać zasoby i blokady dań.
      1: Zamówienie ze statusem „Oczekuje na płatność” jest po 15 minutach zmieniane na „Anulowane”.
11. Konfiguracja czasu pracy [S] Jako administrator, chcę konfigurować godziny przyjmowania zamówień, aby zapobiec zamówieniom poza czasem pracy kuchni.
      1: Koszyk i płatności są zablokowane poza zdefiniowanymi godzinami działania stołówki.
System
12.Odbiór powiadomień o sukcesie [M] Jako system stołówki, chcę asynchronicznie odbierać powiadomienia od operatora płatności o zaksięgowaniu środków, aby natychmiast, bez udziału człowieka, przekazać zamówienie do realizacji na kuchnię.
      1: Po otrzymaniu kryptograficznie zweryfikowanego powiadomienia o sukcesie, system zmienia status zamówienia na „Opłacone”.
      2: Jeśli użytkownik zamknie przeglądarkę zanim wróci ze strony banku do aplikacji, zamówienie i tak musi zostać poprawnie opłacone dzięki komunikacji w tle.
      3: Potwierdzenie jednej płatności przyjdzie tylko jedno, niezależnie od tego ile wyśle ich operator
13. Automatyczne zwroty środków [M] Jako pracownik stołówki, chcę, aby po moim ręcznym anulowaniu już opłaconego zamówienia (np. z powodu nagłego braku prądu lub zepsucia się ostatniej porcji), system automatycznie zlecał zwrot środków do operatora płatności, aby klient szybko odzyskał pieniądze bez interwencji księgowości.
      1: Po kliknięciu „Anuluj zamówienie” na opłaconym zamówieniu, system wysyła żądanie do bramki płatniczej na pełną kwotę transakcji.
      2: System zapisuje w historii zamówienia informację „Zlecono zwrot środków”.
      3: W przypadku błędu API administrator otrzymuje powiadomienie e-mail o konieczności ręcznego wykonania zwrotu.

Wykluczone z obecnego zakresu (Won't have)
      1. Rozliczanie płatności gotówkowych przy kasie w aplikacji.
      2. Dzielenie rachunku (split bill) między użytkowników.
      3. Program lojalnościowy
2. Wymagania niefunkcjonalne
    • Wydajność i Skalowalność: System musi obsłużyć nagłe skoki ruchu wynikające z przerw między zajęciami, umożliwiając jednoczesne, bezproblemowe korzystanie z aplikacji przez minimum 500 użytkowników na jednym wydziale.
    • Użyteczność: Interfejs użytkownika musi być w pełni responsywny, zaprojektowany w pierwszej kolejności pod ekrany urządzeń mobilnych.
    • Bezpieczeństwo i Autoryzacja: Konta pracowników muszą być chronione loginem i hasłem.
    • Dostępność (Availability): System powinien gwarantować bezawaryjne działanie na poziomie 99,9% w zdefiniowanych godzinach otwarcia stołówki.
    • Aktualizacja danych w czasie rzeczywistym: Ekran statusu zamówienia u klienta oraz lista zamówień u pracownika powinny odświeżać się automatycznie bez konieczności ręcznego przeładowywania strony przez użytkownika.
