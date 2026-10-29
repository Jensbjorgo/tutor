# Retningslinjer for quiz

## Innhold
1. Når og hvordan starte
2. Korte spørsmål underveis
3. Format og verktøy
4. Spørsmålstyper
5. Gode feilalternativer
6. Tilbakemelding
7. Tilpass vanskelighetsgraden
8. Oppsummering
9. Repetisjon over tid

## 1. Når og hvordan starte

- **Etter en leksjon** (se Leksjonsmodus i SKILL.md): når brukeren velger «Til quizen» etter siste runde, start oppsummeringsquizen. Se under.
- **Etter en forklaring i samtale**: tilby en quiz («Vil du teste deg selv med 5 korte spørsmål?»). Ikke start uten at brukeren sier ja.
- Ber brukeren om en quiz, start direkte. Mangler tema eller nivå, still ett spørsmål om det, ellers anta ut fra samtalen.
- Standard er **5 spørsmål**. Brukeren kan be om flere eller færre.
- Si kort hva quizen dekker før første spørsmål («5 spørsmål om Poisson-fordeling, fra lett til litt vanskeligere»), og at det er lov å hoppe over («Skriv «hopp over» hvis du ikke orker eller står fast»).

### Oppsummeringsquiz etter en leksjon

- Minst ett spørsmål per deltema, og minst ett spørsmål som kombinerer deltemaer (f.eks. «Finn P(X + Y > 100)», som krever både lineærkombinasjon og standardisering). Typisk 6–8 spørsmål totalt.
- Gå fra lett til vanskelig og følg rekkefølgen i leksjonen.
- Gjenbruk ikke spørsmålene fra rundene, men test gjerne de samme misforståelsene på nytt, særlig der brukeren svarte feil underveis.
- Bruk andre tall og situasjoner enn i forklaringen, så brukeren må bruke metoden og ikke bare huske svaret.
- Gi hvert spørsmål `topic` lik navnet på deltemaet, så oppsummeringen viser hvilke deltemaer som sitter.
- Regn ut alle fasitsvar med kode før du viser quizen, når du har kodekjøring.

## 2. Korte spørsmål underveis

I leksjonsmodus har hver runde 1–2 korte flervalgsspørsmål (se [runder.md](runder.md)). De skal sjekke én ting, ikke gi karakter.

- **Ett begrep per spørsmål**, det som nettopp ble forklart.
- **Kort:** spørsmålet under ca. 25 ord, 2–4 alternativer på én linje hver.
- **Hvert galt alternativ er en vanlig feil** (se del 5). Med bare 2–3 alternativer: velg de feilene som er mest fristende akkurat her.
- **Ingen regning som tar mer enn ett steg.** Lengre regning hører hjemme i «Ett eksempel til» med gradvis mindre hjelp.
- **Gode typer:** «hvilket tall er riktig?», «hva skjer hvis …?», «hvilken figur viser …?», «hva er neste steg?».
- **Ikke tell poeng** underveis, men husk hvilke begreper brukeren bommet på, og bruk dem i oppsummeringsquizen og repetisjonen.

**Tilbakemelding** (1–3 setninger):
- **Riktig:** bekreft og si kort hvorfor, så det ikke bare var flaks.
- **Galt:** si hva det valgte alternativet faktisk er, og hvorfor det er fristende («0,93 er det vi nettopp regnet ut, men det er arealet til *venstre*»). Gi så riktig svar.
- To feil på rad om samme begrep: ikke still et tredje spørsmål. Tilby en ny vinkel, som ved «Jeg henger ikke med».

**Gjett-spørsmål** i starten av en runde følger de samme formreglene, men skal kunne besvares med magefølelse og vurderes aldri som riktig eller galt for brukeren. Svaret brukes til å knytte forklaringen til gjetningen.

Bruk klikkbare valg når miljøet har det (`AskUserQuestion` i Claude Code, valgknapper i Claude.ai). Legg ikke hint i beskrivelsen av alternativene. Ellers: A–D i chat.

## 3. Format og verktøy

**Ett spørsmål om gangen.** Still spørsmålet, vent på svar, gi tilbakemelding, og still så neste. Ikke vis alle spørsmålene samtidig og ikke avslør fasiten før brukeren har svart. Vis fremdrift: «Spørsmål 2 av 5».

**Alltid lov å hoppe over.** Hvert spørsmål skal kunne hoppes over, både i quizen og i de korte spørsmålene underveis. Med valgknapper: ha «Hopp over» som eget valg (med maks 4 valg, bruk da 3 svaralternativer). I chat: si i starten at brukeren kan skrive «hopp over». Hopper brukeren over:
- ikke mas, og ikke tilby hint; brukeren har sagt at de ikke orker akkurat nå
- vis riktig svar med en kort forklaring (1–2 setninger), og gå videre
- tell spørsmålet som ikke riktig, men vis det for seg i resultatet («3 av 5 riktige · 1 hoppet over»)
- ta med deltemaet under «Bør repeteres» og i repetisjonen senere

Hopper brukeren over flere spørsmål på rad, spør kort om de vil avslutte quizen og heller ta den senere, eller få en kort repetisjon av deltemaet først.

Velg format i denne rekkefølgen:

1. **Innebygd verktøy for spørsmål/valg**, hvis miljøet har det (f.eks. `AskUserQuestion` i Claude Code eller valgknapper i Claude.ai). Passer godt for flervalg. Åpne spørsmål stilles i vanlig chat.
2. **Chat.** Fungerer overalt. Nummerer flervalgsalternativer A–D, så brukeren kan svare med én bokstav.
3. **HTML-malen** i `assets/quiz-template.html`, når brukeren vil øve på egen hånd, ha en quiz å ta med seg eller dele, eller ber om en interaktiv quiz. Kopier malen, fyll inn `QUIZ`-objektet øverst i skriptet (med `lang: "en"` for engelsk), og lagre filen (eller vis den som artifact der det finnes). Malen støtter flervalg og tallsvar; åpne «forklar med egne ord»-spørsmål passer bedre i chat.

For oppsummeringsquizen etter en leksjon: der miljøet viser artifacts (som Claude.ai), bruk HTML-malen som artifact, så brukeren får en interaktiv quiz med resultat per deltema. Ellers (f.eks. i en terminal) still spørsmålene ett om gangen med punkt 1 eller 2, og tilby HTML-filen til slutt for videre øving.

## 4. Spørsmålstyper

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

## 5. Gode feilalternativer

Feilalternativer (distraktorer) skal være svar en person med en *bestemt misforståelse* ville valgt. Da avslører valget hva brukeren har misforstått.

Eksempel: «I en pose er det 5 røde og 3 blå kuler. Du trekker 2 uten tilbakelegging. Hva er P(begge røde)?»

- A) 5/14 ✓ (5/8 · 4/7)
- B) 25/64 – regnet med tilbakelegging (5/8 · 5/8)
- C) 5/8 – glemte andre trekk
- D) 10/56 – uordnede utfall i telleren (C(5,2) = 10), men ordnede i nevneren (8 · 7 = 56)

Unngå alternativer som er åpenbart tullete, «alle de ovenfor», og at riktig svar alltid er det lengste. Varier posisjonen til riktig svar.

## 6. Tilbakemelding

Gi forklarende tilbakemelding på **alle** svar, ikke bare de gale:

- **Riktig:** bekreft kort, og si *hvorfor* det er riktig, gjerne med en ekstra innsikt. Et riktig svar kan være en gjetning; forklaringen sikrer at det sitter.
- **Galt:** si vennlig at det ikke stemmer, pek på den sannsynlige misforståelsen («Det ser ut som du regnet med tilbakelegging …»), vis riktig fremgangsmåte, og gå videre. Ikke gjør det til en lang forelesning.
- **Delvis riktig** (vanlig på «forklar med egne ord»): si hva som var bra, og hva som mangler.
- **«Vet ikke»:** gi et hint og la brukeren prøve én gang til før du viser svaret. (Skriver brukeren «hopp over», er det noe annet: vis svaret direkte, se del 3.)

## 7. Tilpass vanskelighetsgraden

- Start på middels nivå for det brukeren har lært.
- To riktige på rad: gjør neste spørsmål litt vanskeligere (flere steg, mindre hjelp, mer anvendelse).
- Feil svar: gjør neste spørsmål litt enklere eller sjekk det samme begrepet fra en annen vinkel.
- Gjentatte feil på samme begrep: stopp quizen kort, tilby en ny forklaring av akkurat det, og fortsett etterpå.

## 8. Oppsummering

Avslutt med en kort oppsummering:

```
Resultat: 3 av 5 riktige · 1 hoppet over

Det sitter:
- Å kjenne igjen når Poisson passer (spm. 1, 3)
- Å regne P(X = k) (spm. 2)

Bør repeteres:
- P(X ≤ k) er en sum, ikke ett ledd (spm. 4)
- Når Poisson ikke passer (spm. 5, hoppet over)

Forslag: [ett konkret neste steg, f.eks. «Prøv 3 oppgaver der du må regne kumulativ sannsynlighet»]
```

Tilby til slutt en ny runde med fokus på det som bør repeteres.

## 9. Repetisjon over tid

Det man henter fram igjen etter noen dager, sitter mye bedre enn det man leser to ganger.

**Lagre huskelisten.** Etter oppsummeringsquizen: tilby å lagre huskelisten som et dokument. Bruk miljøets dokumentverktøy hvis det finnes, ellers en `.md`-fil. Dokumentet inneholder:
- kartet over deltemaene
- knaggene, ordrett som i leksjonen
- formlene med symbolene forklart, og fremgangsmåten
- de vanligste fellene, særlig de brukeren gikk i
- 3–5 repetisjonsspørsmål, med fasit samlet nederst

**Når brukeren kommer tilbake til temaet.** Ser du i samtalen, minnet eller den lagrede huskelisten at brukeren har jobbet med temaet før, start med 2–3 raske repetisjonsspørsmål før noe nytt:
- ett spørsmål per deltema, med det brukeren bommet på sist først
- korte flervalg eller ett-stegs regning, med andre tall enn sist
- kort tilbakemelding, så videre. Bommer brukeren på et deltema, tilby en kort runde på det før dere går videre

**Planlagt repetisjon.** Har miljøet planlagte oppgaver (f.eks. `/schedule` i Claude Code eller planlagte oppgaver i Claude.ai), tilby én gang etter leksjonen: «Vil du at jeg sender deg 3 repetisjonsspørsmål om to dager?» Sett det bare opp hvis brukeren sier ja. Oppgaven skal stille spørsmålene ett om gangen, gi tilbakemelding, og avslutte med hva som sitter og hva som bør repeteres.
