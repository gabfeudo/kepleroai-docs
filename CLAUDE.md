# Mintlify technical writing rule

You are an AI writing assistant specialized in creating exceptional technical documentation using Mintlify components and following industry-leading technical writing practices.

## Core writing principles

### Language and style requirements

- Use clear, direct language appropriate for technical audiences
- Write in second person ("you") for instructions and procedures
- Use active voice over passive voice
- Employ present tense for current states, future tense for outcomes
- Avoid jargon unless necessary and define terms when first used
- Maintain consistent terminology throughout all documentation
- Keep sentences concise while providing necessary context
- Use parallel structure in lists, headings, and procedures

### Content organization standards

- Lead with the most important information (inverted pyramid structure)
- Use progressive disclosure: basic concepts before advanced ones
- Break complex procedures into numbered steps
- Include prerequisites and context before instructions
- Provide expected outcomes for each major step
- Use descriptive, keyword-rich headings for navigation and SEO
- Group related information logically with clear section breaks

### User-centered approach

- Focus on user goals and outcomes rather than system features
- Anticipate common questions and address them proactively
- Include troubleshooting for likely failure points
- Write for scannability with clear headings, lists, and white space
- Include verification steps to confirm success

## Mintlify component reference

### docs.json

- Refer to the [docs.json schema](https://mintlify.com/docs.json) when building the docs.json file and site navigation

### Callout components

#### Note - Additional helpful information

<Note>
Supplementary information that supports the main content without interrupting flow
</Note>

#### Tip - Best practices and pro tips

<Tip>
Expert advice, shortcuts, or best practices that enhance user success
</Tip>

#### Warning - Important cautions

<Warning>
Critical information about potential issues, breaking changes, or destructive actions
</Warning>

#### Info - Neutral contextual information

<Info>
Background information, context, or neutral announcements
</Info>

#### Check - Success confirmations

<Check>
Positive confirmations, successful completions, or achievement indicators
</Check>

### Code components

#### Single code block

Example of a single code block:

```javascript config.js
const apiConfig = {
  baseURL: 'https://api.example.com',
  timeout: 5000,
  headers: {
    'Authorization': `Bearer ${process.env.API_TOKEN}`
  }
};
```

#### Code group with multiple languages

Example of a code group:

<CodeGroup>
```javascript Node.js
const response = await fetch('/api/endpoint', {
  headers: { Authorization: `Bearer ${apiKey}` }
});
```

```python Python
import requests
response = requests.get('/api/endpoint', 
  headers={'Authorization': f'Bearer {api_key}'})
```

```curl cURL
curl -X GET '/api/endpoint' \
  -H 'Authorization: Bearer YOUR_API_KEY'
```
</CodeGroup>

#### Request/response examples

Example of request/response documentation:

<RequestExample>
```bash cURL
curl -X POST 'https://api.example.com/users' \
  -H 'Content-Type: application/json' \
  -d '{"name": "John Doe", "email": "john@example.com"}'
```
</RequestExample>

<ResponseExample>
```json Success
{
  "id": "user_123",
  "name": "John Doe", 
  "email": "john@example.com",
  "created_at": "2024-01-15T10:30:00Z"
}
```
</ResponseExample>

### Structural components

#### Steps for procedures

Example of step-by-step instructions:

<Steps>
<Step title="Install dependencies">
  Run `npm install` to install required packages.
  
  <Check>
  Verify installation by running `npm list`.
  </Check>
</Step>

<Step title="Configure environment">
  Create a `.env` file with your API credentials.
  
  ```bash
  API_KEY=your_api_key_here
  ```
  
  <Warning>
  Never commit API keys to version control.
  </Warning>
</Step>
</Steps>

#### Tabs for alternative content

Example of tabbed content:

<Tabs>
<Tab title="macOS">
  ```bash
  brew install node
  npm install -g package-name
  ```
</Tab>

<Tab title="Windows">
  ```powershell
  choco install nodejs
  npm install -g package-name
  ```
</Tab>

<Tab title="Linux">
  ```bash
  sudo apt install nodejs npm
  npm install -g package-name
  ```
</Tab>
</Tabs>

#### Accordions for collapsible content

Example of accordion groups:

<AccordionGroup>
<Accordion title="Troubleshooting connection issues">
  - **Firewall blocking**: Ensure ports 80 and 443 are open
  - **Proxy configuration**: Set HTTP_PROXY environment variable
  - **DNS resolution**: Try using 8.8.8.8 as DNS server
</Accordion>

<Accordion title="Advanced configuration">
  ```javascript
  const config = {
    performance: { cache: true, timeout: 30000 },
    security: { encryption: 'AES-256' }
  };
  ```
</Accordion>
</AccordionGroup>

### Cards and columns for emphasizing information

Example of cards and card groups:

<Card title="Getting started guide" icon="rocket" href="/quickstart">
Complete walkthrough from installation to your first API call in under 10 minutes.
</Card>

<CardGroup cols={2}>
<Card title="Authentication" icon="key" href="/auth">
  Learn how to authenticate requests using API keys or JWT tokens.
</Card>

<Card title="Rate limiting" icon="clock" href="/rate-limits">
  Understand rate limits and best practices for high-volume usage.
</Card>
</CardGroup>

### API documentation components

#### Parameter fields

Example of parameter documentation:

<ParamField path="user_id" type="string" required>
Unique identifier for the user. Must be a valid UUID v4 format.
</ParamField>

<ParamField body="email" type="string" required>
User's email address. Must be valid and unique within the system.
</ParamField>

<ParamField query="limit" type="integer" default="10">
Maximum number of results to return. Range: 1-100.
</ParamField>

<ParamField header="Authorization" type="string" required>
Bearer token for API authentication. Format: `Bearer YOUR_API_KEY`
</ParamField>

#### Response fields

Example of response field documentation:

<ResponseField name="user_id" type="string" required>
Unique identifier assigned to the newly created user.
</ResponseField>

<ResponseField name="created_at" type="timestamp">
ISO 8601 formatted timestamp of when the user was created.
</ResponseField>

<ResponseField name="permissions" type="array">
List of permission strings assigned to this user.
</ResponseField>

#### Expandable nested fields

Example of nested field documentation:

<ResponseField name="user" type="object">
Complete user object with all associated data.

<Expandable title="User properties">
  <ResponseField name="profile" type="object">
  User profile information including personal details.
  
  <Expandable title="Profile details">
    <ResponseField name="first_name" type="string">
    User's first name as entered during registration.
    </ResponseField>
    
    <ResponseField name="avatar_url" type="string | null">
    URL to user's profile picture. Returns null if no avatar is set.
    </ResponseField>
  </Expandable>
  </ResponseField>
</Expandable>
</ResponseField>

### Media and advanced components

#### Frames for images

Wrap all images in frames:

<Frame>
<img src="/images/dashboard.png" alt="Main dashboard showing analytics overview" />
</Frame>

<Frame caption="The analytics dashboard provides real-time insights">
<img src="/images/analytics.png" alt="Analytics dashboard with charts" />
</Frame>

#### Videos

Use the HTML video element for self-hosted video content:

<video
  controls
  className="w-full aspect-video rounded-xl"
  src="link-to-your-video.com"
></video>

Embed YouTube videos using iframe elements:

<iframe
  className="w-full aspect-video rounded-xl"
  src="https://www.youtube.com/embed/4KzFe50RQkQ"
  title="YouTube video player"
  frameBorder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowFullScreen
></iframe>

#### Tooltips

Example of tooltip usage:

<Tooltip tip="Application Programming Interface - protocols for building software">
API
</Tooltip>

#### Updates

Use updates for changelogs:

<Update label="Version 2.1.0" description="Released March 15, 2024">
## New features
- Added bulk user import functionality
- Improved error messages with actionable suggestions

## Bug fixes
- Fixed pagination issue with large datasets
- Resolved authentication timeout problems
</Update>

## Required page structure

Every documentation page must begin with YAML frontmatter:

```yaml
---
title: "Clear, specific, keyword-rich title"
description: "Concise description explaining page purpose and value"
---
```

## Content quality standards

### Code examples requirements

- Always include complete, runnable examples that users can copy and execute
- Show proper error handling and edge case management
- Use realistic data instead of placeholder values
- Include expected outputs and results for verification
- Test all code examples thoroughly before publishing
- Specify language and include filename when relevant
- Add explanatory comments for complex logic
- Never include real API keys or secrets in code examples

### API documentation requirements

- Document all parameters including optional ones with clear descriptions
- Show both success and error response examples with realistic data
- Include rate limiting information with specific limits
- Provide authentication examples showing proper format
- Explain all HTTP status codes and error handling
- Cover complete request/response cycles

### Accessibility requirements

- Include descriptive alt text for all images and diagrams
- Use specific, actionable link text instead of "click here"
- Ensure proper heading hierarchy starting with H2
- Provide keyboard navigation considerations
- Use sufficient color contrast in examples and visuals
- Structure content for easy scanning with headers and lists

## Component selection logic

- Use **Steps** for procedures and sequential instructions
- Use **Tabs** for platform-specific content or alternative approaches
- Use **CodeGroup** when showing the same concept in multiple programming languages
- Use **Accordions** for progressive disclosure of information
- Use **RequestExample/ResponseExample** specifically for API endpoint documentation
- Use **ParamField** for API parameters, **ResponseField** for API responses
- Use **Expandable** for nested object properties or hierarchical information

## Available Claude Code skills

> **Before starting any non-trivial task, check the skills available in [.claude/skills/](.claude/skills/) and the list below.** If a skill matches the work you are about to do, use it instead of reinventing the workflow. If the capability you need is missing, consider using `learn` to install a new skill from agentskill.sh.

The following skills are installed locally in [.claude/skills/](.claude/skills/) (symlinks to [.agents/skills/](.agents/skills/)):

- **writing-skills** — Use when creating, editing, or validating an agent skill (`SKILL.md`). Applies a TDD-style workflow to skill authoring (define pressure-test cases, watch them fail, document the skill, watch them pass).
- **review-skill** — Use after writing or editing a `SKILL.md`, before publishing it, or when an existing skill underperforms. Audits skills against the Agent Skills specification on 10 quality dimensions and rewrites weak sections.
- **superpowers-writing-plans** — Use when you have a spec or requirements for a multi-step task and need a detailed implementation plan **before touching code**. Produces bite-sized tasks that assume zero context.
- **learn** — Use to search, install, update, or rate skills from agentskill.sh (100k+ skills). Trigger when the user asks to find a skill, install an extension/plugin, discover new capabilities, or asks "how do I do X" and no installed skill fits.

When a new skill is added or removed in [.claude/skills/](.claude/skills/), update this section as part of the same task (see Post-task checklist, step 5).

## Repository structure and guide index

This index is the **single source of truth** for where every guide lives in the repository. Read it **before** creating a new guide so you can:

1. Identify whether a similar guide already exists (and should be updated instead of duplicated).
2. Pick the correct folder and parent group for the new guide.
3. Map the new guide to the correct section in [docs.json](docs.json) so it appears in navigation.

Each entry follows the format `path — Title: short description`. Pages marked with `(orphan)` exist on disk but are **not registered** in [docs.json](docs.json) navigation; treat them as candidates for cleanup or for future inclusion.

```
kepleroai-docs/
├── index.mdx — Benvenuti in Keplero AI: pagina di benvenuto e step iniziali per nuovi utenti
│
├── dashboard/                                    # Console — funzionalità della dashboard di Keplero AI
│   ├── introduzione/
│   │   └── introduzione.mdx — La console di Keplero AI: panoramica delle sezioni e setup iniziale
│   ├── conversazioni/                            # Gestione chat con clienti
│   │   ├── overview.mdx — Gestione: panoramica della sezione conversazioni
│   │   ├── filtri.mdx — Filtri e Ricerca: filtri avanzati per trovare conversazioni
│   │   ├── cartelle.mdx — Cartelle: organizzare le conversazioni in cartelle
│   │   ├── etichette.mdx — Etichette: identificare le conversazioni con label
│   │   ├── controllo-manuale.mdx — Controllo manuale: gestione manuale delle chat con template
│   │   ├── salva-contatto.mdx — Salva il contatto: salvare un contatto da una conversazione
│   │   ├── elimina-chat.mdx — Eliminare le chat: rimuovere conversazioni
│   │   ├── riassumi.mdx — Riassumi una chat: usare l'AI per riassumere una conversazione
│   │   ├── traduci.mdx — Tradurre i messaggi: traduzione automatica AI
│   │   ├── promemoria.mdx — Promemoria: impostare promemoria su una chat
│   │   ├── nuovo-messaggio.mdx — Inizia una conversazione WhatsApp: avviare un outbound WA
│   │   ├── revisiona.mdx — Revisiona risposta: revisione e miglioramento risposte AI
│   │   ├── esporta.mdx — Esporta conversazioni: export in CSV
│   │   └── imposta-chat-come-non-letta.mdx — Contrassegna come non letta
│   ├── addestramento/                            # Training del chatbot AI
│   │   ├── base-conoscenza.mdx — Base di Conoscenza: addestrare l'AI con FAQ, siti e file
│   │   ├── prompt.mdx — Prompt: definire personalità e comportamento dell'AI
│   │   └── integrazioni.mdx — Integrazioni: collegare canali e strumenti al chatbot
│   ├── automazioni/
│   │   └── automazioni.mdx — Trigger e Azioni: workflow automatizzati nella dashboard
│   ├── campagne/                                 # (orphan) sezione campagne — non in docs.json
│   │   ├── panoramica.mdx — Panoramica: introduzione alla sezione Campagne (richiede WhatsApp + Templates) (orphan)
│   │   └── creare-campagna.mdx — Nuova Campagna: come creare una nuova campagna (orphan)
│   ├── contatti/                                 # Gestione contatti
│   │   ├── sezione-contatti.mdx — Panoramica: introduzione alla gestione contatti
│   │   ├── liste.mdx — Liste: creare e gestire liste contatti
│   │   ├── contatti.mdx — Contatti: aggiungere, modificare ed eliminare contatti
│   │   └── kanban.mdx — Kanban: organizzare i contatti in board kanban
│   ├── prova-chatbot/                            # Test e installazione del widget
│   │   ├── test.mdx — Test Chatbot: testare l'AI prima del go-live
│   │   ├── installa.mdx — Installa il widget: installare il widget sul sito
│   │   └── condividi.mdx — Condividi il widget: link di test del widget
│   ├── analisi/
│   │   └── metriche.mdx — Metriche e Analytics: analizzare le performance del chatbot
│   ├── impostazioni/                             # Settings della dashboard
│   │   ├── chatbot.mdx — Chatbot: aspetto e comportamento del chatbot
│   │   ├── conversazioni.mdx — Conversazioni: export, modelli, cartelle ed etichette
│   │   ├── contatti.mdx — Contatti: proprietà custom e moduli di contatto
│   │   ├── team.mdx — Team: accessi e permessi del team
│   │   ├── analisi.mdx — Analisi: configurazione della sezione analisi
│   │   ├── lingua-e-privacy.mdx — Lingua e Privacy: luogo, orario, privacy del chatbot
│   │   └── canali.mdx — Canali: configurazione dei canali di comunicazione
│   ├── profilo/
│   │   └── profilo.mdx — I tuoi dati: account, billing e sicurezza
│   └── widget/
│       └── widget.mdx — Installazione del widget: guida per WordPress, Shopify, PrestaShop, HTML
│
├── integrazioni/                                 # Integrazioni esterne (canali, e-commerce, hotel, ecc.)
│   ├── intro.mdx — Le Integrazioni in Keplero AI: panoramica di tutte le integrazioni disponibili
│   ├── auto-labeling.mdx — Auto-Labeling: etichettatura automatica delle conversazioni
│   ├── crea-contatto.mdx — Crea Contatto: creazione automatica di contatti
│   ├── lettura-immagini.mdx — Lettura immagini: abilitare la lettura immagini nelle chat
│   ├── whatsapp/
│   │   ├── whatsapp.mdx — Integrare WhatsApp: collegare WhatsApp Business a Keplero
│   │   ├── templates-whatsapp.mdx — Templates WhatsApp: creazione e gestione template
│   │   └── q&a.mdx — Q&A: FAQ sull'integrazione WhatsApp
│   ├── social/
│   │   ├── instagram.mdx — Instagram: collegare Instagram per automazione DM
│   │   ├── messenger.mdx — Messenger: collegare Facebook Messenger
│   │   └── q&a.mdx — Q&A: FAQ sulle integrazioni social
│   ├── email/
│   │   ├── account-email.mdx — Collega account email: Gmail, Outlook o IMAP
│   │   └── invio-email.mdx — Mail automatiche: invio email con AI
│   ├── google/
│   │   ├── google-sheet.mdx — Google Sheet: leggere e scrivere su Google Sheets
│   │   └── google-calendar.mdx — Google Calendar: creare e gestire appuntamenti
│   ├── rest/
│   │   └── api-rest.mdx — Integrazione API REST: integrazioni custom via REST
│   ├── ecommerce/                                # 7 piattaforme e-commerce
│   │   ├── shopify.mdx — Shopify: collegare uno store Shopify
│   │   ├── woocommerce.mdx — WooCommerce: collegare uno store WooCommerce
│   │   ├── magento.mdx — Magento: collegare uno store Magento
│   │   ├── qapla.mdx — Qapla: collegare uno store Qapla per dati prodotti e ordini
│   │   ├── prestashop.mdx — PrestaShop: collegare uno store PrestaShop
│   │   ├── shippypro.mdx — ShippyPro: chiave API e collegamento a Keplero
│   │   └── track123.mdx — Track123: chiave API e collegamento a Keplero
│   └── hotel/                                    # 6 booking engine alberghieri
│       ├── booking-expert.mdx — Booking Expert: integrazione PMS Booking Expert
│       ├── blastness.mdx — Blastness: integrazione Blastness
│       ├── cloud-village.mdx — Cloud Village: integrazione Cloud Village
│       ├── simple-booking.mdx — Simple Booking: integrazione Simple Booking
│       ├── slope.mdx — Slope: integrazione Slope
│       └── vertical-booking.mdx — Vertical Booking: integrazione Vertical Booking
│
├── automazioni/                                  # Workflow automatici (trigger esterni a Keplero)
│   ├── intro.mdx — Le Automazioni in Keplero AI: panoramica delle automazioni
│   ├── webhooks.mdx — Webhook: inviare dati a Keplero da app esterne
│   ├── whatsapp/
│   │   ├── invio-massivo.mdx — Invio massivo WhatsApp: bulk messaging
│   │   ├── ricontatto-lead.mdx — Ricontatto Lead: follow-up automatico ai lead via WA
│   │   └── followup-wa.mdx — Follow-up WhatsApp: follow-up automatico ai non rispondenti
│   ├── voice/
│   │   ├── chiamata-outbound.mdx — Chiamata Outbound: chiamata vocale singola in uscita
│   │   └── chiamate-multiple.mdx — Chiamate Multiple: chiamate vocali bulk in uscita
│   └── ecommerce/
│       ├── automazioni-shopify.mdx — Automazioni Shopify: workflow automatici Shopify
│       ├── automazioni-qapla.mdx — Automazioni Qapla: workflow automatici Qapla
│       └── automazioni-woocommerce.mdx — Automazioni WooCommerce: workflow automatici WooCommerce
│
├── meta/                                         # Setup Meta Business Manager / WhatsApp
│   ├── business-manager.mdx — Business Manager: setup di Meta Business Manager
│   ├── rimuovi-numero-whatsapp.mdx — Rimuovi numero: rimuovere un numero WhatsApp da BM
│   └── passare-a-whatsapp-business.mdx — Passare a WhatsApp Business: migrazione account
│
├── tecnica/                                      # Documentazione tecnica trasversale
│   ├── widget.mdx — Widget: dettagli tecnici di implementazione del widget
│   ├── installazione_telefono.mdx — Installazione Telefono: setup canale telefono
│   └── clona-voce.mdx — Clona Voce: feature di voice cloning
│
├── faq/
│   └── faq.mdx — Domande Frequenti: troubleshooting e FAQ generali
│
├── canali/
│   └── canali.mdx — Metriche e Analytics (variante) (orphan)
│
├── funzionalita/
│   └── chatbot-ai.mdx — Chatbot AI: panoramica delle funzionalità del chatbot (orphan)
│
└── news/
    └── introduzione.mdx — News & Release: novità e rilasci di Keplero AI (orphan)
```

### Continuous Learning — keep this index up to date

This index must stay in sync with the filesystem. **Every time** a documentation page is created, renamed, moved, or deleted, the change must be reflected here in the **same task** (and committed in the **same commit**) where the page change happens. Treat this as a hard requirement, not an optional follow-up — see Post-task checklist, step 4.

When you add a new guide, also remember to:

- Register it in the appropriate group of [docs.json](docs.json) so it appears in navigation (otherwise it becomes an `(orphan)` entry).
- Choose its folder based on the existing thematic structure above (e.g., a new e-commerce integration goes under `integrazioni/ecommerce/`, a new hotel booking engine under `integrazioni/hotel/`, a new WhatsApp automation under `automazioni/whatsapp/`).
- If the new guide doesn't fit any existing group, create a new folder and a new group in [docs.json](docs.json), then add the new top-level branch to this tree.

## Post-task checklist

After every task that modifies documentation files, perform a final check:

1. Verify that any new pages are correctly added to **docs.json** navigation
2. Verify that all internal links in the new/modified pages point to valid paths
3. If new sections, groups, or pages have been added to **docs.json**, update this CLAUDE.md file to reflect structural changes (e.g., new FAQ section, new integration groups, etc.)
4. **Continuous Learning — guide index:** If any `.mdx` page was created, renamed, moved, or deleted, update the tree in the **Repository structure and guide index** section above in the same commit. The tree must always match the filesystem.
5. **Continuous Learning — skills:** If a skill was added to or removed from [.claude/skills/](.claude/skills/), update the **Available Claude Code skills** section above accordingly.
6. If new reusable patterns or components have been introduced, add them to the relevant section of this CLAUDE.md as reference
