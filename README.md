# comptox-ontology (DSSTox Ontology)

> **Important Naming Notice:** Following expert review and to accurately reflect its foundation on the DSSTox database, this ontology is officially named the **DSSTox Ontology**. The GitHub repository retains the `comptox-ontology` name and namespace strictly to preserve the functional links and URIs cited in our published proceedings.

## Overview
The DSSTox Ontology provides an expert-guided, semantically structured representation for chemicals, with a specific focus on Per- and Polyfluoroalkyl Substances (PFAS) and their properties. Developed as part of the SAWGraph project, it is designed to support integrated environmental contaminant monitoring, data querying, and decision-making by linking chemical identities with their physicochemical, toxicological, and environmental fate properties.

## Ontology Structure & Taxonomy
The ontology is anchored under the `owl:Thing` root class, with the core semantic model centering on the `PFASChemical` class. It is organized into interconnected modules designed to address specific domain requirements.

### 1. The PFAS Taxonomy (`ChemicalEntity` Module)
Organizes PFAS compounds into distinct structural subclasses that influence their environmental fate and transport:

* **Perfluoroalkyl Acids (PFAAs)**
  * *Perfluoroalkyl Carboxylic Acids (PFCAs)* (e.g., PFOA)
  * *Perfluoroalkyl Sulfonic Acids (PFSAs)* (e.g., PFOS)
* **Perfluoroalkyl Ether Acids (PFEAs)**
  * *Perfluoroalkyl Ether Carboxylic Acids (PFECAs)* * *Perfluoroalkyl Ether Sulfonic Acids (PFESAs)*
* **Perfluoroalkane Sulfonamides (FASAa)** (e.g., Perfluorooctanesulfonamide)
* **Perfluoroalkane Sulfonamido Substances (FASAs)**
  * *N-Ethyl Perfluoroalkane Sulfonamides (N-EtFASAs)*
  * *N-Ethyl Perfluoroalkane Sulfonamido Acetic Acids (N-EtFASAAs)*
  * *N-Methyl Perfluoroalkane Sulfonamides (N-MeFASAs)*
  * *N-Methyl Perfluoroalkane Sulfonamido Acetic Acids (N-MeFASAAs)*
* **Polyfluoroalkyl Acid Substances (Fluorotelomer substances - FTs)**
  * *Fluorotelomer Carboxylic Acids*
  * *Fluorotelomer Sulfonic Acids*

### 2. Characteristic Properties
The ontology links chemicals to comprehensive property data derived from authoritative sources like the EPA CompTox Chemicals Dashboard.

* **Chemical Identifiers:** `hasDTXSID`, `hasCASRN`, `hasSMILES`, `hasMolecularFormula`, `hasAverageMass`
* **Molecular Characterization:** * `CarbonChainLength` 
  * `NumberOfFluorineAtoms`
  * `FunctionalGroup`
  * `polymer` (boolean indicator)
* **Toxicological Properties:** `Exposure`, `HazardData`, `PhyschemProperty`, `SafetyData`
* **Environmental Fate and Transport:** * `hasBioconcentrationFactor` (BCF)
  * `hasBiodegradationHalfLife`
  * `hasAtmosphericHydroxylationRate`
  * `hasFishBiotransformationHalfLife`
  * `hasSoilAdsorptionCoefficient` ($K_{oc}$)
  * `hasReadyBiodegradability`
* **OPERA Properties:** Incorporates computational predictions and QSAR/QSPR model estimates for chemicals lacking experimental values.

## Technical Specifications
* **Format:** RDF, RDFS, OWL 2 DL
* **Metrics:** 71 classes, 18 data properties, 15 annotation properties, 752 total axioms (85 logical, 101 declaration).
* **Standards:** Incorporates XSD for data types, Dublin Core for metadata, and aligns with Linked Data principles. Constructed using the KNARM methodology and the ROBOT tool.

## Citation
If you use the DSSTox Ontology in your research, please cite the following paper:

> Zhang, Y., Moavenzadeh, S., Amjad, J., Apul, O., Barua, A., Evrendilek, F., Hahmann, T., Hettiarachchi, G., Hitzler, P., Kedrowski, D., Kilaru, V., Lashkari, P., Schweikert, K., Williams, A., & McGinty, H. (2026). **CompTox Ontology: Leveraging Knowledge Graphs for PFAS Monitoring and Decision-Making**. *Proceedings of the ACM Web Conference 2026 (WWW '26)*, 9352–9360. https://doi.org/10.1145/3774904.3792985
