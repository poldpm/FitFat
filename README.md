# FitFat

Comptador de calories i proteïnes amb balanç diari. App autònoma (PWA) sense dependències externes.

## Fitxers
- `index.html` — l'app sencera (HTML + CSS + JS en un sol fitxer)
- `manifest.webmanifest` — metadades de la PWA
- `sw.js` — service worker (funcionament offline)
- `icon-192.png`, `icon-512.png`, `icon-512-maskable.png`, `icon-180.png` — icones

## Desplegament a GitHub Pages
1. Puja tots els fitxers a l'arrel del repositori (o a `/docs`).
2. Settings → Pages → Branch: `main` → carpeta `/root` (o `/docs`).
3. Obre la URL que et dona GitHub. Tots els camins són relatius (`./`), així que funciona igual en un subdirectori tipus `usuari.github.io/fitfat/`.

## Instal·lar a la pantalla d'inici
- **iPhone (Safari):** compartir → "Afegeix a la pantalla d'inici".
- **Android (Chrome):** menú ⋮ → "Instal·la l'aplicació" / "Afegeix a la pantalla d'inici".

Un cop instal·lada s'obre a pantalla completa amb icona pròpia i funciona sense connexió.

## Vistes
- **Dia:** registre de menjars (Dinar, Berenar, Sopar) i tancament del dia amb el balanç.
- **Setmana:** mitjanes diàries, balanç dia a dia (toca un dia per obrir-lo) i balanç acumulat.
- **Mes:** mitjanes, gràfic de balanç de tot el mes i acumulat.

Navega entre dies/setmanes/mesos amb les fletxes ‹ ›.

## Dades i còpia de seguretat
Tot es desa a `localStorage` del domini (per dia, amb històric i objectius). L'app demana al navegador emmagatzematge persistent per reduir la neteja automàtica, però les dades viuen al dispositiu: no se sincronitzen entre dispositius i es poden perdre si buides les dades del lloc, desinstal·les la PWA o (a iOS) no l'obres durant molts dies.

Per protegir-te, a **⚙ → Còpia de seguretat** pots **exportar** totes les dades a un fitxer JSON i **importar-lo** després (en aquest o un altre dispositiu). Fes còpia de tant en tant.

Si vols sincronització automàtica entre mòbils, caldria connectar-hi un backend (per exemple Google Sheets via Apps Script, com ja has fet en altres projectes).

## Notes de càlcul
- **Balanç = cremades − ingerides.** Positiu → dèficit; negatiu → superàvit.
- Les "cremades" són les que et dona el rellotge. Si el teu rellotge dona el **total del dia** (basal + activitat), el dèficit surt directe. Si només dona l'**activitat**, hi has de sumar el metabolisme basal a mà.
