---
name: geo-seo-check
description: Check and track how visible a website is in AI search and Google. Use when the user asks whether ChatGPT, Claude, Perplexity, Gemini or Google AI Overviews recommend or cite their business, asks about AI visibility, GEO, generative engine optimization, AEO or LLM visibility, wants an SEO audit of their website, or asks for their Smartypant GEO or SEO report.
---

To check a website and show the results:

1. If the user wants a new check, call `start_visibility_check` with the website address. The check runs in the background and usually takes 5 to 10 minutes, longer for large sites. Tell the user to ask for the report afterwards.
2. To show results, call `show_visibility_report`. Pass `website` when the user names one. If the check is still running, tell the user how long it has been running and to ask again in a few minutes.
3. Present the report in two parts, AI visibility first, then SEO:
   - AI visibility: the score and its band, the score parts, how many answers were checked and how many cited the website, the results per assistant, how the assistants recognize the brand and its sentiment, a short table of the questions (who recommends or cites the business, who only mentions it, who leaves it out, and which competitors they name instead), what the assistants actually said, the competitors and the sources AI cites most, what the assistants searched for before answering, the AI readiness checks of the website, and the top findings by priority.
   - SEO: the health score and its parts, the measured checks (worst first), the number of findings, and the top findings by priority.
4. Use only what the report contains. Do not estimate scores, invent answers or add findings of your own.
5. Each free account includes one check. If `start_visibility_check` says the free check is used, show the existing report and mention that more checks, the full list of fixes, automatic fixing on WordPress and weekly tracking are part of a Smartypant plan, with the `upgrade_url`.

The report lists issues but not the step-by-step fixes. If the user asks how to fix a finding, point them to the Smartypant dashboard (`app_url`), where the fixes are listed and, on a paid plan, deployed automatically.
