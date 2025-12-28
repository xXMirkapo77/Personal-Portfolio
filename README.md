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

## Server Flask (opzionale, locale/rete)
Prerequisiti: Python 3 e pip.

1) Installa le dipendenze
```powershell
cd "c:\Users\Administrator\Desktop\Personal-Portfolio"
py -3 -m pip install --upgrade pip
py -3 -m pip install -r requirements.txt
```

2) Avvia il server (porta predefinita 80, richiede PowerShell/cmd amministratore per bind sulla 80)
```powershell
start-server.bat
```
	- Porta alternativa (es. 8080): `start-server.bat 8080`

3) Ferma il server
```powershell
stop-server.bat
```

4) Riavvia il server
```powershell
restart-server.bat
```

Note server (sintesi): PID in `server.pid`; serve i file statici con cache semplice; la porta 80 richiede terminale Admin (altrimenti usa >1024); Flask built-in è solo sviluppo: per esposizione pubblica usa un reverse proxy o un tunnel.

## Come aggiornare i contenuti
- Modifica `index.html` con i tuoi dati.
- Mantieni la semantica (heading, liste, paragrafi brevi).

## Pubblicazione DDNS/port forwarding (opzionale)
- Se usi DDNS, configura dominio e token nel tuo script di update.
- Imposta port forwarding sul router verso la porta del server (80 o altra) e apri il firewall locale.
- Per HTTPS usa un reverse proxy o un tunnel.

### Nota log
Se vedi 400 con caratteri binari su porta HTTP significa che richieste HTTPS stanno arrivando su HTTP; è rumore già respinto.

## Accessibilità e performance (check veloce)
- Focus visibile, skip-link, contrasto alto già presenti nel CSS; `prefers-reduced-motion` azzera transizioni per chi lo richiede.
- `color-scheme: dark` indica al browser il tema scuro per controlli nativi.
- Evita testi lunghi in maiuscolo; mantieni la gerarchia di heading (h1/h2/h3) già impostata.
- Mantieni un solo colore di accento; verifica sempre il contrasto se cambi palette.
- Immagini: usa formati moderni (WebP/AVIF) e dimensioni ottimizzate; aggiungi `loading="lazy"` se inserisci img.
- Preferisci porte non privilegiate (es. 8080) se non lanci il server come Admin.

## Test manuali base (da eseguire ad ogni release)
- **Layout responsive**: mobile (≤375px), tablet (~768px), desktop (≥1280px); controlla navigazione e griglie.
- **Tab order**: prova `Tab`/`Shift+Tab` dalla skip-link al footer; verifica focus visibile su link e pulsanti.
- **Menu mobile**: a ≤720px apri/chiudi il toggle e controlla che `aria-expanded` cambi.
- **Console**: nessun errore in DevTools all'apertura della Home.
- **Lighthouse (opzionale)**: esegui un audit Performance/SEO/A11y; target >90. Se cali, riduci peso immagini e verifica contrasto.

### Automazione DDNS (opzionale)
Sono inclusi script di esempio (`duckdns-update.ps1`, `update-duckdns.bat`); personalizza dominio/token e, se serve, pianifica un task.

## Certificazioni (PDF)
- Metti eventuali PDF in `assets/certifications/` e collega i file nelle card in `index.html`.
- Se usi badge pubblici, linkali direttamente nelle card.

## Manutenzione
- Mantenere un solo colore di accento per coerenza.
- Verificare contrasto dopo ogni modifica cromatica.
- Aggiornare la timeline (`data-order="desc"`) e gli elenchi mantenendo ordinamento coerente.
