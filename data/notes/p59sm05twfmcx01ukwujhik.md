
- We are returning `status` and `rejectedStatus` and each category has a `dateConsented`.
- The `/latest-version` endpoint returns each category and the `publishedAt` date for it.
- The script then iterates through rejected status and it builds the `rejected kv targets`.
- The script goes through status and checks to see if consent is valid if it is, it builds it as a `consented kv target` or a `outdated kv target`.
-  