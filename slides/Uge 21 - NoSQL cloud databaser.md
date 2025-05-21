---
theme: default
marp: true
paginate: true
---
# Uge 21 - NoSQL databaser
---
## Agenda
- Teori om NoSQL
- Specifikt om MongoDB og dets software
- Workshop i MongoDB's programmer
- Workshop i MongoSh og MongoDB's C++ interface
---
## Hvad er en NoSQL database?
- NoSQL - *N*ot *O*nly *S*equel
- Relativt ustruktureret ifht. SQL 
- Mere skalerbart
- JSON er dataformatet
---
## Hvorfor bruge NoSQL?
- Det er mere udviklervenligt da dataen er i JSON format
- De fleste programmeringssprog har direkte JSON-kompabilitet, så det er let at integrere i programmer 
- Kan let lave ændringer i strukturen af data 
- Storage er skalerbart - en til disk til serveren som skal bruges til databasen? Nemt.
---
## Sammenligning mellem SQL og NoSQL
- SQL har en striks struktur hvilket tillader bedre performance og præcise queries
- NoSQL har en løs struktur med lavere performance og queries kan være upræcise
- SQL er låst til én server, NoSQL kan let distribuere data og interfaces
---
## Ulemper ved NoSQL
- Ingen SQL
- Ingen standardisering - forskellige NoSQL servere kan have forskellige måder at arbejde på
- Ingen ACID - mere om det på næste slide
---
## MongoDB
- MongoDB er én af mange NoSQL databaser 
- En af de ældre, derfor god dokumentation og stort miljø, kompatibelt med mange sprog
- F.eks. er det let at køre i Docker, og har gode eksempler på hvordan vi kan indsætte og query data 
- Sikkerhed og administration er også tilgængeligt og veldokumenteret
---
## MongoDB miljøet
- Mongosh - mongoshell, altså ren CLI som er backbone til alt MongoDB 
- Mongo-express - administrationsdashboard, ofte bundled i Docker versionen
- MongoDB Compass - GUI til at se data 
 
