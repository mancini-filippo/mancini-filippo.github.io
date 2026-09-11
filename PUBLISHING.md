# Pubblicare gratuitamente su GitHub Pages

Il sito è una personalizzazione del template originale al-folio. I file sono tuoi e puoi modificarli o spostarli su un altro servizio. Il link privato di revisione fornito in chat è separato dal futuro sito pubblico su GitHub Pages.

## Prima pubblicazione

1. Crea un account gratuito su [GitHub](https://github.com/signup), se non lo hai già. Il nome utente determinerà l’indirizzo del sito.
2. Crea un repository **pubblico** chiamato esattamente `NOMEUTENTE.github.io`, sostituendo NOMEUTENTE con il tuo nome utente GitHub. Puoi partire dal pulsante “Use this template” di [al-folio](https://github.com/alshedivat/al-folio); in questo caso sostituisci poi il contenuto con i file personalizzati consegnati, evitando di conservare le pagine di esempio.
3. Trasferisci nella radice del repository i contenuti della cartella del sito, incluse `.github`, `_pages`, `_data`, `assets`, `_config.yml`, `Gemfile` e `Gemfile.lock`. Non caricare `node_modules`, `dist`, `_site`, `.jekyll-cache`, `.bundle`, `.git` o `.openai`. Il pacchetto ZIP per GitHub fornito con il sito è già pulito. GitHub Desktop è utile per caricare anche le cartelle nascoste e gestire gli aggiornamenti; il trascinamento nel browser può non includerle.
4. Apri **Settings → Pages**. In **Build and deployment → Source**, scegli **GitHub Actions**.
5. Apri **Actions → Publish academic website → Run workflow** e scegli `main`. Se un primo tentativo era partito prima dell’attivazione di Pages, eseguilo di nuovo adesso.
6. Attendi il completamento delle fasi `build` e `deploy`. GitHub mostrerà l’indirizzo pubblico `https://NOMEUTENTE.github.io/`.

Il workflow incluso configura automaticamente l’indirizzo del sito. Non devi modificare `url` e `baseurl` per la prima pubblicazione. La versione privata di revisione usa una configurazione separata.

Il piano gratuito richiede che il repository sia pubblico. Un indirizzo `github.io` non richiede l’acquisto di un dominio; un dominio personale è facoltativo e comporta un costo separato.

## Aggiornamenti

Modifica i file nel ramo `main` e salva con “Commit changes”. Il sito si aggiornerà automaticamente.

- `_pages/about.md`: biografia e notizie nella home.
- `_data/publications.yml`: pubblicazioni, autori, anno, sede e DOI.
- `_pages/teaching.md`: corsi, supervisione e divulgazione.
- `_pages/talks.md`: conferenze ed eventi.
- `_pages/cv.md`: curriculum online.
- `assets/pdf/Filippo-Mancini-CV.pdf`: CV scaricabile.
- `_config.yml`: nome, descrizione e impostazioni generali.

Per aggiornare una pubblicazione, copia la struttura di una voce esistente in `_data/publications.yml`. Tieni le voci ordinate dalla più recente, lasciando “Forthcoming” in cima. Conserva i titoli originali delle opere.

## Foto

La prima versione non include una foto. Per aggiungerla, salva il file in `assets/img/profile.jpg` e sostituisci `profile: null` nell’intestazione di `_pages/about.md` con:

```yaml
profile:
  align: right
  image: profile.jpg
  image_circular: false
```

## Anteprima locale facoltativa

Con Ruby 3.3 e Bundler disponibili:

```sh
bundle install
bundle exec jekyll serve
```

Apri l’indirizzo indicato dal comando. Per aggiornare il sito dal browser GitHub non devi installare questi strumenti sul computer.

## Riferimenti

- [Documentazione ufficiale GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages)
- [Workflow personalizzati per GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages)
- [Template al-folio](https://github.com/alshedivat/al-folio)
