# PROVENANCE — how this rendering came to be

*Tigrinya, chair 79. Lit 2026-09-18. Floor 23,213 verses.*

This is the record of how the text in this repository was produced and
what went wrong with it. A machine-assisted rendering has no standing
unless you can see how it was made, so this file says both.

---

## The approach

Every verse is rendered from the Hebrew of that verse, under a written
discipline — `docs/methodology/translation-discipline/ti.md` in the
Selah repository, itself written in Tigrinya, following the structure of
`xh.md` and taking its D1 precedent and its SOV rule from `am.md`, the
Amharic sister. Eight rules govern it: the Hebrew letters pass letter by
letter; the Name stays the Name; a double faithfulness to Deut 6:4 (add
no doctrine, flatten no plural); no foreknowledge (Gen 22:1 does not
know Gen 22:13); the Tanakh's own vocabulary only; the four registers;
numbers and marks stay put; and the translator has no note of its own.

**Word order is Tigrinya's, alignment is Hebrew's.** Tigrinya puts the
verb at the end and Hebrew often puts it first, so — as at the am, ko
and ja chairs — the `tokens` row holds Hebrew order strictly, one gloss
per token, while the assembled `translation` obeys Tigrinya grammar.
Alignment is preserved at the token; the reading is natural.

**The `⟨ ⟩` brackets do two different jobs.** `⟨את⟩` is the Hebrew
direct-object marker, which Tigrinya has no word for; it is left
standing so the reader sees it. `⟨ቃል⟩` is a word Hebrew did not write
but Tigrinya grammar requires — visibly marked, so you can always tell
what the Hebrew said from what the grammar needed.

## The fight on this chair is the Name

| Hebrew | here | rejected |
|---|---|---|
| יהוה | **ያህዌህ** | እግዚኣብሄር, ጎይታ, ኣምላኽ in the Name's place, ይሆዋ |
| אלהים | **ኤሎሂም** | ኣምላኽ in the Name's place |
| אדני | **ኣዶናይ** | ጎይታ, ጎይታ እግዚኣብሄር |
| שדי | **ሻዳይ** | ኩሉ ዚኽእል alone |
| אל | **ኤል** | ኣምላኽ as a type-name |
| צבאות | **ጸባኦት** | "of hosts" as a substitute |

እግዚኣብሄር and ጎይታ are what the Tigrinya Bible prints for יהוה, and the
model has seen them very often. They are not bad Tigrinya; they stand
*in the Name's place*. ኣምላኽ and ጎይታ keep their lawful seats over the
nations' gods and over a human lord, and the token's Hebrew surface
applies that distinction, never the spelling.

**Scott ruled the form on 2026-09-19** — *"what is truest to our
posture?"* The Ge'ez syllabary carries all four letters of יהוה (ያ י ·
ህ ה · ዌ ו · ህ ה), so the final ה is written: **ያህዌህ**, one form with the
live Amharic chair. ያህዌ is a Latin-chair shape and is a slip, not an
erasure.

## The burn and the gate

The relay rendered 23,179 of 23,213 verses and moved on with a residue
of **34**; the gleaning ladder landed all of them. A first-hour gate
(`dev/scripts/ti_gate.clj`) — the Name, the את family, Amharic words,
liturgical Ge'ez, Latin letters — passed and was tended to the end.

The corpus was committed to git **before any pass touched it**
(`7111a610`), so every repair below is a diff you can read.

## Finding: the instrument changed under the burn

`fill-aleph-tav` gained object-based flow markers (selah `b6b46cc4`)
and was hot-redefined into the engine **mid-burn**. Flow-marker loss
fell **10.1% → 5.6%** on verses rendered after the redefinition. The
improvement is real and every later chair has it from its first verse,
but the seam is inside *this* corpus: verses rendered before and after
differ in marker coverage, and no diff shows where the seam falls. It
is one more reason the marker residue here is left for a re-press
rather than patched.

## Finding: Tigrinya has no letter that proves itself

The Latin-script chairs could use one letter as a closed probe. Here
that fails. **ቐ** is Tigrinya's own and Amharic does not write it — but
its *absence* proves nothing: Gen 1:1 in Tigrinya carries no ቐ and is
clean Tigrinya. **ኸ/ኽ** occurs in Amharic too. **ኣ vs አ** is a
convention writers differ on. So the thermometer is vocabulary, and the
rule is **whitelist first** — which the gate's own first read confirmed
twice: **ሰባት** is Tigrinya for *people*, not Amharic *seven*, and
**ሴት** is the name *Seth*. A thermometer without a whitelist measures
its own blindness.

Two probes stayed closed, and both are orthographic: any Latin letter
in the flow, and any Hebrew letter outside the ⟨את⟩ family.

## Finding: the chair spends a letter from the wrong script

The defect this corpus shows most is one behaviour in two places. On the
Hebrew side of the row it wrote Ge'ez and Latin into `surface`, a field
that is not the chair's to write; the fleet's `surface_restore`
(`873646d3`) put the floor's Hebrew back and a second run reported zero.
On the Tigrinya side it wrote Hebrew into the Name: `1-samuel/1/3` and
`1-samuel/2/20` carry U+05CB HEBREW POINT RAFE inside ያህዌህ where a
syllable belongs. Same mechanism, opposite direction — the same one the
ug chair was convicted of at scale.

Nine further Name seats are not corrupt but **empty of Tigrinya**: the
gloss is the Hebrew word itself (`leviticus/8/21` twice, `15/14`,
`15/15`, `16/30`, `numbers/18/19`, `ezekiel/16/8`, `36/32`, `39/1`).

## Finding: a word arrives from nowhere

Eighty-two flows carry Latin letters. Seventy-four are English left
untranslated *inside* a ⟨supplied-word⟩ bracket — the lesson the tw
chair taught. Four are `1-chronicles/11/37`–`11/40`, David's warrior
list written as **romanized Hebrew** instead of Ge'ez. The last four are
single splices, and one of them is `jeremiah/19/12`, which ends on the
English word **`Tasmania`**.

That one matters out of proportion to its count. A script probe finds it
only by accident — the rest of the flow is Ge'ez, the grammar holds, and
nothing about the sentence announces the intrusion. The ug chair learned
the same thing from Chinese 葡萄 inside a Uyghur word: **the defect
class is not orthographic, it is substitution**, and a probe that
counts characters is looking at the wrong thing.

## The cure, in order

| pass | what |
|---|---|
| gleaning ladder | 34 residue seats (`ffa9f7d5`) |
| flow markers | **95** verses placed by proof from the Hebrew; **1,028** left for the re-press (`e9a26480`) |
| surface restore | the floor's Hebrew back in `surface`; second run zero (`873646d3`) |
| prune | present-but-wrong verse files removed for the relay to refill (`1fa694d0`) |
| refill | the pruned verses re-rendered; surfaces restored again (`231ceb0e`) |
| last holes | 23,213 of 23,213 (`eaca35a1`) |

Markers were written **only where the Hebrew proved the placement**.
Where it could not, nothing was written — the lesson of the marker tool
that guessed at the xh chair and had to be reverted whole.

## Open — declared, not repaired

- **No census has been run on this chair**, and no hand pass. The
  counts in `NOTES.md` are a read taken 2026-09-24, at the writing of
  these files.
- **Eleven Name seats** — nine holes left in Hebrew, two with a Hebrew
  point spliced into ያህዌህ.
- **The marker residue** — 1,028 verses whose flows lost a ⟨את⟩ the row
  still carries; and the inflected family (⟨ואת⟩ 442 · ⟨אתו⟩ 188 · …),
  which is a fleet question, not a chair defect.
- **82 Latin flows · 130 flows with Hebrew outside the markers.**
- **A native ear.** Tigrinya is not the writer's language. The rails
  carry their own review list; `NOTES.md` names the load-bearing items.

## Final

**23,213 / 23,213 verses · 305,507 token rows.** ያህዌህ in **6,817 of
6,828** Name seats, with the eleven above declared. Read it alongside
the Hebrew.
