## Shop database

Vi prøver at binde shell scripts, databaser og C++ sammen for at løse en opgave for en butik. Samme teknikker, men vi får det øvet igennem 1 gang til og med mere fokus på databasedesign.

### Opgavebeskrivelse

**Opgave 1 - Design**

I skal vælge en butik, lad os sige jeres favorit webshop. Til denne skal i prøve at oprette en database til et udvalg af deres varer og kunder.

Krav er som følger:

Tabellen skal indeholde de tabelnavne som er i eksemplet nedenfor.

Resten der skal tilføjes/ændres er som minimum:

* I skal integrere produktgrupper/varekategorier. F.eks. hvis det nu er Proshop, så SSD, CPU, GPU osv. Hav 5 forskellige varegrupper med relevante navne.
* I skal have flere produkter der falder i hver kategori.
* Det skal være synligt hvem der har købt hvilke produkter og hvor mange.
* Brugere skal være enten business eller privat.
* Udvid purchased table så det er tydeligt hvilke produkter hver kunde har købt.
* I skal bestemme hvilke af de eksisterende felter der er relevante for jeres webshop og fjerne dem der er irrelevante
* I skal tilføje relevante relationer (one-to-many, many-to-one etc.)

Ekstra challenges:

* Hvert produkt skal have hver sit unikke produkt ID.
* Hver bruger skal kunne give en rating per produkt

**Opgave 2 - SQL**

Når i har design på plads, indsæt nogle produkter samt kunder der har købt visse produkter via shell script.

### DB diagram

Til at designe jeres database og generere SQL kode til at lave tabeller, anbefaler jeg at bruge [https://dbdiagram.io/home](https://dbdiagram.io/home). Kan bruges uden login til at designe et databasediagram, men med et GitHub login kan i eksportere SQL koden der kan bruges til at oprette tabellerne.

<iframe width="560" height="315" src='https://dbdiagram.io/e/67b46e1f263d6cf9a08fb114/67b4714b263d6cf9a09020c2'> </iframe>

### DB diagram kode til eksemplet

```dbml
Table purchased {
  product_id integer 
  created_at timestamp 
}

Table users {
  id integer [primary key]
  username varchar
  role varchar
  created_at timestamp
}

Table products {
  product_id integer [primary key]
  title varchar
  body text [note: 'product description']
  user_id integer
  status varchar
  created_at timestamp
}

Ref: users.id < purchased.product_id

Ref: purchased.product_id - products.product_id
```

Hint: Brug deres dokumentation til relationships [https://dbml.dbdiagram.io/docs/#relationships--foreign-key-definitions](https://dbml.dbdiagram.io/docs/#relationships--foreign-key-definitions).

