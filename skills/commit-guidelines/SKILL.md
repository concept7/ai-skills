---
name: git-auto-commit-analyst
description: Generates structured commit messages based on 'git diff --staged', focusing on technical accuracy, brevity, and automatic changelog category assignment. Use when generating commit messages or applying commit guidelines.
---

# Skill: Git Auto-Commit Analyst

## 1. Doel

Het genereren van een gestructureerde commit message op basis van de inhoud van `git diff --staged`. De focus ligt op technische nauwkeurigheid, beknoptheid en het automatisch toewijzen van een changelog-categorie.

## 2. Formaat Richtlijnen

Elke output moet strikt voldoen aan deze opbouw:

-   **Subject Line:** Maximaal 50 tekens, gebiedende wijs (bijv. "Fix", "Add", "Update"), begint met een hoofdletter.
-   **Description:** Eén witregel na de subject line. Beschrijf de context (waarom is dit gedaan?) in plaats van de letterlijke code-wijziging.
-   **Trailer:** Eindig direct na de beschrijving met de juiste `Changelog: <type>` tag.

## 3. Classificatie Logica

Analyseer de staged files en bepaal het type op basis van de volgende definities:

| Type            | Wanneer te gebruiken                                                  |
| :-------------- | :-------------------------------------------------------------------- |
| **added**       | Nieuwe functionaliteiten, nieuwe componenten of nieuwe bestanden.     |
| **fixed**       | Bugfixes, oplossen van crashes, of correcties van foutieve logica.    |
| **changed**     | Wijzigingen aan bestaande features die geen nieuwe functie toevoegen. |
| **deprecated**  | Markeren van code die in toekomstige versies verwijderd zal worden.   |
| **removed**     | Verwijderen van oude features of ongebruikte code.                    |
| **security**    | Dichten van beveiligingslekken of updates aan authenticatie.          |
| **performance** | Optimalisaties die de snelheid of geheugengebruik verbeteren.         |
| **other**       | Refactoring, documentatie, of wijzigingen in build-scripts.           |

---

## 4. Instructie voor Generatie

Wanneer de `git diff` of een lijst met wijzigingen wordt aangeleverd:

1. Scan de wijzigingen op kernfunctionaliteit.
2. Schrijf de subject line en beschrijving.
3. Selecteer het meest relevante changelog type.
4. **Output uitsluitend de commit message zelf**, zonder extra uitleg of Markdown code-blocks (tenzij anders gevraagd).

---

## 5. Voorbeeld Output

Update user authentication timeout

Increased the session duration from 30 to 60 minutes to reduce
re-login frequency for active dashboard users.

Changelog: changed
