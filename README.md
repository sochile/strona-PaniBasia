# Projekt Pani Basia

## Witaj w projekcie Pani Basia
To jest nasze **centrum współpracy i dokumentacji projektu**. Tutaj zapisujemy wszystkie decyzje, plany, zasady i kody Pani Basi.

## Podstrony / Sekcje
- Pani Basia – kim jest
- Jak współpracujemy
- Plan rozwoju
- Co już mamy
- Kody Pani Basi
- Zasady współpracy i kodu / Plan rozwoju Pani Basi

## Plan funkcji i kierunek rozwoju
Pani Basia będzie rozwijana i udoskonalana. Plan może się zmieniać w miarę postępu prac i nowych ustaleń.

### Funkcje i moduły Pani Basi
- Sekretarka – rozmowa i porządkowanie spraw
- Przypomnienia i kalendarz
- Pomoc w wyszukiwaniu (np. dom, samochód)
- Nauka języków

### Kolejność działań / Roadmapa
1. Połączyć stronę lokalną z Netlify z dostępem AI do tej strony
2. Rozpocząć prace w GitHub
3. Rozwijanie modułów zgodnie z listą funkcji

## Zasada działania AI
- AI **nie może sam uzupełniać, zmieniać, usuwać ani wprowadzać żadnych zmian** bez wcześniejszego ustalenia z człowiekiem.
- AI działa wyłącznie jako **doradca** i proponuje rozwiązania.

## Współpraca człowiek + AI

### Zasady współpracy
- Najpierw ustalamy koncepcję i kolejność działań, potem dopiero kod i funkcje.
- Wszystko, co AI podaje, musi być **wiarygodne i sprawdzone**.
- AI **nie zmienia, nie usuwa, nie dodaje** ani nie robi nic, czego wcześniej nie ustalił z człowiekiem.
- Decyzje zapisujemy, aby były **łatwo dostępne i przejrzyste**.

### Role w projekcie
- **AI** – pomaga w tłumaczeniu, porządkowaniu i proponowaniu rozwiązań.
- **Człowiek** – decyduje, co jest dobre i potrzebne oraz zatwierdza zmiany.

### Dodatkowe uwagi
- Wszystkie propozycje AI są traktowane jako sugestie – **nigdy gotowy kod do wdrożenia**.
- Najpierw opisujemy funkcję lub pomysł, potem kod – nigdy odwrotnie.
- AI działa wyłącznie w ramach ustalonych z człowiekiem – **nie może podejmować samodzielnych działań**.

## Co już mamy
- Działająca **strona lokalna**
- Struktura podstron gotowa
- Opis Pani Basi opracowany
- Ustalony sposób współpracy człowiek + AI
- Połączone konto Netlify i GitHub
- Konto na Telegram – Token i ID gotowe
- Supabase jako baza danych z tabelą `messages`

**Uwagi dotyczące Bota / Agenta:**
- Bot/Agent działa tylko w ramach ustaleń z człowiekiem
- Nie wprowadza zmian samodzielnie – wszystko jest propozycją do zatwierdzenia
- W przyszłości będzie rozwijany modułowo w oparciu o ten stan początkowy

## Połączenie GitHub i Netlify
Projekt **Strona Pani Basia** działa już w pełni online dzięki integracji GitHub i Netlify:

- **GitHub** – przechowuje wszystkie pliki projektu, w tym HTML, CSS, kody, README.md oraz pod-README.md.  
- **Netlify** – wyświetla stronę w przeglądarce, automatycznie aktualizując ją przy każdym pushu do GitHub.  
- Dzięki temu każda zmiana w repo (np. nowy moduł, aktualizacja dokumentacji) jest **natychmiast widoczna online** na stronie: [https://strona-pani-basia.netlify.app/](https://strona-pani-basia.netlify.app/).

### Korzyści
- AI zawsze ma dostęp do aktualnej dokumentacji z GitHub.  
- Człowiek może szybko przeglądać stronę w Netlify i weryfikować zmiany.  
- Strona jest modularna, łatwa w aktualizacji i rozwijaniu kolejnych funkcji.

### 🗄️ Konfiguracja Supabase (Baza danych)

Baza danych projektu to **Basia1**. 

 Struktura tabeli `messages`:
| Kolumna | Typ | Opis |
| :--- | :--- | :--- |
| `id` | uuid | Klucz główny (generowany automatycznie) |
| `source` | text | Źródło wiadomości (np. Telegram) |
| `user_id` | text | ID użytkownika z Telegrama |
| `content` | text | Treść wiadomości |
| `created_at` | timestamptz | Data i godzina zapisu |
