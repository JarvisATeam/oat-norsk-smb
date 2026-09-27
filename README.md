# OAT Norsk SMB

Norske arbeidsverktøy for håndverkere og små bedrifter i Claude Cowork og Claude Code.

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

Skillene dukker opp som `/oat-norsk-smb:brreg-oppslag`, `/oat-norsk-smb:tilbud-handverk` og `/oat-norsk-smb:purring-inkasso`. Oppdater senere med `claude plugin update oat-norsk-smb@oat-marketplace`.

## Eksempler

- "Sjekk org.nr 923609016 før vi sender tilbud"
- "Lag tilbud på nytt sikringsskap til en privatkunde, fastpris 18 500 eks. MVA"
- "Kunden har ikke betalt faktura 1042. Forfall var for 20 dager siden. Lag purring."

## Krav

Ingen nøkler. Firmaoppslag bruker det åpne API-et til Enhetsregisteret og trenger nettilgang.

## Forbehold

Pluginen gir praktisk hjelp, ikke juridisk rådgivning. Gebyrsatser er hentet fra Finanstilsynet for 2026 og må sjekkes årlig. Ingen meldinger sendes uten at du selv godkjenner og sender.

## Vil du ha dette koblet til dine egne systemer?

OAT – Olsen's A-Team setter opp dette mot regnskap, e-post og CRM for norske SMB-er. Se [giniesystem.no](https://giniesystem.no).

## Lisens

MIT. Se [LICENSE](LICENSE).
