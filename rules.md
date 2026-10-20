# FROID Rules

_Derived from the MODE_ONE and MODE_TWO node bodies by `collate_three_rs.py`; the bodies are the source of truth (see AGENTS.md). Do not edit by hand._

## [SYSROOT] — 00-00-00.00-00-00.00-00-00

- A01: [SYSROOT] catalogs the namespace

## [PROJTIME] — 00-00-00.01-00-00.00-00-00

- A01: [PROJTIME] carries the [TIME] catalog

## [TIME] — 00-00-00.01-01-00.00-00-00

- A01: [TIME] catalogs encoded times

## [PROJOWN] — 00-00-00.02-00-00.00-00-00

- A01: [PROJOWN] carries the [OWNER] catalog

## [OWNER] — 00-00-00.02-01-00.00-00-00

- A01: [OWNER] catalogs owner records

## [FILEHAND] — 00-00-00.04-00-00.00-00-00

- A01: [FILEHAND] catalogs file handling standards

## [MARKDOWN] — 00-00-00.04-01-00.00-00-00

- A01: [MARKDOWN] is defined by CommonMark 0.31.2

## [YAML] — 00-00-00.04-02-00.00-00-00

- A01: [YAML] is defined by YAML 1.2.2

## [CSV] — 00-00-00.04-03-00.00-00-00

- A01: [CSV] is defined by RFC 4180

## [EXTSPECS] — 00-00-00.05-00-00.00-00-00

- A01: [EXTSPECS] catalogs external specifications

## [SHA256] — 00-00-00.05-01-00.00-00-00

- A01: [SHA256] is defined by FIPS 180-4
- A02: a [SHA256] digest is written as lowercase hexadecimal
- A03: a [SHA256] digest is 64 hexadecimal characters

## [UTF8] — 00-00-00.05-02-00.00-00-00

- A01: [UTF8] is defined by RFC 3629

## [MKDNLINT] — 00-00-00.05-03-00.00-00-00

- A01: [MKDNLINT] is defined by markdownlint 0.37

## [X660] — 00-00-00.05-04-00.00-00-00

- A01: [X660] is defined by ITU-T X.660

## [UNIXRTRN] — 00-00-00.05-05-00.00-00-00

- A01: [UNIXRTRN] is defined by POSIX.1-2017
- A02: a [UNIXRTRN] status of 0 signals success
- A03: a [UNIXRTRN] status other than 0 signals failure
- A04: a [UNIXRTRN] status is an integer from 0 through 255

## [UNIXTIME] — 00-00-00.05-06-00.00-00-00

- A01: [UNIXTIME] is defined by POSIX.1-2017

## [LANGDEFS] — 00-00-00.06-00-00.00-00-00

- A01: [LANGDEFS] catalogs language definitions
- A02: the first-position configuration of a language is its default

## [PYTHON] — 00-00-00.06-01-00.00-00-00

- A01: [PYTHON] is defined by Python 3.14
- A02: [PYTHON] catalogs configurations

## [BASH] — 00-00-00.06-02-00.00-00-00

- A01: [BASH] is defined by Bash 5.2
- A02: [BASH] catalogs configurations

## [RUST] — 00-00-00.06-03-00.00-00-00

- A01: [RUST] is defined by Rust 1.85
- A02: [RUST] catalogs configurations

## [EGO_OPTS] — 00-00-00.07-00-00.00-00-00

- A01: [EGO_OPTS] catalogs option categories

## [ERRORS] — 00-00-00.07-01-00.00-00-00

- A01: [ERRORS] catalogs error handling options

## [NULLVALS] — 00-00-00.08-00-00.00-00-00

- A01: [NULLVALS] catalogs the values of absence

## [NULL] — 00-00-00.08-01-00.00-00-00

- A01: [NULL] reads `null`

## [GSYSHASH] — 00-00-00.08-02-00.00-00-00

- A01: [GSYSHASH] is the [SHA256] of no input
- A02: [GSYSHASH] is `e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855`

## [FROID_FS] — 00-01-00.00-00-00.00-00-00

- A01: in [FROID_FS] a [NOD_CSTR] directory without a [FOLIO] takes the name of the [ND_SGMNT] at its position in the [NODE_ID]
- A02: in [FROID_FS] directories representing [NOD_BIN] take `FF` as their name
- A03: in [FROID_FS] a [NOD_CSTR] directory with a [FOLIO] has its name in the format: {ND_SGMNT}-{NOD_TAG}
- A04: [FROID_FS] catalogs the grammar
- A09: a zero [ND_SGMNT] directory in series with the root carries a copy of the root [FOLIO]'s [FRD_BODY]
- A10: in [FROID_FS] a non-trailing [NOD_BIN] of a leaf [NODE] not shared with a non-leaf [NODE] takes its value as its name
- A11: in [FROID_FS] a trailing zero [ND_SGMNT] of a [NODE_ID] takes no directory
- A12: in [FROID_FS] the trailing [NOD_BIN] of a [NODE_ID] takes no directory
- A13: [FROID_FS] stores a projection of at least one [NOD_BLOK]
- A14: the first [NOD_BLOK] of a [NODE_ID] is constructed of the namespace root [ND_SGMNT], the projection [ND_SGMNT], any projection-defined [ND_SGMNT], and the [MODE] [NOD_BIN]
- A15: the second [NOD_BLOK] of a [NODE_ID] is the root [NOD_BLOK] of its projection

## [NODE] — 00-01-00.01-00-00.00-00-00

- A01: [NODE] catalogs identifier grammar

## [NODE_ID] — 00-01-00.01-02-00.00-00-00

- A01: [NODE_ID] may have any number of associated [NOD_TAG]
- A02: [NODE_ID] requires zero or one associated [FOLIO]
- A03: a [NODE_ID] without [FOLIO] is a reference point, and may be a placeholder for a future [FOLIO]
- A04: [NODE_ID] separates each [NOD_BLOK] with `.`
- A05: a [NODE_ID] converts to an [X660] object identifier
- A06: the conversion renders each hexadecimal value as a decimal arc
- A07: the conversion normalizes `-` and `.` to `.`
- A08: [NODE_ID] catalogs id parts

## [NOD_BLOK] — 00-01-00.01-02-00.01-00-00

- A01: [NOD_BLOK] catalogs block parts
- A04: [NOD_BLOK] separates each [ND_SGMNT] with `-`
- A05: <blkwidth> is determined at projection instantiation
- A06: <bins> is determined at projection instantiation
- A07: a [NOD_BLOK] closes with <bins> [NOD_BIN]
- A08: every [ND_SGMNT] before the closing [NOD_BIN] is a [NOD_CSTR]
- A09: <bins> is one or more [NOD_BIN]
- A10: <blkwidth> exceeds <bins>

## [ND_SGMNT] — 00-01-00.01-02-00.01-01-00

- A01: <segwidth> is two or more hexadecimal digits :E01
- A02: a [ND_SGMNT] is an uppercase hexadecimal value :E01
- A03: <segwidth> is determined at namespace instantiation

## [NOD_TAG] — 00-01-00.01-02-00.02-00-00

- A01: [NOD_TAG] maps to one and only one [NODE_ID]
- A02: a [NOD_TAG] is chosen for a [NODE], not derived from its [NODE_ID]
- A03: a [NOD_TAG] is composed of capital letters, digits, and underscores

## [NODE_FNC] — 00-01-00.01-03-00.00-00-00

- A01: [NODE_FNC] catalogs segment functions

## [NOD_CSTR] — 00-01-00.01-03-00.02-00-00

- A01: [NOD_CSTR] increases from a parent [NODE] to its child
- A02: sibling [NODE]s take distinct [NOD_CSTR] values
- A03: a leaf [NODE] has no child [NOD_CSTR]

## [NOD_BIN] — 00-01-00.01-03-00.03-00-00

- A01: the [NOD_BIN] of the first [NOD_BLOK] classifies the [MODE]
- A02: the [NOD_BIN] of the second [NOD_BLOK] classifies the [TYPE_FRD]
- A04: a [NOD_BIN] of `00` is unused
- A05: the body-header [NODE_ID] sets the [NOD_BIN] of the first and second [NOD_BLOK] to `00`
- A06: an artifact filename sets the [NOD_BIN] of the first [NOD_BLOK] to the artifact's [MODE]
- A07: an artifact filename sets the [NOD_BIN] of the second [NOD_BLOK] to the artifact's [TYPE_FRD]
- A11: a [MODE] or [TYPE_FRD] classification code is its [NOD_CSTR] value
- A13: the catalog a [NOD_BIN] selects from beyond the second [NOD_BLOK] is assigned by its projection
- A14: an artifact of a [TYPE_FRD] that is not [FRD_BODY] or [FRD_MISC] sets the [NOD_BIN] of the first [NOD_BLOK] to `00`
- A15: a [FRD_MISC] artifact filename sets the [NOD_BIN] of the first [NOD_BLOK] to [MODE_ONE] or [MODE_TRE]

## [FOLIO] — 00-01-00.02-00-00.00-00-00

- A03: [FOLIO] may have zero or one [FOL_INDX]
- A04: [FOLIO] requires one and only one [FOL_MFST]
- A05: [FOLIO] requires one [FOL_TYPE] of [FRD_BODY] of [MODE_ONE] or [MODE_TWO]
- A07: [FOLIO] may have zero or more additional [FLIO_ART]
- A08: [FOLIO] has at most one [FOL_TYPE] of [FRD_BODY] for each of [MODE_ONE] and [MODE_TWO]
- A01: an undeposited [FOLIO] may be revised
- A02: an undeposited [FOLIO] may be assigned a different [NODE_ID]
- A09: a [FOLIO] enters the namespace at deposition
- A10: [FOLIO] requires one and only one [FOL_TYPE] of [FRD_SMRY]

## [FLIO_LCS] — 00-01-00.02-01-00.00-00-00

- A01: [FLIO_LCS] is one of [FOL_NORM], [FOL_DESC], or [FOL_REAL]

## [FOL_NORM] — 00-01-00.02-01-00.01-00-00

- A01: a [FOL_NORM] [FLIO_ART] binds realization

## [FOL_DESC] — 00-01-00.02-01-00.02-00-00

- A01: a [FOL_DESC] [FLIO_ART] is authored outside the namespace

## [FOL_REAL] — 00-01-00.02-01-00.03-00-00

- A01: a [FOL_REAL] [FLIO_ART] is raised by the [OWN_OWNR] over a [FOL_NORM] or a [FOL_DESC]
- A02: a [FOL_REAL] [FLIO_ART] records a realization decision that no existing [FOLIO] specifies
- A03: a [FOL_REAL] [FLIO_ART] is a placeholder awaiting [OWN_OWNR] review
- A04: a [FOL_REAL] [FLIO_ART] covers the realization decisions that depend on it
- A05: a [FOL_REAL] [FLIO_ART] may be promoted to a [FOL_NORM] at deposition
- A06: a [FOL_REAL] [FLIO_ART] may be deposited as a [FOL_BUG]
- A07: a [FOL_REAL] [FLIO_ART] may be discarded at deposition
- A08: a [FOL_REAL] [FLIO_ART] deposited as a [FOL_BUG] records a decision observable at a [MODE_TWO]
- A09: a [FOL_REAL] [FLIO_ART] is a [MODE_TRE] [FRD_BODY], conditioning [MODE_TRE]:B01
- A10: a [FOL_REAL] [FLIO_ART] resides in the directory of the [FOLIO] it is raised over, conditioning [MODE_TRE]:A05

## [FLIO_TCH] — 00-01-00.02-02-00.00-00-00

- A01: [FLIO_TCH] is one of [FOL_STRC] or [FOL_OVLY]

## [FOL_STRC] — 00-01-00.02-02-00.01-00-00

- A01: a [FOL_STRC] [FLIO_ART] fixes the position of its [NODE] in the namespace
- A02: a [FOL_STRC] [NODE] requires a [FOLIO]

## [FOL_OVLY] — 00-01-00.02-02-00.02-00-00

- A01: a [FOL_OVLY] [FLIO_ART] applies to a [NODE] regardless of its position in the namespace
- A02: a [FOL_OVLY] [NODE] carries a [MODE_TWO] and no [MODE_ONE]
- A03: a [FOL_OVLY] [MODE_TWO] governs realization from outside the [NODE]'s own spec
- A04: a [FOL_OVLY] [FLIO_ART] binds only the realization it is selected for, conditioning [FOL_NORM]:A01

## [FLIO_ART] — 00-01-00.02-03-00.00-00-00

- A01: every [FLIO_ART] declares its [NODE_ID] in the first available position
- A02: every [FLIO_ART] is either [FOL_BUG], [FOL_INDX], [FOL_MFST], or [FOL_TYPE]

## [FOL_MFST] — 00-01-00.02-03-00.02-00-00

- A01: [FOL_MFST] is defined by [FRD_MFST]

## [FOL_TYPE] — 00-01-00.02-03-00.03-00-00

- A01: a [FOL_TYPE] of [FRD_BODY] is defined by [FRD_BODY]
- A02: a [FOL_TYPE] of [FRD_SMRY] is defined by [FRD_SMRY]
- A03: a [FOL_TYPE] of [FRD_MISC] is defined by [FRD_MISC]

## [FOL_BUG] — 00-01-00.02-03-00.05-00-00

- A01: [FOL_BUG] is defined by [FRD_BUG]

## [FOL_INDX] — 00-01-00.02-03-00.06-00-00

- A01: [FOL_INDX] is defined by [FRD_INDX]
- A07: each [NODE_ID] in [FOL_INDX] is unique
- A08: a [NODE_ID] is added to [FOL_INDX] without superseding the [FOLIO]
- A09: every [NOD_TAG] below a [FOL_INDX]'s [FOLIO] is listed in it or in the [FOL_INDX] of a [NODE] it lists
- A10: a namespace root [FOLIO] carries a [FOL_INDX]
- A11: a [FOL_INDX] lists the [NOD_TAG] of its own [FOLIO]

## [MODE] — 00-01-00.03-00-00.00-00-00

- A01: [MODE] catalogs modes
- A04: a [MODE] may take any [TYPE_TYP]

## [MODE_ONE] — 00-01-00.03-01-00.00-00-00

- A03: a [MODE_ONE] [FRD_BODY] takes precedence over any other [FLIO_ART] of its [NODE]
- A04: the [MODE_ONE] [TO_DFNTN] takes precedence over the [MODE_TWO] [TO_DFNTN] of its [NODE]
- A05: a [FRD_BODY] of [MODE_ONE] uses [TO_RULES] in place of [TO_TERMS]

## [MODE_TWO] — 00-01-00.03-02-00.00-00-00

- A02: a [MODE_TWO] may restate an aspect of its [MODE_ONE]
- A03: a [MODE_TWO] exposes the contract surface of the [MODE_ONE] of its [NODE]
- A04: more than one [MODE_TWO] may overlay one [MODE_ONE]
- A05: a [MODE_TWO] with no [MODE_ONE] is the interface of a [FOL_OVLY] [NODE]
- A06: a [MODE_TWO] tolerates leakage across the seam
- A07: a [MODE_TWO] [TO_DFNTN] matches the [MODE_ONE] [TO_DFNTN] of its [NODE]
- A08: a [FRD_BODY] of [MODE_TWO] uses [TO_TERMS] in place of [TO_RULES]
- A09: a [FRD_BODY] of [MODE_TWO] takes zero or one [TO_RSTRC]

## [MODE_TRE] — 00-01-00.03-03-00.00-00-00

- A01: [MODE_TRE] realizes the [MODE_ONE] and any [MODE_TWO] of a [NODE]
- A02: [MODE_TRE] shares the [NODE_ID] of the [MODE_ONE] and [MODE_TWO] it realizes
- A03: a decision in [MODE_TRE] not specified by [MODE_ONE] or [MODE_TWO] is covered by a [FOL_REAL]
- A05: a [MODE_TRE] [FLIO_ART] is outside the namespace
- A06: a canonical [MODE_TRE] [FLIO_ART] is picked by the [OWN_OWNR]

## [TYPE] — 00-01-00.04-00-00.00-00-00

- A01: Each [TYPE_TYP] must have a reference to its [NODE_ID] in the first available position
- A02: [TYPE] catalogs type families

## [TYPE_FRD] — 00-01-00.04-01-00.00-00-00

- A01: [TYPE_FRD] catalogs defined artifact kinds

## [FRD_SMRY] — 00-01-00.04-01-00.01-00-00

- A01: [FRD_SMRY] is defined by [TYP_MKDN]
- A02: a [FRD_SMRY] is realized from the [FLIO_ART] of its [FOLIO]
- A03: a [FRD_SMRY] states the identity of its [NODE] in prose

## [FRD_MFST] — 00-01-00.04-01-00.02-00-00

- A01: [FRD_MFST] must contain in this order [MF_NODID], [MF_NODTG], [MF_LOCUS], [MF_ATCH], [MF_OWNER], [MF_DEPST], [MF_SPRUP], [MF_HSHID]
- A02: [FRD_MFST] may also contain in this order [MF_ARFCT], [MF_HSHAR], [MF_SPRDN], [MF_HSHSP]
- A03: [FRD_MFST] is created with its [SHA256] fields reading [NULL]
- A04: [FRD_MFST] writes its [SHA256] fields at deposition
- A05: a [FRD_MFST] writes [MF_SPRDN] and [MF_HSHSP] at supersession
- A06: a [FRD_MFST]'s terminal [SHA256] is [MF_HSHID] and following [MF_HSHAR] and following [MF_HSHSP]
- A07: [FRD_MFST] is defined by `{NOD_TAG}.yaml`
- A08: [FRD_MFST] is defined by [TYP_YAML]

## [MF_NODID] — 00-01-00.04-01-00.02-01-00

- A01: [MF_NODID] must be a valid [NODE_ID]

## [MF_NODTG] — 00-01-00.04-01-00.02-02-00

- A01: [MF_NODTG] must be a valid [NOD_TAG]

## [MF_LOCUS] — 00-01-00.04-01-00.02-03-00

- A01: [MF_LOCUS] must be a valid [FLIO_LCS]
- A02: [MF_LOCUS] asserts the [FLIO_LCS] of the [FOLIO]'s [MODE_ONE] and [MODE_TWO] [FLIO_ART]

## [MF_ATCH] — 00-01-00.04-01-00.02-04-00

- A01: [MF_ATCH] must be a valid [FLIO_TCH]

## [MF_OWNER] — 00-01-00.04-01-00.02-05-00

- A01: [MF_OWNER] resolves to a [OWN_OWNR] cataloged by the namespace root of the [FOLIO]

## [MF_DEPST] — 00-01-00.04-01-00.02-06-00

- A01: [MF_DEPST] resolves to a [TIM_TIME] cataloged by the namespace root of the [FOLIO]
- A02: an undeposited [FOLIO]'s [MF_DEPST] carries a placeholder [TIM_TIME]

## [MF_SPRUP] — 00-01-00.04-01-00.02-07-00

- A01: [MF_SPRUP] must be a list of valid [NODE_ID]
- A02: a [FOLIO] superseded in [MF_SPRUP] lists this [FOLIO] in its [MF_SPRDN]
- A03: [MF_SPRUP] lists superseded [FOLIO] or [GSYSHASH]

## [MF_HSHID] — 00-01-00.04-01-00.02-08-00

- A01: [MF_HSHID] is [SHA256]
- A02: [MF_HSHID] hashes, each value line feed terminated, the text values of the following fields in order:
  1. mf_nodid
  2. mf_nodtg
  3. mf_locus
  4. mf_atch
  5. mf_owner
  6. mf_depst
  7. mf_sprup

## [MF_ARFCT] — 00-01-00.04-01-00.02-09-00

- A01: [MF_ARFCT] is a list of [FLIO_ART] each followed by the [SHA256] of its content
- A02: every [FLIO_ART] of [FRD_BODY] precedes every other [FLIO_ART] in [MF_ARFCT]
- A03: [MF_ARFCT] orders its [FLIO_ART] of [FRD_BODY] by ascending filename [NODE_ID]
- A04: [MF_ARFCT] requires a following [MF_HSHAR]

## [MF_HSHAR] — 00-01-00.04-01-00.02-10-00

- A01: [MF_HSHAR] is [SHA256]
- A02: [MF_HSHAR] hashes the prior [SHA256] then, for each [FLIO_ART] in [MF_ARFCT] order, its filename and its content [SHA256], every value line feed terminated

## [MF_SPRDN] — 00-01-00.04-01-00.02-11-00

- A01: [MF_SPRDN] must be a list of valid [NODE_ID]
- A02: [MF_SPRDN] requires a following [MF_HSHSP]

## [MF_HSHSP] — 00-01-00.04-01-00.02-12-00

- A01: [MF_HSHSP] is [SHA256]
- A02: [MF_HSHSP] hashes, each value line feed terminated, the following in order:
  1. the [SHA256] from [MF_HSHID] and following [MF_HSHAR]
  2. the [NODE_ID] of each [FOLIO] that supersedes this [FOLIO]

## [FRD_BODY] — 00-01-00.04-01-00.03-00-00

- A01: [FRD_BODY] is defined by [TYP_MKDN]
- A02: a parameter another [NODE] sets is written in angle brackets `<>` :E01
- A03: [FRD_BODY] has one or more <sctn> :E02
- A04: [FRD_BODY] begins with <sctn> defined by [TO_DFNTN]
- A05: a [FRD_BODY] declares its [SHA256] as a level-2 [MARKDOWN] heading
- A06: a [FRD_BODY] declares its [SHA256] in its third line :E03
- A07: the [SHA256] of a [FRD_BODY] hashes it as stored from the first <sctn> heading to its end
- A09: a [FRD_BODY] with at least one [TO_RULES], [TO_RSTRC], [TO_TERMS], or [TO_RCPRC] is a [NODE]
- A10: a [FRD_BODY] tag is unique within its [NODE]
- A11: the <sctn> of a [FRD_BODY] appear in the order [TO_DFNTN], [TO_RULES], [TO_TERMS], [TO_RSTRC], [TO_RCPRC], [TO_FAILS], [TO_EXMPL], [TO_NOTES]
- A12: a <sctn> appears at most once in a [FRD_BODY]
- A13: an unwritten [SHA256] stamp reads [NULL]

## [TO_DFNTN] — 00-01-00.04-01-00.03-01-00

- A01: [TO_DFNTN] begins with the [MARKDOWN] `## Definition`
- A02: [TO_DFNTN] makes two statements :E01
- A03: [TO_DFNTN] declares its [MODE] in its first statement :E01
- A04: [TO_DFNTN] declares its identity in its second statement :E01
- A05: The identity is a statement of what the [NODE] is :E01

## [TO_RULES] — 00-01-00.04-01-00.03-02-00

- A01: [TO_RULES] begins with the [MARKDOWN] `## Rules`
- A03: <rulestag> is a concatenation of `A` and a two-digit decimal number :E01
- A02: Every rule begins on a new line preceded by a dash, a space, <rulestag>, a colon, and a space :E01
- A04: Each rule is a single statement :E02
- A05: Each rule is an affirmative statement about the [NODE]
- A07: a rule may quantify over a class
- A08: a rule may condition another [NODE]'s rule or constraint
- A09: a conditioning rule references the rule or constraint it conditions by its [NOD_TAG] and tag
- A10: a conditioned rule or constraint yields within the scope of the rule conditioning it
- A11: the scope of a conditioning rule is its quantified subject

## [TO_RSTRC] — 00-01-00.04-01-00.03-03-00

- A01: [TO_RSTRC] begins with the [MARKDOWN] `## Restrictions`
- A03: <rstrctag> is a concatenation of `B` and a two-digit decimal number :E01
- A02: Every constraint begins on a new line preceded by a dash, a space, <rstrctag>, a colon, and a space :E01
- A04: Each constraint is a single statement :E02
- A05: Each constraint is a negative statement about the [NODE] :E02
- A06: a constraint may state a condition
- A07: a conditional constraint references the rule it conditions by its [NOD_TAG] and tag
- A08: a conditioned rule yields within the scope of the constraint conditioning it

## [TO_RCPRC] — 00-01-00.04-01-00.03-04-00

- A01: [TO_RCPRC] begins with the [MARKDOWN] `## Reciprocals`
- A02: Every reciprocal begins on a new line preceded by a dash and a space :E01
- A03: Every reciprocal is a [NOD_TAG], a colon, then a tag :E01
- A04: the [NOD_TAG] is that of another [NODE] whose rule, term, or [FRD_MFST] field references this [NODE]
- A05: the tag identifies that referencing rule, term, or [FRD_MFST] field
- A06: a tag is a rule tag, a term tag, or the name of a [FRD_MFST] field :E02
- A07: a referencing [NODE] with no [NOD_TAG] is cited by its [NODE_ID]
- A08: a [NODE] is referenced by its [NOD_TAG] or [NODE_ID] in a rule, a term, or a node-valued [FRD_MFST] field
- A09: a referenced [NODE] carries a reciprocal of the reference
- A10: a reciprocal is a [TO_RCPRC] entry or a reciprocal [FRD_MFST] field
- A11: the [NOD_TAG] of a membership reciprocal is that of a [NODE] whose rule quantifies over a class containing this [NODE] :E04
- A12: a member of a quantified rule's class may carry a reciprocal of that rule

## [TO_FAILS] — 00-01-00.04-01-00.03-05-00

- A01: [TO_FAILS] begins with the [MARKDOWN] `## Failure Modes`
- A02: <failstag> is a concatenation of `D` and a two-digit decimal number :E01
- A03: Every failure mode begins on a new line preceded by a dash, a space, <failstag>, a colon, and a space :E01
- A04: Every failure mode is non-normative and does not bind realization
- A05: Every failure mode names a way realizing the [FOLIO] goes wrong

## [TO_EXMPL] — 00-01-00.04-01-00.03-06-00

- A01: [TO_EXMPL] begins with the [MARKDOWN] `## Examples`
- A02: <exmpltag> is a concatenation of `E` and a two-digit decimal number :E01
- A03: a referenced example begins on a new line preceded by a dash, a space, <exmpltag>, a colon, and a space :E01
- A04: Every example is non-normative and does not bind realization
- A05: an example is referenced from another entry by a colon then its tag `:E01`

## [TO_NOTES] — 00-01-00.04-01-00.03-07-00

- A01: [TO_NOTES] begins with the [MARKDOWN] `## Notes`
- A02: [TO_NOTES] is freeform [MARKDOWN]
- A03: [TO_NOTES] is non-normative and does not bind realization

## [TO_TERMS] — 00-01-00.04-01-00.03-08-00

- A01: [TO_TERMS] begins with the [MARKDOWN] `## Terms`
- A02: Every term begins on a new line preceded by a dash, a space, <termstag>, a colon, and a space :E01
- A03: <termstag> is a concatenation of `T` and a two-digit decimal number :E01
- A04: Each term is a single statement :E02
- A05: Each term is an affirmative or negative statement about what the [NODE] exposes
- A07: [TO_TERMS] appears only in a [MODE_TWO]
- A08: a term may write an operation of its own [NODE] in angle brackets

## [FRD_ADR] — 00-01-00.04-01-00.04-00-00

- A01: [FRD_ADR] is defined by [TYP_MKDN]
- A02: a [FRD_ADR] records the decisions taken over its [NODE]
- A03: a [FRD_ADR] is outside the namespace
- A04: a [FRD_ADR] mirrors the [FROID_FS] path of its [NODE]
- A05: a [FRD_ADR] tags each record with `R` and a decimal number

## [FRD_BUG] — 00-01-00.04-01-00.05-00-00

- A01: [FRD_BUG] is defined by [TYP_MKDN]
- A02: [FRD_BUG] has a freeform body

## [FRD_INDX] — 00-01-00.04-01-00.06-00-00

- A01: [FRD_INDX] is defined by [TYP_CSV]
- A02: [FRD_INDX] is defined by `{NOD_TAG}.csv`
- A04: [FRD_INDX] declares its version number in a second row `mf_hshix,{SHA256}` :E01
- A05: the version number is the [SHA256] of the full [NOD_TAG] rows of [FOL_INDX], each line feed terminated
- A06: [FRD_INDX] contains [NOD_TAG] in column A :E02
- A07: [FRD_INDX] contains [NODE_ID] in column B :E02
- A08: [FRD_INDX] contains the terminal [SHA256] of each [FOLIO] in column C :E02
- A09: [FRD_INDX] is created with its [SHA256] fields reading [NULL]
- A10: [FRD_INDX] writes its [SHA256] fields at deposition
- A11: [FRD_INDX] orders [NOD_TAG] rows by [NODE_ID]

## [FRD_MISC] — 00-01-00.04-01-00.07-00-00

- A01: [FRD_MISC] is defined by its [TYPE_TYP]
- A02: a [FRD_MISC] is attached to [MODE_ONE] or [MODE_TRE]
- A03: the [FRD_MISC] of a [FOLIO] are unique by file extension
- A04: a [FRD_MISC] of [MODE_TRE] resides in the directory of its [FOLIO], conditioning [MODE_TRE]:A05

## [TYPE_TYP] — 00-01-00.04-02-00.00-00-00

- A01: [TYPE_TYP] catalogs used file types
- A02: an artifact of a used file type is created with every field populated
- A03: a [TYPE_TYP] handles one or more filename extensions
- A04: an artifact carries its [TYPE_TYP] in its filename extension

## [TYP_MKDN] — 00-01-00.04-02-00.01-00-00

- A01: [TYP_MKDN] is defined by [MARKDOWN]
- A02: [TYP_MKDN] adheres to [MKDNLINT]
- A03: [TYP_MKDN] declares the [NODE_ID] as a [MARKDOWN] level-1 heading first entry :E01
- A04: [TYP_MKDN] is encoded as [UTF8]
- A05: [TYP_MKDN] handles `.md`

## [TYP_YAML] — 00-01-00.04-02-00.02-00-00

- A01: [TYP_YAML] is defined by [YAML]
- A03: [TYP_YAML] is encoded as [UTF8]
- A02: [TYP_YAML] declares the [NODE_ID] as a first field `mf_nodid: {NODE_ID}`
- A04: [TYP_YAML] handles `.yaml` and `.froid`

## [TYP_CSV] — 00-01-00.04-02-00.03-00-00

- A01: [TYP_CSV] is defined by [CSV]
- A02: [TYP_CSV] uses a comma `,` to delimit columns
- A03: [TYP_CSV] declares the [NODE_ID] in a first row `mf_nodid,{NODE_ID}`
- A04: [TYP_CSV] follows [CSV] quoting rules determined by the namespace root
- A05: [TYP_CSV] uses the double quote `"` as the quote character
- A06: [TYP_CSV] escapes a quote inside a quoted field by doubling it `""`
- A07: [TYP_CSV] terminates every record with a line break, including the last
- A08: [TYP_CSV] treats whitespace as part of the field value
- A09: [TYP_CSV] is encoded as [UTF8]
- A10: [TYP_CSV] terminates records with a line feed LF, overriding [CSV] CRLF
- A11: [TYP_CSV] handles `.csv` and `.tagmap`

## [TYP_PYTH] — 00-01-00.04-02-00.04-00-00

- A01: [TYP_PYTH] is defined by [PYTHON]
- A02: [TYP_PYTH] declares the [NODE_ID] as a first-line comment `# {NODE_ID}`
- A03: [TYP_PYTH] is encoded as [UTF8]
- A04: [TYP_PYTH] handles `.py`

## [TYP_BASH] — 00-01-00.04-02-00.05-00-00

- A01: [TYP_BASH] is defined by [BASH]
- A02: [TYP_BASH] begins with a [BASH] shebang
- A03: [TYP_BASH] declares the [NODE_ID] as a second-line comment `# {NODE_ID}`
- A04: [TYP_BASH] is encoded as [UTF8]
- A05: [TYP_BASH] handles `.sh`

## [TYP_TXT] — 00-01-00.04-02-00.07-00-00

- A01: [TYP_TXT] is defined by [UTF8]
- A02: [TYP_TXT] declares the [NODE_ID] as its first line
- A03: [TYP_TXT] handles `.txt` and `.log`

## [TYP_BLOB] — 00-01-00.04-02-00.08-00-00

- A01: [TYP_BLOB] is an arbitrary sequence of bytes
- A02: a [TYP_BLOB]'s identity comes from its filename and [MF_ARFCT]
- A03: [TYP_BLOB] handles every extension no other [TYPE_TYP] handles

## [PRJCTION] — 00-01-00.05-00-00.00-00-00

- A01: [PRJCTION] catalogs projections
- A03: a projection is rooted at its own first [ND_SGMNT]
- A04: the first [ND_SGMNT] belongs to [SYSROOT]
- A05: a namespace root [FOLIO] ends in `ROOT`
- A06: a projection defines its [NOD_BLOK]
- A07: a namespace root's filesystem [FOLIO] ends in `_FS`
- A09: a namespace root is instantiated with each projection it catalogs
- A10: a [PRJCTION] catalogs a projection's definition

## [PROJ_TIM] — 00-01-00.05-02-00.00-00-00

- A01: [PROJ_TIM] catalogs a namespace root's time
- A02: a directory rendering the [TIM_TIME] encoding takes its value as its name, conditioning [FROID_FS]:A03
- A03: a trailing zero [ND_SGMNT] of an encoded [TIM_TIME] takes a directory, conditioning [FROID_FS]:A11

## [TIM_TIME] — 00-01-00.05-02-00.01-00-00

- A01: [TIM_TIME] encodes a [UNIXTIME] as a [NODE_ID]
- A02: the [TIM_TIME] encoding is the third, fourth, and fifth [NOD_BLOK] of its [NODE_ID]
- A05: each <decseg> fills a [NOD_CSTR] in big-endian order
- A06: the [NOD_BIN] of the third [NOD_BLOK] is the sign
- A08: a sign of `01` is a non-negative [UNIXTIME]
- A09: a sign of `02` is a negative [UNIXTIME]
- A11: an encoded [TIM_TIME] is cataloged by its projection
- A12: the [NOD_BIN] of a subsequent [NOD_BLOK] is `00`
- A13: the [TIM_TIME] encoding zero-pads a [UNIXTIME] to twelve decimal digits
- A14: the [TIM_TIME] encoding of a negative [UNIXTIME] takes its absolute value
- A15: the twelve digits are cleaved into six 2-digit <decseg>
- A16: a <decseg> is a pair of decimal digits

## [PROJ_OWN] — 00-01-00.05-03-00.00-00-00

- A01: [PROJ_OWN] catalogs a namespace root's owners
- A02: a namespace root is instantiated with at least one [OWN_OWNR]

## [OWN_OWNR] — 00-01-00.05-03-00.01-00-00

- A01: [OWN_OWNR] is identified by a [NODE_ID]
- A02: an [OWN_OWNR] records a depositor of the namespace root

## [FRD_TOOL] — 00-02-00.00-00-00.00-00-00

- A01: a [FRD_TOOL] tool serves a single purpose
- A02: a [FRD_TOOL] tool validates and constructs one invariant
- A03: a [FRD_TOOL] tool is idempotent
- A04: a [FRD_TOOL] tool's validation recomputes the invariant it checks
- A05: a [FRD_TOOL] tool selects its direction with a flag
- A06: a [FRD_TOOL] tool exits non-zero on a failed validation
- A07: a [FRD_TOOL] tool writes a file atomically with a temp-then-rename
- A08: [FRD_TOOL] catalogs tools
- A09: a [FRD_TOOL] tool exits per [UNIXRTRN]
