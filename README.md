# Prawo polskie

Wtyczka podłącza asystenta AI do serwera MCP z tekstami polskich ustaw i historią zmian przepisów (https://polskie-prawo.app). Usługa jest bezpłatna i nie wymaga konta.

## Co potrafi

- `search_law`: wyszukiwanie obowiązujących przepisów po znaczeniu, słowach kluczowych lub adresie („art. 415 KC”).
- `get_provision`: pełny tekst przepisu, opcjonalnie na wskazany dzień.
- `get_provision_history`: zmiany przepisu w czasie, z różnicami.
- `list_acts`: lista zaindeksowanych aktów i stan ich tekstów.

Wszystkie narzędzia są tylko do odczytu. Wtyczka zawiera też skill `prawo-pl`, który podpowiada asystentowi, jak cytować przepisy (artykuł, akt, stan tekstu, zastrzeżenia).

## Instalacja

Claude Code:

```bash
claude plugin marketplace add mattttttttttyyyy/prawo-pl-plugin
claude plugin install prawo-pl@prawo
```

Albo samo połączenie z serwerem, bez wtyczki:

```bash
claude mcp add --transport http prawo-pl https://polskie-prawo.app/mcp
```

ChatGPT i Claude w przeglądarce: dodaj własny konektor z adresem `https://polskie-prawo.app/mcp`. Instrukcja: https://polskie-prawo.app/docs.

## Dane, prywatność i ograniczenia

- Teksty pochodzą z oficjalnego API Sejmu RP (ELI). Każda odpowiedź podaje stan tekstu i znane późniejsze zmiany.
- To informacja, nie porada prawna. Brak wyniku nie oznacza, że przepis nie istnieje.
- Serwer nie wymaga logowania, nie zapisuje treści zapytań ani adresów IP w swojej bazie. Przy wyszukiwaniu znaczeniowym tekst frazy trafia do Cloudflare Workers AI. Szczegóły: https://polskie-prawo.app/privacy.
- Wtyczka nie uruchamia żadnego kodu na Twoim komputerze: łączy się wyłącznie z `https://polskie-prawo.app/mcp`.
- Regulamin: https://polskie-prawo.app/terms. Pomoc: https://polskie-prawo.app/support.

## Licencja

Zobacz plik LICENSE.
