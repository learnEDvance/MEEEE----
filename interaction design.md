**this whole thing is the interaction spec of an idea of mine. i wanna copy this for my website. nothing more**


# AURONIMA

## Primitive Prototype — Complete Interaction System & Specification

### Core principle

> **Knowledge should unfold.**

Auronima is not primarily a document viewer, graph viewer, or mind map.

The fundamental idea is:

**Start with a resource → select something inside it → unfold that thing → discover further knowledge without losing the original context.**

The original resource remains an anchor.

Instead of opening another page, tab, window, or screen, related knowledge appears as another spatial layer.

The prototype deliberately uses extremely primitive visual elements:

* rectangles
* lines
* text
* simple planes/layers
* a small navigation map

No elaborate UI is required at this stage.

---

# 1. THE FUNDAMENTAL SPATIAL MODEL

Auronima uses three spatial dimensions:

```text
             Y
             ↑
             |
             |
             +----------→ X
            /
           /
          Z
```

More practically:

* **X** = horizontal movement
* **Y** = vertical movement
* **Z** = depth / unfolding

The important difference from a conventional document viewer is Z.

### Conventional document

A PDF/book behaves approximately like:

```text
PAGE
 ↓
scroll Y
 ↓
PAGE
 ↓
PAGE
```

Auronima behaves more like:

```text
        [SOURCE]
            |
            Z
            ↓
      [RELATED OBJECT]
            |
            Z
            ↓
       [DEEPER IDEA]
            |
            Z
            ↓
        [EXAMPLE]
```

The user does not simply scroll through one long document.

They **move through knowledge**.

---

# 2. THE BASIC VISUAL PRIMITIVES

There are only two fundamental graphical primitives in the first prototype.

## 2.1 Rectangle = Object

Every rectangle represents one object.

Examples:

```text
┌─────────────────────┐
│                     │
│       OBJECT        │
│                     │
└─────────────────────┘
```

An object could eventually represent:

* a book
* a PDF
* a paragraph
* an equation
* an image
* a diagram
* a video
* a concept
* an explanation
* an analogy
* an experiment
* a question
* another resource

But the primitive prototype does not need to understand all of these.

At first:

**Rectangle = Object.**

Nothing more complicated is required.

---

# 3. THREAD = CONNECTION

A line between objects represents a connection.

```text
┌───────────┐
│ OBJECT A  │
└───────────┘
      |
      |
      |
┌───────────┐
│ OBJECT B  │
└───────────┘
```

This line is conceptually a **thread**.

The thread represents:

> "Following this leads from this knowledge to that knowledge."

The thread is not merely decorative.

It has its own interaction.

---

# 4. OBJECT GRAPH

At the highest level, Auronima is therefore a spatial structure:

```text
             ┌────────────┐
             │  Object A  │
             └──────┬─────┘
                    │
              ┌─────┴─────┐
              │           │
              ▼           ▼
        ┌──────────┐ ┌──────────┐
        │ Object B │ │ Object C │
        └────┬─────┘ └──────────┘
             │
             ▼
        ┌──────────┐
        │ Object D │
        └──────────┘
```

The graph describes relationships.

But unlike a conventional graph:

**objects can themselves unfold into spatial layers.**

---

# 5. OBJECT EXPANSION

This is the most important interaction in the prototype.

### Clicking an object expands it.

Suppose:

```text
┌──────────────┐
│   BOOK/PDF   │
└──────────────┘
```

The user clicks it.

Instead of navigating away:

```text
        Z
        ↓

┌──────────────┐
│   BOOK/PDF   │
└──────────────┘
        │
        ▼
┌──────────────┐
│  CONTENT     │
└──────────────┘
```

The object unfolds into another layer.

More layers can follow:

```text
Layer 0

┌──────────────┐
│    BOOK      │
└──────────────┘

       ↓ Z

Layer 1

┌──────────────┐
│   CHAPTER    │
└──────────────┘

       ↓ Z

Layer 2

┌──────────────┐
│  PARAGRAPH   │
└──────────────┘

       ↓ Z

Layer 3

┌──────────────┐
│   EQUATION   │
└──────────────┘
```

This is the core of Auronima.

---

# 6. Z-LAYERS ARE NOT NORMAL SCROLLING

This distinction is critical.

Auronima should not simply simulate a PDF with fancy scrolling.

The layers represent **relationships**, not merely sequential pages.

For example:

```text
             [Newton's Laws]
                    │
                    ▼
              [Force]
                    │
                    ▼
              [F = ma]
                    │
                    ▼
            [Mass concept]
                    │
                    ▼
             [Experiment]
```

Each expansion represents a decision:

> "I want to look inside this."

Therefore Z is essentially the **dimension of discovery**.

---

# 7. THE SOURCE REMAINS THE ANCHOR

Auronima should preserve the original context.

Suppose the user starts with an NCERT Physics page.

The original page is the anchor.

The user explores something inside it.

The original resource should not simply disappear.

Conceptually:

```text
                     Z

        ┌────────────────────┐
        │   ORIGINAL SOURCE  │
        └────────────────────┘
                    │
                    ▼
        ┌────────────────────┐
        │ SELECTED CONCEPT   │
        └────────────────────┘
                    │
                    ▼
        ┌────────────────────┐
        │ EXPLANATION        │
        └────────────────────┘
```

The user can move back toward the source.

This prevents the major problem with ordinary learning:

```text
PDF
 ↓
Google
 ↓
Website
 ↓
YouTube
 ↓
Another page
 ↓
"What was I even studying?"
```

Auronima instead keeps the learning context spatially connected.

---

# 8. AN OBJECT CAN CONTAIN MULTIPLE SLICES

An object does not necessarily expand into one thing.

It can expand into a sequence of slices.

For example:

```text
               [BOOK]

                  Z

              [Chapter]

                  Z

              [Section]

                  Z

              [Paragraph]

                  Z

              [Equation]
```

The important point is that these are **slices through the object/discovery path**.

The user moves through them in Z.

---

# 9. SUBLAYERS

A major rule:

> **Objects inside a Z expansion are not automatically connected to their parent by ordinary graph threads.**

For example:

```text
             ┌───────────────┐
             │    OBJECT A   │
             └───────────────┘
                     │
                    Z
                     ↓
             ┌───────────────┐
             │    SLICE 1    │
             └───────────────┘
                     │
                    Z
                     ↓
             ┌───────────────┐
             │    SLICE 2    │
             └───────────────┘
```

The Z relationship is an **expansion relationship**.

It is different from a normal thread connecting two independent objects.

This distinction is important because otherwise everything becomes one giant tangled graph.

---

# 10. TWO DIFFERENT TYPES OF RELATIONSHIP

Auronima therefore has at least two fundamental relationships.

## A. Thread relationship

```text
Object A ───────── Object B
```

Meaning:

> A is connected to B.

## B. Expansion relationship

```text
Object A
   ↓ Z
Slice 1
   ↓ Z
Slice 2
```

Meaning:

> A has been unfolded into deeper information.

These should remain conceptually separate.

---

# 11. CLICKING AN OBJECT

The basic interaction:

### State 1 — collapsed

```text
┌───────────────┐
│    OBJECT     │
└───────────────┘
```

### User clicks object.

### State 2 — expanded

```text
┌───────────────┐
│    OBJECT     │
└───────────────┘
        ↓
┌───────────────┐
│    SLICE 1    │
└───────────────┘
        ↓
┌───────────────┐
│    SLICE 2    │
└───────────────┘
```

The expansion happens in Z.

---

# 12. CLICKING A THREAD

Threads are interactive.

Clicking a thread means:

> **Fold everything following that line.**

Example:

```text
A
│
│
B
│
│
C
│
│
D
```

Click the thread between B and C:

```text
A
│
B
```

Everything downstream of that thread is folded away.

So the thread acts somewhat like a **branch control**.

This gives the user a way to remove an entire downstream exploration without manually closing every object.

---

# 13. THREAD FOLDING

Suppose:

```text
             A
             │
             B
            / \
           C   D
           │
           E
```

Clicking the thread leading into C causes:

```text
             A
             │
             B
            / \
         folded D
```

More precisely, the clicked thread defines the point at which the downstream branch is folded.

This is important for exploration because the user may create a very deep structure.

Instead of:

```text
close
close
close
close
close
```

one interaction can collapse the entire continuation.

---

# 14. OUTSIDE-CLICK COLLAPSING

There is another form of folding.

If the user clicks outside the currently active object/layer:

**the outermost node collapses.**

This provides a natural "back out" interaction.

For example:

```text
A
 ↓
B
 ↓
C
```

Click outside the active region.

Result:

```text
A
 ↓
B
```

Another outside click:

```text
A
```

This allows the user to retreat through the hierarchy.

---

# 15. SPECIAL CASE: BOOK/PDF

Books/PDFs behave slightly differently because they themselves are containers.

The current interaction rule is:

> **A book requires two outside clicks to fully back out.**

Conceptually:

```text
BOOK
 ↓
PAGE/CONTENT
 ↓
EXPLORATION
```

First outside click:

```text
BOOK
 ↓
PAGE/CONTENT
```

Second outside click:

```text
BOOK
```

This prevents accidentally exiting the book's internal structure with one click.

---

# 16. X/Y NAVIGATION

The user can move through the normal plane using X/Y.

This is the spatial overview.

For example:

```text
             Object B

Object A                  Object C


             Object D
```

The user can move around this environment.

X/Y therefore represent the **knowledge landscape**.

---

# 17. Z NAVIGATION

Z is different.

Moving through Z means moving through the currently explored depth.

Conceptually:

```text
                Z+
                 ↑
                 │
             [deep]
                 │
             [concept]
                 │
             [source]
                 │
                 ↓
                Z-
```

The user can therefore:

* move deeper
* move back toward the source
* inspect different layers
* return from an exploration

---

# 18. THREE-DIMENSIONAL USER MOVEMENT

The prototype therefore allows:

```text
X → move horizontally
Y → move vertically
Z → move through depth
```

This is not necessarily literal 3D graphics.

The prototype can represent the system with simple planes/slices.

The important thing is the **interaction model**, not graphical realism.

---

# 19. THE USER'S POSITION

The system should conceptually maintain the user's position:

```text
user_position = (x, y, z)
```

This becomes important later because Auronima is not just displaying a graph.

The user is actually **moving through it**.

---

# 20. ACTIVE OBJECT

At any point, one object/layer can be considered the active object.

Conceptually:

```text
[Object A]
   ↓
[Object B]  ← active
   ↓
[Object C]
```

The active object is the one currently being explored/interacted with.

The prototype does not need a fancy highlight.

A simple visual distinction is enough.

---

# 21. THE PATH

The system should keep track of where the user has travelled.

For example:

```text
A → B → C → D
```

If the user returns:

```text
A → B → C
```

and later explores another route:

```text
A → B → E → F
```

the system can retain the visited structure.

This leads into the map.

---

# 22. THE MAP

Auronima has a small map in the **top-left corner**.

The map is not the primary interface.

It is a navigation aid.

The main environment remains the actual knowledge space.

The map provides a miniature representation of explored territory.

---

# 23. MAP CONTENT

The map shows:

* visited nodes
* visited connections
* the path travelled
* detours
* the user's current position

Conceptually:

```text
┌──────────────────────────┐
│ MAP                      │
│                          │
│      ●────●              │
│      │    │              │
│      ●────●──●           │
│           │              │
│           ●              │
│                          │
└──────────────────────────┘
```

Only the relevant explored structure needs to be shown.

It does not have to show the entire universe.

---

# 24. TRAVELLED PATH

The travelled path is represented distinctly.

The current agreed behavior is:

> **The travelled path is shown in green.**

So:

```text
●────●
     │
     ●────●
          │
          ●
```

becomes conceptually:

```text
●════●
     ║
     ●════●
          ║
          ●
```

where the highlighted path represents where the user actually travelled.

---

# 25. DETOURS

The map should also retain detours.

Suppose the user does:

```text
A → B → C → D
        ↓
        E
        ↓
        F
```

Then returns to C and takes another path:

```text
C → G → H
```

The map can preserve both.

This means the map represents the user's **exploration history**, not merely a static graph.

---

# 26. CLICKING A VISITED NODE ON THE MAP

Visited nodes on the map are clickable.

Clicking one allows the user to return to that point in the knowledge space.

Conceptually:

```text
Main world:

A → B → C → D → E
        ↑
        current


Map:

A ─ B ─ C ─ D ─ E
```

Click C.

The user is returned to C.

This gives the map practical navigational value.

---

# 27. RETURN-HOME INDICATOR

The map also has a moving thick rim segment.

Its purpose is to indicate the direction/home relationship.

The idea is:

> **The moving thick rim segment points toward home.**

So the map is not just:

> "Here is where I am."

It also helps communicate:

> "Here is where I came from / where home is."

This becomes increasingly useful as the explored structure becomes large.

---

# 28. THE MAP IS NOT THE MAIN GRAPH EDITOR

This distinction should remain strict.

The map is:

**navigation + orientation.**

The main environment is:

**interaction + discovery.**

Do not turn the map into another complicated graph editor during the primitive prototype.

---

# 29. WHAT HAPPENS WHEN THE USER OPENS A RESOURCE?

Example:

Initial environment:

```text
┌──────────────────────┐
│ NCERT PHYSICS        │
└──────────────────────┘
```

User clicks it.

It unfolds:

```text
┌──────────────────────┐
│ NCERT PHYSICS        │
└──────────────────────┘
          ↓ Z
┌──────────────────────┐
│ CHAPTER              │
└──────────────────────┘
          ↓ Z
┌──────────────────────┐
│ SELECTED SECTION     │
└──────────────────────┘
```

The user then selects something interesting.

For example:

```text
[Newton's Second Law]
```

That can unfold further:

```text
[Newton's Second Law]
          ↓
       [F = ma]
          ↓
       [Mass]
          ↓
       [Acceleration]
```

The original resource remains part of the structure.

---

# 30. VIDEO INTERACTION

The same philosophy can apply to video.

A video is an object:

```text
┌──────────────────┐
│      VIDEO       │
└──────────────────┘
```

Certain meaningful moments in the video can become objects/layers.

For example:

```text
VIDEO
  ↓
timestamp 01:24
  ↓
EXPLANATION
  ↓
DIAGRAM
```

Instead of treating the timeline as the only way to interact with the video, Auronima can treat meaningful moments as discoverable knowledge objects.

The important principle is:

> A timestamp becomes significant because of what happens there, not merely because time passed.

This feature can remain conceptual in the first primitive prototype.

---

# 31. IMAGE / DIAGRAM INTERACTION

Images and diagrams can eventually be treated similarly.

For example:

```text
┌────────────────────┐
│     DIAGRAM        │
└────────────────────┘
```

A component can eventually become selectable:

```text
┌────────────────────┐
│   [component]      │
│                    │
│       diagram      │
│                    │
└────────────────────┘
```

Clicking that component could unfold knowledge related to it.

However:

**automatic image segmentation/SAM2 is NOT part of the current prototype.**

That is deliberately off the table for now.

The primitive prototype only needs to prove the interaction architecture.

---

# 32. OBJECT DATA MODEL

Even though the prototype visually uses rectangles, internally an object should conceptually contain information such as:

```text
Object
├── id
├── position
├── size
├── content
├── parent
├── children
├── expansion layers
└── state
```

A minimal conceptual object could be:

```text
Object {
    id
    x
    y
    z
    width
    height
    content
}
```

The prototype does not need a huge database architecture yet.

---

# 33. THREAD DATA MODEL

A thread can conceptually contain:

```text
Thread {
    id
    source
    destination
    state
}
```

Where:

```text
source → destination
```

defines the relationship.

The important additional behavior is:

```text
click(thread)
    → fold downstream
```

---

# 34. EXPANSION DATA MODEL

Expansion is different from a thread.

Conceptually:

```text
Expansion {
    parent
    layers[]
    current_layer
}
```

For example:

```text
parent = Book

layers = [
    Chapter,
    Section,
    Paragraph,
    Equation
]
```

The system then knows how to move through those layers in Z.

---

# 35. OBJECT STATES

The primitive prototype only needs a few states.

### Collapsed

```text
[OBJECT]
```

### Expanded

```text
[OBJECT]
   ↓
[SLICE]
```

### Deeply expanded

```text
[OBJECT]
   ↓
[SLICE]
   ↓
[SLICE]
   ↓
[SLICE]
```

### Folded

The downstream structure exists internally but is visually hidden.

This is important.

**Folded does not mean deleted.**

---

# 36. FOLDING VS DELETING

Auronima should never interpret folding as destruction.

If:

```text
A → B → C → D
```

and the user folds C onward:

```text
A → B
```

C and D still exist.

They are simply hidden.

Opening that path again restores them.

This is essential because the user's exploration history should not disappear merely because the user backed out.

---

# 37. CLICK PRIORITY

Because several interactive things can overlap, the prototype should use a simple interaction priority.

Conceptually:

```text
1. Object
2. Thread
3. Empty space
```

But when a thread itself is directly clicked, the thread interaction takes precedence over ordinary background behavior.

The exact hitboxes can remain primitive.

---

# 38. EMPTY-SPACE CLICK

Empty-space clicking is the retreat mechanism.

If the user clicks outside the active content:

```text
collapse outermost active node
```

This gives the system a simple universal "go back" behavior without needing a permanent back button.

---

# 39. NO NORMAL BACK BUTTON IS REQUIRED

The spatial model itself provides navigation.

The user can:

* move backward in Z
* click outside
* click a thread to fold downstream
* use the map to return to a visited point

Therefore the primitive prototype does not need to be cluttered with conventional browser-style controls.

---

# 40. CORE INTERACTION LOOP

The complete basic loop is:

```text
             ┌─────────────┐
             │ See object  │
             └──────┬──────┘
                    │
                  click
                    ↓
             ┌─────────────┐
             │ Expand      │
             └──────┬──────┘
                    │
                  move Z
                    ↓
             ┌─────────────┐
             │ Discover    │
             └──────┬──────┘
                    │
             choose direction
              /             \
             ↓               ↓
       expand further     follow thread
             │               │
             ↓               ↓
       deeper knowledge   another object
             │               │
             └───────┬───────┘
                     ↓
                  continue
```

Or retreat:

```text
       outside click
             ↓
       fold outer layer
             ↓
       move toward source
```

---

# 41. COMPLETE EXAMPLE

Imagine the starting resource is an NCERT Physics chapter.

Initial screen:

```text
             ┌─────────────────┐
             │ NCERT PHYSICS    │
             └─────────────────┘
```

User clicks it.

```text
             ┌─────────────────┐
             │ NCERT PHYSICS    │
             └─────────────────┘
                      ↓
             ┌─────────────────┐
             │ LAWS OF MOTION   │
             └─────────────────┘
```

User opens Laws of Motion.

```text
             ┌─────────────────┐
             │ LAWS OF MOTION   │
             └─────────────────┘
                      ↓
             ┌─────────────────┐
             │ NEWTON'S 2ND LAW │
             └─────────────────┘
```

The user encounters:

```text
             ┌─────────────────┐
             │      F = ma      │
             └─────────────────┘
```

They expand it.

```text
                    [F = ma]
                       ↓
              ┌─────────────────┐
              │     FORCE       │
              └─────────────────┘
                       ↓
              ┌─────────────────┐
              │      MASS       │
              └─────────────────┘
                       ↓
              ┌─────────────────┐
              │  ACCELERATION   │
              └─────────────────┘
```

Now suppose Force connects to another object elsewhere:

```text
[F = ma]
    │
    └──────────────→ [FORCE DIAGRAM]
```

That is a **thread relationship**, not simply another Z slice.

The user can follow it.

---

# 42. THREAD VS Z IN THIS EXAMPLE

This distinction becomes:

```text
                    Z
                    ↓
                [F = ma]
                    ↓
                 [Mass]
                    ↓
              [Acceleration]


[F = ma] ───────────────→ [Force Diagram]
             THREAD
```

The user can therefore explore:

### Deeper

```text
Z
↓
inside the current thing
```

### Elsewhere

```text
Thread
↓
related thing
```

This is arguably the most important structural distinction in Auronima.

---

# 43. CLOSING THE EXAMPLE

Suppose the user has reached:

```text
NCERT
 ↓
Chapter
 ↓
Newton
 ↓
F = ma
 ↓
Mass
 ↓
Acceleration
```

They click empty space.

The outermost layer collapses.

Then:

```text
NCERT
 ↓
Chapter
 ↓
Newton
 ↓
F = ma
 ↓
Mass
```

Another outside click:

```text
NCERT
 ↓
Chapter
 ↓
Newton
 ↓
F = ma
```

And so on.

The user is effectively **unfolding and refolding knowledge**.

---

# 44. MAP DURING THIS EXPLORATION

Meanwhile, the map might show:

```text
┌───────────────────────┐
│ MAP                   │
│                       │
│   ●                   │
│   ║                   │
│   ●══●                │
│       ║               │
│       ●══●            │
│                       │
└───────────────────────┘
```

The travelled route is highlighted.

If the user takes a detour, the detour remains visible.

If they click an old node, they return to that point.

---

# 45. WHAT THE USER SHOULD FEEL

The interface should feel less like:

> "I opened another document."

and more like:

> "I opened this idea."

That is the conceptual heart of Auronima.

The user should feel that knowledge has **depth**.

---

# 46. THE MINIMUM VIABLE PROTOTYPE

The first working prototype should be extremely small.

It only needs:

### Visual primitives

```text
Rectangle
Line
Text
```

### Spatial primitives

```text
X
Y
Z
```

### Object interaction

```text
click object
→ expand
```

### Layer interaction

```text
move Z
→ inspect deeper layer
```

### Thread interaction

```text
click thread
→ fold downstream
```

### Empty-space interaction

```text
click outside
→ collapse outermost node
```

### Navigation

```text
move X/Y/Z
```

### Map

```text
top-left map
visited nodes
visited connections
travelled path
detours
clickable visited nodes
home-direction indicator
```

That is enough.

---

# 47. WHAT THE FIRST DEMO SHOULD ACTUALLY CONTAIN

Do NOT begin with:

* real PDFs
* AI-generated explanations
* video processing
* SAM2
* semantic search
* automatic graph generation
* collaboration
* complicated UI
* databases
* authentication
* fancy 3D graphics

The first demo should literally look primitive.

Something like:

```text
          ┌─────────────┐
          │             │
          │   OBJECT A  │
          │             │
          └──────┬──────┘
                 │
                 │
                 │
          ┌──────▼──────┐
          │   OBJECT B  │
          └─────────────┘


 ┌───────────────┐
 │      MAP      │
 │   ●──●        │
 │      │        │
 │      ●        │
 └───────────────┘
```

And that should already demonstrate:

1. object selection
2. object expansion
3. Z movement
4. thread creation
5. thread folding
6. outside-click collapse
7. X/Y movement
8. Z movement
9. map tracking
10. map navigation

If those work, the core idea works.

---

# 48. PROTOTYPE DEVELOPMENT ORDER

The safest implementation order is:

## Stage 1 — Rectangle

Create one rectangle.

```text
┌─────────┐
│ OBJECT  │
└─────────┘
```

Make it clickable.

---

## Stage 2 — Two objects

```text
A

B
```

Click A.

Make something happen.

---

## Stage 3 — One Z expansion

```text
A
↓
A1
```

Click A → A1 appears.

---

## Stage 4 — Multiple Z slices

```text
A
↓
A1
↓
A2
↓
A3
```

Allow movement through them.

---

## Stage 5 — Threads

```text
A ───────── B
```

Make the line clickable.

---

## Stage 6 — Thread folding

```text
A ─ B ─ C ─ D
```

Click the B→C thread.

C/D disappear.

---

## Stage 7 — Outside-click collapse

Click empty space.

Outermost layer disappears.

---

## Stage 8 — X/Y navigation

Allow the user to move around the 2D environment.

---

## Stage 9 — Full Z navigation

Allow movement through depth.

---

## Stage 10 — Map

Add the top-left map.

Track:

```text
visited nodes
visited edges
current position
travelled path
detours
```

---

## Stage 11 — Map navigation

Click a visited node.

Return there.

---

## Stage 12 — Home indicator

Add the moving thick rim segment that points toward home.

---

# 49. THE FIRST REAL TEST

The best first test is not an entire textbook.

Use something absurdly tiny.

For example:

```text
             [BOOK]
                ↓
             [PAGE]
                ↓
           [EQUATION]
```

Then:

```text
[EQUATION]
     │
     └──────────→ [RELATED IDEA]
```

Now test every interaction.

### Test A

Click BOOK.

Expected:

```text
PAGE appears in Z
```

### Test B

Move deeper.

Expected:

```text
EQUATION appears
```

### Test C

Click thread.

Expected:

```text
RELATED IDEA branch folds
```

### Test D

Click outside.

Expected:

```text
outermost expansion collapses
```

### Test E

Open map.

Expected:

```text
visited structure appears
```

### Test F

Click visited node.

Expected:

```text
user returns to that location
```

If all six work, the fundamental interaction system is alive.

---

# 50. COLLABORATION-READY DIRECTION

The eventual architecture can separate:

```text
MAIN VIEWER
     │
     ├── Object module
     ├── Object module
     ├── Object module
     ├── Thread module
     └── Resource module
```

Each object can expose a relatively simple interface/variable structure.

The reason is to allow multiple people to work on separate objects without one modification breaking the entire viewer.

But this is an **architecture direction**, not something the primitive prototype needs to solve immediately.

The prototype should first establish the interaction language.

---

# 51. WHAT AURONIMA IS REALLY PROVING

The prototype is not trying to prove:

> "We can make a cool 3D interface."

It is trying to prove:

> **Knowledge can be navigated as an expandable spatial structure while preserving the original context.**

The rectangle is therefore not important.

The line is not important.

The map is not even the most important part.

The important interaction is:

```text
             SEE
              ↓
            SELECT
              ↓
            UNFOLD
              ↓
           EXPLORE
              ↓
        FOLLOW / DEEPEN
          ↙          ↘
      THREAD          Z
         ↓            ↓
     RELATED       DEEPER
         ↓            ↓
       EXPLORE      EXPLORE
          \          /
           \        /
             RETURN
                ↓
              FOLD
```

---

# 52. COMPLETE INTERACTION TABLE

| User action                       | System response                           |
| --------------------------------- | ----------------------------------------- |
| Click object                      | Expand object                             |
| Move in X                         | Move horizontally through environment     |
| Move in Y                         | Move vertically through environment       |
| Move in Z                         | Move through knowledge depth              |
| Click thread                      | Fold everything downstream of that thread |
| Click outside active content      | Collapse outermost active node            |
| Second outside click on a book    | Fully back out of book exploration        |
| Click visited map node            | Return to that location                   |
| Travel through new object         | Add it to explored map                    |
| Travel through new connection     | Add connection/path to map                |
| Take alternate route              | Preserve detour in map                    |
| Move through exploration          | Update current position                   |
| Move around map/home relationship | Update home-direction indicator           |

---

# 53. CURRENTLY OUT OF SCOPE

The primitive prototype should NOT attempt to solve:

* automatic semantic understanding
* AI tutoring
* automatic knowledge extraction
* automatic PDF decomposition
* automatic video understanding
* SAM2 image segmentation
* collaborative editing
* sophisticated permissions
* massive-scale data storage
* beautiful visual design
* realistic 3D environments
* production-level performance

Those are later problems.

The prototype's job is much simpler:

**Can a person understand and use the spatial interaction model?**

---

# 54. FINAL PROTOTYPE DEFINITION

The entire primitive Auronima system can therefore be summarized as:

```text
                 AURONIMA
                    │
          ┌─────────┴─────────┐
          │                   │
       OBJECTS             THREADS
          │                   │
       RECTANGLES            LINES
          │                   │
       CLICK                  CLICK
          │                   │
      EXPANSION             FOLD
          │                   │
          ↓                   ↓
         Z                 DOWNSTREAM
          │
          ↓
       SLICES
          │
          ↓
      KNOWLEDGE
       DEPTH


          USER MOVEMENT
               │
       ┌───────┼───────┐
       ↓       ↓       ↓
       X       Y       Z
       │       │       │
     plane   plane   depth


              MAP
               │
       ┌───────┼────────┐
       ↓       ↓        ↓
    visited  paths   detours
       │
       ↓
 clickable
 visited nodes
       │
       ↓
    RETURN
```

And the central loop is:

```text
             RESOURCE
                 ↓
              OBJECT
                 ↓
              CLICK
                 ↓
             EXPAND
                 ↓
               Z
                 ↓
             EXPLORE
            ↙       ↘
        THREAD       Z
          ↓           ↓
      RELATED       DEEPER
       OBJECT       OBJECT
          ↓           ↓
        EXPLORE    EXPLORE
             \       /
              \     /
               FOLD
                 ↓
              RETURN
```

## The prototype succeeds if this feels natural.

Everything else comes later.

The **rectangle → click → Z expansion → thread → fold → map → return** loop is the actual thing you are trying to demonstrate.
