# STL Studio

En webbaserad 3D-visare för STL-filer, byggd med Three.js.

## Funktioner

- Öppna lokala STL-filer via filväljare eller dra-och-släpp.
- Ladda en STL-fil från en direkt HTTP(S)-länk (servern måste tillåta CORS).
- Rotera, zooma och panorera med mus eller pekskärm.
- Vy framifrån, ovanifrån och isometrisk vy.
- Visa modellmått, rutnät, XYZ-axlar och trådmodell.
- Fungerar som statisk webbplats; ingen egen server behövs.

## Köra lokalt

Eftersom appen använder JavaScript-moduler och import maps behöver du öppna den via en lokal HTTP-server, inte direkt som `file://`.

Exempel med Python installerat:

```bash
python -m http.server 8000
```

Öppna sedan http://localhost:8000.

## Publicera med GitHub Pages

1. Öppna repositoryts **Settings → Pages**.
2. Under **Build and deployment**, välj **Deploy from a branch**.
3. Välj grenen `main` och mappen `/ (root)`, spara.
4. Vänta på att publiceringen blir klar. GitHub visar webbplatsens URL på samma inställningssida.

## Format och begränsningar

- STL (binär och ASCII) stöds.
- STL-formatet innehåller inte en pålitlig uppgift om enhet eller färg. Appen tolkar måtten som millimeter, vilket är vanligt men inte garanterat.
- URL-import kräver en direktlänk till filen och att värdservern tillåter cross-origin-förfrågningar (CORS).
- Three.js laddas från jsDelivr, så internetanslutning krävs.
- 3MF, OBJ och GLB ingår inte i den första versionen.

## Teknik

- Three.js
- `STLLoader`
- `OrbitControls`
