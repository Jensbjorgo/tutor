# Tutor – en lærer-skill for Claude

En [Agent Skill](https://agentskills.io) som gjør Claude til en bedre lærer. Skriv for eksempel

```
/tutor kan du hjelpe meg å lære om normalfordeling: standardisering, finne sannsynligheter, kvantiler, lineærkombinasjoner
```

og Claude vil

- **lage en plan** og gå gjennom deltemaene ett for ett, i en rekkefølge der de bygger på hverandre
- **forklare enkelt**: intuisjon og et konkret eksempel først, formelen etterpå, med hvert symbol forklart og typiske feil vist
- **illustrere** der en tegning faktisk hjelper: kurver med skravert areal, fordelinger, strukturer, og **animasjoner** du kan spille av steg for steg når temaet er en algoritme
- **avslutte med en oppsummeringsquiz** som dekker alle deltemaene, med forklaring på hvert svar og resultat per deltema

Skillen er skrevet på norsk og vektlegger matematikk, statistikk og programmering, men fungerer for alle fag. Claude svarer på språket du skriver på, så den fungerer like godt på engelsk.

## Eksempler

| Du skriver | Claude gjør |
|---|---|
| «/tutor normalfordeling: standardisering, sannsynligheter, kvantiler, lineærkombinasjoner» | Gir en leksjon i fire deler med figurer av arealet under kurven, en huskeliste med formlene, og en quiz med minst ett spørsmål per del |
| «/tutor Dijkstras algoritme» | Forklarer ideen, lager en animasjon som viser hvordan avstandene oppdateres steg for steg, og quizzer deg til slutt |
| «Forklar hypergeometrisk fordeling» | Starter med et kortstokk-eksempel, viser fordelingen som stolpediagram, forklarer N, K, n og k hver for seg, og viser forskjellen fra binomisk fordeling |
| «Jeg skjønner ikke derivasjon» | Sjekker nivået ditt, forklarer derivert som stigning og som fart, og spør et kontrollspørsmål før neste trinn |
| «Quiz meg på Poisson-fordeling» | 5 spørsmål av ulike typer (flervalg, regning, finn feilen), ett om gangen, og tilpasser vanskelighetsgraden etter svarene dine |
| «Kan du forklare rekursjon?» | Sporer et lite kodeeksempel trinn for trinn og tegner kall-stakken |
| «/tutor teach me binary search» | Det samme, på engelsk |

Skillen trigges ikke på korte faktaspørsmål («hva er hovedstaden i Peru?») eller vanlige kodeoppgaver («fiks denne buggen»).

## Innhold

```
tutor/
├── SKILL.md                    # Hovedinstruksjoner: pedagogikk og arbeidsflyt
├── references/
│   ├── visuals.md              # Når og hvordan lage illustrasjoner, med eksempler
│   └── quizzing.md             # Spørsmålstyper, distraktorer, tilbakemelding, oppsummering
└── assets/
    ├── quiz-template.html      # Interaktiv quiz med resultat per deltema (norsk/engelsk, lys/mørk modus)
    └── animation-template.html # Steg-for-steg-animasjon av algoritmer (eksempel: boblesortering)
```

## Installasjon

### Claude.ai

Krever et abonnement med Skills og kodekjøring slått på.

1. Last ned **[tutor.zip](https://github.com/Jensbjorgo/tutor/releases/latest/download/tutor.zip)** fra siste release. (Ikke bruk GitHubs grønne «Code → Download ZIP»; den pakker hele repoet og kan ikke lastes opp direkte.)
2. Åpne **Settings** i Claude.ai, finn **Skills** og last opp `tutor.zip`.
3. Slå på skillen. Den brukes automatisk når du ber om forklaringer eller quiz, eller når du starter meldingen med «/tutor». I Claude.ai vises figurer, animasjoner og quiz som interaktive artifacts.

### Claude Code

Kopier `tutor/`-mappen til skill-mappen din:

```bash
git clone https://github.com/Jensbjorgo/tutor.git
# For deg selv, i alle prosjekter:
cp -r tutor/tutor ~/.claude/skills/
# Eller bare for ett prosjekt:
cp -r tutor/tutor .claude/skills/
```

Start Claude Code på nytt. Skriv `/tutor` etterfulgt av det du vil lære, f.eks. `/tutor Bayes' setning`. Skillen brukes også automatisk når du ber om en forklaring uten `/tutor`.

### Malene uten Claude

`tutor/assets/quiz-template.html` og `tutor/assets/animation-template.html` kan åpnes direkte i nettleseren. Claude fyller dem med innhold, men du kan også redigere `QUIZ`- eller `ANIM`-objektet i filene selv.

## In English

A tutoring skill for Claude. Type `/tutor` followed by what you want to learn (e.g. `/tutor normal distribution: standardization, probabilities, quantiles, linear combinations`) and Claude gives a step-by-step lesson with plain-language explanations, visuals (animations for algorithms) and a closing quiz covering every subtopic. The instructions are written in Norwegian, but Claude answers in the language you write in. Install as described above.

## Bidra

Forslag til bedre forklaringer, flere fagspesifikke råd eller nye illustrasjonseksempler tas gjerne imot som issues eller pull requests. Hold `SKILL.md` kort; detaljer hører hjemme i `references/`.

## Lisens

[MIT](LICENSE) © 2026 Jens Bjørgo
