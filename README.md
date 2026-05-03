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
3. Keywords highlight in color instantly - across the full page
4. A panel appears top-right showing:
   - **Match score** (% of green + blue keywords found in main content)
   - **Your CV** - green tags for matched CV keywords
   - **Role Keywords** - blue tags for matched role keywords
   - **Negative signals** - red tags for mismatch indicators (shown only if found)
   - **Missing** - dimmed red tags for keywords not found in each list
   - **Copy found** - copies all matched green + blue keywords to clipboard for CV tailoring
5. Click **Clear** or the bookmark again to remove highlights

## Score calculation

The match score counts only keywords found in elements that are in normal document flow (position static or relative, not hidden). This excludes navigation bars, sticky headers, sidebars, and fixed overlays - so the score reflects the actual job description content, not repeated site chrome.

## Keywords

Three color-coded lists:

### Green - Your CV (55 keywords)
Keywords directly from the CV:
CI/CD, Scrum, agile, agile methodology, Jira, Confluence, Jenkins, Docker, Linux, Python, Bash, GitHub, Bitbucket, Git, simulation, synthetic data, ML pipeline, data pipeline, autonomous, ADAS, cloud migration, DevOps, generative AI, LLM, agentic, release management, release process, release lifecycle, acceptance testing, UAT, requirements traceability, requirements management, regression testing, end-to-end, end to end, PoC to production, cross-functional, cross functional, stakeholder, stakeholder management, sprint, milestone, roadmap, product roadmap, version control, AWS, self-service, self service, enablement, adoption, workshop, requirements elicitation, scrum master, system engineering, Automotive

### Blue - Role Keywords (51 keywords)
Common signals for target roles (Senior TPM, Delivery Manager, Release Manager, AI Program Manager, Technical Account Manager, etc.):
program manager, programme manager, project manager, project lead, technical program manager, delivery manager, release manager, AI program manager, technical account manager, product owner, project lifecycle, release cycle, release lifecycle, cross-functional teams, cross functional teams, R&D teams, engineering teams, global teams, matrix management, matrix environment, escalation, escalation management, dependency management, risk management, risk mitigation, capacity planning, resource allocation, resource planning, executive stakeholder, change management, process improvement, continuous improvement, operational excellence, technical roadmap, definition of done, DoD, vendor management, onboarding, customer onboarding, program planning, programme management, OKR, KPI, go-live, go live, team leadership, technical leadership, technical background, senior leadership, software development lifecycle, project/program management

### Red - Negative Signals (44 keywords)
Indicators that a role is likely a mismatch:
junior, associate, student, entry level, sales, account executive, business development, marketing, finance, recruiter, chip, silicon, VLSI, ASIC, FPGA, semiconductor, hardware engineer, mechanical engineer, software engineer, data scientist, data engineer, ML engineer, DevOps engineer, QA engineer, technical support, tier 1, tier 2, help desk, full stack, frontend, backend, React, Node.js, Java, C++, C#, Golang, TypeScript, REST API development, microservices, hands-on coding, write code, coding skills required, software engineering experience

## Customize

To change the keyword lists, update `bookmarklet_src.js`, re-encode with the PowerShell snippet below, and paste the output into the `<textarea>` value in `bookmarklet.html`, then reinstall the bookmark.

```powershell
$src = Get-Content "bookmarklet_src.js" -Raw -Encoding UTF8
$src = $src.TrimEnd("`r","`n"," ")
$url = "javascript:" + [System.Uri]::EscapeDataString($src)
$url | Set-Clipboard
```
