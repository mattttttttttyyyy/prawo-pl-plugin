---
name: prawo-pl
description: Odpowiadaj na pytania o polskie prawo na podstawie tekstów ustaw z serwera prawo-pl, z numerem artykułu, stanem tekstu i zastrzeżeniem, że to informacja, a nie porada prawna. Używaj, gdy użytkownik pyta o przepis, kodeks, ustawę lub zmianę przepisu w Polsce, a także gdy sam chcesz zacytować polski przepis.
---

# Prawo polskie

Korzystaj z narzędzi serwera `prawo-pl`. Nie cytuj przepisów z pamięci bez sprawdzenia: numeracja i brzmienie mogły się zmienić.

## Znasz numer przepisu (także z pamięci)

Wywołaj `get_provision` i sprawdź brzmienie, zanim je zacytujesz.

- Akt podaj tak, jak go znasz: `KP`, `k.p.c.`, `Kodeks pracy`, `ustawa o podatku dochodowym od osób fizycznych`, `ustawa o VAT`. Możesz też wpisać go w `ref`, np. `ref: "art. 41 k.p."`.
- Fragment: `art. 417¹ § 2` (także `417^1`, `417(1)`), `art. 21 ust. 1 pkt 3`.
- Kilka artykułów jednym wywołaniem: `art. 41, 45 i 52 KP`, `art. 41–44 k.p.` (do 5).
- Brzmienie z przeszłości: `as_of` w formacie RRRR-MM-DD. Zmiany w czasie: `get_provision_history`.
- Gdy przepisu nie ma w akcie, odpowiedź podpowiada akty z przepisem o tym numerze. Sprawdź, czy nie pomyliłeś aktu.

## Szukasz przepisu

Wywołaj `search_law` z zapytaniem językiem ustawy, a nie pytaniem użytkownika słowo w słowo.

- Dobrze: `wypowiedzenie umowy o pracę w czasie usprawiedliwionej nieobecności`. Gorzej: `czy szef może mnie zwolnić na L4`.
- Inne ujęcia tego samego problemu podaj w `queries` (do 2), np. `zakaz wypowiedzenia umowy o pracę`, `ochrona pracownika w czasie choroby`. To jedno wywołanie zamiast kilku.
- Gdy wiesz, w którym akcie szukać, zawęź przez `acts`, np. `["KP"]`. Nazwa aktu w samym zapytaniu („w kodeksie pracy”, „VAT”) też zawęża wyniki.
- Chcesz sprawdzić cytat z pamięci: umieść fragment w cudzysłowie, np. `„wyrządził drugiemu szkodę”`; zostanie wyszukany jako dokładna fraza.
- Wyniki to obowiązujące przepisy z fragmentem treści. Przed zacytowaniem pobierz pełny tekst przez `get_provision`.
- Nie wiesz, czy akt jest zaindeksowany: `list_acts`.

## Odpowiedź

Zawsze podaj akt i numer przepisu (z paragrafem i punktem, jeśli dotyczy), stan tekstu (`as_of`) oraz ostrzeżenia z odpowiedzi narzędzia o późniejszych zmianach. Brak wyniku nie dowodzi, że przepis nie istnieje; akt może jeszcze nie być zaindeksowany. Zaznacz, że to informacja, a nie porada prawna, a w sprawach wiążących warto skonsultować się z prawnikiem.
