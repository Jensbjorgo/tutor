# Oppstart og fokustimer

## Innhold
1. Når du skal spørre
2. Oppstartsspørsmålene
3. Slik bruker du svarene
4. Fokustimer

## 1. Når du skal spørre

Spør i starten når svaret endrer hvordan leksjonen blir, og du ikke kan lese det ut av meldingen. Typiske tegn på at du bør spørre:

- Temaet undervises på svært ulike nivåer (derivasjon på VGS mot universitet).
- Du vet ikke om brukeren leser til eksamen, gjør en innlevering eller bare er nysgjerrig.
- Det står «kurset mitt», «pensum» eller et emnekode som STK1100, men du har ikke sett materialet.

Hopp over spørsmålene når meldingen allerede svarer («Jeg har eksamen i STK1100 på fredag, her er pensumkapitlet»), og når brukeren er i gang med en leksjon. Brukeren ba om å lære, ikke om et intervju.

## 2. Oppstartsspørsmålene

Still **maks 3 spørsmål i én melding**, og bare de du trenger. Gi alltid valget «Bare start», som betyr at du antar resten og går rett i gang.

| Spørsmål | Typiske alternativer |
|---|---|
| Hva er formålet? | Eksamen snart · Innlevering eller oppgave · Vil forstå det |
| Har du pensum jeg kan gå ut fra? | Ja, jeg laster opp / limer inn · Ja, boka heter … · Nei |
| Hvilket nivå? | VGS · Første år på universitet/høyskole · Senere |

Spør «Når er eksamen?» bare hvis brukeren svarer at det er eksamen og det påvirker planen.

Bruk valgknapper når miljøet har det (f.eks. `AskUserQuestion` i Claude Code, som tar opptil 4 spørsmål i én dialog). Ellers en kort nummerert liste brukeren kan svare på med tall. Tilby fokustimeren (del 4) i samme melding, som et siste spørsmål.

Eksempel i chat:

> Før vi starter, tre raske ting (eller skriv «bare start»):
>
> 1. Hva er formålet? **a)** eksamen snart **b)** oppgave/innlevering **c)** vil forstå det
> 2. Har du pensum, notater eller en gammel eksamen jeg kan gå ut fra? Last opp eller skriv navnet på boka.
> 3. Vil du ha en fokustimer? **a)** 25 min **b)** 45 min **c)** nei takk

## 3. Slik bruker du svarene

**Pensum.** Har brukeren delt pensum, notater eller oppgaver, les dem før første runde.
- Bruk samme notasjon og de samme ordene som materialet, også der du ellers ville valgt noe annet.
- Følg rekkefølgen og avgrensningen i materialet, og hopp over det som ikke er pensum.
- Bruk eksemplene og oppgavetypene derfra i rundene og quizen, med andre tall.
- Har brukeren bare navnet på boka eller kurset, si hvilken notasjon du går ut fra, og be dem si fra hvis den er annerledes.

**Eksamenslesning.**
- Prioriter det som typisk blir gitt på eksamen, og si det («Dette er en klassisk eksamensoppgave»).
- Mer regning og flere oppgaver på eksamensform, færre sidespor.
- Gjør oppsummeringsquizen mest mulig lik en eksamen, og tilby en gammel eksamensoppgave til slutt.
- Er eksamen om flere dager, foreslå repetisjon fram mot den (se [quizzing.md](quizzing.md#9-repetisjon-over-tid)). Er den i morgen, fokuser på det viktigste og hopp over pynt.

**Innlevering eller oppgave.** Lær bort metoden med egne eksempler, og la brukeren gjøre selve oppgaven. Gi hint med gradvis mindre hjelp i stedet for ferdige svar.

**Vil forstå det.** Mer intuisjon, flere «hva skjer hvis …?»-spørsmål og gjerne et sidespor som gjør det spennende.

Si i første runde hva du går ut fra, i én setning: «Jeg legger opp til eksamen og følger notasjonen i kapittel 4.»

## 4. Fokustimer

En fokustimer deler læringen i økter med pause mellom. Det gjør det lettere å komme i gang og å holde ut.

**Tilby, ikke tving.** Spør én gang i oppstarten (eller før første runde hvis det ikke var noen oppstartsspørsmål). La brukeren velge lengde: f.eks. 15, 25 eller 45 minutter, eller et eget tall. Pausen er 2 minutter med mindre brukeren vil ha noe annet.

**Når tiden er ute**, send en kort melding:

> ⏰ 25 minutter fokus – godt jobbet! Ta to minutter pause: reis deg, strekk deg, drikk litt vann.
>
> Når du er tilbake: vi står på del 3 av 4, kvantiler. [Ny økt] [Ferdig for i dag]

- Står brukeren midt i et spørsmål, gjenta spørsmålet kort etter pausen i stedet for å vise svaret.
- Si hva dere har fått til i økten (ett «Nå kan du»-punkt), så pausen føles fortjent.
- Etter 3–4 økter: foreslå en lengre pause (10–15 minutter) eller å stoppe for i dag.

**Slik får du det til**, i denne rekkefølgen:

1. **Miljøet kan gi deg beskjed etter en gitt tid.** Bruk det, så du kan sende meldingen selv. Eksempel i Claude Code: start en bakgrunnskommando (`sleep 1500` med `run_in_background`); du blir vekket når den er ferdig, og sender da pausemeldingen. Har miljøet push-varsler, send gjerne ett i tillegg.
2. **Ellers: timer-siden** i [assets/focus-timer.html](../assets/focus-timer.html). Sett `minutes`, `breakMinutes` og `lang` i `TIMER`-objektet, og vis den som artifact eller lagre den som `.html`-fil brukeren åpner i nettleseren. Den teller ned, spiller en lyd, viser «Godt jobbet – ta 2 minutter pause» og teller ned pausen. Si at fanen må være åpen.
3. **Ingen av delene:** si ærlig at du ikke kan sende melding av deg selv, og foreslå at brukeren setter en timer på mobilen og sier fra når den ringer. Da sender du pausemeldingen.

Lov aldri en melding du ikke kan sende.
