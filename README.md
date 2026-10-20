# FROID

A specification that reads cold.

Every node is a **FOLIO** — a directory holding a `.froid` manifest, an abstract
and a `.md` body, all sharing one NODE_ID. The body states what the node is and
the rules that bind it. Read it literally; the rules are mechanical, not advisory.

This namespace is **mechanics only**. It states true instructions and nothing
else — no rationale, no commentary, nothing to interpret. The *why* is not here.
It is either derivable from the rules, or recorded in ADR held privately.

Start at `namespace/00-SYSROOT`. `[TAG]` cites another node;
`00-00-00.00-00-06.00-00-00.tagmap` at that root resolves a tag to its NODE_ID.
In a node's directory the abstract is `…-00.…-01.….md`, the manifest is the
`.froid`, and the body is `…-01.…-03.….md` (MODE_ONE) or `…-02.…-03.….md`
(MODE_TWO). 

`rules.md`, `restrictions.md`, `terms.md` and `reciprocals.md` are roll-ups
collated from the bodies by tooling. Derived; the bodies are the source.
