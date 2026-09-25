---
name: brreg-oppslag
description: Slår opp norske virksomheter i Enhetsregisteret (Brønnøysundregistrene) via det åpne API-et. Brukes når brukeren sier "sjekk firmaet", "slå opp org.nr", "finn orgnummer til", "er dette firmaet ekte", "hvem er daglig leder", "sjekk kunden før vi sender tilbud", eller oppgir et 9-sifret organisasjonsnummer.
---

# Firmaoppslag i Brønnøysundregistrene

Hent fakta om en norsk virksomhet fra Enhetsregisteret. Bruk kun data fra registeret. Dikt aldri opp felt som mangler.

## Kilde

Åpent API, ingen nøkkel:

```
https://data.brreg.no/enhetsregisteret/api/enheter/{orgnr}
https://data.brreg.no/enhetsregisteret/api/enheter?navn={navn}&size=10
https://data.brreg.no/enhetsregisteret/api/enheter/{orgnr}/roller
```

Hent med `curl -s` i Bash når shell er tilgjengelig. Hvis nettverket er blokkert, be brukeren åpne `https://virksomhet.brreg.no` og lime inn svaret. Oppgi aldri tall du ikke har hentet.

## Fremgangsmåte

1. Rens input. Fjern mellomrom i org.nr. Et gyldig org.nr har 9 sifre.
2. Valider kontrollsiffer (MOD11, vekter 3,2,7,6,5,4,3,2). Si fra hvis det er ugyldig før du slår opp.
3. Søk på navn hvis brukeren ikke har org.nr. Vis maks 5 treff med navn, org.nr og kommune. La brukeren velge.
4. Hent enheten. Hent roller hvis brukeren spør om daglig leder, styre eller signatur.
5. Presenter svaret kort på norsk.

## Svarformat

Skriv korte setninger. Ta med kun feltene som finnes:

- Navn og org.nr
- Organisasjonsform (AS, ENK, NUF osv.)
- Næringskode med beskrivelse
- Forretningsadresse
- Antall ansatte, hvis oppgitt
- Registrert i MVA-registeret: ja eller nei
- Stiftelsesdato
- Konkurs, under avvikling eller tvangsavvikling: vis tydelig øverst hvis noe av dette er sant

## Risikoflagg før tilbud eller kreditt

Flagg dette tydelig når brukeren vurderer å levere på kreditt:

- `konkurs`, `underAvvikling` eller `underTvangsavviklingEllerTvangsopplosning` er true
- Ikke registrert i MVA-registeret selv om virksomheten fakturerer
- Stiftet for under 6 måneder siden
- Slettet enhet (`slettedato` finnes)

Skriv at flaggene er signaler, ikke en kredittvurdering. Anbefal full kredittsjekk ved store beløp.

## Grenser

- Ikke slå opp privatpersoner. Enhetsregisteret gjelder virksomheter.
- Ikke lagre eller sammenstill personopplysninger om roller utover det brukeren trenger nå.
