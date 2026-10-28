# VERIFY — ai0S-deepdive

> **Bundle Address:** `ai0S-deepdive@sha256:becb3095d2902f6546ee36575ecfc06b7808f18793e3c5e585cecaf344edc78b`
> **Origin Anchor (`PID 1`):** `ai0S@sha256:b3aeee619d9cb691cc6618466407d56598e830c53c6d024748d4582887c57d13` *(Bitcoin `971315, 971319, 971354, 971357`)*
> **Signer (Ed25519):** `9F4D9A266D720FE6336574D87B410637560297CF`

## Core Files

| Datei / File | Rolle / Role | Zustand / State |
|---|---|---|
| `HANDBUCH-PROSASSEMBLER-DE.md` | Deepdive 01 · Prosassembler (DE) | Handbuch für Menschen: *Das Weggelassene ist die Wahrscheinlichkeit* (~15–18 Min.) |
| `HANDBOOK-PROSASSEMBLER-EN.md` | Deepdive 01 · Prosassembler (EN) | Handbook for Humans: *What Is Left Out Is Probability* (~15–18 min.) |
| `AI-PROSASSEMBLER.0s` | Deepdive 01 · Prosassembler für AIs | `.0s`-Protokoll (`00–09`) für KI-Systeme unter `Note 1` |
| `HANDBUCH-BACK-TRANSLATION-DE.md` | Deepdive 02 · Back-Translation (DE) | Handbuch für Menschen: *Die Werkzeuge der Evolution in der Welt der KI* (~6–7 Min.) |
| `HANDBOOK-BACK-TRANSLATION-EN.md` | Deepdive 02 · Back-Translation (EN) | Handbook for Humans: *The Tools of Evolution in the World of AI* (~6–7 min.) |
| `AI-BACK-TRANSLATION.0s` | Deepdive 02 · Back-Translation für AIs | `.0s`-Protokoll (`00–04`) für KI-Systeme |
| `HANDBUCH-NEGATIVE-SHAPE-DE.md` | Deepdive 03 · Negative-Shape (DE) | Handbuch für Menschen: *Wie das Ausgeschlossene dem Intent seine Form gibt* (~6–7 Min.) |
| `HANDBOOK-NEGATIVE-SHAPE-EN.md` | Deepdive 03 · Negative-Shape (EN) | Handbook for Humans: *How What Is Ruled Out Gives the Intent Its Form* (~6–7 min.) |
| `AI-NEGATIVE-SHAPE.0s` | Deepdive 03 · Negative-Shape für AIs | `.0s`-Protokoll (`00–04`) für KI-Systeme |
| `HANDBUCH-FUTURE-GAP-DE.md` | Deepdive 04 · Future-Gap (DE) | Handbuch für Menschen: *Die Lücke in die Zukunft und die zwei Fragen dahinter* (~5–6 Min.) |
| `HANDBOOK-FUTURE-GAP-EN.md` | Deepdive 04 · Future-Gap (EN) | Handbook for Humans: *The Gap into the Future and the Two Questions Behind It* (~5–6 min.) |
| `AI-FUTURE-GAP.0s` | Deepdive 04 · Future-Gap für AIs | `.0s`-Protokoll (`00–03`) für KI-Systeme |
| `HANDBUCH-REALIZATION-DE.md` | Deepdive 05 · Realization (DE) | Handbuch für Menschen: *Die innere Klarheit (`Bootloader v2`) und die äußere Verwirklichung im Harness* (~6 Min.) |
| `HANDBOOK-REALIZATION-EN.md` | Deepdive 05 · Realization (EN) | Handbook for Humans: *Inward Clarity (`Bootloader v2`) and Outward Execution in the Harness* (~6 min.) |
| `AI-REALIZATION-DEEPDIVE.0s` | Deepdive 05 · Realization für AIs | `.0s`-Protokoll (`00–03`) für KI-Systeme |
| `HANDBUCH-ADAPTIVE-DE.md` | Deepdive 06 · Adaptive Intelligence (DE) | Handbuch für Menschen: *Warum das „a" in `ai0S` nicht für künstlich steht* (~5–6 Min.) |
| `HANDBOOK-ADAPTIVE-EN.md` | Deepdive 06 · Adaptive Intelligence (EN) | Handbook for Humans: *Why the "a" in `ai0S` Does Not Stand for Artificial* (~5–6 min.) |
| `AI-ADAPTIVE.0s` | Deepdive 06 · Adaptive Intelligence für AIs | `.0s`-Protokoll (`00–03`) für KI-Systeme |
| `HANDBUCH-SAFETY-VIEW-DE.md` | Synthese · `ai0S-Safety-View` (DE) | Handbuch für Menschen: *Die strukturellen Sicherheitsprobleme heutiger KI und wie `ai0S` helfen kann* (~8–10 Min.) |
| `HANDBOOK-SAFETY-VIEW-EN.md` | Synthesis · `ai0S-Safety-View` (EN) | Handbook for humans: *Structural Safety Problems of Today's AI and How `ai0S` May Help* (~8–10 min.) |
| `README.md` | Zweisprachiger Index (DE + EN) | Übersicht über alle 6 Deepdives, `ai0S-Safety-View` und die 10 Kerngedanken |

## Verify Commands

```sh
gpg --import pubkey.asc
gpg --verify MANIFEST.json.sig MANIFEST.json
sha256sum -c <(jq -r '.files[] | "\(.sha256)  \(.path)"' MANIFEST.json)
cat MANIFEST.json MANIFEST.json.sig | sha256sum   # = becb3095d2902f6546ee36575ecfc06b7808f18793e3c5e585cecaf344edc78b
```

Per-file signatures (detached, Ed25519):

```sh
for f in *.0s HANDBOOK-*.md HANDBUCH-*.md README.md; do
  gpg --verify "$f.sig" "$f"
done
```
