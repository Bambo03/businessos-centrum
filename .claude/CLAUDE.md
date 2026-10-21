# Zasady pracy nad stroną businessos-centrum

- Język: polski. Właściciel: Kamil.
- Wspólne zasady projektu: `CLAUDE.md` w repozytorium Bambo03/BusinessOS.

## Scalanie i wdrażanie (decyzja Kamila, 21.10.2026)

- PR do `main` scala się sam: workflow `.github/workflows/auto-scalanie.yml` scala go, gdy wszystkie testy (CI) są zielone i nie ma konfliktu. Wątki i agenci mogą też scalać same, gdy CI jest zielone, a zmiana sprawdzona — bez czekania na „scal” od Kamila.
- Zatrzymanie: szkic (draft) albo etykieta `wstrzymane` (praca trwa, scali wątek) lub `decyzja-kamila` (PR czeka na decyzję Kamila — oznacz go tak od razu przy zakładaniu). Konflikt rozwiązuje wątek, który prowadzi PR.
- Po scaleniu wątek sam wdraża (strona, migracje, funkcje serwera, paczka na laptopa według WGRANIE.md — jedna naraz, z kopią i możliwością cofnięcia). Nie zostawiaj Kamilowi kroków „scal” ani „wdrażaj”.
- Kamila pytaj tylko o decyzje: wybór między wersjami funkcji, koszty i płatne usługi, prywatność, pieniądze, konta i klucze, zmiany nieodwracalne (np. usunięcie danych).
- Scalenie tokenem GitHub Actions nie uruchamia workflowów `push` na `main`, więc auto-scalanie uruchamia je samo (`PO_SCALENIU` w pliku workflow). Nowy workflow `push` na `main` → dodaj mu `workflow_dispatch` i dopisz go do `PO_SCALENIU`; nowy workflow testów PR → dopisz go do `CI_WORKFLOWS` i `on.workflow_run.workflows`.
- To repozytorium nie ma testów, więc PR scala się od razu (strona polityki prywatności dla zgody Google OAuth — nie usuwaj jej i nie zmieniaj bez potrzeby).

