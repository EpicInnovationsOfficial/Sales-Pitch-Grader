READ ME
(Also available here: https://github.com/EpicInnovationsOfficial/Sales-Pitch-Grader/blob/main/sales-pitch-grader-repo/README.md)

Sales Pitch Grader — Sales Communication Scorecard & Rewriter
Built by Epic Innovations, Inc., shared for anyone who wants an honest, structured read on their sales emails and call transcripts.

What this is
A Claude skill that grades sales emails, scripts, proposals, or call transcripts against established sales-psychology frameworks — tonality, rapport-building, question quality, objection handling, reframing, positioning, and closing — and hands back a scorecard plus a rewritten version. It's built to catch the structural and delivery issues that cost sales reps deals: predictable questions, answering objections instead of reframing them, chasing the prospect instead of being chased, and more.

This skill is modular. For the word-and-phrase-level pass (removing fear-, pressure-, and cliché-triggering language), it calls Epic Innovations' companion skill, **Objection-Proof Editor**, rather than duplicating that logic. You'll want both skills installed together — see Setup below.

Setup (5 minutes)

1. Copy this whole `sales-pitch-grader` folder wherever your Claude surface loads skills from.
2. Also install the companion skill, **Objection-Proof Editor** (separate repository) — Sales Pitch Grader calls it during the review, and won't produce a full result without it.
3. Have your sales email, script, or call transcript ready — paste it in or attach it.
4. Ask Claude to run the Sales Pitch Grader on it, and tell it what stage of the sales cycle the content is from if it doesn't ask (cold outreach, early discovery, rapport-building, or late-stage/closing) — several techniques are only graded as correct once rapport is established.
5. You'll get back: a stage confirmation, a category-by-category scorecard with an overall letter grade, a rewritten version of your content, a summary of the changes and why they were made, and (for two-sided call transcripts) notes on anything the prospect said worth paying attention to.

Why grade instead of just rewrite
A straight rewrite tells you what to say differently. A grade tells you where you actually stand — which parts of your pitch are already strong, which are genuinely weak, and which matter most for the stage you're at — so you know what to prioritize practicing, not just what to paste into your next email.

Privacy
Whatever you submit for review is your own sales material. Nothing here is intended to train or improve any third-party model, and you shouldn't need to share your content outside your own Claude conversations.

License and terms
© 2026 Epic Innovations, Inc. All rights reserved. This repository is shared free of charge under specific terms — see [LICENSE](https://github.com/EpicInnovationsOfficial/Sales-Pitch-Grader/blob/main/sales-pitch-grader-repo/LICENSE) and [TERMS_OF_USE.md](https://github.com/EpicInnovationsOfficial/Sales-Pitch-Grader/blob/main/sales-pitch-grader-repo/TERMS_OF_USE.md) before using or sharing it. In short: free to download and use for your own sales work, not free to resell, rebrand, or redistribute as your own.
