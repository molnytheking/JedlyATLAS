# Jedlý atlas dejín – PWA balík

Obsah: `index.html`, `app.js` (React je zabalený, žiadne CDN), `manifest.webmanifest`, `sw.js` (offline), `icons/`.
Všetky cesty sú relatívne, takže balík funguje aj v podadresári (napr. GitHub Pages).

## 1. Nasadenie (stačí jedno)
Aplikácia musí bežať cez **HTTPS** (inak iPhone nepovolí offline režim).

- **Netlify:** na app.netlify.com → Add new site → Deploy manually → pretiahnite sem *obsah* priečinka (nie zip).
- **Cloudflare Pages:** Workers & Pages → Create → Pages → Upload assets → nahrajte súbory.
- **GitHub Pages:** nový repozitár, nahrajte súbory do koreňa, Settings → Pages → Deploy from branch (main, / root). Adresa: `https://meno.github.io/repozitar/`.

## 2. iPhone – Pridať na plochu
1. Otvorte adresu v **Safari**.
2. Ťuknite na tlačidlo Zdieľať (štvorec so šípkou).
3. Zvoľte **Pridať na plochu** → **Pridať**.
4. Pri prvom otvorení buďte online, aby sa aplikácia uložila; potom funguje aj bez internetu.

## 3. Aktualizácia
Po nahraní nových súborov zmeňte v `sw.js` riadok `const V='atlas-v1'` na `atlas-v2` (atď.). Nová verzia sa zobrazí po druhom otvorení aplikácie.

## Poznámky
- Nákupný zoznam a nastavenia sa ukladajú iba v zariadení (localStorage); iOS ich môže zmazať po dlhšej nečinnosti, preto si zoznam v prípade potreby exportujte.
- Písma Inter/Newsreader sa sťahujú z Google Fonts a po prvom načítaní sa uložia do cache; bez nich sa použije systémové písmo.
- Odkazy na obchody sú len demo/vyhľadávanie.
