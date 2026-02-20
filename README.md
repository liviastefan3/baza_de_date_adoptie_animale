# baza_de_date_adoptie_animale
Sistem Adopție Animale (Oracle APEX + SQL)

Aplicație realizată în Oracle APEX pentru gestionarea unui adăpost de animale: evidența animalelor, vaccinurilor și cererilor de adopție + rapoarte statistice.

Funcționalități

Vizualizare toate animalele

Adăugare animal nou (formular)

Vizualizare toate cererile de adopție

Istoric vaccinuri pentru un animal (filtrare după codA)

Filtrare animale:

după tip (ierarhie aTip → aAnimal)

după vârstă (Page Item)

Rapoarte:

număr animale + vârstă medie per tip

număr cereri adopție per animal (inclusiv 0)

Structura bazei de date
Tabele implementate:

aTip — tipuri de animale

tip (PK)

denumire

necesarAvizM (CHECK: 'da' / 'nu')

aAnimal — animale

codA (PK)

tip (FK → aTip)

rasa, nume, varsta, descriere, poza (BLOB)

aListaVaccin — istoric vaccinuri

PK compus: (codA, vaccin)

FK → aAnimal

aCerereAdoptie — cereri adopție

cID (PK)

codA (FK → aAnimal)

data, cnp, nume, tel

Integritate referențială implementată (PK, FK, CHECK)

Fișiere incluse

AnimalSchema.sql — creare tabele + constrângeri (DDL)

AnimalDate.sql — inserare date (DML)

Set de date:

3 tipuri de animale

24 animale

16 vaccinuri

8 cereri de adopție

Pagini Oracle APEX

Vizualizare animale

Vizualizare cereri adopție

Vizualizare animale pe tip

Adăugare animal

Vizualizare animale după vârstă

Vizualizare istoric vaccinuri

Raportare statistică animale

Raportare cereri adopție

Tehnologii utilizate

Oracle Database

Oracle APEX

SQL (DDL + DML)

JOIN / OUTER JOIN

Funcții agregate (COUNT, AVG)

Rulare proiect

Rulați AnimalSchema.sql

Rulați AnimalDate.sql

Creați paginile în Oracle APEX pe baza tabelelor și interogărilor

Autori

Ștefan Livia 

Vlaicu Ana-Maria
