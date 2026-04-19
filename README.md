# comptox-ontology (DSSTox Ontology)

> **Important Naming Notice:** Following expert review and to accurately reflect its foundation on the DSSTox database, this ontology is officially named the **DSSTox Ontology**. The GitHub repository retains the `comptox-ontology` name and namespace strictly to preserve the functional links and URIs cited in our published proceedings.

## Overview
The DSSTox Ontology provides an expert-guided, semantically structured representation for chemicals, with a specific focus on Per- and Polyfluoroalkyl Substances (PFAS) and their properties. Developed as part of the SAWGraph project, it is designed to support integrated environmental contaminant monitoring, data querying, and decision-making by linking chemical identities with their physicochemical, toxicological, and environmental fate properties.

## Repository Structure & Versioning
The active, current release of the ontology is located in the **`V2`** directory. 

All other directories (`v0`, `v0.1`, `v1`, `old`) contain deprecated previous versions. As detailed in our methodology, all development artifacts are retained in this repository for version control purposes. This provides transparent change tracking and supports collaborative development across institutions and external contributors.

## Ontology Structure & Taxonomy
The ontology is anchored under the `owl:Thing` root class, with the core semantic model centering on the `ChemicalEntity` and `PFAS` classes. It relies on a well-defined taxonomy using the `<http://w3id.org/pfas/v2/>` and `<http://w3id.org/DSSTox/v2/>` namespaces.

### 1. The PFAS Taxonomy
Organizes PFAS compounds into distinct structural subclasses that influence their environmental fate and transport:

* **`PerFAS` (Perfluoroalkyl substances)**
  * **`PFAAs` (Perfluoroalkyl acids)**
    * `PFCA` (Perfluoroalkyl carboxylic acids) - *e.g., PFOA, PFNA, PFDA*
    * `PFSA` (Perfluoroalkyl sulfonic acids) - *e.g., PFOS, PFHxS*
  * **`PFEAs` (Perfluoroalkyl ether acids)**
    * `PFECA` (Perfluoroalkyl ether carboxylic acids)
    * `PFESA` (Perfluoroalkyl ether sulfonic acids)
  * **`FASAs` (Perfluoroalkane sulfonamido substances)**
    * `N-EtFASA` (N-Ethyl perfluoroalkane sulfonamides)
    * `N-EtFASAA` (N-Ethyl perfluoroalkane sulfonamido acetic acids)
    * `N-MeFASA` (N-Methyl perfluoroalkane sulfonamides)
    * `N-MeFASAA` (N-Methyl perfluoroalkane sulfonamido acetic acids)
  * **`FASAa` (Perfluoroalkane sulfonamides)** * **`PolyFAS` (Polyfluoroalkyl substances)**
  * **`FTs` (Fluorotelomer substances)**
    * `FTCA` (Fluorotelomer carboxylic acids)
    * `FTSA` (Fluorotelomer sulfonic acids)

### 2. Characteristic Properties (`PFASDescriptor`)
The ontology links chemicals to comprehensive molecular characterization data:
* `CarbonChainLength`
* `FunctionalGroup`
* `NumberOfFluorineAtoms`
* `polymer` (boolean indicator)

### 3. Chemical Identifiers & Core Data
Individual PFAS entities (e.g., `DTXSID8031865` for PFOA) are heavily annotated with standard identifiers and exact chemical counts:
* `hasDTXSID`, `hasCASRN`, `hasInChIKey`, `hasSMILES`, `hasPubChemCID`
* `hasAverageMass`
* `hasNumberOfCarbonAtoms`, `hasNumberOfC-Cbonds`, `hasNumberOfC-Fbonds`

### 4. Toxicological & Environmental Properties
Captures data directly aligned with the EPA CompTox Chemicals Dashboard.

* **`ToxicologicalProperty` Classes:** `Exposure`, `HazardData`, `PhyschemProperty`, `SafetyData`
* **`ExposureData` Properties:** `biomonitoringData`, `chemicalFunctionalUse`, `chemicalWeightFraction`, `exposurePredictions`, `productAndUseCategories`, `productionVolume`, `toxicsReleaseInventory`
* **`EnvironmentalFateAndTransportProperty` Properties:** * `atmosphericHydroxylationRate`
  * `bioconcentrationFactor`
  * `biodegradationHalfLife`
  * `fishBiotransformationHalfLifeKm`
  * `readyBiodegradability`
  * `soilAdsorptionCoefficientKoc`
* **`OPERAProperty`:** Incorporates computational predictions and QSAR/QSPR model estimates for chemicals lacking experimental values.

## Technical Specifications
* **Format:** RDF, RDFS, OWL 2 DL
* **Metrics:** 71 classes, 18 data properties, 15 annotation properties, 752 total axioms (85 logical, 101 declaration).
* **Standards & Tooling:** Incorporates XSD for data types, Dublin Core for metadata, and aligns with Linked Data principles. Constructed using the [KNARM methodology](#references) and automated via the [ROBOT tool](#references).

## Citation
If you use the DSSTox Ontology in your research, please cite the following paper:

> Zhang, Y., Moavenzadeh, S., Amjad, J., Apul, O., Barua, A., Evrendilek, F., Hahmann, T., Hettiarachchi, G., Hitzler, P., Kedrowski, D., Kilaru, V., Lashkari, P., Schweikert, K., Williams, A., & McGinty, H. (2026). **CompTox Ontology: Leveraging Knowledge Graphs for PFAS Monitoring and Decision-Making**. *Proceedings of the ACM Web Conference 2026 (WWW '26)*, 9352–9360. https://doi.org/10.1145/3774904.3792985

## References

**Methodology:**
* McGinty, H. K. (2020). *KNowledge Acquisition and Representation Methodology (KNARM)* [Doctoral dissertation, University of Miami]. Scholarship@Miami. https://scholarship.miami.edu/esploro/outputs/doctoral/KNowledge-Acquisition-and-Representation-Methodology-KNARM/991031447865202976

**Tooling:**
* Jackson, R. C., Balhoff, J. P., Douglass, E., Harris, N. L., Mungall, C. J., & Overton, J. A. (2019). ROBOT: A Tool for Automating Ontology Workflows. *BMC Bioinformatics*, 20(1), 407. https://doi.org/10.1186/s12859-019-3002-3 | [GitHub Repository](https://github.com/ontodev/robot)
