# Korte runder

## Innhold
1. Rundens tre meldinger
2. Kartlinje og kobling
3. Krok og gjett
4. Knagger og «Nå kan du»
5. Språk og lengde
6. Tempo-valg
7. Sidespørsmål
8. Gradvis mindre hjelp
9. Forklar det tilbake
10. Avslutning: pek framover
11. Eksempel på en komplett runde

## 1. Rundens tre meldinger

En runde dekker ett deltema, eller én del av et stort deltema. Den består av tre korte meldinger, og hver av dem slutter med noe brukeren skal gjøre:

| Melding | Innhold | Slutter med |
|---|---|---|
| 1. Krok og gjett | kartlinje, kobling, krok, gjett-spørsmål | brukeren gjetter |
| 2. Forklaring | knytt til gjetningen, knagg, forklaring, figur, evt. vanlig feil | 1–2 flervalgsspørsmål |
| 3. Avslutning | tilbakemelding, «Nå kan du» | tempo-valg |

Velger brukeren «Videre», starter neste runde med melding 1. Første melding i en leksjon har i tillegg nivået du antar og kartet over alle deltemaene.

Del et deltema over flere runder heller enn å presse det inn i én. Normalfordeling med «finne sannsynligheter» kan for eksempel bli to runder: P(X ≤ x), og så P(X > x) og P(a < X < b).

## 2. Kartlinje og kobling

Øverst i melding 1 og 2 står en kartlinje, så brukeren alltid ser hvor de er:

```
Del 2 av 4 · Standardisering ✓ → **Sannsynligheter** (her) → Kvantiler → Lineærkombinasjoner
```

Ferdige deler får ✓, nåværende del er uthevet. Blir linjen lang, forkort deltemaene som kommer senere («→ …»).

Rett under kommer én linje som kobler til forrige del: «Forrige gang: vi gjorde om en høyde til en z-verdi.» Bruk det brukeren faktisk gjorde, gjerne med tallene derfra. I første del: koble til noe brukeren kan fra før, eller hopp over linjen.

## 3. Krok og gjett

Kroken er grunnen til å bry seg: et overraskende problem, en hverdagssituasjon eller et «visste du at» der temaet trengs. Ofte er kroken og gjett-spørsmålet det samme.

Et godt gjett-spørsmål:
- kan besvares med magefølelse, uten det brukeren skal lære
- har 2–4 alternativer, der det riktige svaret overrasker litt
- er kort (1–3 setninger pluss alternativene)

Skriv alltid at det er greit å gjette feil, med egne ord: «Bare gjett – det er helt greit å bomme. Poenget er å se om magefølelsen stemmer.»

Start melding 2 med gjetningen:
- **Gjettet feil:** «Du gjettet B (75 %). Svaret er C, ca. 93 %.» Så én setning om hvorfor magefølelsen bommet; det er ofte selve poenget.
- **Gjettet riktig:** «Du gjettet riktig: C.» Så hvorfor, så det ikke bare var flaks.

Ikke regn gjett-svar med i noen poengsum.

### «Jeg kan dette fra før»

Tilby dette valget sammen med gjett-spørsmålet. Har valgverktøyet maks 4 valg (som `AskUserQuestion`), bruk da 3 gjett-alternativer pluss dette. Velger brukeren det:

1. Still ett kontrollspørsmål som krever at man faktisk kan deltemaet (ofte en ett-stegs regning eller «hva er neste steg?», ikke gjenkjenning).
2. **Riktig:** bekreft kort, gi knaggen i én linje så den kommer med i huskelisten, marker deltemaet med ✓ i kartlinjen og gå til neste runde.
3. **Galt:** si det vennlig, og kjør runden som vanlig, med forklaringen knyttet til svaret de ga.

Hopper brukeren over flere deltemaer på rad, er nivået sannsynligvis satt for lavt. Gjør de neste rundene litt mer krevende: kortere intuisjon, mer regning.

## 4. Knagger og «Nå kan du»

Hvert nytt begrep får en **knagg**: én kort setning eller et bilde å henge det på, merket med 🧩.

- 🧩 **z-verdi** = hvor mange standardavvik unna snittet du er.
- 🧩 **Sannsynlighet** = areal under kurven.
- 🧩 **Kvantil** = samme vei som sannsynlighet, bare baklengs: fra areal til verdi.

Knaggen kommer når begrepet først brukes, ikke i en liste til slutt. Gjenta knaggen ordrett i huskelisten etter leksjonen.

Melding 3 slutter med ✅ **Nå kan du:** og 1–2 punkter som begynner med et verb: «finne P(X > x) som 1 − Φ(z)». Skriv det brukeren kan *gjøre*, ikke hva dere «har gått gjennom».

## 5. Språk og lengde

- Melding 1: under ca. 100 ord. Melding 2: ca. 200–250 ord pluss én figur. Melding 3: under ca. 100 ord.
- Korte setninger og korte avsnitt (1–3 setninger), med luft mellom delene.
- Hverdagsordet først, fagordet etterpå: «hvor langt unna snittet du er – det kalles z-verdi».
- Ett nytt fagbegrep per melding. Trenger forklaringen to, del runden.
- Bruk ikonene fra fargekoden (🎯 🧩 📐 ⚠️ ✅) som overskrifter for blokkene, så meldingen kan skumleses. Se [visuals.md](visuals.md#4-farger-og-visuell-struktur).
- Overskrider du lengden, kutt i forklaringen, ikke i det brukeren skal gjøre.
- **Alltid med i melding 2:** kobling til gjetningen, knaggen og flervalgsspørsmålet. Formel, regnet eksempel og vanlig feil kan flyttes til «Ett eksempel til» eller neste runde når meldingen blir full. Det er bedre med en runde til enn en tett melding.

## 6. Tempo-valg

Etter hver runde, tilby:

| Valg | Hva du gjør |
|---|---|
| **Videre** | neste runde (melding 1) |
| **Ett eksempel til** | nytt eksempel på samme nivå, eller ett steg mindre hjelp (se 8) |
| **Tegn det** | en figur eller animasjon av det samme, med 2–3 setninger forklaring |
| **Jeg henger ikke med** | ny vinkel, ikke samme forklaring på nytt (se «Når brukeren står fast» i SKILL.md) |

Bruk valgknapper når miljøet har det (f.eks. `AskUserQuestion` i Claude Code eller klikkbare valg i Claude.ai). Skriv da selve meldingen først og vis knappene til slutt. Ellers: en nummerert liste brukeren kan svare på med ett tall. Brukeren kan alltid skrive noe annet.

Etter siste runde byttes «Videre» ut med «Til quizen».

## 7. Sidespørsmål

Spør brukeren om noe på siden («men hvorfor er kurven symmetrisk?»), er det et godt tegn: de er nysgjerrige.

- **Lite spørsmål:** svar kort, 2–5 setninger, gjerne med en knagg. Gå så tilbake med kartlinjen og gjenta det brukeren skulle gjøre («Tilbake til spørsmålet: hvor stor andel er høyere enn 185 cm?»).
- **Stort spørsmål** (et eget tema): gi én setning nå, og tilby å ta det som en egen runde etter leksjonen. Noter det, og nevn det igjen i avslutningen.
- **Spørsmål som avslører en misforståelse:** ta det på alvor nå. Det er ofte grunnen til at brukeren ville bommet videre. Behandle det som «Jeg henger ikke med».

Svarer brukeren på et flervalg og stiller et sidespørsmål samtidig: gi tilbakemelding på svaret først, så sidespørsmålet.

## 8. Gradvis mindre hjelp

Regneoppgaver trappes ned over rundene eller via «Ett eksempel til»:

1. **Helt løst eksempel.** Vis hvert steg.
2. **Brukeren gjør siste steg.** Gjør alt fram til siste utregning: «z = 1,5. Hva blir P(X > 185)?»
3. **Brukeren gjør nesten alt.** Gi bare oppgaven og stikkord for fremgangsmåten: «Finn P(X < 160). Husk: standardiser først.»

Går et steg galt, gå ett trinn tilbake på trappen i stedet for å vise hele løsningen.

## 9. Forklar det tilbake

Én gang per leksjon, helst ved det mest sentrale deltemaet eller rett før quizen: be brukeren forklare en idé med egne ord i stedet for et flervalgsspørsmål.

> Forklar med egne ord, som til en venn: hvorfor gjør vi om til z før vi slår opp i tabellen? 2–3 setninger holder.

Tilbakemeldingen skal være konkret:
- hva som var riktig, med brukerens egne ord sitert
- hva som manglet eller var upresist, og én setning som retter det
- ingen ny forelesning

## 10. Avslutning: pek framover

Når quizen er ferdig, skal brukeren sitte igjen med lyst til å fortsette, ikke bare en poengsum.

1. **Vis fremgangen:** «For 30 minutter siden visste du ikke hva Φ var. Nå kan du …» med 2–3 punkter fra «Nå kan du»-listene.
2. **Krok til neste tema:** et lite problem de nesten kan løse med det de nettopp lærte, og som peker mot det naturlige neste temaet. «Du kan nå regne på én høyde. Men hva om vi måler snittet av 30 elever – blir det like spredt? Det er sentralgrenseteoremet.» Ikke forklar svaret; det er kroken for neste leksjon.
3. **Ekte oppgave:** tilby å ta en oppgave fra brukerens pensum, øvingssett eller en gammel eksamen, så de ser at det virker på ordentlige oppgaver. Bruk gradvis mindre hjelp (se 8).
4. Nevn eventuelle sidespørsmål som ble satt på vent.
5. Tilby å lagre huskelisten og planlagt repetisjon (se [quizzing.md](quizzing.md#9-repetisjon-over-tid)).

Hold avslutningen like kort som en vanlig runde, og gi valgene som knapper: f.eks. «Neste tema», «Ta en eksamensoppgave», «Lagre huskelisten», «Ferdig for i dag».

## 11. Eksempel på en komplett runde

Leksjon om normalfordeling, del 2. Brukeren har nettopp fullført del 1 (standardisering) og valgt «Videre».

**Melding 1 – Krok og gjett**

> Del 2 av 4 · Standardisering ✓ → **Sannsynligheter** (her) → Kvantiler → Lineærkombinasjoner
>
> Forrige gang: vi gjorde om en høyde til en z-verdi.
>
> 🎯 **Gjett først**
>
> Høyden i en klasse er normalfordelt med snitt 170 cm og standardavvik 10 cm. Hvor stor andel av klassen er lavere enn 185 cm?
>
> A) ca. 50 %  B) ca. 75 %  C) ca. 93 %
>
> Bare gjett – det er helt greit å bomme. Poenget er å se om magefølelsen stemmer.
>
> [A] [B] [C] [Jeg kan dette fra før]

**Melding 2 – Forklaring** (brukeren svarte B)

> Del 2 av 4 · Standardisering ✓ → **Sannsynligheter** (her) → Kvantiler → …
>
> Du gjettet B (75 %). Svaret er C, ca. 93 %. 185 cm høres ikke så ekstremt ut, men det er halvannet standardavvik over snittet. Det er lenger ut enn det føles.
>
> 🧩 **Sannsynlighet = areal under kurven.**
>
> *[Figur: normalkurven med arealet til venstre for 185 skravert og «93 %» skrevet inni. Over x-aksen står 170 og 185, under står z = 0 og z = 1,5.]*
>
> Slik finner vi tallet:
>
> 1. Gjør om til z (det kan du fra forrige del): z = (185 − 170) / 10 = 1,5
> 2. Slå opp Φ(1,5) i tabellen: 0,933
>
> 📐 **P(X ≤ x) = Φ(z), der z = (x − μ) / σ**
> - Φ («fi») = arealet til venstre for z under standardkurven
> - μ = 170 (snittet), σ = 10 (standardavviket)
>
> ⚠️ **Vanlig feil:** å svare med z-verdien (1,5) i stedet for arealet (0,933). z sier *hvor* du er. Φ(z) sier *hvor mye* som ligger til venstre.
>
> **Sjekk deg selv:** Hvor stor andel er *høyere* enn 185 cm?
>
> A) 0,93  B) 0,07  C) 0,50

**Melding 3 – Avslutning** (brukeren svarte A)

> Ikke helt. 0,93 er andelen *lavere* enn 185. Det er fristende, for det er tallet vi nettopp fant. Høyere enn 185 er resten av arealet: 1 − 0,933 = 0,067. Riktig svar er B.
>
> ✅ **Nå kan du:**
> - finne P(X ≤ x) ved å standardisere og slå opp Φ(z)
> - finne P(X > x) som 1 − Φ(z)
>
> Hva vil du nå?
> [Videre: kvantiler] [Ett eksempel til] [Tegn det] [Jeg henger ikke med]

Hadde brukeren svart B, ville melding 3 startet med «Riktig. Kurven har totalareal 1, så det som ikke er til venstre, er til høyre.»
