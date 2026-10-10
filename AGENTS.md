# AGENTS.md

## 1. What this is
Static personal site: HTML + one external CSS file + vanilla JS inline in the HTML
(single <script> at end of <body>). No framework, no build step, no npm — never
introduce one. Verification = open the page in a browser. There are no
build/test/lint commands, and none should ever be added.

Entry files are **ME.html + ME.css** (they were HTML-tutorial scratch, then wiped
and rebuilt as the project). Default viewing is plain **file://** (double-click);
the user may occasionally run VS Code Live Server, but nothing in the project
needs a server (no fetch of local files, no ES modules). Do not relitigate either
choice.

## 2. Specs are .md files in root — read before coding
- intro.md is NOT a repo overview despite its name — it's the full spec for the
  3D scroll greeting intro. It currently defines **NINE Z-layers (Z=0..8)**; an
  English "Greetings" layer was added then removed, and §26 still says "Z = 9" —
  §3/§28 are canonical. Any agent will misread this file otherwise.
- interaction design.md = **AURONIMA**, the user's main-site interaction system
  (rectangles = objects, lines = threads, Z = expansion, top-left map). It has a
  full implementation order in §48 (Stages 1–12) and MVP definitions in §46–47.
  The intro is built FIRST; AURONIMA is a later sprint.
- mainstr.md = the 6 sections + non-linear "layers and nets" arrangement (content
  for the later site).
- Readme.md is a stub; ignore it.
- **Specs change mid-project without warning** (intro.md was edited after first
  read; new spec files appear). RE-READ all root *.md fresh at the start of every
  session; never trust memory or old summaries of them.
- Deviation from spec: intro.md §22 demands a single self-contained HTML file.
  User chose an external CSS file instead — follow the user, not the spec.

## 3. The working relationship (non-negotiable)
- HIERARCHY: the user is the LEAD ARCHITECT — they own design, content, naming,
  structure, and every product decision. Sessions are the senior engineer UNDER
  them: the goal is having the USER write every line (the user vibecoded for a
  year and is re-learning fundamentals through this process), teaching properly,
  enforcing engineering discipline, and pushing back on ENGINEERING only — never
  on design/product calls. A session may flag a design consequence, but the user
  decides. Architecture deviations from the spec docs are the user's to make and
  the session's to record.
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
- Directory name is MEEEE!!!! — quote it in shell commands ('MEEEE!!!!') or
  history expansion/globs will bite.
- ME.html / ME.css are the project's entry files now — do not treat them as
  throwaway scratch (they no longer are).
- Remote: github.com/learnEDvance/MEEEE---- — run git status before work; user
  does not always commit.
- GitHub Pages deploy explicitly deferred; not configured.

## 5. Current scope & state (dated: 2026-10-10)
- **INTRO FIRST.** The current build target is the intro alone (intro.md MVP §27,
  adapted to 9 layers), submission-grade: it will be graded by an external
  reviewer who opens it cold.
- Grade-adjusted priorities: robustness for a cold grader (scroll, bottom-bar
  jump, resize, mid-scroll refresh; no stuck/dead states, no console errors;
  Chrome is the only target browser); personal content that is "reflective of the
  user" (the Bangla info objects carry real, user-authored material); and one
  hand-placed "weird thing" for voice (intro.md §23/§25).
- Planned task order: T1 DOM skeleton (9 layers) → T2 3D stage (perspective,
  preserve-3d, translateZ) → T3 scroll-driven camera (spacer, custom properties,
  requestAnimationFrame) → T4 bottom greeting bar + click-to-jump → T5 Bangla
  info objects → T6 polish + handoff placeholder. Confirm with the user which
  task is current — session history is not shared.
- Pre-sprint homework (user owes): Bangla info-object content and a layer-7
  assembly snippet choice. The pre-sprint unbilled brief covers the four hard
  concepts of T2/T3.
- Architect-owned visual design (current, changes freely): black background;
  greetings in pure-white text, `Cascadia Mono` at weight 500, set inside hollow
  boxes — no fill, white dotted border. Layer-7 assembly = x86_64 Linux syscall
  "Hello, world!" snippet (user-chosen, approved).
- Confirmed ARCHITECT decisions (canon, do not second-guess): Sanskrit layer uses
  `प्रणामः` deliberately (`नमस्ते` is reserved for the Hindi layer); the math
  layer uses the architect's own formula `∀ u ∈ U, ∃ h ∈ H: greet(h,u)=True`
  (the spec's version was rejected); math lines want visible indents (`&nbsp;`),
  since HTML collapses spaces.
- Whitespace on code layers (architect decided, reasoned): explicit `<br>` +
  `&nbsp;` chosen over `white-space: pre` because editor tab/space drift would
  silently change rendering — deterministic output is preferred. Code boxes keep
  `text-align: center` deliberately (design fingerprint), font-size 26px, class
  `greetcode`. NOTE: `.greetcode` currently duplicates the whole `.greeting` rule
  — a class-stacking refactor (`.greeting greetcode` + delta rule) is queued for
  the T6 polish pass, not blocking.
- T1 status: GREEN — all nine layers carry `class="greeting"`; visual system applied
  (white, Cascadia Mono 500, hollow dotted-white box, text-align center, padding
  10px 10px, border-radius 18px uniform — NOTE: `%` radius was tried and rejected
  by the architect for making elliptical "parabolic" corners; `px` is the box
  standard). Math indent uses `&nbsp;`. Console log currently `"temp"`.
  CURRENT TASK: T2 — the 3D stage.
- ARCHITECT'S SPATIAL INTERACTION MODEL (design contract for T3/T5): only the
  layer nearest the camera is visible/dominant; approaching layers grow and whiz
  past the camera plane. Because main objects are transparent, layers far from
  the camera must fade/shrink hard (no center-soup). Each layer has TWO STATES:
  TRAVELING (its info objects clump into the main box; layer is compact) and
  SETTLED (info objects emerge to their orbital positions when the camera arrives
  at/near the layer's Z). Implemented via a settle-detector: |cameraZ - layerZ|
  ≈ 0 → unfurl, else → clump. Info objects arrive in T5; opacity-by-distance is
  T3's job.
- The rest of the site (mainstr.md sections + AURONIMA from "interaction
  design.md") is DEFERRED to later sprints — do not start it.