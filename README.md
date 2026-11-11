# End-to-End Cheminformatics, Drug Discovery & Chemistry AI Portfolio

A complete, reproducible computational chemistry and AI evaluation portfolio combining **Ligand-Based Machine Learning (QSAR)**, **Structure-Based Physics Modeling (Molecular Docking)**, and **Automated Chemistry AI Verification** using **Python** and **RDKit**.

---

### 1. Ligand-Based Virtual Screening (`EGFR_Bioactivity_QSAR_Portfolio.ipynb`)
- **Data Curation & Medicinal Chemistry Hygiene:** Automated retrieval of experimental $\text{IC}_{50}$ records for Human EGFR (`ChEMBL203`) via the ChEMBL API, median multi-assay deduplication, $p\text{IC}_{50}$ transformation, **PAINS** substructure filtering, and **Lipinski Rule of 5** profiling.
- **Leak-Free Validation:** 2048-bit Morgan Fingerprints (**ECFP4**) paired with **Bemis-Murcko scaffold splitting** to test true out-of-scaffold generalization.
- **Dual Modeling:** Random Forest classification (ROC-AUC) and quantitative $p\text{IC}_{50}$ regression benchmarked on clinical inhibitors (**Gefitinib**, **Osimertinib**) and negative controls.

### 2. Structure-Based Molecular Docking (`EGFR_Molecular_Docking_Portfolio.ipynb`)
- **Receptor & 3D Conformer Preparation:** Crystal structure extraction (`PDB: 1M17`), physiological protonation (`pH 7.4`), and **RDKit ETKDGv3 + MMFF94** 3D ligand conformer optimization.
- **AutoDock Vina Docking & Redocking Validation:** Active-site docking of **Erlotinib**, **Gefitinib**, **Osimertinib**, and non-kinase controls, validated by crystallographic **Erlotinib redocking RMSD** ($< 2.0\text{ \AA}$).
- **3D Binding Pose Visualization:** Interactive `py3Dmol` superposition of crystallographic and docked poses inside the EGFR ATP-binding pocket.

### 3. Automated Chemistry AI Evaluation & Verification (`Chemistry_AI_Verification_Portfolio.ipynb`)
- **SMILES Valence & Hallucination Auditing:** Programmatic syntax/valence sanitization and two-layer `InChIKey` comparison (14-character connectivity vs. full 27-character stereochemistry) to detect invalid structures or dropped stereocenters in LLM outputs.
- **Stereochemical & Chiral Center Inspection:** Automated CIP `(R)/(S)` assignment and unassigned stereocenter detection (`Chem.FindMolChiralCenters`).
- **Reaction Rule & Mass-Balance Auditing:** Forward organic reaction verification via `SMARTS` templates (`rdChemReactions`) and heavy-atom mass-balance checks for RLHF grading and scientific benchmarks.
