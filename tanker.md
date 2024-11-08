# Mine tanker om HTTP metodene

##--HttpGet--
Get er en metode som sender en forespørsel om data fra en ressurs(gjerne en API).
Spørsmålet om data sendes som en tekststreng (bestående av navn/verdi par) i form av en URL adresse i Get forespørsler. Hvilken data du får kan spesifiseres noe lunde ut i fra hva du ber om i URL adressen, men det kommer ann på hvordan endepunktene er satt opp.
Get forespørsler brukes bare for å spørre om data og du vil ikke kunne modifisere den, men med hjelp av klasser kan du endre hvilken data du vil vise og hvordan den vises.
OBS! Get forespørsler har en lengde restriksjon, og bør aldri brukes til sensitiv data.

##--HttpPost--
Post er en metode som sender en forespørsel til serveren om å ta imot dataen vi har lagt inn i feltet vi kaller body, og lage en ny underordnet ressurs i en samling av ressurser (f.eks. en ny film i en liste av filmer, eller en ny post på bloggsiden din). Serveren vil ofte ha et krav om hva forespørselen må inneholde, og vil gi en feil melding dersom noe mangler eller en melding om at forespørselen ble akseptert om du oppfyller kravene.
I motsetning til Get har Post ingen lengde restriksjoner, og det som blir skrevet i body vil ikke vises i URL adressen.

##--HttpPut--
Put er en motde som sender en forespørsel til serveren om å modifesere en ressurs, og vi bruker en nøkkel (gjerne ID) for å spesifisere hvilken ressurs vi vil endre på. Hvilken ressurs vi vil endre på sendes i from av en URL adresse (samme som i Get, men må også inkludere nøkkelen i URL adressen), og hva vi vil endre på spesifiserer vi i body ved hjelp av feltets navn og endringen vi vil gjøre.
Hvis ressursen ikke finnes vil serveren lage den, du vil få en melding om du oppdaterte en ressurs(200(OK)) eller lagde en ny en(201 (Created)).

##--HttpDelete--
Delete er en metode som sender en forespørsel til serveren om å slette en ressurs, og vil som i Put bruke en nøkkel i URL feltet for å finne ressursen som skal slettes. Ut i fra hvordan serveren er satt opp vil du få en melding med 200(OK) hvis serveren har slettet ressursen, 202(Accepted) hvis den har mottat forespørselen men ikke godtatt den enda, eller 204(No Content) hvis ressursen er slettet men ikke gir deg noen detaljer.

(kanskje til senere, om jeg får tid)

--HttpPatch--

--HttpHead--

--HttpTrace--

--HttpOptions--

--HttpConnect--

# Tanker om Server-Client forholdet

Når vi snakker om Client så mener vi stort sett brukere (enten det er en person eller en organisasjon) av en tjeneste, men i dataverden referer Client til datamaskiner, og datamaskiner er verten som er i stand til og ta i mot og bruke informasjon og tjenester fra tjenesteleverandøren(i.e. en Server).
I forholdet mellom partene kan vi bruke en analogi med en restaurant. I denne analogien så vil brukeren være kunden, som sender en bestilling(forespørsel) til kjøkkenet gjennom servitøren(datamaskinen) i henhold til en meny(en samling av funksjoner/metoder med spesifike utfall). Når servitøren leverer bestillingen(forespørselen med funksjon/metode) til kjøkkenet(serveren) sjekke om de kan gjennomføre orderen(det som blir bedt om) og sende retten(svaret, eller en feilmelding) tilbake til kunden(brukeren) gjennom servitøren(datamaskinen).
