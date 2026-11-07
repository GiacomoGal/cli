# Ingresso umano — fork `GiacomoGal/cli`

Pagina di ingresso per chi apre questo fork. Il prodotto descritto nel resto del tree è il Google Workspace CLI `gws` pubblicato a monte. Qui si registra solo ciò che, su **questo** fork, risulta da metadati pubblici e dal testo già presente al commit di base.

Uso corrente, installazione effettuata e account Google di questo fork sono **unknown**. La scheda locale del 7 novembre 2026 classifica il repository come UNMAPPED (`identity_proven` falso, `unknowncurrentuse` vero, `nextdocscope` unresolved, elenchi di evidenze e di proposte vuoti). Questa pagina non attesta attività, non dichiara il repository funzionante e non è un esito di review.

## Stato osservato

Controlli di metadati pubblici GitHub nella sessione iniziata il 2026-11-07T20:45:01Z. I conteggi di branch e pull request sono stati riletti con `per_page=100` nella stessa sessione. Il remote `origin` di questo clone punta a `https://github.com/GiacomoGal/cli`. Quel fatto prova l'identità configurata del clone, non l'uso corrente, la canonicità rispetto a una VPS, né una sincronizzazione.

| Campo | Valore osservato |
| --- | --- |
| Fork | sì, parent `googleworkspace/cli` |
| Archivio | no |
| Branch predefinito | `main`. L'API branches con `per_page=100` ha restituito un solo nome |
| Commit di `main` sul fork e in questo clone | [`7e22a3d0e31e41b70bbfcb53317a62730a3284bb`](https://github.com/GiacomoGal/cli/commit/7e22a3d0e31e41b70bbfcb53317a62730a3284bb) |
| Stesso commit sul parent | [`7e22a3d0e31e41b70bbfcb53317a62730a3284bb`](https://github.com/googleworkspace/cli/commit/7e22a3d0e31e41b70bbfcb53317a62730a3284bb), 2026-03-10T21:53:11Z, messaggio `chore: release versions (#390)` |
| Punta `main` del parent alla stessa query | [`cd3697e07eb520056dcf142d0c7439bbb9ba32e9`](https://github.com/googleworkspace/cli/commit/cd3697e07eb520056dcf142d0c7439bbb9ba32e9), 2026-10-30T15:47:59Z |
| Compare `googleworkspace:main...main` sul fork | `status` behind, `ahead_by` 0, `behind_by` 105, `total_commits` 0 |
| Pull request sul fork | 0. L'API pulls `state=all` con `per_page=100` ha restituito un elenco vuoto |
| `pushedAt` del fork | 2026-03-10T21:53:41Z |
| Licenza dichiarata dall'API | Apache-2.0; il file `LICENSE` è presente nel tree |
| Descrizione API | Google Workspace CLI, Discovery Service, skill per agenti |

Il contenuto dei 105 commit con cui il parent è avanti non è stato letto. Non c'è stato allineamento del fork al parent.

Il ref di inventario `main` coincide con lo SHA sopra. Questo non è un riscontro di allineamento a una VPS. Le voci vuote della scheda (evidenze di identità, proposte, decisioni, ricevute di esecuzione) restano vuote.

## Come si legge il tree

I documenti upstream restano al loro posto, compresi quelli annidati. Questa pagina non li riscrive, non alza di rango una roadmap o un workflow, e non abbassa un contratto vigente.

Scala di lettura usata solo qui, per non confondere i destinatari. Non sostituisce le priorità già scritte a monte (per esempio la precedenza delle credenziali nel README, o il rinvio vincolante di `CLAUDE.md` verso `AGENTS.md`).

| Rango | Chi | Quando si applica |
| --- | --- | --- |
| 1 | Agenti e chi contribuisce codice | Contributo al repository. `CLAUDE.md` rende `AGENTS.md` vincolante per quel ruolo |
| 2 | Persone | Lettura del README, contributo umano, segnalazione di sicurezza, condotta |
| 3 | Agente dell'estensione Gemini | Il file nominato da `gemini-extension.json` viene caricato come contesto |
| 4 | Agente che carica una skill | Il file `skills/*/SKILL.md` entra nel contesto. L'indice è un catalogo di file |
| 5 | Agente che sceglie un workflow annidato | Solo se segue `.agent/` o `.gemini/` |
| 6 | CI del parent, se un job parte | Condizione scritta nel workflow |
| 7 | Chi documenta questo fork | Questa pagina. Sta sotto i ranghi 1–6 |

## Matrice fonte → questa pagina

Le righe citano il testo al commit di base. «Destinazione» è il punto di questa pagina che ne tiene conto. I path di host sono nominati per conservarli; non sono stati aperti.

### Identità e contratti di ingresso

| ID | Fonte | Righe | Rango | Destinatario | Trigger | Destinazione | Motivo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| F1 | Scheda lotto 5, sezione 5, allegato locale | 69–80 | 7 | Chi scrive la guida del fork | Mandato documentale sul solo `GiacomoGal/cli` | Stato osservato; conflitti | Perimetro UNMAPPED. Le altre sezioni dell'allegato non sono questo repository |
| F2 | `README.md` | 1–416 | 2 | Persona che apre il repository | Lettura del README | Banner in cima al README; questa pagina | Ingresso umano prima dei comandi. Il corpo resta il testo upstream |
| F3 | `AGENTS.md` | 1–205 | 1 | Agenti e contributori | Modifica del progetto | Nota in testa ad `AGENTS.md` | Stesso perimetro del README, senza sostituire le sezioni successive |
| F4 | `CLAUDE.md` | 1 | 1 | Agenti Claude | Contributo | Secondo paragrafo di `CLAUDE.md` | Resta l'obbligo di seguire `AGENTS.md`. Il paragrafo nuovo indica la stessa pagina |
| F5 | `gemini-extension.json` | 1–6 | 3 | Gemini CLI | Caricamento estensione, campo `contextFileName` | Scala di lettura, rango 3; riga F6 | Configurazione non modificata. Il nome del contesto è `CONTEXT.md` |
| F6 | `CONTEXT.md` | 1–74 | 3 | Agente Gemini | Contesto caricato dall'estensione | Esempi fuori mandato | Contratto dell'estensione, annidato sotto F5. Non è stato promosso sopra `AGENTS.md` né ritirato |
| F7 | `docs/CONTRIBUTING.md` | 7–33 | 2 | Contributori umani del progetto upstream | Prima di inviare una patch a monte | Conflitti | CLA e review restano il processo upstream. Nessuna PR è aperta sul parent. Lo stato della CLA non è stato interrogato |
| F8 | `docs/CODE_OF_CONDUCT.md` | 1–20 e seguito | 2 | Comunità | Partecipazione | Nessun adattamento | Testo comunitario upstream, presente e non modificato |
| F9 | `SECURITY.md` | 1–6 | 2 | Chi segnala una vulnerabilità | Segnalazione | Host ref | Intake `https://g.co/vulnz` conservato. La pagina non è stata aperta e nessuna segnalazione è stata inviata |

### Regole di contribuzione e condizioni

| ID | Fonte | Righe | Rango | Destinatario | Trigger | Destinazione | Motivo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| C1 | `AGENTS.md` | 7–11 | 1 | Chi aggiunge un servizio o dipendenze Node | Modifica delle API coperte, o pacchetti Node del repository | Nessun adattamento | Discovery a runtime (7–8) e `pnpm` al posto di `npm` (10–11). Nessun crate `google-*` è stato aggiunto. `Cargo.toml` non è stato modificato |
| C2 | `AGENTS.md` | 13–22 | 1 | Chi modifica codice | Build, lint, test, coverage `codecov/patch` | Conflitti | I comandi restano nel contratto. Non sono stati eseguiti |
| C3 | `AGENTS.md` | 24–36 | 1 | Autori di PR | Ogni PR, testo senza condizione | `.changeset/docs-fork-ingresso.md` | Obbligo adempiuto. Livello `patch`, il grado che la riga 36 assegna a fix e chore. Lo skip CI di C6 non è una deroga e non è stato usato per omettere il file. Il testo di `AGENTS.md` non è stato indebolito |
| C4 | `AGENTS.md` | 81–153 | 1 | Chi aggiunge helper o flag | Nuovo input da CLI | Nessun adattamento | Validazione path, encoding, resource name. Gli esempi di path restano esempi di rifiuto nel contratto, non accessi |
| C5 | `AGENTS.md` | 86–87, 167–205 | 1 | Agenti | Argomenti CLI non fidati; variabili d'ambiente fidati se impostate dalla persona | Host ref | I nomi delle variabili restano. I valori non sono stati letti. `.env` non è stato aperto |
| C6 | `.github/workflows/policy.yml` | 42–49 | 6 | CI su `pull_request` | Il job di changeset esce subito se il diff non contiene `.rs` né `Cargo.toml` / `Cargo.lock` | C3 | Enforcement più stretto di C3. Un exit 0 non modifica il contratto e non autorizza a omettere il file. Workflow non modificato e non lanciato |
| C7 | `.github/workflows/policy.yml` | 35–41 | 6 | CI | Presenza di crate `google-*` in `Cargo.toml` | Nessun adattamento | Regola allineata a C1. Non eseguita da questa sessione |
| C8 | `docs/CONTRIBUTING.md` | 62–74, 88–93 | 2 | Contributori | PR con codice e validazione | C3 per il changeset; conflitti per i test | Il changeset delle righe 62–74 è lo stesso file di C3. `cargo test` alle righe 88–93 resta non eseguito |
| C9 | `.gemini/style_guide.md` | 1–26 | 5 | Review nell'albero `.gemini` | Review di codice | C3 per le righe 18–20 | Quelle righe ripetono il changeset `patch` per i chore. Adempiute dallo stesso file di C3. Il resto del file resta a rango 5 e non è stato riscritto |
| C10 | `.github/PULL_REQUEST_TEMPLATE.md` | 1–16 | 2 | Autori di PR | Apertura di una PR | C3 per il changeset; ricevuta della PR per il resto | La voce changeset è adempiuta da C3. Dry-run, fmt, clippy e test non sono stati eseguiti: questa modifica non aggiunge comandi né Rust |
| C11 | `AGENTS.md` | 60–79 | 1 | Chi rigenera i demo | Uso di VHS | Nessun adattamento | Resta la norma dei demo |
| C12 | `.agent/skills/vhs.md` | 1–40 e seguito | 5 | Chi edita i `.tape` | Quel compito | Nessun adattamento | Annidato. Non sostituisce C11. Fuori da questo mandato |
| C13 | `src/helpers/README.md` | 1–40 | 5 | Chi aggiunge helper | Modifica dei helper | Esempi fuori mandato | Documentazione di modulo, non ingresso del fork. Non modificata |

### Catalogo skill, esempi, invio, admin

| ID | Fonte | Righe | Rango | Destinatario | Trigger | Destinazione | Motivo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| S1 | `docs/skills.md` | 1–4, 11–124 | 4 | Lettori del catalogo | Consultazione dell'indice | Catalogo | Intestazione: generato da `gws generate-skills`, non editare a mano. Indice lasciato com'è |
| S2 | `skills/*/SKILL.md` | file interi | 4 | Agente che carica la skill | Caricamento del file | Catalogo | 92 file, gli stessi 92 link dell'indice, nessuno orfano. Il catalogo non installa skill e non autorizza un account |
| S3 | `README.md` | 4, 214–225 | 2 e 4 | Lettori | Sezione skill e prima frase del README | Catalogo | «40+» (riga 4) e «100+» / «50 curated recipes» (riga 216) restano. Il conteggio dei file è un altro numero: vedi Catalogo |
| S4 | `README.md` | 227–240 | 2 | Chi segue il blocco OpenClaw | Blocco `<details>` opzionale | Catalogo; nessun sync | Symlink verso `~/.openclaw/skills/` e frase «stays in sync». Non è una sincronizzazione di memorie. Non eseguito |
| S5 | `README.md` | 238 | 2 | Lettori | Frase sull'install block di `gws-shared` | Catalogo | La frase resta. Nel file della skill, alle righe lette, il blocco non c'è: vedi S6 |
| S6 | `skills/gws-shared/SKILL.md` | 1–66 | 4 | Agente che carica la skill condivisa | Caricamento | Catalogo | Front matter `openclaw.requires.bins: ["gws"]` (righe 6–9). Sezione Installation che rinvia al README (14–16). Sezione Authentication che nomina un comando e `GOOGLE_APPLICATION_CREDENTIALS`. Nessuna chiave `install:` in quel file. Corpo non riscritto |
| S7 | `skills/gws-gmail-send/SKILL.md`, `skills/gws-chat-send/SKILL.md`, `skills/gws-admin-reports/SKILL.md`, `skills/recipe-send-team-announcement/SKILL.md`, `skills/persona-it-admin/SKILL.md` | non aperte oltre l'indice | 4 | Agente che le carica | Caricamento | Esempi fuori mandato | Presenti nell'indice. Invio, Chat send e admin non sono questo mandato. I corpi non sono stati copiati |
| S8 | `CONTEXT.md` | 49–65 | 3 | Agente Gemini | Esempi nel corpo di quelle righe | Esempi fuori mandato | Le righe contengono esempi di scrittura, invio e admin. Non sono stati ricopiati né eseguiti |
| S9 | `README.md` | 69–101, 257–286 | 2 | Lettori degli esempi | Quick start, Chat, Sheets | Esempi fuori mandato | Esempi nel testo upstream. Separati dallo stato osservato |
| S10 | `.agent/workflows/verify-skills.md` | 1–73 | 5 | Agente che segue il workflow | Invocazione esplicita del workflow | Conflitti | Chiede di eseguire il binario, incluso `admin`, e `cargo build`. Non eseguito. Non promosso a norma del fork |
| S11 | `.github/workflows/generate-skills.yml` | 61–104 | 6 | CI di sync skill | `schedule` o `workflow_dispatch`, e diff su `skills/` o `docs/skills.md` | Nessun sync | Rigenera le skill dalla Discovery e può aprire una PR con changeset `sync-skills`. Non lanciato. Il secret nominato nel workflow non è stato letto |

### Account, installazione, path di host

| ID | Fonte | Righe | Rango | Destinatario | Trigger | Destinazione | Motivo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| H1 | `README.md` | 17–67, 242–255 | 2 | Chi installa seguendo il README | Scelta della persona | Stato unknown | npm, cargo, Nix, Gemini extension e release puntano a `googleworkspace/cli` o al pacchetto npm upstream. Gli URL non sono stati riscritti verso il fork. Installazione non eseguita e non osservata |
| H2 | `README.md` | 103–212, 332–398 | 2 | Chi configura OAuth | Sezione Authentication e troubleshooting | Stato unknown; host ref | Precedenza token, file, credenziali cifrate, `~/.config/gws/credentials.json`. Testo conservato. Nessun login |
| H3 | `docs/CONTRIBUTING.md` | 35–58 | 2 | Manutentori del secret di smoketest CI | Scadenza del token di smoketest | Host ref | Procedura di export e `gh secret set`. Non eseguita |
| H4 | `.github/workflows/ci.yml` | occorrenze note da ricerca testuale intorno a 336–368 | 6 | Job CI upstream | Quei job, se partono | Host ref | Il workflow assegna `GOOGLE_WORKSPACE_CLI_CREDENTIALS_FILE` a un path sotto `/tmp`. File e valori non aperti. CI non lanciata |

## Catalogo skill

`docs/skills.md` e i file sotto `skills/` sono un catalogo di Markdown nel tree a `7e22a3d`.

Conteggio sul disco, senza eseguire `gws generate-skills`: 18 servizi, 23 helper, 10 personas, 41 ricette, 92 file `SKILL.md`. L'indice ha 92 link e combacia con i file. Il README, lasciato intatto, scrive «40+», «100+» e «50 curated recipes».

Il catalogo non è un'installazione: i comandi `npx skills add` nel README restano istruzioni upstream verso `googleworkspace/cli`, non un'azione fatta qui e non una prova che una skill sia installata su un host. Non è un'autorizzazione di account: nessuna skill è stata installata, e nessun consenso OAuth è stato richiesto.

Esempi, invio ed admin restano nei file upstream (S7, S8, S9, C13). Questo mandato non li esegue e non li trascrive.

## Adattamenti minimi in questo fork

Cinque file Markdown, contati sul diff cumulativo rispetto al commit di base.

| File | Modifica |
| --- | --- |
| `docs/ingresso-fork.md` | Questa pagina |
| `README.md` | Un avviso subito sotto il titolo, prima del testo upstream |
| `AGENTS.md` | Una nota subito sotto il titolo. Le sezioni sotto la nota restano il contratto di rango 1 |
| `CLAUDE.md` | Un paragrafo che punta qui e conferma il rinvio a `AGENTS.md` |
| `.changeset/docs-fork-ingresso.md` | Changeset `patch` richiesto da C3. Non è una modifica di `.changeset/config.json` |

Nessuna sincronizzazione di memorie. Al commit di base una ricerca di `memory` nei file `*.md` non ha restituito occorrenze, e non c'è un file il cui nome contenga `memory`. Le occorrenze introdotte da questa modifica sono solo le frasi che escludono quella sincronizzazione. Il symlink OpenClaw (S4) e il workflow di sync skill (S11) non sono stati eseguiti.

Nessun altro file è stato modificato: niente codice, configurazione, script, dati, media, lockfile, skill o workflow.

## Conflitti dichiarati

Restano aperti. I testi che li contengono non sono stati modificati per farli coincidere.

1. **C6 non deroga C3.** `AGENTS.md` 24–36, `docs/CONTRIBUTING.md` 62–74, `.gemini/style_guide.md` 18–20 e il template di PR chiedono un changeset per ogni PR. Nessuna di queste fonti introduce un'eccezione per il solo Markdown. `policy.yml` 42–49 può uscire 0 quando il diff non tocca `.rs`, `Cargo.toml` o `Cargo.lock`: limita l'enforcement automatico, non il contratto. Il file `.changeset/docs-fork-ingresso.md` adempie l'obbligo, con `patch` come da riga 36 per un chore documentale. Il nome del pacchetto è quello già scritto in `AGENTS.md` e in `package.json`. I testi di `AGENTS.md`, `policy.yml` e `release-changesets.yml` non sono stati modificati. Sul primo head della PR il file mancava; quella omissione non resta. Il workflow di release, innesco `push` su `main` o `workflow_dispatch`, non è stato eseguito: pubblicare o versionare il pacchetto è fuori da questa correzione.
2. **C2, C8 e C10 contro il perimetro di questa modifica.** Il contratto di codice chiede `cargo test`, clippy, fmt e, per un comando nuovo, un dry-run. Questa modifica non aggiunge comandi. Quei controlli non sono stati eseguiti. Le righe restano obbligatorie per il codice.
3. **H1 e H2 contro lo stato unknown.** Il README insegna installazione e login. Sul fork, uso, installazione e account non sono accertati. Le istruzioni restano. Il banner dice che sono testo, non uno stato osservato, e che nominare un comando non autorizza a eseguirlo.
4. **S3 e S5 contro il conteggio e contro S6.** Le cifre del README e la frase sull'install block di OpenClaw non coincidono con i file contati e con `skills/gws-shared/SKILL.md` righe 1–66. Le frasi upstream non sono state corrette.
5. **S10 e S11 contro il divieto di esecuzione.** I workflow annidati chiedono CLI, build o Discovery live. Restano nel tree. Non sono stati lanciati e non diventano la norma di questa pagina.
6. **F7 contro una PR solo sul fork.** Il contributo upstream prevede CLA e review sul progetto Google. Questa modifica non apre una PR su `googleworkspace/cli` e non verifica la CLA.
7. **Il parent è 105 commit avanti.** Allineare il fork copierebbe documentazione e codice non letti. Non è stato fatto.

## Riferimenti di host conservati e non aperti

| Riferimento | Dove è scritto | Trattamento |
| --- | --- | --- |
| `~/.config/gws/`, `.encryption_key`, `client_secret.json`, `credentials.json` | README 118, 150, 210; `AGENTS.md` 174, 183 | Nominati. Directory non aperta |
| `~/.openclaw/skills/` | README 232, 235 | Nominato. Non aperto, nessuno symlink |
| `.env` | README 212, 318; `AGENTS.md` 87, 205 | Citato. Nel checkout il path `.env` è assente. `.env.example` è presente e non è stato letto |
| `GOOGLE_WORKSPACE_CLI_TOKEN`, `GOOGLE_WORKSPACE_CLI_CREDENTIALS_FILE`, `GOOGLE_WORKSPACE_CLI_CLIENT_ID`, `GOOGLE_WORKSPACE_CLI_CLIENT_SECRET`, `GOOGLE_WORKSPACE_CLI_CONFIG_DIR`, `GOOGLE_WORKSPACE_CLI_KEYRING_BACKEND`, `GOOGLE_WORKSPACE_CLI_SANITIZE_TEMPLATE`, `GOOGLE_WORKSPACE_CLI_SANITIZE_MODE`, `GOOGLE_WORKSPACE_PROJECT_ID`, `GOOGLE_APPLICATION_CREDENTIALS` | README, `AGENTS.md`, `skills/gws-shared/SKILL.md` 25 | Solo i nomi già scritti nei documenti. Valori non letti |
| `smoketest-creds.json`, secret di Actions nominato in `docs/CONTRIBUTING.md` 35–58 | CONTRIBUTING | Procedura non eseguita. Secret non letto |
| Path credenziali nei job di `.github/workflows/ci.yml` | H4 | Non aperto |
| Secret del bot nel workflow S11 | `generate-skills.yml` | Non letto |
| `src/oauth_config.rs`, `src/token_storage.rs`, `src/credential_store.rs` | albero `src/` | Solo i nomi dei file. Contenuto non letto |
| `https://g.co/vulnz`, console Google, Discovery Service, npm, CLA | README, SECURITY, CONTRIBUTING | Non richiesti in questa sessione |
| `https://github.com/googleworkspace/cli` e i due SHA del parent | README, API GitHub | Metadati pubblici già in Stato osservato. Nessun push verso il parent |

## Verifiche, effetti, limiti

Effetto cumulativo rispetto al commit di base, una volta integrata sul fork: cinque file Markdown, tra cui `.changeset/docs-fork-ingresso.md`. Nessun binario, nessun account, nessuna skill installata, nessuna chiamata alle API Google. Il push del branch di PR non è un push su `main` e non invoca il workflow di release.

Verifiche fatte, tutte documentali:

- All'inizio della sessione, `HEAD` e `origin/main` erano `7e22a3d0e31e41b70bbfcb53317a62730a3284bb`. I commit di questa PR stanno sul branch, non su `main`.
- API GitHub pubblica del fork: fork, parent, branch, commit, compare, elenco PR. Dettaglio nella tabella di stato.
- Presenza di path citati: `LICENSE`, `docs/skills.md`, `docs/demo.tape`, `docs/CONTRIBUTING.md`, `AGENTS.md`, `CLAUDE.md`, `CONTEXT.md`, `gemini-extension.json`, `.env.example`. Assenza di `.env`.
- Conteggio dei `SKILL.md` e incrocio con i link di `docs/skills.md`.
- Lettura dei Markdown di contratto elencati nella matrice, più le righe 1–66 di `skills/gws-shared/SKILL.md` e le righe citate dei workflow. I corpi delle skill di invio e admin non sono stati aperti.
- Forma del changeset confrontata con `AGENTS.md` 29–36 e con changeset storici già nel parent (stesso front matter `"@googleworkspace/cli": patch`). Nessun comando `changeset` è stato lanciato.

Limiti, da non leggere come un esito positivo:

- Nessuna installazione, build, test, lint, esecuzione di `gws`, login, Discovery live, chiamata a API Google, provider, SSH, sync, invio, merge, deploy o archive.
- Nessuna lettura di env, token, OAuth, sessioni, credenziali, `.env.example`, backup, memorie, dati Workspace, email, file o calendari privati.
- I link npm, la documentation Discovery, la console Google e `g.co/vulnz` non sono stati scaricati. Il loro stato HTTP è unknown.
- L'API compare non descrive il contenuto dei 105 commit.
- La CI di questa PR, se partirà, non è stata osservata qui. Questa pagina non assegna un PASS.

La coppia SHA base/head e il diff stanno nella descrizione della pull request: un file non può nominare in modo stabile l'hash del commit che lo introduce.
