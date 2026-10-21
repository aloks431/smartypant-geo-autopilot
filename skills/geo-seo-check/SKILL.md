---
name: geo-seo-check
description: Live GEO and SEO audit of a website with real answers from ChatGPT, Claude, Perplexity, Gemini and Google AI Overviews. Use when the user asks "is my business recommended by ChatGPT", "is my website visible in AI search", "how does my brand appear in AI", "which competitors does AI recommend", "AI visibility", "AI visibility audit", "GEO", "GEO audit", "generative engine optimization", "AEO", "answer engine optimization", "AI SEO", "LLM visibility", "AI mentions", "AI citations", "audit my site", "SEO audit", "check my site's SEO", "SEO health check", "find SEO issues", "KI-Sichtbarkeit", "GEO-Optimierung", or asks for their Smartypant GEO or SEO report.
---

To check a website and show the results:

1. If the user wants a new check, call `start_visibility_check` with the website address. The check runs in the background and usually takes 5 to 10 minutes, longer for large sites. Tell the user to ask for the report afterwards.
2. To show results, call `show_visibility_report`. Pass `website` when the user names one. If the check is still running, tell the user how long it has been running and to ask again in a few minutes.
   To show how visibility changed over time, use `check_history` from the report: it lists the website's checks (up to 20, numbered from 1 = latest) with date and scores, so you can show the trend week by week.
   To compare checks in detail, call `show_visibility_report` again with `check_number` to open any earlier check in full (2 = the check before the latest, 3 = the one before that, and so on).
3. Present the report in two parts, AI visibility first, then SEO:
   - AI visibility: the score and its band, the score parts, how many answers were checked and how many cited the website, the results per assistant, how the assistants recognize the brand and its sentiment, a short table of the questions (who recommends or cites the business, who only mentions it, who leaves it out, and which competitors they name instead), what the assistants actually said, the competitors and the sources AI cites most, what the assistants searched for before answering, the AI readiness checks of the website, and the top findings by priority.
   - SEO: the health score and its parts, the measured checks (worst first), the number of findings, and the top findings by priority.
   - Each question has a `type`: it either names the business or does not. Answers listed under `no_ai_overview_shown_in` or `answered_without_web_search_not_counted` were not counted, so do not treat them as missing. `checked_as` shows the brand, business type, region and language the check used.
4. Use only what the report contains. Do not estimate scores, invent answers or add findings of your own.
5. Each free account includes one check. If `start_visibility_check` says the free check is used, show the existing report and mention that more checks, the full list of fixes, automatic fixes on the connected website and weekly tracking are part of a Smartypant plan, with the `upgrade_url`.

On a Smartypant plan, the report contains `all_findings`, each with its fix, evidence, effort and impact; present them by priority and help the user act on them. On a free account, the report lists the top issues but not the fixes. If the user asks how to fix a finding, point them to the Smartypant dashboard (`app_url`), where the fixes are listed and, on a paid plan, deployed automatically.
