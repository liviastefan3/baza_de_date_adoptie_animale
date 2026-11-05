English Version
Animal Shelter & Adoption Management System
An Oracle APEX web application backed by an Oracle Database designed to streamline shelter operations: tracking animal profiles, vaccination medical records, and processing adoption requests with analytical reporting.

Key Features
Animal & Health Registry: CRUD operations for animals (demographics, descriptions, BLOB image uploads) alongside multi-record vaccination logs per animal (codA).

Adoption Workflow: Intake and tracking of adoption applications linked directly to shelter residents.

Dynamic Filtering: Hierarchical type-based filtering (aTip → aAnimal) and parameterized age filtering via APEX Page Items.

Statistical Dashboards: Interactive reports showing animal counts and average age per species, plus adoption demand tracking per animal (via SQL OUTER JOIN to include animals with zero requests).

Database Architecture
aTip: Species catalog with medical approval constraints (PK: tip, CHECK: necesarAvizM IN ('da', 'nu')).

aAnimal: Core registry storing profiles, photos, and species relations (PK: codA, FK: tip).

aListaVaccin: Composite primary key junction table tracking vaccinations (PK: (codA, vaccin), FK: codA).

aCerereAdoptie: Adoption applications log (PK: cID, FK: codA).

Tech Stack
Database: Oracle Database, SQL (DDL, DML, composite keys, constraints).

Platform: Oracle APEX (Interactive Grids/Reports, Forms, Chart Dashboards).

Advanced Queries: Aggregations (COUNT, AVG), Multi-table Inner & Outer Joins.

Setup
Execute AnimalSchema.sql to generate schema tables and referential integrity constraints.

Execute AnimalDate.sql to seed base data (types, animals, vaccination history, and sample adoption requests).

Import or configure the APEX application components linked to the database objects.

Authors: Livia Ștefan, Ana-Maria Vlaicu

Versiunea în Română 
Sistem de Gestiune și Adopție Animale
Aplicație web dezvoltată în Oracle APEX pe o bază de date Oracle, dedicată managementului operațional dintr-un adăpost: evidența animalelor, fișe medicale de vaccinare, procesarea cererilor de adopție și rapoarte statistice.

Funcționalități Principale
Evidență Animale & Profil Medical: Gestionare completă a animalelor (date, descrieri, stocare foto BLOB) și istoric complet al vaccinurilor corelat prin identificator unic (codA).

Management Adopții: Înregistrarea și monitorizarea cererilor de adopție asociate fiecărui animal.

Filtrare Dinamică: Navigare ierarhică după tip de animal (aTip → aAnimal) și parametri de vârstă prin Page Items APEX.

Rapoarte Statistice: Dashboards interactive pentru distribuția animalelor și vârsta medie pe categorii, respectiv analiza cererilor per animal (interogări cu OUTER JOIN pentru includerea celor fără cereri).

Structura Bazei de Date
aTip: Nomenclator tipuri de animale și cerințe avize (PK: tip, constrângere CHECK).

aAnimal: Registrul principal al animalelor și fotografiilor (PK: codA, FK: tip).

aListaVaccin: Tabela de legătură pentru vaccinuri (PK compus: (codA, vaccin), FK: codA).

aCerereAdoptie: Evidența solicitărilor de adopție și a datelor de contact (PK: cID, FK: codA).

Tehnologii Utilizate
Bază de date: Oracle Database, SQL (DDL, DML, integritate referențială PK/FK/CHECK).

Platformă: Oracle APEX (Rapoarte Interactive, Formulare, Grafice).

Interogări SQL: Funcții agregate (COUNT, AVG), INNER JOIN, OUTER JOIN.

Instrucțiuni de Rulare
Rulați scriptul AnimalSchema.sql pentru generarea tabelelor și a constrângerilor de integritate.

Rulați scriptul AnimalDate.sql pentru popularea cu datele inițiale.

Configurați/importați componentele aplicației în Oracle APEX conectate la schema creată.

Autori: Livia Ștefan, Ana-Maria Vlaicu
