# Flingan – chattwidget för Falun 2027

AI-guiden Flingan på falun2027.com. Byggd av Smartsvar, svaren kommer från Voiceflow.

## Lägga in på sajten

```html
<script src="https://chatlabsextension.github.io/falun2027-chat/falun2027-widget.js" data-project="VOICEFLOW_PROJEKT_ID" defer></script>
```

- `data-project`: Flingans projekt-id i Voiceflow.
- `data-version="development"`: kör testversionen. Utan attributet körs den publicerade versionen.

## Filer

- `falun2027-widget.js`: hela widgeten (utseende, loggor, koppling till Voiceflow).
- `index.html`: testsida. Byt `BYT_TILL_PROJEKT_ID` mot projekt-id:t.

## Knapparna byts efter datum

Schemat står överst i `falun2027-widget.js` under `KNAPPSCHEMA`. En period gäller från sitt datum, men bara om `klar` är `true`.
Sätt `klar: true` först när Flingan svarar bra på frågan bakom varje knapp. Annars ligger föregående periods knappar kvar.
Popupen på sajten visar alltid bara den första knappen.

Förhandsvisa ett datum genom att lägga till `?flingan-datum=2027-02-25` i adressen.

## Bra att veta

- Varje besökare får ett eget slumpat id som gäller tills fliken stängs. "Börja om" ger ett nytt id.
- Ett påbörjat samtal följer med mellan sidorna på sajten.
- Öppningstexten är fast text i widgeten. Voiceflows egen hälsning visas aldrig.
- `FalunChat.open()`, `FalunChat.close()` och `FalunChat.reset()` går att anropa från sidan.
