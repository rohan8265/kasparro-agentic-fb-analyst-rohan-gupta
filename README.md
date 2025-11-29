# kasparro-agentic-fb-analyst-rohan-gupta

**Kasparro Applied AI Engineer — Agentic Facebook Performance Analyst**

This repository contains a multi-agent system design, prompts, sample outputs, and a sample report for diagnosing Facebook Ads performance and generating creative improvements. It is a delivery-ready draft to upload to GitHub for the assignment.

## Repo contents
- `README.md` — this file
- `insights.json` — sample validated insights + evaluator outputs
- `creatives.json` — sample creative suggestions for low-CTR campaigns
- `report.md` — human-readable final report (Planner output)
- `planner_prompt.txt` — Planner agent prompt
- `data_agent_prompt.txt` — Data agent prompt
- `insight_agent_prompt.txt` — Insight agent prompt
- `evaluator_agent_prompt.txt` — Evaluator agent prompt
- `creative_agent_prompt.txt` — Creative generator prompt
- `logs/langfuse_traces_example.txt` — (optional) example logs / traces
- `RELEASE_NOTES.md` — release instructions and v1.0 tag

## Setup — local
1. Clone or create a new local folder called `kasparro-agentic-fb-analyst-rohan-gupta`.
2. Copy the provided files into that folder.
3. Place the dataset at the path referenced in prompts: `/mnt/data/synthetic_fb_ads_undergarments.csv`.
   - If running locally, update the path in `data_agent_prompt.txt` to the local CSV path.
4. (Optional) If you are using LangChain or other orchestrator, wire the prompt files into your agent runner.

## How to validate sample outputs
Sample outputs (`insights.json`, `creatives.json`, `report.md`) are provided as examples. To generate your own:
- Run the Planner agent which will call DataAgent → InsightAgent → EvaluatorAgent → CreativeGenerator with the provided prompts and the dataset summary.
- Save outputs to `insights.json` and `creatives.json` and generate `report.md` using the Planner’s final assembly.

## How to publish to GitHub
From your local folder run:

```bash
git init
git add .
git commit -m "Initial commit — Kasparro Agentic FB Analyst v1.0"
# create repo with GitHub CLI
gh repo create kasparro-agentic-fb-analyst-rohan-gupta --public --source=. --remote=origin
git push -u origin main
# create & push the v1.0 tag
git tag -a v1.0 -m "v1.0 — initial submission"
git push origin v1.0
```

(If you don't have `gh` installed, create a new repo on github.com and push to the remote manually.)

## Sample output preview
See `report.md` for a human-readable sample report. The JSON artifacts are in `insights.json` and `creatives.json`.

## License
MIT
