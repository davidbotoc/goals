# Goals 2027 – Trecerea la nivel Mid

Draft pentru discuția cu team lead-ul. Valorile numerice și numele proceselor sunt placeholder-uri, de înlocuit cu baseline-ul real.

## 1. Subiectele inițiale, grupate pe categorii

**A. Azure DevOps, repository-uri și proces de livrare**

- Best practices în ADO
- Versiuni Major.Minor.Patch în ADO
- Branch policies/securitate („God mode”)
- Agenda mai bună pentru deployment, cu planificarea fiecărui deployment

**B. AI și agenți**

- Agent care evită greșelile în ADO/repository-uri
- Agent pentru code review
- NotebookLM/chatbot pentru aplicații
- Agentic AI în containere Docker pe un server: testarea aplicațiilor / simularea unei echipe de QA

**C. Calitate și standardizare aplicații**

- Logging/teste/semantic versioning pentru fiecare aplicație
- Backup pentru aplicațiile obsolete (date din baze de date și repository-ul de cod legacy), pentru aplicațiile cu date real-time și pentru repository-uri

**D. Infrastructură, medii și operațiuni**

- Docker + yaml
- Version managers: nvm pentru Node, echivalente pentru .NET etc.
- Version managers pentru servere
- Tool de monitorizare a serverelor

**E. Baze de date și modelarea datelor**

- PostgreSQL
- Best practices pentru baze de date
- ACID > consistență
- Principii de modelare: normalizare, denormalizare controlată, Single Source of Truth
- Principii de integritate a datelor
- Tipare moderne de persistență și scriere: CQRS, Event Sourcing, idempotență la nivel de date

**F. Proiect integrator**

- Platformă cu 3 mici aplicații: integrare PostgreSQL + .NET + Angular

## 2. Diferența dintre junior și mid: cele 6 puncte

1. **Transformă code review-ul din rol informal în sistem:** standarde și checklist documentate, reviewere rotiți, mentorat pe feedback, ca să nu devii un blocaj.
2. **Preia explicit migrarea SQL Server → PostgreSQL:** ownerul tehnic, nu doar cel care învață tehnologia.
3. **Documentează deciziile de design:** ADR-uri și prezentarea soluțiilor în echipă, ca designul bun să fie vizibil.
4. **Arată că poți conduce, nu doar executa:** onboarding pentru juniori, sesiuni interne, mentoring cu dovezi.
5. **Predictibilitate și estimare:** estimările comparate cu realitatea, riscuri semnalate devreme.
6. **Ownership operațional:** răspunzi de o aplicație cap-coadă, inclusiv după livrare (monitorizare, incidente, postmortem, prevenire).

## 3. Goals rescrise

Textele sunt în engleză, ca să poată fi lipite direct în formular. Sunt 4 goals. Dacă formularul permite doar 3, Goal 2 și Goal 3 pot fi unite.

### Goal 1

**Goal name:** AI-Assisted SDLC & Autonomous Agentic Testing

**Performance goal description:** By Q4 2027, deploy on a dedicated, isolated server an agentic AI testing environment (Docker containers) that autonomously tests the team's applications and returns a structured results report (pass/fail, defects found, evidence), using non-production data only. Complement it with: (a) an ADO guardrail agent that detects recurring repository/pipeline mistakes, (b) an AI code-review assistant based on the team's codified review rules, (c) a NotebookLM/chatbot knowledge base for 2 applications. Success criteria: autonomous test runs cover at least 3 applications with a report for every release candidate; avoidable ADO/repo mistakes reduced by 30% vs. baseline; PR review turnaround reduced by 20%.

**Milestones:**

- **Q1:** Baseline measured (top recurring ADO/repo mistakes, review turnaround); isolated-environment design approved (network isolation, no production data, secrets handling). *Check-in note: baseline report and approved design.*
- **Q2:** Environment running; first application tested autonomously with a first report; guardrail agent piloted on 3 repositories. *Check-in note: sample report, mistakes caught, false positives.*
- **Q3:** Coverage expanded to 3 applications; code-review assistant and chatbot piloted. *Check-in note: review turnaround vs. baseline, usage statistics, feedback.*
- **Q4:** Report accuracy compared with manual testing (missed and false defects); documentation and internal demo delivered. *Check-in note: accuracy results, risks, recommendation for next year.*

**Organization Alignment:** Goal 1 – AI SDLC Integration, Developer Tooling & Full Agentic AI.

### Goal 2

**Goal name:** Unified Platform Replacing 3 Processes (Application Ownership)

**Performance goal description:** By Q4 2027, design, build and own in production a platform (PostgreSQL + .NET + Angular, containerized, deployed through ADO CI/CD) that replaces 3 existing processes (\[Process A, B, C\]), including operating it after go-live. The platform ships with structured logging, automated tests on critical paths, Major.Minor.Patch versioning, documented architecture decisions (ADRs) and a data model based on integrity principles (single source of truth, controlled denormalization, idempotent writes). CQRS/Event Sourcing is evaluated through an ADR and applied only where justified. Success criteria: 3 of 3 processes replaced and the old ones decommissioned; processing time/manual effort reduced by X% vs. baseline; every incident in the first 90 days after go-live has a documented root cause.

**Milestones:**

- **Q1:** Baseline of the 3 processes (time, effort, errors); requirements, architecture and first ADRs approved. *Check-in note: baseline numbers, architecture review.*
- **Q2:** Process 1 live in production. *Check-in note: go-live results, issues, user feedback.*
- **Q3:** Processes 2 and 3 live; runbook and support documentation written. *Check-in note: metrics vs. baseline, incidents and root causes.*
- **Q4:** 90 days of stable operation; old processes decommissioned; lessons-learned session delivered. *Check-in note: final metrics, incident log, handover documentation.*

**Organization Alignment:** Goal 2 – Enterprise Tech Debt Reduction & Application Modernization.

### Goal 3

**Goal name:** SQL Server → PostgreSQL Migration Ownership & Legacy Data Protection

**Performance goal description:** By Q4 2027, take responsibility for the SQL Server → PostgreSQL data migration: assess schemas, T-SQL objects, data types, queries and ORM compatibility; produce a migration playbook; migrate a pilot database with validation and a tested rollback; and, if the migration is approved, execute it for the agreed scope. In parallel, implement verified backups (database data and code repositories) for 100% of obsolete applications. Decision gate: by the end of Q1, deliver an assessment and recommendation so leadership can decide; if the migration is not approved, the scope reduces to the playbook and a pilot in a test environment. Success criteria: zero data loss (row counts and checksums validated), key-query performance within an agreed margin of the SQL Server baseline, rollback tested, 100% of obsolete applications backed up with at least one successful restore test each.

**Milestones:**

- **Q1:** Assessment of the pilot database and recommendation delivered. *Check-in note: assessment report, risks, decision outcome.*
- **Q2:** Migration playbook drafted; pilot migrated in a test environment. *Check-in note: playbook review, issues found during pilot.*
- **Q3:** Validation, performance comparison and rollback test completed; backups for all obsolete applications in place. *Check-in note: validation results, benchmark numbers, backup coverage %.*
- **Q4:** Production migration of the agreed scope (if approved) or a readiness package (if not); knowledge-sharing session delivered. *Check-in note: migration results or readiness status, lessons learned.*

**Organization Alignment:** Goal 2 – Enterprise Tech Debt Reduction & Application Modernization.

### Goal 4

**Goal name:** Predictable Delivery & Team Engineering Standards

**Performance goal description:** By Q4 2027, improve delivery predictability and team quality by: (a) applying an ADO best-practices standard (branch policies, least-privilege permissions, pipeline templates, Major.Minor.Patch versioning, runtime version managers such as nvm and .NET SDK pinning) to 100% of active repositories; (b) making a deployment planning agenda mandatory for production deployments; (c) implementing server monitoring with alerting on 100% of production servers; (d) documenting a code-review standard and checklist, training rotating reviewers, mentoring at least one junior developer and delivering 2 internal sessions. Success criteria: failed or rolled-back deployments reduced by 30%; at least 90% of planned deployments delivered on the committed date; review turnaround reduced by 20% with at least 3 active reviewers; estimates vs. actuals tracked quarterly.

**Milestones:**

- **Q1:** Audit of ADO setup (policies, permissions, pipelines) and baseline of deployment failures and delays. *Check-in note: audit findings and baseline metrics.*
- **Q2:** Standard applied to 50% of repositories; review standard published; deployment template piloted. *Check-in note: % repositories compliant, pilot feedback.*
- **Q3:** 100% of repositories compliant; deployment agenda mandatory; monitoring tool selected and running on the first servers; reviewer rotation started. *Check-in note: deployment success rate vs. baseline, active reviewers.*
- **Q4:** Monitoring on all production servers; mentoring and sessions completed; final metrics reviewed. *Check-in note: final metrics vs. targets, estimate-vs-actual trend.*

**Organization Alignment:** Goal 3 – Operational Delivery Excellence: Regional Commitment & Delivery Predictability (secondary: Goal 2).

## 4. Criteriile pentru mid, actualizate

Coloana „Unde ești acum” se bazează doar pe ce a fost spus în discuție, nu pe o evaluare.

| Criteriu | Ce se așteaptă de la mid | Unde ești acum | Ce să dovedești în 2027 |
| --- | --- | --- | --- |
| **Autonomie și ownership** | Duce o componentă sau o aplicație de la cerințe la producție | Platforma care înlocuiește 3 procese e o dovadă puternică. Ca să fie „bifat” complet, include și perioada de după go-live (operare, incidente, suport) | Platforma în producție, 90 de zile de operare stabilă, runbook, incidente cu cauze-rădăcină |
| **Calitate tehnică și design** | Alege soluții cu compromisuri argumentate, cod mentenabil | Bun pe cod și arhitectură | ADR-uri scrise, design prezentat și validat de echipă |
| **Code review și standarde** | Ridică nivelul calității în echipă | Reviewerul echipei, feedback apreciat | Standard și checklist documentat, reviewere rotiți, timp de review măsurat |
| **Mentoring și colaborare** | Ajută activ alți colegi să crească | Informal, prin review-uri | Onboarding pentru cel puțin un junior, 2 sesiuni interne |
| **Livrare și predictibilitate** | Estimează realist, semnalează riscuri, respectă angajamentele | De măsurat (baseline) | Estimate vs. realizat urmărite trimestrial, ≥90% livrări la termen |
| **Comunicare și influență** | Documentează, raportează proactiv, convinge cu argumente | Comunicare bună în review-uri | Raportare la fiecare check-in, propuneri adoptate de echipă |
| **Impact organizațional** | Îmbunătățiri măsurabile care folosesc echipei sau altor echipe | Procese ADO îmbunătățite | Platforma, playbook-ul de migrare PostgreSQL și agentul de testare reutilizate de alte echipe |

### Subiectele inițiale, grupate pe categorii

**A. Azure DevOps, repository-uri și proces de livrare**

- Best practices în ADO
- Versiuni Major.Minor.Patch în ADO
- Branch policies/securitate („God mode”)
- Agenda mai bună pentru deployment, cu planificarea fiecărui deployment

**B. AI și agenți**

- Agent care evită greșelile în ADO/repository-uri
- Agent pentru code review
- NotebookLM/chatbot pentru aplicații
- Agentic AI în containere Docker pe un server: testarea aplicațiilor / simularea unei echipe de QA

**C. Calitate și standardizare aplicații**

- Logging/teste/semantic versioning pentru fiecare aplicație
- Backup pentru aplicațiile obsolete (date din baze de date și repository-ul de cod legacy), pentru aplicațiile cu date real-time și pentru repository-uri

**D. Infrastructură, medii și operațiuni**

- Docker + yaml
- Version managers: nvm pentru Node, echivalente pentru .NET etc.
- Version managers pentru servere
- Tool de monitorizare a serverelor

**E. Baze de date și modelarea datelor**

- PostgreSQL
- Best practices pentru baze de date
- ACID > consistență
- Principii de modelare: normalizare, denormalizare controlată, Single Source of Truth
- Principii de integritate a datelor
- Tipare moderne de persistență și scriere: CQRS, Event Sourcing, idempotență la nivel de date

**F. Proiect integrator**

- Platformă cu 3 mici aplicații: integrare PostgreSQL + .NET + Angular
