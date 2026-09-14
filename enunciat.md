# PROJECTE INTERMODULAR - DAM

## 1. Objectiu

L'objectiu principal es demostrar que sou capaços d'afrontar un projecte de desenvolupament de programari de principi a fi, treballant en equip, prenent decisions tècniques, resolent problemes i utilitzant les eines disponibles --inclosa la IA-- de manera crítica i responsable

Haureu de dissenyar i desenvolupar **diferents aplicacions que comparteixen informació i treballen sobre una mateixa base de dades**. El projecte haurà d’incloure obligatòriament:

- Una **aplicació mòbil**
- Una **aplicació d’escriptori**
- Una **aplicació web**

---

## 2. Temàtica del Projecte

Una de les característiques principals del projecte és que **vosaltres decidireu què voleu desenvolupar**

No hi haurà un únic projecte igual per a tota la classe. Haureu de detectar una necessitat, un problema o una situació que pugui solucionar-se mitjançant un sistema informàtic

Alguns **exemples** podrien ser:

- Gestió d'un gimnàs
- Gestió d'una acadèmia
- Gestió d'un centre mèdic
- Gestió d'una residència d'animals
- Gestió d'un hotel
- Gestió d'un club esportiu
- Gestió d'un torneig de videojocs
- Gestió d'una escola de música
- Gestió d'una biblioteca
- Gestió d'un servei de lloguer de vehicles

Podeu proposar qualsevol projecte sempre que sigui:

- realista
- tècnicament viable
- prou complet
- adequat al nivell de DAM
- compatible amb els requisits establerts en aquest enunciat

### I si no tinc cap idea?

Podeu partir d'un problema o sector que us interessi:

```text
Esport
Educació
Salut
Animals
Oci
Comerç
Hostaleria
Automoció
Videojocs
Música
Turisme
Productivitat
...
```

També podeu inspirar-vos en aplicacions o sistemes que ja existeixen i pensar:

> **"Com podria millorar-lo?"**

No cal inventar una idea completament revolucionària

El que importa és que sigueu capaços de **dissenyar, desenvolupar i justificar un sistema complet**

---

## 3. Funcionalitat de les tres aplicacions

Les tres aplicacions formaran part del **mateix sistema**, però **no hauran de fer exactament el mateix**. Cada aplicació haurà de tenir una funció concreta

### Exemple: sistema de gestió d'un gimnàs

#### Aplicació mòbil

Pensada principalment per als clients:

- consultar activitats
- consultar horaris
- reservar classes
- consultar les seves reserves
- consultar la seva informació
- consultar pagaments, etc

#### Aplicació d'escriptori

Pensada principalment per al personal del gimnàs:

- gestionar clients
- gestionar activitats
- gestionar entrenadors
- gestionar horaris
- gestionar reserves
- gestionar pagaments, etc

#### Aplicació web

Pensada principalment per a administració i consulta:

- estadístiques
- informes
- informació global
- gràfics
- gestió o consulta de determinats elements del sistema

---

## 4. Arquitectura del sistema

El projecte haurà d'utilitzar una arquitectura basada en un **backend/API**, és a dir les aplicacions no accediran directament a la base de dades sinó que ho faran mitjançant una API

La comunicació serà:

```text
Mòbil---------┐
              |
Escriptori ---┼--> API REST --> MySQL/PostgreSQL
              |
Web ----------|
```

---

## 5. Backend i API REST

El projecte haurà d'incloure un **backend senzill** que proporcioni una **API REST**. L'objectiu no és construir inicialment un backend excessivament complex, sinó entendre com les diferents aplicacions poden comunicar-se amb un servidor central

## 5.1. Backend mínim obligatori

El backend haurà d'incloure, com a mínim:

### API REST

Utilització dels principals mètodes HTTP:

```text
GET
POST
PUT
DELETE
```

Per exemple:

```text
GET    /api/clients
GET    /api/clients/15
POST   /api/clients
PUT    /api/clients/15
DELETE /api/clients/15
```

Els endpoints concrets dependran del projecte

---

### Comunicació amb la base de dades

El backend haurà de poder:

- consultar dades
- inserir dades
- modificar dades
- eliminar dades
- consultar informació relacionada entre diferents taules

---

### Comunicació amb JSON

La comunicació entre les aplicacions i l'API utilitzarà **JSON** quan correspongui

Per exemple:

```json
{
  "nombre": "Laura",
  "email": "laura@example.com"
}
```

---

### Gestió bàsica d'errors

El backend haurà de gestionar situacions com:

- recurs inexistent
- dades incorrectes
- camps obligatoris absents
- errors de base de dades
- operacions no permeses

---

## 5.2. Backend avançat — ampliació per pujar nota

El backend bàsic és **obligatori**. Els alumnes que vulguin demostrar un nivell tècnic superior podran ampliar-lo amb funcionalitats avançades. Aquestes ampliacions seran **voluntàries** i podran contribuir a obtenir una qualificació superior

Algunes possibilitats són:

### Autenticació

Implementar un sistema d'autenticació d'usuaris

Per exemple:

```text
POST /api/login
POST /api/register
```

---

### Usuaris, rols i permisos

Diferenciar diferents tipus d'usuari:

```text
CLIENT
EMPLEAT
ADMINISTRADOR
```

I controlar quines operacions pot realitzar cadascun

---

### Lògica de negoci

Implementar regles pròpies del sistema

Per exemple:

> Un usuari no pot reservar una activitat si no queden places disponibles

O:

> Un usuari no pot cancel·lar una reserva quan l'activitat ja ha començat

Aquest tipus de regles hauran de ser gestionades pel backend

---

### Validació avançada

Implementar validacions més completes:

- tipus de dades
- formats
- rangs
- dependències entre camps
- coherència entre dades
- regles específiques del projecte

---

### Arquitectura interna del backend

Organitzar el backend separant adequadament les diferents responsabilitats

Per exemple:

```text
backend/
│
├── routes/
├── controllers/
├── services/
├── models/
├── middleware/
├── database/
└── app.js
```

No és obligatori utilitzar exactament aquesta estructura

El que es valorarà és que existeixi una **organització coherent i justificada**

---

### Consultes avançades

Implementar:

- filtres
- cerques
- ordenació
- paginació
- estadístiques
- informes
- consultes que combinin diverses taules
- altres funcionalitats que aportin valor al projecte

---

### Proves de l'API

Realitzar proves específiques dels endpoints amb eines com:

- Postman
- Thunder Client
- altres eines equivalents

Per exemple:

```text
✓ GET /api/clientes
✓ GET /api/clientes/15
✓ POST /api/clientes
✓ PUT /api/clientes/15
✓ DELETE /api/clientes/15
✓ Client inexistent
✓ Dades incorrectes
✓ Operació no autoritzada
```

### Important

**Afegir complexitat no significa automàticament obtenir més nota**

Una funcionalitat avançada haurà d'estar:

- ben dissenyada
- correctament implementada
- provada
- documentada
- explicada per l'alumne

No es valorarà positivament afegir funcionalitats simplement per tenir més codi

---

## 6. Base de dades

El projecte haurà d'utilitzar una **base de dades relacional** i relacionar diferents entitats.

Per exemple:

```text
CLIENTS
   │
   ├──── RESERVES
   │
   │       │
   │       └──── ACTIVITATS
   │
   └──── PAGAMENTS
```

Com a mínim, s'haurà de mostrar:

- claus primàries
- claus foranes
- relacions entre taules
- integritat de les dades
- insercions
- modificacions
- eliminacions
- consultes
- consultes relacionant diverses taules

---

## 7. Tecnologies

Si no sabeu quines tecnologies escollir, podeu utilitzar les que treballareu a classe

| Part                | Tecnologia de referència |
| ------------------- | ------------------------ |
| Mòbil               | React Native             |
| Web                 | HTML + CSS + JavaScript  |
| Escriptori          | JavaFX                   |
| Backend/API         | Node.js + Express        |
| Base de dades       | MySQL / PostgreSQL       |
| Control de versions | Git + GitHub             |

**No és obligatori utilitzar aquesta combinació**

Podeu proposar les tecnologies que considereu adequades sempre que:

- siguin adequades
- siguin viables
- pugueu justificar-ne l'elecció
- disposeu dels coneixements o recursos necessaris
- no posin en risc la finalització del projecte

---

## 8. Treball en equip

El projecte es realitzarà **per parelles**. Cada integrant tindrà responsabilitats concretes però **no es permetrà una divisió com aquesta**:

```text
Alumne A → només aplicació mòbil

Alumne B → web + escriptori + backend
```

Aquesta distribució no permet demostrar que els dos integrants tenen una visió global del projecte. **Tots dos hauran de participar en diferents parts del projecte**

Per exemple:

### Perfil A

Responsable principal de:

```text
Clients
Usuaris
Pagaments
```

### Perfil B

Responsable principal de:

```text
Activitats
Reserves
Entrenadors
```

Però **tots dos hauran de desenvolupar funcionalitats en:**

```text
Mòbil
Web
Escriptori
API
Base de dades
```

Les responsabilitats hauran d'estar equilibrades en dificultat i volum de feina

### Organització del treball

Durant el projecte haureu de mantenir un sistema de seguiment de les tasques. Teniu que ajudar-vos d'una eina digital, per exemple:

- Word/ Excel
- GitHub Projects
- Trello
- Jira
- una altra eina acordada amb el professor

Les tasques es poden organitzar, per exemple, en:

- PER FER
- EN PROCÉS
- ACABAT

Cada tasca haurà d'indicar, com a mínim:

- què s'ha de fer
- qui n'és responsable
- estat
- incidències importants, si n'hi ha

---

### Anotacions individuals

**Cada alumne haurà de mantenir el seu propi seguiment de projecte.**. No serà suficient amb el seguiment de tasques de la parella.

El diari haurà d'incloure, com a mínim:

- data
- temps aproximat dedicat
- tasques planificades
- tasques realitzades
- problemes trobats
- com s'han solucionat
- ús de la IA, si n'hi ha hagut
- properes tasques

### Exemple

```text
15/10/2026

Temps: 1 h 30 min

Tasques planificades:
- Crear GET /api/clientes

Tasques realitzades:
- GET /api/clientes
- GET /api/clientes/:id

Problema:
- L'API retornava un error 500 quan el client no existia

Solució:
- He modificat la gestió d'errors

IA:
- He utilitzat IA per analitzar les possibles causes
  de l'error

Proper pas:
- Implementar POST /api/clientes
```

El diari haurà de mantenir-se **durant tot el projecte** i no reconstruir-se al final

---

## 9. Requisits tècnics mínims

Perquè el projecte es consideri complet haurà d'incloure, com a mínim:

### Aplicacions

- Aplicació mòbil
- Aplicació d'escriptori
- Aplicació web

### Backend

- API REST
- comunicació HTTP
- JSON
- CRUD
- connexió amb la base de dades
- gestió bàsica d'errors

### Base de dades

- base de dades relacional
- diverses taules
- PK i FK
- relacions
- consultes relacionades

### Aplicacions

- formularis
- validació
- llistats
- cerques i/o filtres
- gestió d'errors
- comunicació amb l'API

### En el Desenvolupament

- Control de versions
- Documentació
- Proves
- Treball en equip

---

## 10. Utilització de la Intel·ligència Artificial

La IA forma part del projecte com una **eina de treball i aprenentatge**. Es podrà utilitzar per:

- entendre conceptes
- analitzar errors
- revisar codi
- revisar dissenys
- proposar casos de prova
- simular l'execució d'un programa
- buscar possibles causes d'un problema
- comparar diferents solucions
- millorar la documentació
- estudiar alternatives tècniques

**La IA no es podrà utilitzar per fer el projecte per vosaltres.**

No es tracta de:

```text
"Fes-me tota l'aplicació"
        ↓
Copiar
        ↓
Entregar
```

Es tracta de:

```text
Problema
   ↓
Raonament de l'alumne
   ↓
Pseudocodi / proposta
   ↓
IA revisa o simula
   ↓
Alumne corregeix
   ↓
Implementació
   ↓
IA ajuda a analitzar
   ↓
Execució real
   ↓
Comparació
   ↓
Depuració
```

L'objectiu és que la IA sigui una **eina de raonament, comprovació i aprenentatge**, no un substitut del desenvolupador

---

### Registre de l'ús de la IA

Quan la IA s'utilitzi de manera significativa, s'haurà de deixar constància de la seva utilització

Per exemple:

| Data  | Problema  | Ús de la IA             | Resultat                    |
| ----- | --------- | ----------------------- | --------------------------- |
| 15/10 | Error API | Analitzar error 500     | S'ha localitzat el problema |
| 20/10 | Model BD  | Revisar relacions       | S'ha modificat una FK       |
| 25/10 | Tests     | Proposar casos de prova | S'han afegit 4 proves       |

En els moments importants del projecte es podrà demanar també:

1. prompt utilitzat
2. resposta de la IA
3. què heu decidit vosaltres
4. modificacions realitzades
5. resultat de la prova

---

## 11. Avaluació

El projecte no serà valorat únicament pel resultat final. També es valorarà **com heu arribat a aquest resultat**

Haureu de demostrar que sou capaços de:

- planificar
- dividir el projecte en tasques
- treballar en equip
- utilitzar Git correctament
- documentar el procés
- solucionar problemes
- prendre decisions tècniques
- provar les vostres aplicacions
- utilitzar la IA de manera responsable
- entendre el codi que heu desenvolupat

De manera orientativa els % són aquestos:

### RESULTAT FINAL — 60 %

- funcionament
- aplicació mòbil
- aplicació d'escriptori
- aplicació web
- backend/API
- base de dades
- arquitectura
- qualitat tècnica
- validació i gestió d'errors
- proves
- documentació

### SEGUIMENT — 30 %

- planificació
- seguiment de tasques
- diari individual
- Git
- treball en equip
- presa de decisions
- documentació del procés
- ús responsable de la IA
- capacitat d'explicar el projecte
- defensa final

### DEFENSA — 10 %

Al final del projecte haureu de ser capaços de **demostrar i explicar el funcionament del sistema**. No serà suficient amb mostrar que l'aplicació funciona. Haureu de poder explicar què passa internament

Per exemple:

> **"Què passa des que premo el botó Reservar a l'aplicació mòbil fins que la reserva queda registrada a la base de dades?"**

---
