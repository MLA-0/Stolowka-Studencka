## UC1: Złożenie zamówienia

| Pole                          | Opis                                                                                           |
| ----------------------------- | ---------------------------------------------------------------------------------------------- |
| **Aktor główny**              | Klient                                                                                         |
| **Cel**                       | Wybrać dania z aktualnego menu i zatwierdzić zamówienie z poprawnie obliczoną kwotą            |
| **Warunki wstępne**           | Menu zostało opublikowane, klient ma dostęp do aplikacji                                       |
| **Warunki końcowe (sukces)**  | Zamówienie jest zatwierdzone, a jego końcowa kwota obliczona. Klient może przejść do płatności |
| **Warunki końcowe (porażka)** | Zamówienie nie zostaje zatwierdzone (klient zrezygnował)                                       |
| **Priorytet**                 | Must have                                                                                      |

**Scenariusz główny**
1. Klient otwiera aktualne menu.
2. Klient wybiera dania, które chce zamówić.
3. System sprawdza dostępność wszystkich wybranych dań.
4. Wszystkie dania są dostępne, więc system oblicza końcową kwotę zamówienia.
5. Klient zatwierdza zamówienie.
6. System przechodzi do etapu płatności (UC2).

**Scenariusz alternatywny: niedostępne danie**
1. Co najmniej jedno wybrane danie jest niedostępne; system informuje klienta, które.
2. Klient zmienia zawartość zamówienia (np. usuwa danie lub wybiera inne).
3. System ponownie sprawdza dostępność. Powrót do kroku 3.

---

## UC2: Płatność online za zamówienie

| Pole | Opis |
|---|---|
| **Aktor główny** | Klient |
| **Aktor wspierający** | System płatności (zewnętrzny operator) |
| **Cel** | Opłacić zatwierdzone zamówienie przed odbiorem |
| **Warunki wstępne** | Zamówienie zostało zatwierdzone (UC1), a kwota końcowa jest znana |
| **Warunki końcowe (sukces)** | Zamówienie jest zarejestrowane jako opłacone, ze statusem „Opłacone" |
| **Warunki końcowe (porażka)** | Nieopłacone zamówienie zostaje anulowane, a klient dostaje informację o anulowaniu |
| **Priorytet** | Must have |

**Scenariusz główny**
1. Klient rozpoczyna płatność.
2. System tworzy żądanie płatności i przekazuje je do operatora płatności.
3. Operator przetwarza płatność i zwraca pozytywny wynik.
4. System rejestruje opłacone zamówienie i ustawia status „Opłacone".
5. Zamówienie trafia do obsługi stołówki (UC3).

**Scenariusze alternatywne**
Płatność zakończyła się niepowodzeniem.
  1. System informuje klienta o nieudanej płatności.
  2. Klient wybiera ponowić płatność albo zrezygnować.
  3. Ponowienie: system tworzy nowe żądanie płatności i wraca do kroku 3.
  4. Ponowna płatność kończy się niepowodzeniem. System informuje klienta i anuluje nieopłacone zamówienie.
  5. Rezygnacja. System anuluje nieopłacone zamówienie.
  6. System informuje klienta o anulowaniu zamówienia.

**Reguła biznesowa:** zamówienie nie może zostać zarejestrowane jako opłacone bez potwierdzenia pozytywnego wyniku płatności.

---

## UC3: Realizacja zamówienia

| Pole                         | Opis                                                                           |
| ---------------------------- | ------------------------------------------------------------------------------ |
| **Aktor główny**             | Pracownik stołówki                                                             |
| **Cel**                      | Przyjąć opłacone zamówienie, przygotować je i poinformować klienta o gotowości |
| **Warunki wstępne**          | Zamówienie ma status „Opłacone". Pracownik jest zalogowany                     |
| **Warunki końcowe (sukces)** | Zamówienie ma status „Gotowe do odbioru", a klient widzi tę informację         |
| **Priorytet**                | Must have                                                                      |

**Scenariusz główny**
1. System informuje pracownika o nowym opłaconym zamówieniu.
2. Pracownik przyjmuje zamówienie do realizacji.
3. System ustawia status „W przygotowaniu".
4. Pracownik przygotowuje posiłek.
5. Pracownik oznacza zamówienie jako „Gotowe".
6. System aktualizuje status na „Gotowe do odbioru" i udostępnia klientowi informację o gotowości.

**Następny krok procesu:** klient zgłasza się po odbiór, a pracownik weryfikuje numer i wydaje zamówienie.
