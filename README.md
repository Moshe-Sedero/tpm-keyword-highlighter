# TPM Keyword Highlighter

A browser bookmarklet that highlights Technical Project Manager keywords on any job posting - one click, no extensions needed.

## Install

1. Open `bookmarklet.html` in your browser
2. Drag the gold button to your bookmarks bar (or use Option B to copy the URL and create a bookmark manually)

## Use

1. Browse to any job posting (LinkedIn, Greenhouse, Lever, etc.)
2. Click the **Highlight TPM Keywords** bookmark
3. Keywords light up in yellow instantly
4. A panel appears top-right showing your **match score (%)**, keywords found vs not found
5. Click **Copy found** to copy matched keywords to clipboard (handy for tailoring your CV)
6. Click **Clear** or the bookmark again to remove highlights

## Keywords covered

Agile/Scrum methodology, project management terms (roadmap, milestone, sprint, backlog), technical skills (architecture, cloud, API), tools (JIRA, Confluence, Azure DevOps), certifications (PMP, CSM, PRINCE2), and soft skills (stakeholder, cross-functional, leadership).

## Customize

To change the keyword list, open `bookmarklet.html` in a text editor, update the `keywords` array in the `<script>` block at the bottom, then re-install the bookmark using Option B (copy URL).
