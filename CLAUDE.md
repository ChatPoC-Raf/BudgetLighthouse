# Claude Code - Ustawienia Projektu

## Przegląd Projektu

To jest aplikacja budżetowa (Budget Lighthouse / Cine Cost Copilot) zbudowana z wykorzystaniem:
- **React 18.3** + **TypeScript**
- **Vite** jako build tool
- **shadcn/ui** + **Radix UI** dla komponentów UI
- **Tailwind CSS** do stylizacji
- **React Router** do routingu
- **Supabase** jako backend
- **Tanstack Query** do zarządzania stanem serwera
- **Capacitor** dla aplikacji mobilnych

## Struktura Projektu

```
cine-cost-copilot/
├── src/
│   ├── components/     # Komponenty React
│   │   ├── auth/      # Komponenty autoryzacji
│   │   ├── budget/    # Komponenty budżetu
│   │   ├── common/    # Wspólne komponenty
│   │   └── dashboard/ # Komponenty dashboardu
│   ├── App.tsx        # Główny komponent
│   └── App.css        # Style główne
├── public/            # Pliki statyczne
└── package.json       # Zależności projektu
```

## Konwencje Kodowania

### TypeScript
- Używaj strict mode
- Zawsze typuj zmienne, funkcje i komponenty
- Unikaj `any` - preferuj `unknown` lub odpowiednie typy
- Używaj interfejsów dla obiektów props

### React
- Używaj funkcyjnych komponentów z hokami
- Preferuj named exports dla komponentów
- Organizuj komponenty w katalogu `components/`
- Stosuj React.memo() dla komponentów z częstym rerenderowaniem

### Stylizacja
- Używaj Tailwind CSS jako głównego sposobu stylizacji
- Dla komponentów shadcn/ui trzymaj się ich konwencji
- Stosuj CSS modules lub styled-components tylko gdy Tailwind nie wystarczy

### Nazewnictwo
- Komponenty: PascalCase (np. `BudgetToolbar.tsx`)
- Pliki TypeScript: camelCase dla utils, PascalCase dla komponentów
- Zmienne i funkcje: camelCase
- Stałe: UPPER_SNAKE_CASE

## Wskazówki dla Claude

### Podczas dodawania nowych funkcjonalności:
1. Sprawdź istniejące komponenty w `src/components/` przed utworzeniem nowych
2. Używaj istniejących komponentów shadcn/ui z projektu
3. Zachowaj spójność z istniejącą strukturą katalogów
4. Dodawaj odpowiednie typy TypeScript
5. Rozważ responsywność (mobile-first approach)

### Podczas refaktoryzacji:
1. Zachowaj zgodność z istniejącymi API
2. Utrzymuj backward compatibility
3. Testuj zmiany w różnych przeglądarkach
4. Dokumentuj znaczące zmiany

### Podczas debugowania:
1. Sprawdź console.error() w przeglądarce
2. Zweryfikuj network requests (Supabase)
3. Sprawdź React DevTools
4. Upewnij się, że środowisko (.env) jest prawidłowo skonfigurowane

### Bezpieczeństwo:
- NIE commituj plików .env
- Waliduj wszystkie dane użytkownika
- Używaj Supabase Row Level Security
- Sanityzuj dane wejściowe przed renderowaniem

## Komendy

```bash
# Rozwój
npm run dev              # Uruchom serwer deweloperski

# Build
npm run build           # Build produkcyjny
npm run build:dev       # Build developerski

# Inne
npm run lint           # Sprawdź błędy ESLint
npm run preview        # Podgląd buildu produkcyjnego
```

## Zmienne Środowiskowe

Projekt wykorzystuje Supabase - upewnij się, że plik `.env` zawiera:
```
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

## Dodatkowe Uwagi

- Projekt używa Capacitor dla aplikacji mobilnych (Android/iOS)
- Sentry jest skonfigurowany do monitoringu błędów
- OCR jest dostępny przez Tesseract.js i HuggingFace Transformers
- Projekt obsługuje wielojęzyczność (i18n)
- Obsługa offline (service worker)
