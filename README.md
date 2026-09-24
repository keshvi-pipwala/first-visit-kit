# First Visit Kit

Live demo: https://keshvi-pipwala.github.io/first-visit-kit/

A working concept for one problem: getting a local brand from signup to its first creator visit faster. I made it for Storytime's Software Engineer, Product & Growth application. It's an independent concept and isn't affiliated with Storytime.

Concept, models and product decisions by Keshvi Pipwala. The code was written with AI coding tools.

## The five tools

| Tool | What it does | Decision behind it |
|---|---|---|
| Launch | Starts from one sentence the owner types ("café in Nolita, slow weekday mornings, $10 off"). Fills the setup, and outlines any field under 0.85 confidence for the owner to confirm. Then forecasts creators reached, visits in 30 days, offer cost per post and days to first creator visit, and flags weak settings with a one-tap fix. | Owners don't think in reach tiers. A brand that sees no visit in week one leaves before it sees value, so the forecast is shown before launch, not after. In production the intake is one LLM call with a fixed schema; here a rule-based parser stands in so it runs without a key. |
| Match | Ranks creators with a score out of 100 and the reasons behind it. Everyone held back gets a stated reason. Drafts invites for the top 3. | Distance outweighs follower count by default. A creator nearby can come back; one across the river usually visits once. |
| Post check | Scores each post (brand tag, location tag, caption, paid-post disclosure, timing, wrong venue) and auto-approves only above a confidence threshold. The rest go to a person with a reason. | Default threshold 0.85. Missing disclosure always goes to review. Precision is measured live against 72 labeled posts. |
| Brand report | An eight-week report for a fictional café, written for the owner. | Leads with visits and posts; ends with one thing to change. |
| Growth plan | Activation funnel, event spec, three experiments and a daily stalled-brand queue for the partnerships team. | Each experiment targets one funnel step and has a metric, a guardrail and a decision rule. |

## Data and assumptions

All brands, creators and numbers are synthetic and generated from a fixed seed, so the page is reproducible. Acceptance rates, offer anchors, the funnel shape and post-check weights are my assumptions and are written out on the page under each tool. With real acceptance logs and signup events, each becomes a fitted model.

## Run it

It's one static file. Open `index.html` in a browser, or serve the folder with any static host. No build step, no API keys.
