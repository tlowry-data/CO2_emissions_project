# Checklist & Timeline — 2 Days

This first project is intentionally short: 2 focused days, not a full week.
This is a **suggested pace, not a rigid schedule**, and every item below is
also the actual submission checklist — work through it in order (it matters
here, see the ⚠️ below), don't just treat it as a list to shuffle.

> A note on this: for this first project, we're handing you a ready-made
> timeline because you're still getting oriented to the whole workflow. As
> you move through the program, you'll be expected to plan your own
> pacing — later projects may ask you to set up your own tracking instead of
> working from a timeline someone else wrote for you. Treat this one as a
> model of what breaking a project into checkpoints looks like, not just a
> checklist to follow on autopilot.

This project doesn't involve writing Python code — every step below is a
terminal command you run and record, not a program you write.

## Day 1 — Environment setup, raw look, first commits

- [ ] Terminal, Git, GitHub account, and VS Code installed/ready.
- [ ] Repo created from the template via **"Use this template"** (not Fork)
  and cloned locally — see `README.md`.
- [ ] Your own `.gitignore` created with the lines from `README.md` Step 4
  (and you can explain what each one is for).
- [ ] `field_notes.md`'s "Setup log" section opened and started — log
  commands as you go, in fenced code blocks tagged `bash`, not reconstructed
  from memory later.
- [ ] Confirm `data/co2_emissions_2022.csv` is present — included in the
  template, everyone uses this same file.
- [ ] Look at the raw CSV as plain text **before running any column-preview
  commands** (`field_notes.md` section 1 — which command to use for this is
  part of what's being tested, so it isn't named here).
  > ⚠️ Common mistake: listing column names without ever actually opening and
  > looking at the raw data first.
- [ ] Jot down what you notice from the raw look (section 1).
- [ ] Commit: `git commit -m "add gitignore"`, then
  `git commit -m "add raw data"` — don't wait until everything's done to
  commit for the first time.
- [ ] Find and log a command that shows just the column names, then a
  command that previews real values for at least 5 of the 6 columns
  (sections 2-3) — paste the real output you got, not values you're
  assuming.
  > ⚠️ Common mistake: misclassifying an ID-like or ZIP-code-like column as a
  > true numeric variable.
- [ ] Answer, in your own words: what's the actual difference between a
  list/array and a table? (section 3)
- [ ] State whether the dataset is structured or unstructured, with a reason
  (section 4).
- [ ] Commit: `git commit -m "add column-type notes"` — this is commit #2,
  the MVP bar is met once this lands, but keep going.
  > ⚠️ Common mistake: committing everything in one big "final" commit
  > instead of showing incremental progress.

**Exit criterion:** at least 2 real commits pushed to GitHub by end of day —
`git log --oneline` should already tell a real story, not be empty.

## Day 2 — Reflections, polish, submit

- [ ] Find and log the commands that answer section 5's two counting
  questions (real output pasted, not assumed), then list **at least 2**
  things you'd want to know about how this dataset was collected before
  trusting it.
- [ ] Turn the most specific/checkable of those into one real data-quality
  question for the source (section 6). *(Answers will vary.)*
  > ⚠️ Common mistake: a vague question like "is this data good?" — if the
  > data's maintainer couldn't actually answer it with something concrete,
  > it's not specific enough.
- [ ] Write a **separate** question — something you're genuinely curious to
  explore using this data, not another data-quality check (section 7).
  *(Answers will vary.)*
- [ ] AI-literacy reflection: 2 concrete risks of trusting unverified AI
  output, plus one specific personal rule for double-checking AI-provided
  facts (section 8). *(Answers will vary.)*
  > ⚠️ Common mistake: a rule too vague to actually follow, like "I'll be
  > careful."
- [ ] Commit: `git commit -m "add reflection"`.
- [ ] Setup log has real commands from throughout the project (not just a
  token line), each in a fenced code block tagged `bash`; section 9 includes
  a real error (or unexpected result) and how you diagnosed it.
  > ⚠️ Common mistake: a vague or generic-sounding note that could've been
  > written without actually hitting it.
- [ ] **Replace `README.md`'s content with your own real project README** —
  what the dataset is, its license/source, your data-quality question, and
  your key findings. Write it for someone who's never seen this assignment,
  not someone grading it:
  - **Scenario & Questions** — the real-world scenario this data relates
    to (see `PROJECT_OVERVIEW.md`, before you delete it below) and the
    specific questions you set out to answer by inspecting the file.
  - **Dataset Overview** — what it is, source, license.
  - **What I Found** — real column-type calls and a couple of concrete
    observations.
  - **Data Quality Question** — the one you settled on, and why.
  - **Reflection** — your AI-literacy takeaway.
- [ ] Self-check against this checklist before calling it done.
- [ ] **Delete `PROJECT_OVERVIEW.md` and this file (`CHECKLIST_TIMELINE.md`)**
  — now that their content is captured in your real README, they're just
  "here's what you were asked to build" clutter that shouldn't sit in a
  real portfolio repo.
- [ ] Final push to GitHub — confirm the repo is actually **public** (open
  it in a private/incognito browser window to check).

**Exit criterion:** everything above is done and pushed. That's the whole
submission — the Above & Beyond items below are optional, for if you finish
with real time left over.

## Share-out (this week, during TIP)

This week during TIP, we'll share out your data-quality questions, how you
used AI, and any reflections from the project — so come ready to talk about
your project.

## Above & Beyond

Optional — only if you finish the checklist above with time to spare. Pick
one or two; you don't need to do all of them. A complete submission without
any of these is still a full, passing submission. None of them require
writing code except the last, which gives you the code to run. Log whatever
you do in `field_notes.md`.

- [ ] **Chain terminal commands** (`|`, `&&`) to answer a real question about
  the dataset that a single command couldn't — `grep`, `head`, `wc`, `cut`,
  whatever fits. A starting idea: of the rows missing `gdp` (section 5), how
  many are real countries (non-empty `iso_code`) vs. aggregate rows? That
  needs an `awk` one-liner combining both conditions — worth looking up.
- [ ] **Find the min and max of a numeric column.** Isolate one column (same
  technique as section 3), skip the header row, drop blanks, then sort
  numerically (not alphabetically — figure out which flag does that) and
  look at the first and last result. Try `co2`, `population`, or `gdp`. Does
  anything look suspicious — like a min of exactly 0 that might be a
  missing-value placeholder?
- [ ] **Decide whether to approve an AI-suggested command.** Ask an AI
  assistant for a terminal command to do something in this project.
  **Before running it:** explain in your own words what it does, and flag
  anything destructive or hard to undo (`rm`/`rm -rf`, `git reset --hard`, a
  force-push). Then approve it as-is, modify it, or reject it — and say why.
  Only then run what you approved, and log the real result.
- [ ] **Use a branch instead of committing straight to `main`.** Create a
  branch for your field-notes work, commit there, then merge it back.
- [ ] **Preview of Module 1 — code given, you don't write it.** Save this as
  `preview.py` and run it with `python3 preview.py` (if you don't have
  Python installed, just read through it):
  ```python
  def guess_type(value):
      """Given one value (as a string), guess what type of data it is."""
      if value == "":
          return "missing"
      try:
          int(value)
          return "whole number"
      except ValueError:
          pass
      try:
          float(value)
          return "decimal number"
      except ValueError:
          pass
      return "text"

  print(guess_type("40578847"))    # a population value
  print(guess_type("10.170"))      # a co2 value
  print(guess_type("Afghanistan")) # a country name
  print(guess_type(""))            # a missing gdp value
  ```
  In `field_notes.md`, write 1-2 sentences: does `guess_type()` agree with
  your own column-type table from section 3? Where might it disagree, and
  why?
