# PR Response Doc — CineLog Watchlist Feature

## AI Usage
<!-- Fill in at the end — how you used AI tools during this project -->

## Comment 1 — Rename
**What I did:** Renamed `save_to_watchlist()` to `add_to_watchlist()` to match the project's `verb_to_noun` service naming convention, then updated the watchlist route's import and call site.
**How I verified:** Searched the entire project for both function names, confirmed there were no remaining `save_to_watchlist` references, and ran the test suite.

## Comment 2 — Deduplication
**What I did:** Added `AlreadyInWatchlistError` and made `add_to_watchlist()` query for an existing entry with the same `user_id` and `film_id` before creating one. A duplicate now raises the dedicated error before any database write, following `add_to_collection()`'s pattern.
**How I verified:** Added the same film twice in an isolated in-memory database, confirmed the second call raised `AlreadyInWatchlistError`, and confirmed only one matching `WatchlistEntry` remained. I also ran the full existing test suite.

## Comment 3 — Missing test
**What I did:**
**How I verified:**

## Comment 4 — Default visibility
**My position:**
**Reasoning:**
**Tradeoff acknowledged:**

## Comment 5 — Sort order
**My position:**
**Reasoning:**
**Engagement with reviewer's point:**

## Comment 6 — Rebase
**What conflicted:**
**How I resolved it:**
**How I verified no conflict remains:**

## PR Description
<!-- Written at the end — feature overview, design decisions, manual testing steps -->
