## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/89

**Issue title:** API reference doc is missing the POST /profiles request body schema

**Tier:** [x] Tier 1  [ ] Tier 2  [ ] Tier 3

**Problem summary:**
The API reference doc (docs/API.md) lists the POST /profiles endpoint but only gives a one-line description with no request body details. Looking at the actual route in api/routes/profiles.py, the endpoint accepts three optional fields — github_username, portfolio_url, and resume_file — sent as multipart/form-data rather than JSON, since resume_file is a file upload. None of that is documented, so a developer reading the API reference has no way to know what to actually send without opening the code or the Swagger UI themselves. The fix is to update the POST /profiles entry in API.md to list each field, its type, whether it's optional, and the multipart/form-data content type.

**Branch name:** docs/89-profiles-request-body-schema

**Setup confirmation:** [x] App runs locally at localhost:5173

**Cohort ledger:** [ ] Issue added to cohort ledger



**Selection notes:**
I initially looked at #97, #87, and #101. #87 was Tier 3 (new webhook infrastructure) 
and #97 turned out to be Tier 3 as well, despite reading like a smaller frontend fix — 
its label was the deciding factor. #101 was Tier 2. Since this is my first open source 
contribution, the checklist says to stick with Tier 1, so I went back to the tracker 
filtered by tier-1 and found #89. It's confined to one doc file, has a clear before/after 
(missing schema vs. documented schema), and I confirmed the actual request body by reading 
api/routes/profiles.py before claiming it.