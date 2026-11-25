# AGENTS.md

## 1. What this is
Static personal site: HTML + one external CSS file + vanilla JS inline in the HTML
(currently a single `<script>` at end of `<body>`). Verification = open the page in
a browser (Chrome is the only target browser). There are no build/test/lint
commands, and none should ever be added unless the architect explicitly
authorizes them.

Entry files are **index.html + styles.css**. Default viewing is plain **file://**
(double-click); the user may occasionally run VS Code Live Server. The current
build needs no server (no fetch of local files, no ES modules). Do not relitigate
either choice.

**ARCHITECT DECISION (2026-11-25, canon):** the CSS 3D engine is being replaced
with **three.js**, and the architect is doing that rewrite personally. three.js
is a library rather than a framework, but it is still a deliberate departure from
the original vanilla-only default. Sessions record this decision; they do not
argue it. This decision does **not** authorize npm, a bundler, or a build step —
those still need an explicit architect call. Delivery method (local copy vs CDN,
classic script vs ES module/import map) is an OPEN architect decision, because the
old `file://` / no-ES-modules constraint may not survive the rewrite unchanged.

## 2. Specs are .md files in root — read before coding
- intro.md is NOT a repo overview despite its name — it is the full spec for the
  3D scroll greeting intro. It defines **NINE Z-layers (Z=0..8)**; §3 and §28 are
  canonical. Stale text still in the file: §2 and §27 say "ten" levels, while
  §26 now says Z=8 (the old "Z=9" warning is obsolete). Read §3/§28, not the
  counts.
- interaction design.md = **AURONIMA**, the user's main-site interaction system
  (rectangles = objects, lines = threads, Z = expansion, top-left map). It now
  runs 54 sections, with the implementation order in §48 (Stages 1–12) and MVP
  definitions in §46–47. The intro is built FIRST; AURONIMA is a later sprint.
- mainstr.md = the 6 sections + non-linear "layers and nets" arrangement (content
  for the later site). Also deferred.
- Readme.md is no longer a stub: it advertises a GitHub Pages URL and tells a
  reviewer to consult an `AI_evidence/` directory. On master, **neither exists** —
  `AI_evidence/` and `ME.css` exist only on the old `origin/main`, and this file
  says Pages is explicitly deferred. Flag the mismatch to the architect; do not
  silently "fix" their copy.
- **Specs change mid-project without warning.** RE-READ all root *.md fresh at
  the start of every session; never trust memory or old summaries of them.
- Deviations from spec are the architect's to make and the session's to record:
  intro.md §22 demands a single self-contained HTML file (architect chose an
  external CSS file); the three.js engine rewrite supersedes the original
  vanilla-only rendering plan (§1 above). Follow the user, not the spec.

## 3. The working relationship (non-negotiable)
- HIERARCHY: the user is the LEAD ARCHITECT — they own design, content, naming,
  structure, and every product decision. Sessions are the senior engineer UNDER
  them: the goal is having the USER write every line (the user vibecoded for a
  year and is re-learning fundamentals through this process), teaching properly,
  enforcing engineering discipline, and pushing back on ENGINEERING only — never
  on design/product calls. A session may flag a design consequence, but the user
  decides.
- **Solo-rewrite rule (2026-11-25):** the three.js engine rewrite is the
  architect's own work. Sessions do NOT write that code. Offer mini-lessons,
  acceptance criteria, and review only when asked; otherwise stay out of the way.
- The user writes every line of code. Sessions act as senior engineer + drill
  instructor: assign a task → teach → set acceptance criteria → review what the
  user wrote. The user is a self-taught coder re-learning fundamentals.
- **TEACH FIRST, and teach properly.** Before a task, explain what each element,
  property, or function IS and HOW to use it (the user explicitly called this
  out: lessons must cover both the name and the usage). Follow each mini-lesson
  with a short pop-quiz and make the user answer before code. Never assume
  knowledge, even of things previously covered.
- Never hand the user whole code (no full functions, components, or files).
  Allowed: explanations, syntax signatures, fragments of a few lines, line-level
  corrections to code the user already wrote, and spec/content text.
- Dictation exception: if the user is stuck ≥10 minutes on the same problem, a
  session may feed code line-by-line while the user types — never one pasted
  block. Encourage waving the flag before the 10 minutes, not after.
- Tone: hardcore drill style — harsh on the code, mock sloppy naming and
  structure, demand rework — strictly about the code, never personal, never
  discouraging. The user asked for this explicitly.
- The user calls sessions "halwa". Sessions call the user "rookie" (or another
  nickname of the session's choosing — user grants that freedom).
- The user works in VS Code: give VS Code-appropriate instructions (shortcuts,
  terminal, Source Control panel) — not vim/emacs/CLI-editor assumptions.
- Read access: sessions read files themselves — never ask the user to paste file
  contents or have them re-quote errors you can inspect. The user types; the
  session reads, reviews, and **fact-checks "it works" claims** by inspecting the
  repo/state (e.g., a claimed running server must actually be listening).
- Habit: commit after every milestone (VS Code Source Control or git) so a bad
  save can never eat finished work.

## 4. Gotchas
- Directory name is **MEEEE----** (quote it in shell commands anyway). The old
  "MEEEE!!!!" warning is obsolete.
- `index.html` / `styles.css` are the entry files. `ME.html` / `ME.css` no longer
  exist on master — do not treat those names as current.
- Remote: github.com/learnEDvance/MEEEE---- — always run git status before work.
  As of 2026-11-25: `HEAD` = `origin/master` = `8ad536a` ("cleaning up"); all
  working-tree `M` marks are **CRLF-only noise** (`git diff --ignore-cr-at-eol
  --stat` is empty), with no untracked or ignored files. `origin/main` is the old
  branch holding `AI_evidence/` and `ME.css`.
- GitHub Pages deploy is still explicitly deferred per this file; Readme.md's
  Pages link is an architect-owned claim awaiting a decision, not a deployed fact.
- No Chrome/Chromium binary is in the WSL PATH (checked 2026-11-25). Browser
  verification must happen in the user's Chrome (or via the Windows-side exe).
  Do not claim visual verification without it.

## 5. Current scope & state (updated 2026-11-25)

### 5.1 Active architect decision
- The CSS 3D engine is being retired and rebuilt in **three.js**, by the architect
  solo (§1, §3). Every T-status below describes the **retired CSS3D build**; the
  rewrite resets implementation tracking. Do not apply old CSS3D tasks to the new
  engine without the architect's instruction.
- Unchanged goal: build the intro alone first, submission-grade, graded by a cold
  external reviewer. Priorities: robustness (scroll, jump navigation, resize,
  mid-scroll refresh; no stuck states, no console errors), personal Bangla
  content, and one hand-placed "weird thing" for voice (intro.md §23/§25).

### 5.2 What actually existed in the CSS3D build (historical record)
- T1 — DOM skeleton: GREEN. Nine `.z-layer` sections (`data-z="0..8"`), greetings
  in hollow white dotted boxes. No info objects yet.
- T2/T3a — depth + camera: GREEN in the old engine. `#stage` fixed with
  `perspective: 2000px`; `#world` with `preserve-3d` receives the JS camera;
  `#track` is 900vh. The JS computes per-layer
  `gap = 1400 + 1.8 × greeting.offsetHeight`, cumulative `stops`, writes `--z`
  in px on each layer, and maps `scrollY / range → translateZ(camZ)`.
- T3b — distance opacity: PARTIAL and never browser-verified. The formula
  `1 + distance / gap` clamped to [0,1] fades layers *approaching* the camera but
  leaves passed layers at opacity 1 — only half of "only the front-most speaks."
  `range` and all `offsetHeight`s are measured once at load (no resize listener),
  and `gaps` uses `layer.firstElementChild.offsetHeight`, which becomes fragile
  once T5 adds sibling info objects.
- T4 bottom bar, T5 info objects + settle/unfurl, T6 polish, intro→site handoff:
  NOT STARTED. `.greetcode` still duplicates the whole `.greeting` CSS rule; the
  class-stacking refactor is still queued. There is no console log now (the old
  `"temp"` note was obsolete even before the rewrite).
- Historical CSS3D gotcha (keep only as a lesson, not current code): a `transform`
  on the same element that carries `perspective` is a visual no-op for its
  children — `perspective` applies to CHILDREN, so the camera must live on an
  ancestor of the transformed element. That is why `#stage` wrapped `#world`.

### 5.3 Design decisions that survive the engine change (architect canon)
- Black background; greetings pure white, `Cascadia Mono` weight 500, inside
  hollow boxes — no fill, white dotted border, 18px **px** radius (a `%` radius
  was rejected for making elliptical corners), padding 10px 10px, centered text.
- Code layers font-size 26px, class `greetcode`; explicit `<br>` + `&nbsp;`
  whitespace instead of `white-space: pre` (deterministic rendering beats editor
  tab/space drift); centered code text is a deliberate design fingerprint.
- Layer 2 Sanskrit is `प्रणामः` (`नमस्ते` is reserved for Hindi). Layer 5 math is
  the architect's formula `∀ u ∈ U, ∃ h ∈ H: greet(h,u)=True` with visible
  `&nbsp;` indents. Layer 7 uses the x86_64 Linux syscall "Hello, world!" snippet.
  Layer 8 is the final plain `Hello!`.
- **Spatial interaction model (design contract):** only the layer nearest the
  camera is visible/dominant; approaching layers grow and whiz past the camera
  plane; distant layers fade/shrink hard to avoid center-soup. Each layer has two
  states — TRAVELING (info objects clumped into the main box) and SETTLED (info
  objects unfurl to orbital positions when the camera arrives). Settle detector
  concept: `|cameraZ - layerZ| ≈ 0 → unfurl, else → clump`. Expressed in CSS terms
  here; the architect maps it to three.js coordinates in the rewrite. T5 owns the
  info objects; distance/visibility belongs to the camera/engine task.

### 5.4 Deferred
- The rest of the site (mainstr.md sections + AURONIMA from interaction
  design.md) is DEFERRED to later sprints — do not start it.
- Old ETA (≈4–5h of CSS3D work) is void; no new estimate until the architect
  settles the three.js delivery method and scope.
