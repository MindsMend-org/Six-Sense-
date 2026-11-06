# Six Sense Lab

## Could you predict the next three?

Welcome to a tiny open experiment in intuition, memory, and chance. Learn six colour codes, make an ordered prediction, and see how it compares with a sequence drawn only after your guess is locked.

No special equipment. No account. No need to believe anything in advance. Bring your curiosity and give it a fair try.

**[Open the experiment](index.html)**

## Have a go

1. Open `index.html` in a recent browser. If your browser restricts local files, run a small local server from this folder with `python3 -m http.server 8000`, then visit `http://localhost:8000`.
2. Visit **Learn the code** and take a moment to learn the six number-colour pairs.
3. Start a session and choose how many rounds you want to do. Each round, pick three different numbers in the order you predict.
4. Lock your prediction before the draw. The app then draws and reveals the target sequence.
5. Check **Your results** to review your rounds or export them as JSON.

The exact ordered sequence has 120 possible outcomes, so a uniformly random guess has a 1-in-120 chance of matching all three places. The app also shows partial matches, but an exact ordered match is the experiment's primary outcome.

## The protocol

- The code is fixed: 1 red, 2 blue, 3 white, 4 black, 5 orange, 6 black-and-white stripes.
- Each target is three distinct numbers drawn uniformly without replacement from 1–6. There are $6 × 5 × 4 = 120$ ordered targets.
- The guess is locked before the target is generated.
- Target generation uses the browser's `crypto.getRandomValues` API with rejection sampling, then a Fisher–Yates shuffle.
- The primary outcome is an exact ordered match. For a total number of rounds fixed in advance, independent fair draws give a binomial model with per-round probability $1/120$.
- Results are saved only in your browser's local storage. Nothing is sent to a server. Exported JSON includes each guess, target, timestamp, match count, and protocol identifier.

## Interpret with care

This is an exploratory demonstration, not proof of ESP, a peer-reviewed study, or a test of anyone's abilities. Surprising short runs can happen by chance. The probability shown in the results view is the chance, under the stated fair-and-independent model, of observing at least that many exact matches in that many rounds, assuming the total number of rounds was fixed in advance. It is **not** the probability that ESP is real. Repeatedly checking results or choosing when to stop makes this display unsuitable as confirmatory evidence.

To keep the exercise honest, decide your session length before starting, include every round, and avoid restarting just because a run looks disappointing. If you share findings, include the number of rounds and the complete exported data, not only a striking streak. Participation and sharing are entirely optional.

This is a client-side learning project, not a tamper-proof research instrument. A participant can inspect or modify browser code and local data. A confirmatory experiment would need a preregistered protocol, independent oversight, and an independently audited target-generation process.

## Open science invitation

Try it, inspect the source, ask what could bias the result, and suggest improvements. If you run a session, you can share your exported data and a short note describing how you followed the protocol. Please do not include personal or identifying information. This version has no central results upload, so contributions are not automatically collected or combined.

Useful questions to explore:

- Do results across many rounds look consistent with the chance model?
- Does learning the code change accuracy, or just confidence?
- Which parts of the method would need independent verification before making a stronger claim?

## Project files

- `index.html` — the standalone experiment, protocol, and local results viewer.
- `README.md` — participant instructions and the open-science notes.

No build step or external dependencies are required. The experiment is designed for modern browsers with JavaScript and Web Crypto enabled.