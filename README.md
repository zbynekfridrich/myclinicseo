# MY CLINIC SEO — advertoriální hub

**Privátní interní obsah. Indexace zakázána, crawlery zablokované.**

Statický dashboard pro SEO & content deliverables k advertoriální kampani MY CLINIC (myclinic.cz). Hostováno na `myclinic.seodata.tools`.

## Struktura

```
.
├── index.html                   # dashboard / hub
├── brief-01-kw-analyza.html     # Brief 01 — SEO analýza KW pro advertoriály
├── brief-02-*.html              # Brief 02 — Content brief: Advertoriál 01 (Týmová péče) · PENDING
├── brief-03-*.html              # Brief 03 — Content brief: Advertoriál 02 (Novorozenci) · PENDING
├── brief-04-*.html              # Brief 04 — Content brief: Advertoriál 03 (Školka/imunita) · BLOKOVÁNO
├── robots.txt                   # block všech crawlerů
├── vercel.json                  # security headers + clean URLs (identické s Livendo)
└── README.md
```

## Stav projektu

| Brief | Téma | Stav |
|-------|------|------|
| Brief 01 | KW analýza advertoriálů | ✅ Hotovo |
| Brief 02 | Content brief — Týmová péče | 🔄 V přípravě |
| Brief 03 | Content brief — Novorozenci | 🔄 V přípravě |
| Brief 04 | Content brief — Školka / imunita | ⛔ Blokováno (chybí KW data) |

## Keyword pool (Brief 01)

- **55 klíčových slov** · **~11 700 GSV celkem**
- Advertoriálně adresovatelné: **4 409 GSV** (Cluster A + D)
- Velká SEO příležitost mimo advertoriály: **6 559 GSV** (očkovací cluster)
- Brief 04 blokován: pro téma školka/imunita chybí KW dataset — nutná rozšířená analýza v SEMRUSHu

## Bezpečnostní vrstvy

Stejná konfigurace jako Livendo SEO hub:

### Vrstva 1 — Anti-indexace
- `<meta name="robots">` v každém HTML — `noindex, nofollow, noarchive, nosnippet, noimageindex, notranslate`
- `robots.txt` s explicitním blokem na všechny crawlery včetně AI botů (GPTBot, ClaudeBot, PerplexityBot, atd.)
- HTTP hlavička `X-Robots-Tag` přes vercel.json

### Vrstva 2 — Security headers (vercel.json)
- `Strict-Transport-Security` — vynucený HTTPS 2 roky
- `Content-Security-Policy` — jen self + Google Fonts
- `X-Frame-Options: DENY` — žádné iframe embedding
- `Referrer-Policy: no-referrer`
- `Permissions-Policy` — vypnuté kamery, mikrofony, geolokace

## Deploy

```bash
cd ~/Desktop/myclinic
git add .
git commit -m "Update content"
git push
```

Vercel detekuje push a redeployne během ~30 vteřin. Subdoména `myclinic.seodata.tools` musí být nastavena v Vercel dashboard jako custom domain.

## Bezpečnostní omezení

- Stránka je veřejně dostupná z internetu, jen není indexovaná. Kdokoli, kdo zná URL, se dovnitř dostane.
- Pokud je potřeba ochrana heslem: **Vercel Pro Password Protection** ($20/mo) nebo **Cloudflare Access** (zdarma pro 50 uživatelů).
- Distribuce URL: posílej secure channelem (1Password share, Signal), ne emailem.

## Kontakt

Zbyněk Fridrich · zbynek.fridrich@sherpas.cz · 775 150 657
