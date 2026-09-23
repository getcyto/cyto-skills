---
name: cite-gate
description: Hold any legal work product (memo, brief, filing, class answer, post) until every case, statute and regulation cite clears four checks - it exists, it says what you claim, it is still good law, and it is in the right form. Use before legal writing leaves your hands, when asked to "check the cites", "Shepardize", "KeyCite", or "is this still good law", and whenever a cite came from memory, a casebook, a chat answer, or another model.
---

# Cite gate

A lawyer's signature certifies the law in a filing. Fabricated or dead cites
draw sanctions and bar referrals (Mata v. Avianca, S.D.N.Y. 2023, and many
since). So this is a gate, not a step: nothing moves forward until every cite
clears every layer below. A cite that fails is fixed or cut, never shipped
provisionally.

## The four layers

1. **Exists.** The reporter cite resolves to the named case. Confirm by the
   case name on the landed page, not by the fact that something loaded.
2. **Says it.** Quotes are verbatim in the opinion, pin cites land on the
   right page, and the case holds the proposition it is cited for. This is
   the subtle failure: a real case cited for something it does not hold.
3. **Still good law.** Run a citator (Shepard's on Lexis, KeyCite on
   Westlaw). Read the signal AND the treatment behind it (see below).
4. **Form.** Bluebook, including the official reporter where the
   jurisdiction has one, with the regional reporter as the parallel cite.

Statutes and regulations: read the current text on the official source (the
legislature's site, uscode.house.gov, eCFR) and check for recent amendments.
Statutes change under you; a breach-notice deadline that read "most
expedient time" last year may be a fixed number of days now.

## Reading a citator signal

A signal tells you to go read. It is not the answer.

- **Red**: overruled, reversed or superseded on some point. Find which
  point. If it is the point you rely on, cut the cite.
- **Orange**: validity questioned by a citing court. Read that opinion.
- **Yellow**: often nothing but "distinguished by", meaning a later court
  found the facts different. That is not negative treatment of the law.
  Report the breakdown, e.g. "yellow from 21 distinguished; 231 followed;
  no overruling or criticism: good law."
- **Green or blue**: positive or neutral.

Always report which treatment raised the flag, with counts. A checker that
just says "Caution" alarms people for nothing.

## Running it

- The citator needs the user's own research login. Never handle their
  credentials; ask them to sign in, then batch every cite into that one
  session.
- On Lexis, the search box accepts `shep: <cite>`. If it replies that no
  report exists for that page, the cite is wrong. It usually suggests the
  right first page; confirm by the case name, then fix the cite everywhere
  it appears.
- Open the opinion itself to check a quote. A casebook excerpt, a headnote,
  or a later case's paraphrase is a pointer to the text, not the text.
- Most research platforms can check every cite in an uploaded document at
  once. Use that for long documents, and still read the treatment behind
  every flag it raises.

## Lessons this gate was built on

- **A trusted source can still be wrong.** A casebook gave a leading state
  supreme court case a first page six pages off. The citator had no report
  for it. A casebook, a brief bank, or a model's memory is a lead, never a
  verified cite.
- **Yellow is not a verdict.** Three cases in one answer all showed yellow.
  Every flag came only from "distinguished by". All three were good law.
- **"As I recall" answers about outcomes fail.** A chat answer said a
  circuit court reversed a conviction; it affirmed. Check the disposition
  itself.
- **Say which layers ran.** A check that confirmed existence and quotes but
  never ran the citator is a hallucination check, not a cite gate.

## Output: the cite ledger

One row per cite, and say plainly which layers ran:

| Cite (as corrected) | Exists | Says it | Good law (signal and why) | Form | Verdict |

Verdicts: CLEARED, FIXED (what changed and where), CUT (why), or NOT RUN
(which layer, and what is needed, such as "needs the user's Lexis login").
Never report a layer as passed that did not run.

When fixing a cite inside a shared document, change only that string (find
and replace, confirm exactly one match), then re-read the document to
confirm it saved.

This skill checks citations. It is not legal advice, and it does not replace
the judgment of the lawyer who signs the work.
