# Projekt - Konwersja artykułów na HTML z użyciem OpenAI

Ten projekt umożliwia przetwarzanie artykułów tekstowych do formatu HTML przy użyciu API OpenAI. Artykuły są analizowane, a następnie konwertowane na odpowiednią strukturę HTML z uwzględnieniem obrazków i szczegółowych opisów.

## Opis

Projekt używa modelu GPT-4o do przetworzenia artykułów tekstowych na kod HTML. Główne funkcje obejmują:
- Strukturalizowanie treści artykułu przy użyciu odpowiednich tagów HTML.
- Poprawę polskich znaków diakrytycznych w artykule.
- Dodanie maksymalnie trzech obrazków z tagiem `<img>` oraz atrybutem `alt`.
- Generowanie podpisów do obrazków w tagu `<figcaption>`.

## Instrukcja

Na samym początku musimy określić scieżkę, w której znajduje się nasz klucz API
```
with open("sciezka_do_klucza_API", "r") as f:
    openai.api_key = f.read().strip()
```
Następnie podajemy ścieżkę do pliku txt, w którym znajduje się treść artykułu
```
with open("artykul.txt", "r", encoding="utf-8") as f:
    article_content = f.read()
```
Na sam koniec dodajemy prompty, jakie chcemy przekazać np.
```
prompt = (
    "Przetwórz tekst artykułu na kod HTML zgodnie z poniższymi wymaganiami:"
    "Użyj odpowiednich tagów HTML do strukturyzacji treści."
    "Popraw polskie znaki w treści artykułu"
    "Dodaj znaczniki <img> w miejscach, gdzie warto wstawić grafiki, wstaw maskymalnie 3 grafiki, z atrybutem
src='image_placeholder.jpg'. "
    "Każdy obrazek powinien mieć atrybut alt"
    "Pod obrazkami umieść podpisy w tagu figcaption."
    "Zwrócony kod HTML powinien zawierać tylko zawartość między <body> i </body>, bez CSS ani JavaScript."
    "Treść artykułu:" + article_content
)
```
i dodajemy prompt do listy messages
```
messages=[
        {"role": "user", "content": prompt}
    ],
```

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
