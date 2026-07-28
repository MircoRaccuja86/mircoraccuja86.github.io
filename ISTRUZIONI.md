# Come pubblicare le vCard dinamiche — guida passo passo

## 1. Crea un account GitHub (se non ce l'hai)
Vai su https://github.com/join, registrati gratis con la tua email.

## 2. Crea un nuovo "repository"
- Clicca sul "+" in alto a destra → "New repository"
- Nome: ad esempio `studio-vcard`
- Deve essere **Public** (necessario per GitHub Pages gratuito)
- Clicca "Create repository"

## 3. Carica i file
Nella pagina del repository:
- Clicca "Add file" → "Upload files"
- Trascina dentro l'intera cartella `vcard` (con `index.html` e `contacts.json`)
- Scrivi un messaggio tipo "primo caricamento" e clicca "Commit changes"

Alla fine dovrai avere questa struttura nel repository:
```
studio-vcard/
  vcard/
    index.html
    contacts.json
```

## 4. Attiva GitHub Pages
- Nel repository vai su "Settings" → "Pages" (menu a sinistra)
- In "Branch" seleziona `main` e come cartella `/ (root)`, poi "Save"
- Aspetta 1-2 minuti: GitHub ti mostrerà l'indirizzo del tuo sito, tipo:
  `https://tuonome.github.io/studio-vcard/`

## 5. Trova l'indirizzo della pagina vCard
Sarà:
```
https://tuonome.github.io/studio-vcard/vcard/
```
Provalo nel browser aggiungendo `?id=mrossi`:
```
https://tuonome.github.io/studio-vcard/vcard/?id=mrossi
```
Deve mostrarti la scheda di Mario Rossi con il pulsante "Salva contatto".

## 6. Genera i QR code
- Apri il file `admin/genera-qr.html` **direttamente dal tuo computer** (doppio clic, si apre nel browser — questo file NON va caricato su GitHub, è solo uno strumento locale)
- Incolla l'indirizzo base: `https://tuonome.github.io/studio-vcard/vcard/`
- Carica il file `contacts.json`
- Clicca "Genera QR code" e scarica i PNG, uno per collaboratore

## 7. Aggiungere o modificare un collaboratore
- Vai nel repository su GitHub, apri `vcard/contacts.json`
- Clicca sulla matita (Edit)
- Aggiungi una nuova voce copiando lo schema esistente, cambiando `id`, nome, telefono ecc.
- Salva ("Commit changes")
- Il QR di quella persona **non cambia mai**: basta rigenerarlo una sola volta la prima volta che la aggiungi

## Cose importanti da sapere
- L'`id` di ogni persona deve essere unico (es. `mrossi`, `gbianchi`) e comparirà nell'indirizzo, quindi meglio senza spazi o accenti
- Se modifichi solo dati esistenti (es. cambio numero di telefono), il QR resta identico: è questo che lo rende "dinamico"
- Tutto il sistema è gratuito, nessun servizio esterno coinvolto oltre a GitHub
