# FROID Terms

_Derived from the MODE_ONE and MODE_TWO node bodies by `collate_three_rs.py`; the bodies are the source of truth (see AGENTS.md). Do not edit by hand._

## [PYTHREAL] — 00-00-00.06-01-00.01-00-00

- T01: a [FRD_TOOL] tool realized under [PYTHREAL] is realized in [PYTHON]
- T02: [PYTHREAL] is the default configuration of [PYTHON]

## [BASHREAL] — 00-00-00.06-02-00.01-00-00

- T01: a [FRD_TOOL] tool realized under [BASHREAL] is realized in [BASH]
- T02: [BASHREAL] is the default configuration of [BASH]

## [RUSTREAL] — 00-00-00.06-03-00.01-00-00

- T01: a [FRD_TOOL] tool realized under [RUSTREAL] is realized in [RUST]
- T02: [RUSTREAL] is the default configuration of [RUST]

## [ERR_STD] — 00-00-00.07-01-00.01-00-00

- T01: a [FRD_TOOL] tool realized under [ERR_STD] outputs every error to standard error

## [FRD_BODY] — 00-01-00.04-01-00.03-00-00

- T01: <sctn> are defined by the child [FOLIO] of [FRD_BODY]
- T02: <sctn> must begin with [MARKDOWN] level-2 headings
- T03: When present, <sctn> must be in the following order: :E02
  1. [TO_DFNTN]
  2. [TO_RULES]
  3. [TO_TERMS]
  4. [TO_RSTRC]
  5. [TO_RCPRC]
  6. [TO_FAILS]
  7. [TO_EXMPL]
  8. [TO_NOTES]
- T04: an empty <sctn> is omitted
