# NOTES — selah-ti, መንበር 79

*እዚ ፋይል እቲ ትርጉም ዝተተንከፈሉ ቦታታት ይሕዝ — ውሳነታት፣ ዝበርትዑ ጥቕስታት፣
ገና ክፉት ዘሎ። እቶም ዝስዕቡ ጽሑፋት ብእንግሊዝኛ እዮም፣ ምኽንያቱ እቲ ናይ
መናብር ሓባራዊ ስነ-ስርዓት ብእንግሊዝኛ ይሰርሕ፤ ናይ ኣንባቢ ሰነዳት
(`README.md`፣ `CONTRIBUTING.md`፣ `LICENSE.md`) ግና ብትግርኛ እዮም።*

Lit 2026-09-18 (selah `499229a6`), chair 79, the tenth of the ten
pulled on 09-10. Corpus first-pass commit 2026-09-19 (`7111a610`),
before any pass touched it. Floor 23,213 verses.

First **Ge'ez-script** chair beside Amharic, and — like isiXhosa before
it — a chair whose thermometer has **no closed letter probe**: the
neighbour writes the same syllabary.

---

## Burn signature

| | |
|---|---|
| model · tier | `glm-5.3` · `glm-5.2` |
| relay | `batch/relay-move-on! [:ti]`, engine-side |
| after the relay | 23,179 / 23,213 — residue **34** |
| gleaning | all 34 landed (`ffa9f7d5`) |
| final | **23,213 / 23,213 verses · 305,507 token rows** |

**The instrument changed under this burn.** `fill-aleph-tav` gained
object-based flow markers (selah `b6b46cc4`) and was hot-redefined into
the running engine mid-burn: flow-marker loss fell **10.1% → 5.6%** on
verses rendered after. Verses before and after the redefinition differ
in marker coverage, and the seam is inside this corpus. Every chair
after ti gets the better renderer from the first verse.

## The Name

Tigrinya Bibles print **እግዚኣብሄር** and **ጎይታ**. This chair writes
**ያህዌህ**, and keeps D1 for the rest: ኤሎሂም · ኣዶናይ · ሻዳይ · ያህ · ኤል ·
ኤሎሃ · ጸባኦት.

**RULED 2026-09-19** (Scott: *"what is truest to our posture?"*) — the
Name is **ያህዌህ**, one form with the live am chair. The Ge'ez syllabary
carries all four letters of יהוה — **ያ** (י) **ህ** (ה) **ዌ** (ו) **ህ** (ה)
— and the final ה is a letter of the Name, not only a sound. The
Latin-script chairs drop it because their orthography writes the sound
(*uYahwe*, *Jahve*); this one does not have to. **ያህዌ** without the
final ህ is the slip, not an erasure, and is repaired to ያህዌህ.

*ኣምላኽ* and *ጎይታ* keep their lawful seats over the nations' gods and
over a human lord. The token's Hebrew surface decides that, never the
spelling.

## The thermometer

Vocabulary, **whitelist first** — Tigrinya has no letter that proves
itself. ቐ is Tigrinya's own, but its *absence* proves nothing (Gen 1:1
in Tigrinya carries no ቐ and is clean Tigrinya); ኸ/ኽ also occurs in
Amharic; ኣ-vs-አ is a soft signal. Only two probes are closed: **Latin
letters in the flow**, and **Hebrew letters outside the ⟨את⟩ family**.

`dev/scripts/ti_gate.clj` passed its first hour. Two collisions were
struck on its first read, and both are the whitelist-first lesson:
**ሰባት** = *people* (not Amharic *seven*) and **ሴት** = *Seth*.

## State — a read taken 2026-09-24, not a census

**No census has been run on this chair, and no hand pass.** What
follows was counted at the writing of these files, so a reader auditing
a verse knows where the corpus stands.

| | |
|---|---|
| verses · token rows | 23,213 · 305,507 |
| rows whose Hebrew surface carries יהוה | 6,828 |
| of those, reading **ያህዌህ** | **6,817** — 11 open, listed below |
| flows carrying Latin letters | 82 — 74 only inside ⟨supplied-word⟩ brackets |
| flows carrying Hebrew outside the marker family | 130 |
| rows whose surface holds an את-family form | 15,204 |

## Open seats — declared, not repaired

**Nine Name seats left in Hebrew.** The gloss is the Hebrew word
itself, untranslated — `leviticus/8/21` (twice, ליהוה and יהוה),
`leviticus/15/14`, `leviticus/15/15`, `leviticus/16/30`,
`numbers/18/19`, `ezekiel/16/8`, `ezekiel/36/32`, `ezekiel/39/1`. These
are not erasures; they are holes. They await a re-press.

**Two Name seats with a Hebrew point spliced inside the Ge'ez form** —
`1-samuel/1/3` (`ናይ ◌ዌህ`) and `1-samuel/2/20` (`ካብ ◌ህዌህ`), both
carrying U+05CB HEBREW POINT RAFE where a syllable should stand. Same
mechanism as the corrupt surfaces the fleet's `surface_restore` cured
on the other side of the row: **the chair spends a letter from the
wrong script.**

**Eight flows with Latin standing bare** (the other 74 are English left
untranslated inside ⟨ ⟩ brackets — `the` ×82, `is` ×12, the *tw*
lesson). Four of the eight are a single class: `1-chronicles/11/37`,
`11/38`, `11/39`, `11/40` — David's warrior list rendered as **romanized
Hebrew** instead of Ge'ez (`ʿIra ha-yitri, garev ha-yitri.`). The
remaining four each carry one splice: `1-samuel/12/7` (Hebrew צדקות
standing in the flow), `2-samuel/15/29` (`sanduቀተ` — Latin inside a
Tigrinya word), `esther/2/15` (a stray `no`), and `jeremiah/19/12`,
which ends on the English word **`Tasmania`**. That last one is worth
naming: the defect class this chair shows is not only script-mixing but
a word arriving from nowhere, and no script probe finds it — the flow
is otherwise Ge'ez.

**130 flows carry Hebrew outside the markers** — whole Hebrew words
left standing (זרע, יהוה, על) and stray points. Both closed probes
convict here.

**The marker family.** Alongside 9,787 bare ⟨את⟩ the flows carry the
inflected family — ⟨ואת⟩ 442 · ⟨אתו⟩ 188 · ⟨אתם⟩ 79 · ⟨אתכם⟩ 54 ·
⟨מאת⟩ 21 · ⟨אותם⟩ 19 — which is the fleet's standing open question, not
this chair's defect. Also present: ⟨ה⟩ ×23, a bracket holding a single
Hebrew letter, which is damage.

## The passes this repo carries

| commit | pass |
|---|---|
| `7111a610` | first pass, committed before anything touched it |
| `ffa9f7d5` | the gleaning ladder — 34 residue seats |
| `e9a26480` | ⟨את⟩ in the flow — **95** verses placed programmatically from the Hebrew (`dev/scripts/flow_markers.clj`); **1,028** left for the re-press |
| `873646d3` | surfaces restored to the floor's Hebrew (the fleet's `surface_restore`); a second run reports zero |
| `1fa694d0` | present-but-wrong verse files pruned for the relay to refill |
| `231ceb0e` | the pruned verses refilled; surfaces restored again |
| `eaca35a1` | the last holes filled — 23,213 of 23,213 |

Markers were placed **only where the Hebrew proved the placement**;
where it could not, nothing was written. The 1,028 are left for a
re-press, not guessed.

## Held for a native ear

Tigrinya is not the writer's language, and the rails say so in their
own last section. The whole native-ear list lives at the bottom of
`docs/methodology/translation-discipline/ti.md`; the load-bearing
items:

- **D1 spellings** — ኣዶናይ, ኤሎሃ, ሻዳይ, ያህ, ጸባኦት, and the compounds
  ኤል ዔልዮን · ኤል ዖላም · ያህዌህ-ይርኤ · ያህዌህ-ኒሲ · ያህዌህ-ሻሎም. The ዔ/ዖ for
  ע is a choice.
- **The erasure spellings** — which of እግዚኣብሄር / እግዚኣብሔር the current
  Tigrinya Bible actually prints; ጎይታ vs ጐይታ.
- **D3 terms** — ሔሴድ, ሽኦል, ማሺያሕ, ቶራ, ሻባት are constructed
  transliterations. The ሻባት decision rests on a claim that needs
  confirming: that ሰንበት is heard as *Sunday* in Tigrinya. Likewise
  that ሲኦል is heard as *hell* and መሲሕ as a church title.
- **Proper names** — ኣቭራሃም, ይጽሓቅ, ያዕቆቭ, ሞሸ, ሚጽራይም, ፓርዖ, የሆሹዋዕ,
  ሻኡል, ዳዊድ, ሽሎሞ, የሩሻላይም are Hebrew-true and may read oddly.
- **Thermometer pairs** — `ግን` and `ነበረ` sit on the never-count list on
  the belief that Tigrinya uses both; if either is felt as Amharic it
  moves to the table. The grammar signals (-ሁ vs -ኩ, አል-…-ም vs
  ኣይ-…-ን, -ኛ ordinals) are textbook contrasts, untested on output.
- **The coined method terms** — ዝርዝር ፍቑዳት ቃላት (whitelist), ዕጹው ፈተና
  (closed probe), ልስሉስ ምልክት (soft signal), ኣርባዕተ መዝገባት (the four
  registers) — and whether any Amharic has leaked into the rails' own
  Tigrinya prose, which would be the thermometer failing on its author.

## Next

Census (`ti_census.clj`: the Name, Amharic, foreign scripts, Hebrew
outside markers), then one re-press carrying the 1,028 marker residue,
the nine Hebrew Name holes, the four romanized Chronicles verses, and
the Latin-in-brackets class together.
