# Biochemical Test Practice

An interactive quiz site for NS7011 Applied Molecular Biology and broader bioinformatics/molecular biology revision. Built by Olivia Williams.

**Live site:** https://be-livtastic.github.io/biochemical-test-practice/

---

## Overview

This site provides five quiz modes covering microbiology, molecular techniques, protein science, and bioinformatics tools. Each question includes a hint system, a detailed result card with step context, and a grouped summary at the end that doubles as a revision sheet.

---

## Quiz Modes

### Mode 1 — Organism ID
Given morphology and biochemical clues, identify one of six organisms from the NS7011 practical:
Agrobacterium, Bacillus, E. coli, Micrococcus, Pseudomonas, Staphylococcus aureus.
Each result card shows the identification path and key distinguishing features.

### Mode 2 — Biochemical Tests
Tests knowledge of 13 biochemical tests: Catalase, Coagulase (tube and slide), PYR, Optochin, CAMP, Novobiocin, Oxidase, Indole, Urease, H2S (TSI), MUG, and TSI interpretation.
Three question types: identify-test, interpret-result, explain-step.
Result cards include colour change panels (positive/negative/chemistry), purpose, and common organisms tables.

### Mode 3 — Experiments
Covers five NS7011 practical experiments: DNA Extraction, PCR, Gel Electrophoresis, RFLP, and Streak Plating.
Four question types: identify-step, why-step, shortfall, reagent.
16 questions total. Summary grouped by experiment.

### Mode 4 — Western Blotting
Three themes: WB Fundamentals, Gel & Transfer, Immunodetection.
Five question types: identify-step, why-step, shortfall, reagent, interpret.
18 questions. Covers SDS-PAGE mechanics, transfer method selection, blocking agent choice, antibody optimisation, multiplexing, and linear dynamic range.

### Mode 5 — Omics & Tools
Five themes: Metabolomics, Functional Genomics, Proteomics, EMBL-EBI, AlphaFold & Structural.
Five question types across all themes.
20 questions. Covers targeted vs untargeted metabolomics, CRISPR screens, mass spectrometry proteomics, EMBL-EBI database architecture (Ensembl, UniProt, ENA, PRIDE, Reactome, Expression Atlas), and AlphaFold2 interpretation including pLDDT, PAE, and structural drug discovery caveats.

---

## Project Structure

```
index.html                        ← quiz logic and rendering
data/
  decision-trees.json             ← biochemical ID decision tree content
  quiz-organisms.json             ← Mode 1 questions
  quiz-biochemical.json           ← Mode 2 questions
  quiz-experiments.json           ← Mode 3 questions
  quiz-westernblot.json           ← Mode 4 questions
  quiz-omics.json                 ← Mode 5 questions
styles/
  decision-tree.css
  quiz.css
biochemical_id_decision_tree.html ← redirect page (can be deleted)
README.md
```

---

## Question Schema

All quiz modes share a common JSON structure:

```json
{
  "id": "",
  "theme": "",
  "questionType": "identify-step | why-step | shortfall | reagent | interpret",
  "scenario": "",
  "options": ["A", "B", "C", "D"],
  "correctAnswer": "",
  "hint": "",
  "explanation": "",
  "stepContext": {
    "step": "",
    "whyWeDoThis": "",
    "commonShortfall": "",
    "howToPrevent": "",
    "reagentIfApplicable": ""
  }
}
```

The `reagentIfApplicable` field triggers an amber reagent note block in the result card when non-empty.

---

## Question Type Badges

| Badge | Colour | Description |
|---|---|---|
| identify-step | Purple | Name or order a step or component |
| why-step | Teal | Mechanistic reasoning behind a step |
| shortfall | Red | Diagnose a failed or flawed experiment |
| reagent | Amber | Identify or compare reagents and tools |
| interpret | Navy | Analyse data or weigh trade-offs |

---

## Key Reference Numbers (NS7011)

| Parameter | Value |
|---|---|
| PCR denaturation | 94°C |
| PCR annealing | 51°C |
| PCR extension | 68°C, 2 min |
| PCR cycles | 30 |
| PCR total volume | 25 µL (12.5 master mix + 1 FP + 1 RP + 5.5 water + 1 template) |
| Restriction digest | 37°C, 60 min, 50 µL (5 DNA + 5 buffer + 39 water + 1 enzyme) |
| Heat inactivation | 65°C, 10 min |
| Gel conditions | 1% agarose, 120V, 45 min, Fast Blast stain, white light |
| Gram stain — CV | 30 s |
| Gram stain — iodine | 30 s |
| Gram stain — decolouriser | 3–5 s (critical step) |
| Gram stain — safranin | 1 min |

---

## Tools and Databases Referenced (Mode 5)

| Resource | URL | Category |
|---|---|---|
| KEGG | kegg.jp | Pathway mapping |
| HMDB | hmdb.ca | Human metabolome |
| MetaboLights | ebi.ac.uk/metabolights | Metabolomics repository |
| MetaboAnalyst | metaboanalyst.ca | Metabolomics analysis |
| Ensembl | ensembl.org | Genome annotation |
| Expression Atlas | ebi.ac.uk/gxa | Gene expression |
| UniProt | uniprot.org | Protein knowledgebase |
| ENA | ebi.ac.uk/ena | Nucleotide archive |
| PRIDE | ebi.ac.uk/pride | Proteomics repository |
| Reactome | reactome.org | Pathway database |
| AlphaFold DB | alphafold.ebi.ac.uk | Protein structure predictions |
| PDB | rcsb.org | Experimental structures |
| STRING | string-db.org | Protein interaction networks |
| DisProt | disprot.org | Intrinsically disordered proteins |

---

## Built With

- Vanilla HTML, CSS, JavaScript
- JSON data files (no backend)
- Hosted on GitHub Pages

---

## Author

Olivia Williams
MSc Biotechnology, University of Chester
Commonwealth Scholar 2025–2026
GitHub: [@be-livtastic](https://github.com/be-livtastic)
