# TPM Keyword Highlighter

A browser bookmarklet that highlights keywords on any job posting and shows your match score - one click, no extensions needed.

## Install (one-time setup)

1. Open `bookmarklet.html` in your browser
2. Click **Copy URL**
3. Right-click your bookmarks bar and choose **Add favorite**
4. Set the name (e.g. `Highlight My Keywords`), clear the URL field, paste, and save

## Use

1. Browse to any job posting (LinkedIn, Greenhouse, Lever, etc.)
2. Click the **Highlight My Keywords** bookmark in your bar
3. Keywords highlight in color instantly
4. A panel appears top-right showing:
   - **Match score** (% of keywords found)
   - **Your CV** - green tags for matched CV keywords
   - **Role Keywords** - blue tags for matched role keywords
   - **Missing** - red tags for keywords not found
   - **Copy found** - copies all matched keywords to clipboard for CV tailoring
5. Click **Clear** or the bookmark again to remove highlights

## Keywords

Two color-coded lists tailored to Moshe's profile and target roles:

### Green - Your CV (41 keywords)
Keywords directly from the CV: CI/CD, Scrum, agile, Jira, Confluence, Jenkins, Docker, Linux, Python, Bash, GitHub, Bitbucket, Git, simulation, synthetic data, ML pipeline, data pipeline, autonomous, ADAS, cloud migration, DevOps, generative AI, LLM, agentic, release management, acceptance testing, requirements traceability, regression testing, end-to-end, PoC to production, cross-functional, stakeholder, sprint, milestone, roadmap, version control, AWS, self-service, enablement, adoption, workshop

### Blue - Role Keywords (38 keywords)
Common keywords for target roles (Senior TPM, Delivery Manager, Release Manager, AI Program Manager, Technical Account Manager, etc.): program management, technical program manager, delivery manager, release manager, AI program manager, technical account manager, customer success, OKR, KPI, metrics, risk management, dependency management, escalation management, capacity planning, resource allocation, executive stakeholder, SAFe, PI planning, change management, process improvement, SLA, incident management, go-to-market, launch readiness, MLOps, AI governance, model deployment, continuous improvement, operational excellence, technical roadmap, RACI, data-driven, onboarding, renewal, QBR, NPS, accountability, program planning

## Customize

To change the keyword lists, update the JavaScript source in `bookmarklet_src.js`, re-encode it using the PowerShell snippet below, and paste the output into the `<textarea>` value in `bookmarklet.html`, then reinstall the bookmark.

```powershell
$src = Get-Content "bookmarklet_src.js" -Raw -Encoding UTF8
$src = $src.TrimEnd("`r","`n"," ")
$url = "javascript:" + [System.Uri]::EscapeDataString($src)
$url | Set-Clipboard
```
