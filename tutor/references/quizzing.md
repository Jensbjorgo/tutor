# Retningslinjer for quiz

## Innhold
1. Når og hvordan starte
2. Format og verktøy
3. Spørsmålstyper
4. Gode feilalternativer
5. Tilbakemelding
6. Tilpass vanskelighetsgraden
7. Oppsummering

## 1. Når og hvordan starte

- Tilby en quiz etter en forklaring: «Vil du teste deg selv med 5 korte spørsmål?» Ikke start uten at brukeren sier ja.
- Ber brukeren om en quiz, start direkte. Mangler tema eller nivå, still ett spørsmål om det, ellers anta ut fra samtalen.
- Standard er **5 spørsmål**. Brukeren kan be om flere eller færre.
- Si kort hva quizen dekker før første spørsmål («5 spørsmål om Poisson-fordeling, fra lett til litt vanskeligere»).

## 2. Format og verktøy

**Ett spørsmål om gangen.** Still spørsmålet, vent på svar, gi tilbakemelding, og still så neste. Ikke vis alle spørsmålene samtidig og ikke avslør fasiten før brukeren har svart. Vis fremdrift: «Spørsmål 2 av 5».

Velg format i denne rekkefølgen:

1. **Innebygd verktøy for spørsmål/valg**, hvis miljøet har det (f.eks. `AskUserQuestion` i Claude Code eller valgknapper i Claude.ai). Passer godt for flervalg. Åpne spørsmål stilles i vanlig chat.
2. **Chat.** Fungerer overalt. Nummerer flervalgsalternativer A–D, så brukeren kan svare med én bokstav.
3. **HTML-malen** i `assets/quiz-template.html`, når brukeren vil øve på egen hånd, ha en quiz å ta med seg eller dele, eller ber om en interaktiv quiz. Kopier malen, fyll inn `QUIZ`-objektet øverst i skriptet, og lagre filen (eller vis den som artifact der det finnes). Malen støtter flervalg og tallsvar; åpne «forklar med egne ord»-spørsmål passer bedre i chat.

## 3. Spørsmålstyper

Bland typene. En quiz på 5 spørsmål bør ha minst tre ulike typer.

| Type | Hva den tester | Eksempel |
|---|---|---|
| Flervalg | gjenkjenning, skille mellom begreper | «Hvilken situasjon passer best for Poisson-fordeling?» |
| Regneoppgave | å bruke formelen riktig | «λ = 3 kunder per time. Hva er P(X = 0)?» |
| Forklar med egne ord | dyp forståelse | «Forklar hvorfor variansen til en Poisson-fordeling er lik λ, uten formel.» |
| Finn feilen | gjenkjenne misforståelser | «Ola regnet P(X ≤ 2) = P(X = 2). Hva er feil?» |
| Hva skjer hvis… | intuisjon og sammenhenger | «Hva skjer med fordelingen hvis λ dobles?» |

For programmering passer også: «Hva skriver denne koden ut?», «Hva er tidskompleksiteten?», og «Hvilken linje har feilen?».

Hold hvert spørsmål kort og entydig. Gi alle tall som trengs. For regneoppgaver: si hvor mange desimaler du forventer, og godta avrundingsforskjeller.

## 4. Gode feilalternativer

Feilalternativer (distraktorer) skal være svar en person med en *bestemt misforståelse* ville valgt. Da avslører valget hva brukeren har misforstått.

Eksempel: «I en pose er det 5 røde og 3 blå kuler. Du trekker 2 uten tilbakelegging. Hva er P(begge røde)?»

- A) 5/14 ✓ (5/8 · 4/7)
- B) 25/64 – regnet med tilbakelegging (5/8 · 5/8)
- C) 5/8 – glemte andre trekk
- D) 10/56 – uordnede utfall i telleren (C(5,2) = 10), men ordnede i nevneren (8 · 7 = 56)

Unngå alternativer som er åpenbart tullete, «alle de ovenfor», og at riktig svar alltid er det lengste. Varier posisjonen til riktig svar.

## 5. Tilbakemelding

Gi forklarende tilbakemelding på **alle** svar, ikke bare de gale:

- **Riktig:** bekreft kort, og si *hvorfor* det er riktig, gjerne med en ekstra innsikt. Et riktig svar kan være en gjetning; forklaringen sikrer at det sitter.
- **Galt:** si vennlig at det ikke stemmer, pek på den sannsynlige misforståelsen («Det ser ut som du regnet med tilbakelegging …»), vis riktig fremgangsmåte, og gå videre. Ikke gjør det til en lang forelesning.
- **Delvis riktig** (vanlig på «forklar med egne ord»): si hva som var bra, og hva som mangler.
- **«Vet ikke»:** gi et hint og la brukeren prøve én gang til før du viser svaret.

## 6. Tilpass vanskelighetsgraden

- Start på middels nivå for det brukeren har lært.
- To riktige på rad: gjør neste spørsmål litt vanskeligere (flere steg, mindre hjelp, mer anvendelse).
- Feil svar: gjør neste spørsmål litt enklere eller sjekk det samme begrepet fra en annen vinkel.
- Gjentatte feil på samme begrep: stopp quizen kort, tilby en ny forklaring av akkurat det, og fortsett etterpå.

## 7. Oppsummering

Avslutt med en kort oppsummering:

```
Resultat: 4 av 5

Det sitter:
- Å kjenne igjen når Poisson passer (spm. 1, 3)
- Å regne P(X = k) (spm. 2)

Bør repeteres:
- P(X ≤ k) er en sum, ikke ett ledd (spm. 4)

Forslag: [ett konkret neste steg, f.eks. «Prøv 3 oppgaver der du må regne kumulativ sannsynlighet»]
```

Tilby til slutt en ny runde med fokus på det som bør repeteres.
