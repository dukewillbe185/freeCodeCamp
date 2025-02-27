# How to work on documentation

## Work on the docs content

To work on the contributing guidelines, you can edit or add files in the `docs` directory [available here](https://github.com/freeCodeCamp/freeCodeCamp/tree/main/docs). When your changes are merged, it will be made available automatically at the documentation site.

### How to create an internal link

If you want to create a link targeting a different section of the contributing guidelines, follow this format:

```md
[Link text](target-file-name.md#target-section-heading-id)

// If the target section is within the same page, you can omit the file name
[Link text](#target-section-heading-id)
```

Make sure you include the file extension (`.md`). Don't specify the full URL or append `/` before the file name.

This is necessary to make these links work for the translated version of the document. Otherwise, they will redirect to the English version of the page regardless of the language.

#### Translating docs with internal links

When you work on translating docs on Crowdin, make sure to replace the `#target-section-heading-id` with the id on the translated document. [Learn more about translating docs here](how-to-translate-files.md#translate-documentation).

## Work on the docs theme

> [!NOTE] Un rapido promemoria per ricordarti che non è necessario configurare nulla per lavorare sul contenuto del sito di documentazione.
> 
> To work on the contributing guidelines, see [work on the docs content](#work-on-the-docs-content) section.

### Structure of the docs website

The site is generated using [`docsify`](https://docsify.js.org), and served using GitHub pages.

Typically you would not need to change any configuration or build the site locally. In case you are interested, here is how it works:

- Il sorgente della homepage per questo sito è disponibile in [`docs/index.html`](index.html).
- Serviamo questo file come SPA (Single Page Application) usando `docsify` e GitHub Pages.
- Lo script `docsify` genera il contenuto del `file markdown` nella directory `docs` su richiesta.
- La homepage è generata dal file [`_coverpage.md`](_coverpage.md).
- la navigazione della barra laterale è generata da [`_sidebar.md`](_sidebar.md).

### Serving the documentation site locally

Clone freeCodeCamp:

```console
git clone https://github.com/freeCodeCamp/freeCodeCamp.git
docsify serve docs
```

Install `docsify`:

```console
npm install -g docsify
```

and serve the `/docs` directory

```console
docsify serve docs
```

Alternatively, if you have installed freeCodeCamp locally (see the local setup guide), we bundled the CLI with the development tools so you can run any of the below commands as needed from the root of the repo:

#### Serve and launch the documentation site only

```console
npm run docs:serve
```

#### Serve the documentation site alongside freeCodeCamp locally:

```console
npm run develop
```

> Il sito di documentazione dovrebbe essere disponibile su <http://localhost:3200>
