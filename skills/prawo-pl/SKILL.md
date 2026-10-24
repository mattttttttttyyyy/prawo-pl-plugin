---
name: prawo-pl
description: Odpowiadaj na pytania o polskie prawo na podstawie tekstów ustaw z serwera prawo-pl, z numerem artykułu, stanem tekstu i zastrzeżeniem, że to informacja, a nie porada prawna. Używaj, gdy użytkownik pyta o przepis, kodeks, ustawę lub zmianę przepisu w Polsce.
---

# Prawo polskie

Korzystaj z narzędzi serwera `prawo-pl`. Nie cytuj przepisów z pamięci, jeśli narzędzie może je zwrócić.

1. Jeśli nie wiesz, co jest zaindeksowane, wywołaj `list_acts`.
2. Do szukania użyj `search_law` (pytanie zwykłymi słowami, słowa kluczowe albo adres, np. „art. 415 KC”).
3. Pełny tekst przepisu pobierz przez `get_provision` (np. `act=KP`, `ref=art. 154`). Dla brzmienia z przeszłości dodaj `as_of` (RRRR-MM-DD).
4. Zmiany przepisu w czasie sprawdź przez `get_provision_history`.

W odpowiedzi zawsze podaj: akt i numer artykułu (z paragrafem i punktem, jeśli dotyczy), stan tekstu (`as_of`) oraz ostrzeżenia z odpowiedzi narzędzia o późniejszych zmianach. Brak wyniku nie dowodzi, że przepis nie istnieje; akt może jeszcze nie być zaindeksowany. Zaznacz, że to informacja, a nie porada prawna, a w sprawach wiążących warto skonsultować się z prawnikiem.
