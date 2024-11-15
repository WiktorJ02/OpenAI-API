# Projekt - Konwersja artykułów na HTML z użyciem OpenAI

Ten projekt umożliwia przetwarzanie artykułów tekstowych do formatu HTML przy użyciu API OpenAI. Artykuły są analizowane, a następnie konwertowane na odpowiednią strukturę HTML z uwzględnieniem obrazków i szczegółowych opisów.

## Opis

Projekt używa modelu GPT-4o do przetworzenia artykułów tekstowych na kod HTML. Główne funkcje obejmują:
- Strukturalizowanie treści artykułu przy użyciu odpowiednich tagów HTML.
- Poprawę polskich znaków diakrytycznych w artykule.
- Dodanie maksymalnie trzech obrazków z tagiem `<img>` oraz atrybutem `alt`.
- Generowanie podpisów do obrazków w tagu `<figcaption>`.

## Wymagania

Aby uruchomić ten projekt, musisz mieć:
- Zainstalowaną bibliotekę `openai`.
- Posiadać klucz API OpenAI.
- Plik artykułu w formacie `.txt`.

Aby zainstalować wymagane biblioteki, uruchom:
```bash
pip install openai
```
## Autor
Wiktor Jurczak
