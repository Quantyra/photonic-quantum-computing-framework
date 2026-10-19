# Contributing and citing

Propose focused corrections or additions with authoritative public component evidence. Keep this repository an index and integration guide; CAD, firmware and machine-specific G-code belong in their component repositories.

For a component addition or update, supply repository and exact release/source links, role, design versus packaging version, scoped licenses, compatibility assumptions, and a status that distinguishes CAD checks, user reports and measured validation. Add one entry to both the README table and `components.json`. Use `null` for unpublished DOI/release/source fields and explain the dependency. Never present a reserved DOI as published. Verify concept/version DOI relationships against the public archive record and release metadata before adding badges or links. Do not replace a release snapshot with current main.

Check relative Markdown links and anchors, component file paths at the selected revision, JSON parsing, unique component IDs, DOI agreement with the README, and exact license scope. Keep unmeasured compatibility and performance limitations visible. Do not include private experiments, local paths, raw correspondence or unpublished results.

## Citation

Use [CITATION.cff](CITATION.cff) for index authorship. Cite this index by title, repository URL, exact commit and access date; it currently has no DOI. Cite the component actually used separately. For example:

> Fredriksen, Daniel Eric. Quantyra photodiode jig, v11.1.2, design V11. Zenodo. https://doi.org/10.5281/zenodo.23449089. [single-port or dual-port], commit [exact SHA], [file paths], accessed [date].

The concept DOI identifies the release series; the version DOI identifies an exact archive. Record modifications, variant, source commit, relevant paths and print settings for reproducibility. For the released fixture, cite Quantyra optical fixture system, v1.0.1, Zenodo, https://doi.org/10.5281/zenodo.23485390, source commit `896505162a5071a4d7b6152c34f7ddb40a4cb497`, selected 34 mm or 32 mm stand, relevant paths and access date. Its concept DOI is https://doi.org/10.5281/zenodo.23484827. Index updates do not change the licenses or validation status of component archives.

Documentation here is CERN-OHL-S-2.0 under [LICENSE](LICENSE). Follow the authoritative component license for reused material, including the jig logger's separate AGPL-3.0-only terms. Open-source questions: info@quantyra.org; separate non-copyleft licensing inquiries: info@qxcellerate.com. Compliant commercial use is permitted.
