# FROID Restrictions

_Derived from the MODE_ONE and MODE_TWO node bodies by `collate_three_rs.py`; the bodies are the source of truth (see AGENTS.md). Do not edit by hand._

## [NULL] — 00-00-00.08-01-00.00-00-00

- B01: a field is never unpopulated

## [GSYSHASH] — 00-00-00.08-02-00.00-00-00

- B01: [GSYSHASH] is not superseded
- B02: [GSYSHASH] does not carry a reciprocal of an [MF_SPRUP] reference, conditioning TO_RCPRC:A09

## [FROID_FS] — 00-01-00.00-00-00.00-00-00

- B01: a root [FRD_BODY] copy never differs from the root [FOLIO]'s [FRD_BODY]
- B02: a [NOD_BIN] of a leaf [NODE] not shared with a non-leaf [NODE] does not take `FF`, conditioning FROID_FS:A02

## [ND_SGMNT] — 00-01-00.01-02-00.01-01-00

- B01: [ND_SGMNT] never takes a value of all `F` :E04
- B02: <segwidth> never exceeds thirty-two hexadecimal digits :E06

## [NOD_TAG] — 00-01-00.01-02-00.02-00-00

- B01: a [NOD_TAG] never exceeds eight characters

## [NOD_BIN] — 00-01-00.01-03-00.03-00-00

- B01: an artifact filename or body-header never alters the [NOD_BIN] of the third [NOD_BLOK]

## [FOLIO] — 00-01-00.02-00-00.00-00-00

- B01: the content of a deposited [FOLIO] is never altered
- B02: a deposited [FOLIO] is never assigned a different [NODE_ID]
- B03: the namespace does not alter a [FOLIO]

## [FOL_DESC] — 00-01-00.02-01-00.02-00-00

- B01: a [FOL_DESC] [FLIO_ART] does not bind realization

## [FOL_REAL] — 00-01-00.02-01-00.03-00-00

- B01: a [FOL_REAL] [FLIO_ART] is not binding until the [OWN_OWNR] reviews it
- B02: a [FOL_REAL] [FLIO_ART] does not survive deposition

## [FOL_STRC] — 00-01-00.02-02-00.01-00-00

- B01: a [FOL_STRC] leaf [NODE] does not carry a [MODE_TWO]

## [FOL_OVLY] — 00-01-00.02-02-00.02-00-00

- B01: a [FOL_OVLY] [FLIO_ART] does not define namespace position

## [FLIO_ART] — 00-01-00.02-03-00.00-00-00

- B01: a [TYP_BLOB] artifact has no first available position for a [NODE_ID], conditioning A01

## [FOL_INDX] — 00-01-00.02-03-00.06-00-00

- B01: a [NODE_ID] is never removed from [FOL_INDX]
- B02: the [NOD_TAG] of a [NODE_ID] in [FOL_INDX] is never changed
- B04: no entry in [FOL_INDX] is ever erased, even on supersession
- B05: a [NOD_TAG] listed in neither the root [FOLIO]'s [FOL_INDX] nor the [FOL_INDX] of a [NODE] a listed chain reaches is never valid

## [MODE_TRE] — 00-01-00.03-03-00.00-00-00

- B01: [MODE_TRE] is not a [FRD_BODY]
- B02: [MODE_TRE] does not alter the [MODE_ONE] or [MODE_TWO] it realizes
- B03: a [MODE_TRE] [FLIO_ART] does not bind a subsequent realization

## [TYPE] — 00-01-00.04-00-00.00-00-00

- B01: a [TYP_BLOB] has no first available position for its [NODE_ID], conditioning A01

## [FRD_SMRY] — 00-01-00.04-01-00.01-00-00

- B01: [FRD_SMRY] does not bind realization
- B02: [FRD_SMRY] does not contain rules, terms, or restrictions
- B03: a [FRD_SMRY] is not a [FRD_BODY]

## [FRD_MFST] — 00-01-00.04-01-00.02-00-00

- B01: a [FRD_MFST] field value does not contain whitespace

## [MF_LOCUS] — 00-01-00.04-01-00.02-03-00

- B01: [MF_LOCUS] does not assert the [FLIO_LCS] of a [MODE_TRE] [FLIO_ART]

## [MF_SPRUP] — 00-01-00.04-01-00.02-07-00

- B01: [MF_SPRUP] is not empty
- B02: [MF_SPRUP] does not list [GSYSHASH] with a superseded [FOLIO]

## [MF_HSHID] — 00-01-00.04-01-00.02-08-00

- B01: [MF_HSHID] does not hash all fields in [FRD_MFST]

## [MF_ARFCT] — 00-01-00.04-01-00.02-09-00

- B01: [MF_ARFCT] does not list a [FOL_INDX]
- B02: [MF_ARFCT] does not list a [FOL_MFST]
- B03: [MF_ARFCT] does not list a [FRD_ADR]

## [MF_HSHAR] — 00-01-00.04-01-00.02-10-00

- B01: [MF_HSHAR] does not hash all fields in [FRD_MFST]

## [MF_HSHSP] — 00-01-00.04-01-00.02-12-00

- B01: [MF_HSHSP] does not hash all fields in [FRD_MFST]

## [TO_DFNTN] — 00-01-00.04-01-00.03-01-00

- B01: [TO_DFNTN] does not contain rules, restrictions, or reciprocals :E01
- B02: [TO_DFNTN] does not describe what [NODE] does :E01

## [TO_RULES] — 00-01-00.04-01-00.03-02-00

- B01: Each rule combines no more than one assertion
- B02: Each rule may not contain restrictions
- B03: Each rule states no condition beyond a conditioning citation

## [TO_RSTRC] — 00-01-00.04-01-00.03-03-00

- B01: Each constraint combines no more than one assertion
- B02: Each constraint may not contain rules
- B03: a restriction does not require a [TO_RCPRC] reciprocal

## [TO_RCPRC] — 00-01-00.04-01-00.03-04-00

- B01: a reciprocal does not restate the referenced rule

## [TO_TERMS] — 00-01-00.04-01-00.03-08-00

- B01: Each term combines no more than one assertion

## [FRD_ADR] — 00-01-00.04-01-00.04-00-00

- B01: [FRD_ADR] does not bind realization
- B02: [FRD_ADR] does not contain rules or restrictions
- B03: a [FRD_ADR] is not a [FLIO_ART]

## [FRD_BUG] — 00-01-00.04-01-00.05-00-00

- B01: [FRD_BUG] is non-normative and does not bind realization
- B02: [FRD_BUG] does not contain rules or restrictions

## [FRD_INDX] — 00-01-00.04-01-00.06-00-00

- B01: no two [FRD_INDX] entries share a [NOD_TAG]
- B02: no [NOD_TAG] is `mf_nodid` or `mf_hshix`

## [TYP_CSV] — 00-01-00.04-02-00.03-00-00

- B01: [TYP_CSV] does not use backslash escapes
- B02: [TYP_CSV] does not contain blank lines
- B03: [TYP_CSV] does not contain comment lines
- B04: [TYP_CSV] does not begin with a byte order mark
- B05: [TYP_CSV] does not contain a line break within a field, overriding [CSV]

## [TYP_PYTH] — 00-01-00.04-02-00.04-00-00

- B01: [TYP_PYTH] does not begin with a shebang
- B02: [TYP_PYTH] does not declare a [PYTHON] encoding declaration

## [TYP_BLOB] — 00-01-00.04-02-00.08-00-00

- B01: [TYP_BLOB] has no governing external standard

## [TIM_TIME] — 00-01-00.05-02-00.01-00-00

- B01: a sign is never other than `01` or `02`
- B03: [TIM_TIME] does not attest the time it encodes
- B04: the [TIM_TIME] encoding never exceeds twelve decimal digits

## [OWN_OWNR] — 00-01-00.05-03-00.01-00-00

- B01: [OWN_OWNR] does not authenticate a person or agent
- B02: an [OWN_OWNR] does not authorize a deposition

## [FRD_TOOL] — 00-02-00.00-00-00.00-00-00

- B01: a [FRD_TOOL] tool's validation does not alter the namespace
- B02: a [FRD_TOOL] tool does not execute the content of a [FOLIO]
