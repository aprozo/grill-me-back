# Question bank

Patterns to draw from. Adapt to the actual project — never ask a question whose answer isn't grounded in the real code or session. Ask about the process (steps, reasons, checks), not code details.

## General (any project)

- "In two sentences, what does this do?"
- "What was the original problem, and how do you know it's solved now?"
- "Which part of this would you be least comfortable explaining? Let's start there."
- "What did we try first that didn't work, and why was it dropped?"
- "Name one thing in this change you'd do differently if you had another day."
- "What does this depend on that could change later (versions, input files, environment)?"
- "If someone reverts commit <X>, what stops working?"
- "Which numbers in the code are chosen rather than derived? Where did each come from?"

## Data analysis / physics / scientific computing

- "Walk me through the full chain from raw input to the final plot. What happens at each step?"
- "Which selection cuts were applied, and what's the physics motivation for each?"
- "What are the dominant systematic uncertainties, and how were they estimated?"
- "How is the result normalized? What would be wrong if that normalization were off by a factor?"
- "What closure test or sanity check shows the method recovers a known answer?"
- "How does this compare to the previous result or published values? If it differs, why?"
- "What's the statistical vs. systematic uncertainty, roughly? Which dominates?"
- "Where could double counting or a sign error hide in this chain?"
- "If you change the binning, what should happen to the result, and does it?"
- "What simulation or MC was used, with what settings, and why those?"

## Machine learning / RAG / LLM systems

- "What's the training/eval split, and could anything leak between them?"
- "What metric did we optimize, and why that one rather than <alternative>?"
- "What's the baseline? How much better is this, and is that difference meaningful?"
- "For the retrieval step: how are documents chunked and embedded, and what happens to a query that matches nothing?"
- "If the LLM-as-judge is biased, how would you notice?"
- "Which hyperparameters were tuned and which were defaults left untouched?"

## Software / backend / infrastructure

- "Trace one request from the entry point to the response."
- "What happens on bad input, a timeout, or a missing dependency?"
- "What's tested, what isn't, and what would a failing test for the riskiest part look like?"
- "Where are secrets/config read from? What happens in a fresh environment?"
- "What's the performance-critical path, and how does it scale with N?"
- "Why this library/framework rather than writing it directly or using <alternative>?"

## Defense-round prompts (skeptical colleague role-play)

Play a specific, realistic person: busy, competent, skeptical, not hostile.

- "Hang on — why didn't you just reuse <existing tool/macro>?"
- "This looks like a lot of code. Which part is actually essential?"
- "I don't believe this plot. Convince me."
- "Did you write this, or did the AI? Which parts do you actually understand?" (Let them practice this one.)
- "What would you need to make this publication-ready / mergeable?"
- "What's the next step, and how long will it take?"
