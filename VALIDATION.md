# Publication validation

Reviewed: 2026-09-17.

## Source

- Original author notebook: `Sprint 9 - Aprendizado Supervisionado.ipynb`.
- SHA-256 of the supplied source: `c2e1bae3ef12ee19866550f73b57bbe24ea38c8b2a5ada194d2520c822915d7c`.
- Publication does not imply that the full analysis was reexecuted.

## Changes

- Removed reviewer feedback, academic checklists and empty cells.
- Added data-directory resolution for execution from the repository root or notebooks folder.
- Removed raw customer preview output containing identifiers.
- Corrected the conclusion that compared F1 numerically with ROC-AUC.

## Checks

- Notebook JSON structure and Python code-cell syntax.
- Relative data paths, internal Markdown links and absence of reviewer feedback.
- Numeric claims traced to saved outputs; raw datasets excluded.

## Interpretation

Saved metrics come from the original notebook, not a fresh training run. The split is random and not stratified; one-hot categories were determined before splitting. Exact historical dependency versions are unavailable. F1 and ROC-AUC measure different properties and must not be compared numerically as competing scores. A deployment would need calibration, temporal validation, fairness checks and an intervention experiment.
