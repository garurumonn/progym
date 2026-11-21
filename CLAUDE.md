# Pro Gym – sajt teretane (Bijelo Polje)

Statički sajt bez build koraka. Cloudflare Pages ga objavljuje direktno iz `main` grane
(framework: none, build command: prazno, output directory: `/`).

## Struktura
- `index.html` – cijeli sajt: HTML, CSS (u `<style>`) i JS (u `<script>` na dnu).
  Sekcije: početna (`#pocetna`), zašto Pro Gym (`#zasto`), članarine (`#clanarine`),
  galerija (`#galerija`), novosti (`#novosti`), kontakt sa formom i Google mapom (`#kontakt`).
- `img/` – fotografije (`neon-sala.jpg` je i velika slika na vrhu).
- Fontovi: Anton (naslovi), Oswald (rezerva za ćirilicu), Inter, JetBrains Mono.

## Jezici (ME / EN / RU / TR)
- Prevodivi elementi imaju `data-i18n="kljuc"` (placeholderi: `data-i18n-ph`).
- Crnogorski tekst stoji direktno u HTML-u; prevodi su u objektima `EN`, `RU`, `TR` u skripti.
- Kad mijenjaš tekst, promijeni ga **u HTML-u i u `EN`, `RU` i `TR`**.
- Izbor jezika je padajući meni (`.lang-toggle` + `#langMenu`) sa SVG zastavama; izabrani jezik se pamti u `localStorage`.

## Podaci teretane
- Adresa: Slobodana Penezića, preko puta gasulhane, 84000 Bijelo Polje (poslovni objekat porodice Burdžović)
- Telefon / WhatsApp: 069 837 777 (`38269837777`, konstanta `WHATSAPP` u skripti; forma otvara WhatsApp)
- Instagram: @progymbp
- Radno vrijeme: svaki dan 09:00–22:00
  (oznaka `#openPill` pored logoa: zeleno „do 22:00“ / narandžasto „od 09:00“, funkcija `openNow()`, vrijeme Europe/Podgorica)
- Cijene: dnevna karta 5 €, 3× nedjeljno 15 €/mjesec, svaki dan 25 €/mjesec, bez upisnine
  (cijene su u sekciji „Članarine“ i u pokretnoj traci `ticker` – u HTML-u i u sva 3 prevoda)

## Ponašanje
- Linkovi na sekcije (`#kontakt`…) skroluju bez mijenjanja adrese; sajt se uvijek otvara na vrhu.

## Prije objave
Provjeri sva 4 jezika na širini telefona (375px) i desktopa (1280px) – bez horizontalnog skrola.
Ruski naslovi su duži; za njih postoje posebna pravila `html[lang=ru]` u CSS-u.
