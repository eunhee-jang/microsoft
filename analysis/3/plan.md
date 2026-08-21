# Plan: A foundation model for acute abdomen diagnosis stratification and triage on noncontrast computed tomography

- Issue: https://github.com/eunhee-jang/microsoft/issues/3
- Paper: `recommended/2026-08-20/abdomennet-noncontrast-ct-triage/paper.json`
- DOI: https://doi.org/10.1038/s41467-026-76634-w
- Physician focus: "이 논문의 핵심 주제가 궁금" (what is the core theme of this paper)

## Proposed presentation

Since the physician's question is about the paper's core theme (not yet a
deep transferability request), the dashboard entry should orient a reader
quickly to *what AbdomenNet is, how it was validated, and why it's on our
radar* — before any claim about applicability to our chest X-ray cohort.

1. **Summary card (text, top of entry)** — one paragraph: AbdomenNet is a
   multi-task foundation model for 11 acute abdominal conditions on
   non-contrast CT, pretrained on 103,989 exams, fine-tuned on 5,816
   annotated cases, validated on 2,528 external patients across 3 cohorts.
   Core theme = external generalization + reader-assistance validation
   design, not raw model accuracy alone.
2. **Bar chart: "Validation funnel" (pretrain → fine-tune → external
   validation cohort sizes)** — x-axis = stage, y-axis = number of
   cases/patients (log scale, since 103,989 vs 2,528 differ by ~40x). This
   encodes the paper's core design point (huge scale drop from pretraining
   to clinically-validated cohort) better than prose.
3. **Grouped bar: reader AUROC without vs. with AI assist (0.812 → 0.924)**
   — directly visualizes the paper's headline "clinical practicality"
   finding, one bar pair, unambiguous encoding of the improvement axis
   tagged in `paper.json` (`판독의 임상적 실용성`).
4. **Comparison table (paper cohort vs. our cohort)** — placed after the
   charts, addressing the other tagged axis (`기관 간 일반화`): institution
   count, modality, size, label structure. This is the bridge to "is this
   relevant to us" without pretending we can reproduce their numbers.
5. **Text section: "Why this shows up for our cohort"** — reuse the
   `relevance`/`caveat` fields from `paper.json`, explicit that modality
   (CT vs. our CXR) and body region (abdomen vs. chest) differ, so only the
   *validation design*, not the performance numbers, transfers as a
   reference.

Layout order: summary → validation funnel chart → reader AUROC chart →
dataset comparison table → relevance/caveat text. This puts "what is this
paper" first (matching the physician's literal question) and defers the
transferability discussion to the end, since that wasn't explicitly asked
yet.

## Open questions

- Does the physician want this treated purely as a design-pattern reference
  (multi-reader crossover validation), or do they want an eventual
  quantitative comparison attempt despite the CT/CXR modality mismatch?
- Should the dashboard entry emphasize the AI-assist reader-improvement
  metric (0.812→0.924 AUROC) even though it cannot be replicated on our
  153-patient single-institution chest X-ray data?
- Is a future multi-reader crossover study on our own multi-label CXR cases
  (e.g., Atelectasis|Infiltration, 4 cases) in scope, or is this purely a
  literature-awareness note for now?
