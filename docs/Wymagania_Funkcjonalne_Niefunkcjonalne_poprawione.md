 Wymagania funkcjonalne:
 Klient

**1. Przeglądanie menu i składanie zamówienia [M]** Jako klient, chcę przeglądać aktualne menu, wybierać dania i zatwierdzać zamówienie, aby zamówić posiłek przed przyjściem do stołówki.

1. Klient może przeglądać aktualnie opublikowane menu.
2. Klient może wybrać dania, które chce zamówić.
3. Przed zatwierdzeniem zamówienia system sprawdza dostępność wszystkich wybranych dań.
4. Jeżeli co najmniej jedno wybrane danie jest niedostępne, system przekazuje klientowi informację o niedostępności.
5. Po otrzymaniu informacji o niedostępności klient może zmienić zawartość zamówienia, a system ponownie sprawdza dostępność wybranych dań.
6. Jeżeli wszystkie wybrane dania są dostępne, system oblicza końcową kwotę zamówienia.
7. Klient może zatwierdzić zamówienie po sprawdzeniu dostępności dań i obliczeniu końcowej kwoty.

**2. Płatność online [M]** Jako klient, chcę rozpocząć płatność online po zatwierdzeniu zamówienia, aby opłacić je przed odbiorem.

1. Po zatwierdzeniu zamówienia klient może rozpocząć proces płatności.
2. System tworzy żądanie płatności i przekazuje je do operatora płatności.
3. Operator płatności przetwarza żądanie i przekazuje informację o wyniku płatności.
4. Zamówienie jest rejestrowane jako opłacone dopiero po otrzymaniu potwierdzenia pozytywnego wyniku płatności.

**3. Obsługa nieudanej płatności [M]** Jako klient, chcę otrzymać informację o nieudanej płatności i móc zdecydować o jej ponowieniu lub rezygnacji z zamówienia, aby wiedzieć, jak zakończyć proces zakupu.

1. W przypadku niepowodzenia płatności system przekazuje klientowi informację o nieudanej płatności.
2. Klient może zdecydować o ponowieniu płatności albo zrezygnować z zamówienia.
3. Po wybraniu ponowienia płatności system ponownie tworzy żądanie płatności i przekazuje je do przetworzenia.
4. Jeżeli ponowna płatność zakończy się niepowodzeniem, system informuje klienta o ponownym niepowodzeniu i anuluje nieopłacone zamówienie.
5. Jeżeli klient zrezygnuje z ponowienia płatności, system anuluje nieopłacone zamówienie.
6. Po anulowaniu zamówienia klient otrzymuje informację o jego anulowaniu.

**4. Śledzenie statusu zamówienia [M]** Jako klient, chcę sprawdzać aktualny status zamówienia i otrzymywać informację o gotowości posiłku, aby wiedzieć, kiedy zgłosić się po odbiór.

1. Klient może sprawdzić aktualny status swojego zamówienia.
2. System udostępnia klientowi statusy zamówienia: „Opłacone”, „W przygotowaniu”, „Gotowe do odbioru” oraz „Wydane”.
3. Po oznaczeniu zamówienia jako „Gotowe do odbioru” system aktualizuje jego status i udostępnia klientowi informację o gotowym zamówieniu.

**5. Odbiór zamówienia [M]** Jako klient, chcę odebrać przygotowane zamówienie po przedstawieniu jego numeru, aby otrzymać właściwy posiłek.

1. Klient zgłasza się po odbiór zamówienia i przedstawia jego numer.
2. Jeżeli przedstawiony numer jest nieprawidłowy, pracownik odmawia wydania zamówienia.
3. Po odmowie wydania klient może ponownie przedstawić numer zamówienia do weryfikacji.
4. Zamówienie może zostać wydane klientowi po prawidłowej weryfikacji numeru.

Pracownik stołówki

**6. Zarządzanie dostępnością dań [M]** Jako pracownik stołówki, chcę aktualizować dostępność dań, aby klienci mogli zamawiać wyłącznie pozycje, które są dostępne.

1. Pracownik może aktualizować informację o dostępności dań w menu.
2. Zmiana dostępności jest uwzględniana w aktualnym menu udostępnianym klientom.
3. Podczas składania zamówienia system sprawdza dostępność dań na podstawie aktualnych informacji.

**7. Realizacja aktywnych zamówień [M]** Jako pracownik stołówki, chcę otrzymywać opłacone zamówienia i aktualizować ich status w trakcie przygotowywania, aby prawidłowo organizować realizację posiłków.

1. Pracownik otrzymuje informację o nowym opłaconym zamówieniu.
2. Pracownik może przyjąć zamówienie do realizacji.
3. Po przyjęciu zamówienia system ustawia jego status na „W przygotowaniu”.
4. Pracownik przygotowuje posiłek.
5. Po przygotowaniu posiłku pracownik oznacza zamówienie jako „Gotowe”.
6. Po oznaczeniu zamówienia jako gotowe system aktualizuje jego status i udostępnia klientowi informację o gotowości do odbioru.

**8. Weryfikacja numeru i wydanie zamówienia [M]** Jako pracownik stołówki, chcę weryfikować numer zamówienia przedstawiony przez klienta, aby wydawać posiłki właściwym osobom.

1. Pracownik weryfikuje numer zamówienia przedstawiony przez klienta.
2. Jeżeli numer jest nieprawidłowy, pracownik odmawia wydania zamówienia.
3. Po ponownym przedstawieniu numeru przez klienta pracownik może ponowić jego weryfikację.
4. Jeżeli numer jest prawidłowy, pracownik wydaje zamówienie klientowi.
5. Po wydaniu zamówienia system oznacza je statusem „Wydane” i zapisuje zakończenie realizacji.

Administrator

**9. Przygotowanie i publikacja menu [M]** Jako administrator, chcę dodawać lub aktualizować menu, aby aktualna oferta stołówki mogła zostać udostępniona klientom.

1. Administrator może dodać menu lub zaktualizować istniejące menu.
2. Przygotowanie lub aktualizacja menu jest odrębnym etapem i nie musi być wykonywana przed każdym pojedynczym zamówieniem.
3. Po dodaniu lub aktualizacji menu oraz uaktualnieniu dostępności dań system publikuje aktualne menu.

System

**10. Rejestracja opłaconego zamówienia [M]** Jako system stołówki, chcę rejestrować zamówienie po potwierdzeniu pozytywnego wyniku płatności, aby do realizacji trafiały zamówienia opłacone.

1. Po otrzymaniu potwierdzenia pozytywnego wyniku płatności system rejestruje opłacone zamówienie.
2. Po rejestracji system ustawia status zamówienia na „Opłacone”.
3. Zamówienie, dla którego nie otrzymano potwierdzenia pozytywnego wyniku płatności, nie może zostać zarejestrowane jako opłacone.

Wymagania wykluczone (Won't have)

1. Rozliczanie płatności gotówkowych przy kasie w aplikacji.
2. Dzielenie rachunku (split bill) między użytkowników.
3. Program lojalnościowy.
4. Monitorowanie premii pracowników, w tym naliczanie punktów za wydane zamówienia i prezentowanie statystyk dziennych, tygodniowych lub miesięcznych.
5. Rozbudowana obsługa kont pracowników obejmująca wylogowywanie oraz blokowanie jednoczesnego logowania na to samo konto z różnych urządzeń.
6. Konfigurowanie godzin przyjmowania zamówień i blokowanie składania zamówień poza zdefiniowanymi godzinami pracy stołówki.
7. Automatyczne anulowanie nieopłaconego zamówienia wyłącznie z powodu upływu określonego czasu, np. 15 minut.
8. Automatyczne zwracanie środków za już opłacone zamówienie.

2. Wymagania niefunkcjonalne

- **Wydajność i skalowalność:** System musi obsłużyć nagłe skoki ruchu wynikające z przerw między zajęciami, umożliwiając jednoczesne, bezproblemowe korzystanie z aplikacji przez minimum 500 użytkowników na jednym wydziale.
- **Użyteczność:** Interfejs użytkownika musi być w pełni responsywny i zaprojektowany w pierwszej kolejności z myślą o ekranach urządzeń mobilnych.
- **Bezpieczeństwo i autoryzacja:** Konta pracowników muszą być chronione loginem i hasłem.
- **Dostępność (Availability):** System powinien gwarantować bezawaryjne działanie na poziomie 99,9% w zdefiniowanych godzinach otwarcia stołówki.
- **Aktualizacja danych w czasie rzeczywistym:** Status zamówienia prezentowany klientowi oraz informacje o zamówieniach wykorzystywane przez pracownika powinny aktualizować się automatycznie, bez konieczności ręcznego przeładowywania strony.
