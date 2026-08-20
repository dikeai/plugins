---
description: Search Saudi, UAE, and Egyptian primary legal sources for a topic
---

Call `dike_search` with the user's query (Arabic or English) to find matching statutes, regulations, and case law across the configured jurisdictions.

Present the results as a short list: title, `citation_string`, and a one-line summary of the snippet for each. Don't editorialize about legal conclusions here, that's what `/dike-research` is for, this command is for browsing and comparing sources, not answering a question.

If the user hasn't specified a jurisdiction and it matters (results span multiple countries with materially different law), ask which jurisdiction before filtering, rather than silently picking one.
