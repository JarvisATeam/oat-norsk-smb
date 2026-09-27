# OAT Norsk SMB

Norske arbeidsverktøy for håndverkere og små bedrifter i Claude Cowork og Claude Code.

OAT står for Olsen's A-Team, som lager pluginen. SMB betyr små og mellomstore bedrifter.

## Hva du får

- **brreg-oppslag**: Slå opp firma i Brønnøysundregistrene. Org.nr-validering, roller og risikoflagg før du gir kreditt.
- **tilbud-handverk**: Ferdige tilbud med riktig MVA, omfang, forbehold og akseptfrist. Tilpasset forbruker og bedrift.
- **purring-inkasso**: Påminnelse, purring og inkassovarsel med lovlige frister og gebyrer.

## Installasjon

I Claude Code, fra terminalen:

```bash
claude plugin marketplace add JarvisATeam/oat-norsk-smb
claude plugin install oat-norsk-smb@oat-marketplace
```

Eller i én kommando inne i en økt:

```
/plugin install oat-norsk-smb --marketplace JarvisATeam/oat-norsk-smb
```

Navnet før @ er pluginen. Navnet etter @ er katalogen den hentes fra. Du trenger bare å skrive det én gang.

Skillene dukker opp som `/oat-norsk-smb:brreg-oppslag`, `/oat-norsk-smb:tilbud-handverk` og `/oat-norsk-smb:purring-inkasso`. Oppdater senere med `claude plugin update oat-norsk-smb@oat-marketplace`.

## Eksempler

- "Sjekk org.nr 974760673 før vi sender tilbud" (dette er Brønnøysundregistrenes eget nummer, brukt som eksempel)
- "Lag tilbud på nytt sikringsskap til en privatkunde, fastpris 18 500 eks. MVA"
- "Kunden har ikke betalt faktura 1042. Forfall var for 20 dager siden. Lag purring."

## Krav

Ingen nøkler. Firmaoppslag bruker det åpne API-et til Enhetsregisteret og trenger nettilgang.

## Data og nettverk

Pluginen består bare av skills i Markdown. Den har ingen hooks, ingen MCP-server og ingen kode som kjører av seg selv.

- **brreg-oppslag** henter data fra `data.brreg.no`, det åpne API-et til Brønnøysundregistrene. Det eneste som sendes dit er organisasjonsnummeret eller firmanavnet du selv oppgir. Ingen nøkler, ingen innlogging.
- **tilbud-handverk** og **purring-inkasso** sender ingenting ut. De lager tekst i samtalen ut fra det du skriver inn.
- Pluginen lagrer ingenting. Den sender ingen e-post, SMS eller andre meldinger. Du kopierer og sender selv.

## Forbehold

Pluginen gir praktisk hjelp, ikke juridisk rådgivning. Gebyrsatser er hentet fra Finanstilsynet for 2026 og må sjekkes årlig. Ingen meldinger sendes uten at du selv godkjenner og sender.

## Vil du ha dette koblet til dine egne systemer?

OAT – Olsen's A-Team setter opp dette mot regnskap, e-post og CRM for norske SMB-er. Se [giniesystem.no](https://giniesystem.no).

## Forklaring av navn og forkortelser

- **OAT**: Olsen's A-Team, firmaet bak pluginen.
- **SMB**: små og mellomstore bedrifter.
- **MVA**: merverdiavgift. Vanlig sats er 25 %.
- **Org.nr**: organisasjonsnummer. Alle norske virksomheter har et nummer på 9 sifre.
- **Brreg**: kortnavn for Brønnøysundregistrene. Enhetsregisteret er registeret der alle org.nr ligger.
- **KID**: kundeidentifikasjonsnummer. Nummeret kunden skriver inn når de betaler en faktura i nettbanken.
- **oat-norsk-smb**: pluginens faste tekniske navn. Det endres aldri, fordi installasjoner er knyttet til det.
- **oat-marketplace**: navnet på katalogen i dette repoet som pluginen installeres fra.
- **0.1.2**: versjonsnummeret. Første tall øker ved store endringer, andre ved nye funksjoner, tredje ved rettinger. Når første tall er 0, er pluginen fortsatt i en tidlig fase. Se [CHANGELOG.md](CHANGELOG.md).
- **.claude-plugin/**: mappen med pluginens innstillingsfiler. plugin.json beskriver pluginen, marketplace.json beskriver katalogen.
- **skills/**: mappen med de tre ferdighetene. Hver ferdighet er én tekstfil som forteller Claude hva den skal gjøre.
- **assets/icon.png**: logoen som vises i katalogen.

## Lisens

MIT. Se [LICENSE](LICENSE).
