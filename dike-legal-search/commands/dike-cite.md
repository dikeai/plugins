---
description: Parse and verify a legal citation string against the real document
---

Call `dike_cite` with the citation string the user provided (Arabic legislation, ministerial/presidential decree, cassation ruling, or fatwa formats are all supported).

Report back:
- The parsed components (document type, number, year, article number if present)
- Whether it resolved to a real document (`document` present in the response) or not

If it didn't resolve, say clearly that the citation couldn't be verified against the corpus, don't guess what document it might be referring to. A citation that fails to resolve is meaningful signal (it may not exist, may predate this corpus's coverage, or may be misquoted), not something to paper over.
