---
name: tilbud-handverk
description: Skriver ferdige, profesjonelle tilbud på norsk for håndverkere og små bedrifter, med korrekt MVA-oppstilling, forbehold og akseptfrist. Brukes når brukeren sier "lag et tilbud", "skriv pristilbud", "tilbud på jobben", "kostnadsoverslag", "fastpris til kunden", "tilbud til borettslaget", eller beskriver en jobb og vil ha pris satt opp.
---

# Tilbud for håndverk og tjenester

Lag et tilbud kunden kan si ja til med én gang. Tydelig omfang, tydelig pris, tydelige forbehold.

## Innhent først

Spør bare om det som mangler. Maks 4 spørsmål i én runde:

1. Hvem er kunden? Forbruker eller bedrift. Dette styrer lovverk og om pris vises inkl. MVA.
2. Hva skal gjøres? Omfang, sted, materialer.
3. Pris: fastpris, timepris med overslag, eller begge.
4. Når kan jobben starte, og hvor lenge gjelder tilbudet?

Hvis kunden er en bedrift og org.nr er kjent, bruk skillet `brreg-oppslag` for å fylle inn korrekt navn og adresse.

## Regler for pris

- MVA-sats for vanlige tjenester og varer er 25 %. Regn ut, ikke anslå.
- Forbruker: vis totalpris **inkludert MVA** som hovedtall. Vis MVA-beløpet separat.
- Bedrift: vis pris eks. MVA, MVA og total.
- Timepris med overslag: skriv tydelig at det er et overslag. Se `references/lovverk.md` om hva et overslag binder.
- Regn med kode når det er mer enn 3 linjer. Summer skal alltid stemme.

## Struktur

1. Topp: avsender, org.nr, dato, tilbudsnummer, kunde.
2. Én setning om hva kunden får.
3. Omfang: punktliste over hva som er med.
4. Ikke inkludert: punktliste. Dette forhindrer konflikt senere.
5. Pris: tabell med linjer, sum eks. MVA, MVA, total.
6. Fremdrift: oppstart og varighet.
7. Forbehold: skjulte feil, endringer, tilgang. Korte punkter.
8. Betaling: frist og eventuelle a konto-avdrag, altså delbetalinger underveis i jobben.
9. Aksept: frist og hvordan kunden aksepterer ("svar ja på e-post" holder).

## Skrivestil

- Korte setninger. Ingen salgsfloskler.
- Ikke overdriv. Norske kunder reagerer negativt på skryt.
- Ingen påstander om kvalitet eller erfaring som brukeren ikke har oppgitt.

## Leveranse

Lever som Word-dokument eller PDF hvis brukeren ber om fil. Ellers som ferdig tekst klar til å lime inn i e-post. Tilbudet sendes aldri til kunden uten at brukeren har godkjent det.

Se `references/lovverk.md` for forbruker- og bedriftsregler.
