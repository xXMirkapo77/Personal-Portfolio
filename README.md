# Portfolio statico (uso privato)

README minimale: istruzioni tecniche essenziali, nessun dettaglio di contenuto del portfolio.

## Struttura cartelle (sintesi)
- `index.html` – pagina statica.
- `css/main.css` – stile.
- `js/main.js` – interazioni base (toggle menu).
- `assets/` – asset statici (immagini, certificazioni in PDF).

## Come eseguire (statico)
Apri `index.html` in un browser moderno. Su Windows PowerShell:
```powershell
Start-Process index.html
```

## Come aggiornare i contenuti
- Modifica `index.html` con i tuoi dati.
- Mantieni la semantica (heading, liste, paragrafi brevi).

## Pubblicazione
Puoi distribuire i file statici su qualsiasi hosting statico (GitHub Pages, Netlify, Vercel, S3+CloudFront, o server web semplice). Non sono richiesti servizi backend.

## Accessibilità e performance (check veloce)
- Focus visibile, skip-link, contrasto alto già presenti nel CSS; `prefers-reduced-motion` azzera transizioni per chi lo richiede.
- `color-scheme: dark` indica al browser il tema scuro per controlli nativi.
- Evita testi lunghi in maiuscolo; mantieni la gerarchia di heading (h1/h2/h3) già impostata.
- Mantieni un solo colore di accento; verifica sempre il contrasto se cambi palette.
- Immagini: usa formati moderni (WebP/AVIF) e dimensioni ottimizzate; aggiungi `loading="lazy"` se inserisci img.

## Test manuali base (da eseguire ad ogni release)
- **Layout responsive**: mobile (≤375px), tablet (~768px), desktop (≥1280px); controlla navigazione e griglie.
- **Tab order**: prova `Tab`/`Shift+Tab` dalla skip-link al footer; verifica focus visibile su link e pulsanti.
- **Menu mobile**: a ≤720px apri/chiudi il toggle e controlla che `aria-expanded` cambi.
- **Console**: nessun errore in DevTools all'apertura della Home.
- **Lighthouse (opzionale)**: esegui un audit Performance/SEO/A11y; target >90. Se cali, riduci peso immagini e verifica contrasto.

## Certificazioni (PDF)
- Metti eventuali PDF in `assets/certifications/` e collega i file nelle card in `index.html`.
- Se usi badge pubblici, linkali direttamente nelle card.

## Manutenzione
- Mantenere un solo colore di accento per coerenza.
- Verificare contrasto dopo ogni modifica cromatica.
- Aggiornare la timeline (`data-order="desc"`) e gli elenchi mantenendo ordinamento coerente.
