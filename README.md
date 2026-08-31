# Automation Test Engineer — Take-Home Challenge

Thanks for your interest in Niyam IT.

Build a small UI automation framework against **https://demo.niyamit.com**, a password-protected preview of our new website. It's a real React app — animated, no test hooks, no convenient `data-testid` attributes. That's the interesting part.

**Aim for about two hours.** There's no deadline and nobody's timing you. Start when you have a clear afternoon, stop when you're happy with it, and tell us what you'd have done with more time.

---

## What we care about

**Reusability, mostly.** We're not counting test cases. Three scenarios built on something another engineer could extend beats fifteen copy-pasted ones.

The question in our heads while reading: *if we asked someone to add coverage for a page you never touched, how much of your code would they reuse?*

---

## Getting started

1. **Email us for the password** when you're ready to begin.
2. **Make a private copy of this repo.** GitHub's Fork button always produces a *public* fork, so use [the import tool](https://github.com/new/import) instead — paste `https://github.com/Niyam-Projects/automation-tech-challenge`, name it whatever you like, set it **Private**.
3. **Build.** Java + Selenium is what we use and the smoothest path, but use what you're strongest in — just tell us why in your notes.
4. **Share it back.** Add the interviewer named in your email as a collaborator. That's the whole submission.

The site sits behind an Azure password gate, so every browser session starts there. Keep the password in an environment variable, not in your repo.

---

## The one hard rule

**Don't let a contact form submission reach our servers.** It emails a real inbox. If we get a message from you, that scenario is scored as a failure — everything else on this page is guidance, but this one is firm.

Otherwise: don't automate third-party domains (the job listings link out to an external ATS), don't load-test us, and don't go looking for vulnerabilities.

---

## What to build

Pick **three** of these. They're roughly ordered by how much they'll teach us.

**Careers page filters.** Positions load asynchronously and can be narrowed by department, location, and employment type — and those filters combine. Verify filtering works. This is the best showcase for reusable design, since the combinations multiply fast and the job list changes as we hire.

**Contact form.** Two halves. First, validation — which fields are required, how a bad email is handled, how errors surface. Invalid submissions never leave the browser, so test that freely.

Second, and more interesting: **prove a correctly filled form would build the right request, without sending it.** Not by refusing to click, which tests nothing — by actually verifying the request the app would make. There are several reasonable ways to do this and we're curious which you pick and why. If it eats your whole budget, stop and just write up your approach; that scores fine.

**Navigation.** Get from the home page to three other pages using the site's own nav, including one behind a dropdown. Assert you arrived. The nav is on every page, so it's a good test of whether you wrote it once.

**Anything else that interests you** — the blog's search and pagination, mobile viewport, the accelerator detail pages. Or file a bug report; there are real bugs here, and a good one is worth more to us than another passing test.

---

## A few things worth knowing

Spend ten minutes in DevTools before you write anything. On this site the reconnaissance genuinely is the work — how routing and rendering happen here has direct consequences for how you navigate and wait, and people who skip this step spend the whole afternoon fighting symptoms.

Some honest warnings:

- **There are no test hooks.** Two `aria-label`s in the entire app, some section IDs, and generated class names. Some element IDs aren't stable across reloads — check before you build on one.
- **The site is heavily animated.** Content arrives after the page does, text animates in, and things move while you're trying to click them. An element existing isn't the same as it being ready.
- **No `Thread.sleep()`, please.** If you genuinely can't find a deterministic wait for something, leave a comment saying what you tried — that's a much better answer than a hidden sleep.
- Run your suite a couple of times before sending. If it's flaky, telling us is better than us finding out.

Where a locator feels fragile, say so and tell us what you'd ask a developer to add. The site is pre-launch, so that feedback is real and we'll act on it.

---

## Tell us how you used AI

We expect you to use it, and we want to see how. Using it won't count against you — hiding it will.

Drop a **`AI-USAGE.md`** in the repo with your session transcript (most tools can export one; a copy-paste is fine) and a short note on:

- What you used, and roughly how much of the code came from it
- **Where it was wrong, and how you caught it** — this is the part we actually read
- What you wrote yourself

A transcript showing you rejected three bad suggestions beats polished code you can't explain. Whatever you submit, you own — be ready to walk through any of it with us.

If you didn't use AI at all, just say so.

---

## What to send back

Your private repo, with the interviewer added, containing:

- The tests
- A short **README** — how to run it, and how your code is organized
- **`NOTES.md`** — what you'd do with more time, anything that fought you, any bugs you found
- **`AI-USAGE.md`**
- No secrets committed

That's it. Questions, or something broken? Just email us — and if you get stuck on a locator or a wait, write it up in `NOTES.md` and move on. A clear account of what defeated you earns real credit.

Good luck — we're looking forward to reading it.
