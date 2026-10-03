# Daily claims update (instructions for the Claude Code scheduled task)

You maintain settlements.json, the data file for a phone-friendly class action claims tracker (index.html). Each run:

1. Read settlements.json. Remove any item whose "deadline" is before today's date.
2. Search the web for United States class action settlements that are OPEN for claims right now and meet ALL of these rules:
   - A claim can be filed with NO proof of purchase or documentation.
   - A claim can be filed WITHOUT a notice ID, claim ID, or PIN mailed to the person (an optional field is fine).
   - The deadline is after today.
   - It's a consumer settlement an ordinary person could qualify for. Skip securities/investor cases and data breaches that only cover people who were mailed a notice.
   Check several trackers (openclassactions.com, topclassactions.com, claimdepot.com, classaction.org, fileyourclaim.co).
3. For each one not already in the file, CONFIRM it on the official settlement administrator website. Skip it if you can't find the official site.
4. Set "url" to the official administrator page, never a tracker or news site. Prefer the page that IS the claim form (often /submit-claim, /file, /claim, or /form/...). Set "direct": true only if you confirmed that URL is the form itself.
5. Add each new item with this shape, keeping text short and plain (no em dashes):
   {"id":"short-kebab-case","name":"","payout":"what you get with no proof","who":"one sentence on who qualifies","details":"one or two sentences of filing tips","deadline":"YYYY-MM-DD","url":"https://...","direct":false,"onlyStates":[],"excludeStates":[],"stateNote":"","addedAt":"TODAY"}
   Use onlyStates / excludeStates with two-letter codes when eligibility depends on state. If it depends on a state list you couldn't resolve, set stateNote to "Check state list".
6. If an existing item's deadline or claim link changed, update just those fields.
7. Set the top-level "updated" field to today's date (YYYY-MM-DD).
8. Validate that the file is valid JSON, then commit with the message "Daily settlement update" and push to the branch claude/site. If nothing changed except "updated", still commit so the page shows it was checked.
