# Animal Shelter & Adoption Management System 🐾
### Sistem de Gestiune și Adopție Animale

**Language / Limbă:** [🇬🇧 English](#english) • [🇷🇴 Română](#română)

---

## English

A database-driven web application developed with Oracle APEX and Oracle Database to manage shelter operations, medical records (vaccinations), adoption workflows, and statistical reporting.

### 🌟 Key Features

- **Animal Profiles & Media:** Complete registry storing breed, age, description, and photos (BLOB data type).
- **Medical Tracking:** Vaccination history logs per animal using composite primary keys.
- **Adoption Pipeline:** Intake, applicant verification, and lifecycle management for adoption requests.
- **Dynamic Search & Filtering:**
  - Hierarchical filtering (`aTip` → `aAnimal`).
  - Parameterized age filtering via APEX Page Items.
- **Data Analytics & Reports:**
  - Distribution breakdown: animal counts and average age per species (`COUNT`, `AVG`).
  - Adoption request demand per animal (implemented via `OUTER JOIN` to capture animals with zero requests).

### 🗄️ Database Architecture

| Table | Description | Primary Key | Foreign Key / Constraints |
|---|---|---|---|
| `aTip` | Species catalog | `tip` | `CHECK (necesarAvizM IN ('da', 'nu'))` |
| `aAnimal` | Animal profiles & photos | `codA` | FK: `tip` → `aTip(tip)` |
| `aListaVaccin` | Vaccination history | `(codA, vaccin)` | FK: `codA` → `aAnimal(codA)` |
| `aCerereAdoptie` | Adoption requests & contact info | `cID` | FK: `codA` → `aAnimal(codA)` |

### 🛠️ Tech Stack

- **Database Engine:** Oracle Database
- **Platform:** Oracle Application Express (APEX)
- **Data Language:** SQL (DDL, DML, Composite Keys, Relational Constraints)
- **Techniques:** Aggregations (`COUNT`, `AVG`), Inner/Outer Joins, Interactive Grids & Reports

### 🚀 Getting Started

1. Run `AnimalSchema.sql` to generate tables, constraints, and relational schemas.
2. Run `AnimalDate.sql` to populate sample data (3 animal types, 24 animals, 16 vaccines, 8 adoption requests).
3. Import or build the corresponding UI pages within your Oracle APEX Workspace.

---

## Română

Aplicație web completă realizată în Oracle APEX pe o bază de date Oracle, concepută pentru digitalizarea activității dintr-un adăpost de animale: evidența locatarilor, dosare medicale de vaccinare, gestiunea cererilor de adopție și rapoarte de analiză statistică.

### 🌟 Funcționalități Principale

- **Evidență Animale & Media:** Salvarea detaliilor complete (rasă, vârstă, descriere) și a fotografiilor (BLOB).
- **Fișă Medicală:** Istoric complet al vaccinurilor per animal, utilizând cheie primară compusă.
- **Gestiune Adopții:** Înregistrarea și monitorizarea solicitărilor de adopție și a datelor de contact.
- **Filtrare Dinamică:**
  - Ierarhică pe categorii (`aTip` → `aAnimal`).
  - După vârstă prin intermediul controalelor APEX (Page Items).
- **Rapoarte Statistice:**
  - Număr de animale și vârsta medie per categorie (`COUNT`, `AVG`).
  - Numărul cererilor de adopție per animal (cu `OUTER JOIN` pentru evidențierea inclusiv a celor fără cereri).

### 🗄️ Structura Tabelelor

| Tabelă | Descriere | Cheie Primară (PK) | Constrângeri / Chei Externe (FK) |
|---|---|---|---|
| `aTip` | Nomenclator specii / tipuri | `tip` | `CHECK (necesarAvizM IN ('da', 'nu'))` |
| `aAnimal` | Registru animale și fotografii | `codA` | FK: `tip` → `aTip(tip)` |
| `aListaVaccin` | Istoric vaccinuri | `(codA, vaccin)` | FK: `codA` → `aAnimal(codA)` |
| `aCerereAdoptie` | Solicitări de adopție | `cID` | FK: `codA` → `aAnimal(codA)` |

### 🛠️ Tehnologii Utilizate

- **Bază de date:** Oracle Database
- **Platformă:** Oracle APEX
- **Limbaj:** SQL (DDL, DML, Constrângeri de integritate, Chei compuse)
- **Operații SQL:** `OUTER JOIN`, `INNER JOIN`, Funcții Agregate (`COUNT`, `AVG`)

### 🚀 Instalare și Rulare

1. Executați `AnimalSchema.sql` pentru crearea structurii bazei de date și a constrângerilor.
2. Executați `AnimalDate.sql` pentru inserarea setului de date inițial (3 categorii, 24 animale, 16 vaccinuri, 8 cereri).
3. Configurați sau importați paginile în mediul Oracle APEX.

---

## 👥 Authors / Autori

- Ștefan Livia
- Vlaicu Ana-Maria
