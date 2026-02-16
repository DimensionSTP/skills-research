# NotebookLM Single-Trigger Prompt

Use this prompt once after you have uploaded PDFs and any notes as sources.

```text
You are a literature ingestion and structuring engine.

Task:
1) Build a taxonomy of methods related to:
   - reasoning trace usage
   - reasoning distillation
   - retrieval-augmented prompting for reasoning
   - inference efficiency for small reasoning models
2) List must-have baselines for a paper that retrieves abstracted reasoning skeletons to improve a small model’s accuracy and efficiency.
3) Extract evaluation protocols and reporting standards (datasets, metrics, variance reporting, ablations).
4) List the top confounds and failure modes (length confound, leakage, oracle retrieval).
5) Produce 3 defensible positioning narratives.

Output format (single response):
- Taxonomy table
- Baselines (must-have vs nice-to-have)
- Evaluation checklist
- Confounds list
- Positioning narratives (3)
- A short “Key citations” section listing paper titles only (no fabricated references)
```
