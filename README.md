# Photonic Quantum Computing Framework

A public component index and integration guide for modular optical hardware and fixed-source photodiode commissioning toward future quantum-photonics experiments. Start with the [integration guide](docs/getting-started.md) to combine a photodiode jig, source fixture and ambient hood on a fixed board.

Current evidence covers component design and reported printing; optical and quantum performance remain unvalidated.

## Component master index

| Component / role | Version and source | Concept DOI (all versions) | Version DOI (exact archive) | License and compatibility | Status |
| --- | --- | --- | --- | --- | --- |
| [Photodiode jig](https://github.com/Quantyra/photodiode-jig): fixed single/dual detector holder, shutters and Arduino reference readout | [v11.1.2 release](https://github.com/Quantyra/photodiode-jig/releases/tag/v11.1.2), [V11 source snapshot](https://github.com/Quantyra/photodiode-jig/tree/d7c9fc1ea49c0633ac80b1acda1bc9f219ac0a4f) | [10.5281/zenodo.23449088](https://doi.org/10.5281/zenodo.23449088) | [10.5281/zenodo.23449089](https://doi.org/10.5281/zenodo.23449089) | Hardware/docs CERN-OHL-S-2.0; Arduino AGPL-3.0-only. Fixture cradle targets dual V11, 44 mm fixed body / 10 mm port pitch | Released; both variants reported printed; fit report applies to user's dual-port diodes only. Optical performance unvalidated |
| [Optical fixture system](https://github.com/Quantyra/optical-fixture-system): source stand, dual-jig cradle and lift-off hood | [v1.0.1 release](https://github.com/Quantyra/optical-fixture-system/releases/tag/v1.0.1), [source snapshot](https://github.com/Quantyra/optical-fixture-system/tree/896505162a5071a4d7b6152c34f7ddb40a4cb497) | [10.5281/zenodo.23484827](https://doi.org/10.5281/zenodo.23484827) | [10.5281/zenodo.23485390](https://doi.org/10.5281/zenodo.23485390) | CAD, meshes, G-code/docs CERN-OHL-S-2.0; nominal 20 mm optical axis with seated dual V11; actual component fit requires checking | Released; assembled hood fit and shielding pending. User reports hood printing well after PETG profile correction |

[components.json](components.json) is the machine-readable catalogue. Packaging **v11.1.2** retains design **V11**; the jig's later main branch is not the archived release snapshot. Fixture v1.0.1 is published with its exact source snapshot and [verified Zenodo archive](https://zenodo.org/records/23485390); publication does not establish physical validation.

## Use this index

1. Read the [getting-started and integration guide](docs/getting-started.md), including BOM, print orientations, wiring references and commissioning checks.
2. Obtain fixture parts from its [print and assembly guide](https://github.com/Quantyra/optical-fixture-system/blob/896505162a5071a4d7b6152c34f7ddb40a4cb497/docs/print-and-assembly.md), [STLs](https://github.com/Quantyra/optical-fixture-system/tree/896505162a5071a4d7b6152c34f7ddb40a4cb497/stl) and [G-code notes](https://github.com/Quantyra/optical-fixture-system/blob/896505162a5071a4d7b6152c34f7ddb40a4cb497/gcode/README.md). Prefer the 34 mm stand for the 44 - 10 mm edge-alignment rule. Current stand G-code is dimensionally consistent with the preferred 34 mm stand; exact source slicing is not established. The supported 32 mm narrow STL has no current G-code and requires re-slicing and separately measured lateral placement. This index does not redistribute firmware or G-code.
3. Record the exact component version, commit, variant and paths used. Cite each component archive as well as this guide where relevant; see [citation and contribution instructions](CONTRIBUTING.md).

## Licensing and contact

This index and its documentation are released under [CERN-OHL-S-2.0](LICENSE). Source Location: https://github.com/Quantyra/photonic-quantum-computing-framework. Component licenses remain authoritative: the jig's Arduino code is separately AGPL-3.0-only; these licenses apply to different materials, not as interchangeable choices. Commercial use is permitted when the applicable license requirements are followed.

- Open-source licensing: [info@quantyra.org](mailto:info@quantyra.org).
- Separate non-copyleft commercial licensing inquiries: [info@qxcellerate.com](mailto:info@qxcellerate.com). A separate license requires a written grant from a party with authority; an inquiry grants no rights.

[CITATION.cff](CITATION.cff) describes this index. No DOI is assigned to the index here.
