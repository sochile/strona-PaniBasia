# Jak działa Pani Basia

## Kim jest Pani Basia (na tym etapie projektu)

Pani Basia jest **BOTEM wspomagającym człowieka w projekcie**.  
Jej rolą jest pomoc w myśleniu, porządkowaniu informacji i planowaniu działań.

Na obecnym etapie Pani Basia:
- nie jest agentem autonomicznym
- nie podejmuje decyzji
- nie wykonuje działań samodzielnie

Rozwój w kierunku **agenta** jest możliwy w przyszłości, ale **nie jest założeniem początkowym projektu**.

---

## Jak pracuje Pani Basia

Pani Basia:
- prowadzi rozmowę w formie tekstowej
- analizuje treści dostarczone przez człowieka
- porządkuje notatki, plany i ustalenia
- proponuje rozwiązania i warianty
- zadaje pytania pomocnicze

Każde działanie Pani Basi ma charakter **doradczy**.

---

## Czego Pani Basia NIE robi

Pani Basia:
- nie wdraża zmian
- nie edytuje repozytorium
- nie usuwa ani nie dodaje plików
- nie podejmuje decyzji projektowych
- nie działa bez wyraźnego polecenia człowieka

---

## Relacja człowiek + AI

- Człowiek jest **jedynym decydentem**
- AI jest **narzędziem wspierającym**
- Każda decyzja musi być:
  - omówiona
  - zapisana
  - zatwierdzona przez człowieka

---

## Zasada nadrzędna projektu

> Jeśli nie ma zapisu – nie ma decyzji.

Dokumentacja (README, pod-README, pliki w `docs`) jest **jedynym źródłem prawdy projektu**.
# Jak działa Pani Basia (PB) - Architektura i Logika

## 1. Interfejs i Bezpieczeństwo
* **Kanał**: Wyłącznie komunikator Telegram.
* **Autoryzacja**: Basia reaguje tylko na komendy z konkretnego numeru ID użytkownika. Wykorzystuje Token bota do komunikacji z serwerami Telegram.
* **Brak dodatkowych haseł**: ID użytkownika jest traktowane jako wystarczający klucz dostępu.

## 2. Architektura Hybrydowa (Zapis danych)
System jest zaprojektowany tak, aby działać bez konieczności pracy komputera lokalnego 24/7.

* **Etap 1: Poczekalnia (Chmura)**
  - Gdy komputer główny jest wyłączony, Basia zapisuje wiadomość w tymczasowej bazie w chmurze (np. MongoDB/Supabase).
  - Dane w chmurze są przechowywane w stałym schemacie "szufladek".
* **Etap 2: Synchronizacja i Czyszczenie**
  - Po włączeniu komputera lokalnego, skrypt pobiera dane z poczekalni.
  - Dane są zapisywane w docelowej, bezpiecznej bazie SQLite na dysku twardym.
  - Po potwierdzeniu zapisu, dane w chmurze są natychmiast usuwane.

## 3. Schemat Szufladek (Struktura Bazy)
Każda informacja trafia do odpowiedniej sekcji, co ułatwia późniejsze przeszukiwanie na hasło:
* **FAKTY**: Stałe informacje (np. "Basia, szef lubi czarną kawę").
* **NOTATKI**: Bieżące zapiski i pomysły.
* **ZADANIA**: Rzeczy do zrobienia (To-Do).
* **SYSTEM**: Logi działania i ustawienia bota.

## 4. Język i Technologia
* **Język**: Python (obsługa logiki, Telegram API i synchronizacji).
* **Baza lokalna**: SQLite (plik .db na komputerze szefa).

