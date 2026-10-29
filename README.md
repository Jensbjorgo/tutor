# Tutor – en lærer-skill for Claude

En [Agent Skill](https://agentskills.io) som gjør Claude til en bedre lærer. Når du ber om å få noe forklart, sier at du ikke skjønner noe eller vil øve til eksamen, vil Claude

- **forklare enkelt**: intuisjon og et konkret eksempel først, formelen etterpå, med hvert symbol forklart
- **illustrere** der en tegning faktisk hjelper: fordelinger, prosesser, strukturer, geometri
- **quizze deg** med ett spørsmål om gangen, forklarende tilbakemelding og en oppsummering av hva som sitter og hva du bør repetere

Skillen er skrevet på norsk og vektlegger matematikk, statistikk og programmering, men fungerer for alle fag. Claude svarer på språket du skriver på.

## Eksempler

| Du skriver | Claude gjør |
|---|---|
| «Forklar hypergeometrisk fordeling» | Starter med et kortstokk-eksempel, viser fordelingen som stolpediagram, forklarer N, K, n og k hver for seg, og viser forskjellen fra binomisk fordeling |
| «Jeg skjønner ikke derivasjon» | Sjekker nivået ditt, forklarer derivert som stigning og som fart, og spør et kontrollspørsmål før neste trinn |
| «Quiz meg på Poisson-fordeling» | 5 spørsmål av ulike typer (flervalg, regning, finn feilen), ett om gangen, og tilpasser vanskelighetsgraden etter svarene dine |
| «Kan du forklare rekursjon?» | Sporer et lite kodeeksempel trinn for trinn og tegner kall-stakken |

Skillen trigges ikke på korte faktaspørsmål («hva er hovedstaden i Peru?») eller vanlige kodeoppgaver («fiks denne buggen»).

## Innhold

```
tutor/
├── SKILL.md                    # Hovedinstruksjoner: pedagogikk og arbeidsflyt
├── references/
│   ├── visuals.md              # Når og hvordan lage illustrasjoner, med eksempler
│   └── quizzing.md             # Spørsmålstyper, distraktorer, tilbakemelding, oppsummering
└── assets/
    └── quiz-template.html      # Selvstendig interaktiv quiz (lys/mørk modus)
```

## Installasjon

### Claude.ai

Krever et abonnement med Skills og kodekjøring slått på.

1. Last ned dette repoet og lag en zip-fil av `tutor/`-mappen (mappen som inneholder `SKILL.md`):
   ```bash
   git clone https://github.com/<brukernavn>/<repo>.git
   cd <repo>
   zip -r tutor.zip tutor
   ```
2. Gå til **Settings → Features** (Skills) i Claude.ai og last opp `tutor.zip`.
3. Slå på skillen. Den brukes automatisk når du ber om forklaringer eller quiz.

### Claude Code

Kopier `tutor/`-mappen til skill-mappen din:

```bash
git clone https://github.com/<brukernavn>/<repo>.git
# For deg selv, i alle prosjekter:
cp -r <repo>/tutor ~/.claude/skills/
# Eller bare for ett prosjekt:
cp -r <repo>/tutor .claude/skills/
```

Start Claude Code på nytt. Skriv f.eks. «forklar Bayes' setning» for å teste.

### Interaktiv quiz uten Claude

`tutor/assets/quiz-template.html` kan åpnes direkte i nettleseren. Claude fyller den med spørsmål når du ber om en quiz du kan ta med deg, men du kan også redigere `QUIZ`-objektet i filen selv.

## Bidra

Forslag til bedre forklaringer, flere fagspesifikke råd eller nye illustrasjonseksempler tas gjerne imot som issues eller pull requests. Hold `SKILL.md` kort; detaljer hører hjemme i `references/`.

## Lisens

[MIT](LICENSE) © 2026 Jens Bjørgo
