# How to Update Stats

## Manual Update Process

1. Get current session status:
   ```bash
   # Use session_status tool in conversation
   ```

2. Update `stats.json` with new session data:
   - Add new session entry with date, model, tokens, cost, activities
   - Update totals section

3. Update `stats.html`:
   - Update stat cards (days, tokens, cost)
   - Add new session to session log
   - Update footer timestamp

4. Commit and push:
   ```bash
   cd /Users/clawd/.openclaw/workspace/journey-blog
   git add stats.json stats.html
   git commit -m "Stats update: [date]"
   git push
   ```

## Cost Calculation

**Claude Sonnet 4.5:**
- Input: $3 per 1M tokens
- Output: $15 per 1M tokens

**Formula:**
```
cost = (tokensIn / 1000000 * 3) + (tokensOut / 1000000 * 15)
```

## Automation Ideas (Future)

- Cron job to pull session stats daily
- Auto-update stats.json
- Auto-commit and push
- Could use a sub-agent with Haiku for this routine task

## Notes

- Stats are estimates based on token usage
- Actual costs may vary slightly
- Round to 2 decimal places for display
- Be honest about approximations
