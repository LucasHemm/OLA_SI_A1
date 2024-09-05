# Table of Contents
- [Table of Contents](#table-of-contents)
- [OLA Systems integration Assignment 1](#ola-systems-integration-assignment-1)
  - [Youtube link](#youtube-link)
  - [Task 1](#task-1)
    - [Tech stack](#tech-stack)
  - [Task 2 and 3](#task-2-and-3)
    - [What is Enterprise Integration?](#what-is-enterprise-integration)
    - [What diagramming standards are there?](#what-diagramming-standards-are-there)
    - [What does the code for an integration pattern such as ‘pipes and filters’ look like?](#what-does-the-code-for-an-integration-pattern-such-as-pipes-and-filters-look-like)
      - [Pipes and filters:](#pipes-and-filters)
      - [The saga pattern:](#the-saga-pattern)
      - [Message routing:](#message-routing)
  - [Sources](#sources)
---
# OLA Systems integration Assignment 1

## Youtube link
https://www.youtube.com/watch?v=MZvIwepUU_g


## Task 1
### Tech stack
- Git/github - bliver brugt som versionstyrings-program.
- Visual Studio Code - bliver brugt som vores text editor til dette projekt.
- Markdown - bliver brugt som markup language til at skrive rapporten.
- Google chrome - bliver brugt som vores primære web browser til at researche information.

## Task 2 and 3

### What is Enterprise Integration?

Enterprise Integration er betegnelsen for brugen af flere system-integrations metoder samtidigt. Dette kan eksempelvis være diverse api’er, message-brokers osv. En anden stor metode af enterprise integration er application integration som er praksissen som går ud på at integrere forskellige applikationer sammen. Denne praksis gør det muligt at opdele store systemer i subsystemer, eller bruge data andetsteds fra. Dette kan gøre udviklingsprocessen nemmere da man separere funktionalitet sådan at udviklernes fokus kan holde sig til bestemte applikationer, og hver del for sig, kan blive refaktoreret eller videreudviklet uden at skulle bekymre sig om de andre integrationer.

I forbindelse med enterprise integration snakker vi især om 2 populære software arkitekturer. Monolithics og microservices. Monolithics er store selvstændige applikationer samlet i et stort projekt. Dette vil ofte også kunne ses når man kigger på hvordan produktionen af softwaren fungerer, da det ofte vil være et enkelt projekt som bliver kørt.
Microservices er som navnet beskriver en række mindre programmer som tager sig af forskellige services. Ligesom med monolithics kan man også se forskel i produktionsmiljøet for microservices da de frem for et enkelt stort projekt, vil bliver delt op i flere små.

Disse 2 former for arkitekturer kommer med hver deres fordele og ulemper. Eks. kan monolithics være sværere at skalere korrekt, da enkelte dele af systemer bliver brugt mere andre, men da det er en applikation kan man kun skalere den hele på en gang. Hvorimod med microservices kan skalering være nemmere og billigere, da man kun behøver at skalere de mest brugte services.

For disse 2 arkitekturer adskiller de sig i brugen af enterprise integration. Selvom de kan være forskelligt opbygget, i mindre dele eller en stor, har stort set alle applikationer af den ene eller anden grund brug for at kunne integrere andre software for at fungere. Om det er data fra et api eller en database for at kunne persistere data, indgår enterprise integration.
Selvom begge bruger enterprise integration, er det dog klart hyppigt brugt i microservices, af den grund at microservices bliver brugt sammen i en større integration for at kunne levere løsninger som kan give værdi.

Ser man på hvordan enterprise integration bliver set på i industrien, er det for størstedelen af firmaer en meget høj prioritet. En undersøgelse foretaget af TechTarget / ESG [^1] viser at 83% af organisationer har enterprise integration i deres top 5 prioriteter.  
Også de største firmaer i verdenen gør brug af enterprise integration. Eksmepelvis har IBM endda udviklet deres egen AI baseret enterprise integration platform der hedder ‘IBM cloud pak for integration’ [^2]. Denne platform bruger moderne AI løsninger til at gøre af med bl.a. data siloer og samtidig sikre data når det bliver brugt i deres mange services.

[^1]: [https://www.sap.com/documents/2022/02/3c4b3df8-197e-0010-bca6-c68f7e60039b.html](https://www.sap.com/documents/2022/02/3c4b3df8-197e-0010-bca6-c68f7e60039b.html)  
[^2]: [https://www.ibm.com/products/cloud-pak-for-integration](https://www.ibm.com/products/cloud-pak-for-integration)

 ### What diagramming standards are there?
I forhold til enterprise integration, så har udviklingen af diagrammer for visualiseringen af arkitektur, interaktioner mellem systemer mm. altid spillet en stor rolle. Valget af de rigtige diagrammer og modelleringsteknikker er dog meget svingende, alt afhængigt af hvilken sammenhæng diagrammet skal bruges til. 


Et typisk og velkendt eksempel kan være Unified Modelling Language (UML). I en enterprise integration-sammenhæng, så er UML et kraftfuldt værktøj, når man arbejder med komplekse systemdesign, som kræver detaljeret dokumentation. For eksempel kan aktivitetsdiagrammer og sekvensdiagrammer være et godt bud til visualisering af hvordan forskellige systemer interagerer med hinanden eller flow af data mellem applikationer.
Selvom UML kan være et godt værktøj, så er det mindre populært i arbejdssammenhænge, som er mere agilt, da UML kan ende med at føles meget tungt, og kræve en større arbejdsindsats, både i læring og anvendelse.

Enterprise Integration Patterns (EIP), har en mere fokuseret tilgang til enterprise integration, især når det gælder ting som meddelelser og asynkrone begivenheder. I enterprise integration, hvor meddelelser ofte rykkes mellem forskellige datalag og applikationer, er EIP en god løsning. Den store fordel ved EIP er den modulære tilgang, hvor hvert mønster er designet til at kunne genbruges på tværs af projekter og systemer. Dette gør EIP velegnet i store organisationer, som skal integrere mange forskellige systemer gennem beskedhåndteringssystemer, som eksempelvis Spring Integration.

I modsætning til Business Process Model and Notation (BPMN) er en standard, der især bruges til at modellere forretningsprocesser i enterprise integration. BPMN bruges bredt til at beskrive, hvordan forretningsprocesser udføres på tværs af forskellige systemer. I integrationsprojekter, hvor arbejdsgange og dataoverførsel mellem forskellige afdelinger og systemer er centrale, giver BPMN en letforståelig måde at visualisere disse opgaver på.
For eksempel kan BPMN bruges til at designe workflows, der involverer flere forskellige applikationer, hvilket gør det ideelt til automatisering og integration med ERP-systemer eller cloud-tjenester.
En mere moderne tilgang til systemvisualisering er C4-modellen. C4-modellen er designet til at være en enkel og letforståelig måde at visualisere softwarearkitektur på. C4-modellen bryder systemarkitekturen ned i fire niveauer: Kontekst, Container, Komponent og Kode, og den er særligt nyttig til integration i agile miljøer, hvor hurtig kommunikation og enkelhed er vigtige faktorer.
C4-modellen er ideel til at visualisere enterprise integrationer på højere niveauer, hvor det handler om at forstå, hvordan forskellige systemer kommunikerer med hinanden, og hvilke komponenter der er ansvarlige for integrationen. Dette gør modellen attraktiv for moderne integrationsarkitekturer som microservices og cloud-baserede systemer.

 ### What does the code for an integration pattern such as ‘pipes and filters’ look like?
#### Pipes and filters:
Pipes and filters bruges til at dele mere komplicerede behandlinger af data op i mindre uafhængige dele. Koden fungerer således, at hvert filter har en bestemt opgave, hvor den vil modtage noget data fra dens inbound pipe, udføre dens funktionalitet og sende den behandlede data videre i filtreres outbound pipe. Komponenter vil være bygget op på en måde hvorpå man let kan tilføje, fjerne og re-arrangere filtrene i nye sekvenser uden man behøver at ændre på et eksisterende filter. Så kort sagt vil filters lave operationerne på dataen imens pipes fungerer som en kø, der overfører dataen imellem filtre.

#### The saga pattern:
The saga pattern bruges til længerevarende transaktioner, der deler sig op i flere transaktioner. 
Koden fungerer ved at oprette små transaktioner til forskellige databaser, hvor den holder styr på om en eller flere af transaktionerne fejler. Hvis en transaktion fejler, så vil den rulle de andre transaktioner tilbage.

#### Message routing:
Formålet med en message router, i modsætning til pipes and filters, er ikke at håndtere og manipulere data, men derimod at modtage en strøm af beskeder og fordele dem til de relevante destinationer. Koden fungerer ved, at message routeren modtager en besked. Den læser indholdet og bruger en sorteringsalgoritme til at matche indholdet med en destination i et defineret routing table. Derefter sendes beskeden til den bestemte destination, som f.eks. kunne være en kø, der derefter anvender pipes and filters-mønsteret til videre behandling.


## Sources
https://www.ibm.com/think/topics/enterprise-integration
https://www.atlassian.com/microservices/microservices-architecture/microservices-vs-monolith
https://www.enterpriseintegrationpatterns.com/patterns/messaging/PipesAndFilters.html
https://www.sap.com/documents/2022/02/3c4b3df8-197e-0010-bca6-c68f7e60039b.html
https://usemip.com/blog/enterprise-integration-the-key-to-success-in-the-digital-age/
https://www.enterpriseintegrationpatterns.com/patterns/messaging/MessageRouter.html


