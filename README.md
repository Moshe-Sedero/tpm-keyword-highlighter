# TPM Keyword Highlighter

A browser bookmarklet that highlights Technical Project Manager keywords on any job posting - one click, no extensions needed.

## Install (one-time setup)

1. Open `bookmarklet.html` in your browser
2. Click **Copy URL**
3. Right-click your bookmarks bar and choose **Add favorite**
4. Set the name (e.g. `Highlight My Keywords`), clear the URL field, paste, and save

## Use

1. Browse to any job posting (LinkedIn, Greenhouse, Lever, etc.)
2. Click the **Highlight My Keywords** bookmark in your bar
3. Keywords highlight in yellow instantly
4. A panel appears top-right showing:
   - **Match score** (% of keywords found)
   - **Found** - green tags for every matched keyword
   - **Not found** - red tags for missing keywords
   - **Copy found** - copies matched keywords to clipboard for CV tailoring
5. Click **Clear** or the bookmark again to remove highlights

## Keywords

Tailored to a technical TPM profile with AI/ML, cloud, and DevOps background:

- **AI/ML:** generative AI, LLM, agentic, machine learning, synthetic data, ML pipeline, data pipeline, simulation
- **Cloud/DevOps:** CI/CD, DevOps, Docker, Jenkins, AWS, cloud migration, cloud-native, Linux
- **Tools:** Git, GitHub, Python, Jira, Confluence, Bitbucket
- **Domain:** autonomous, ADAS, end-to-end, PoC to production, release management, acceptance testing
- **PM/Leadership:** cross-functional, stakeholder, technical lead, team lead, roadmap, milestone, sprint, delivery, adoption, enablement

## Customize

To change the keyword list, update the JavaScript source in `bookmarklet.html`, re-encode it (use the PowerShell snippet in the repo), and reinstall the bookmark using the steps above.
