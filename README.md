# Frontend Flashing

**Live:** [https://sonusario.github.io/frontend_flashing/](https://sonusario.github.io/frontend_flashing/)

Flashcards for front-end skills. Each card is a small page to match: write the HTML, CSS or JavaScript until your result matches the target. The path runs from first tags to a working progressive web app (manifest, service worker, offline caching), by way of layout, the DOM, async code, canvas drawing and game logic.

The app is two files: `index.html` and `sw.js`. It installs as a progressive web app and works offline after the first visit.

## How a card works

- **Two previews.** Your page runs live in a 16:9 and a 9:16 view, side by side on wide screens. On a phone, a 16:9 / 9:16 switch on the preview picks one.
- **Code editor.** HTML, CSS and JS tabs. The tab the card is about is editable; the other two can be viewed but not changed. JavaScript cards show the code that runs before and after yours.
- **Console.** Under the editor. Some cards are checked only by what they log.
- **Your page / Target.** A switch on the preview shows the result you are aiming for (the page and its console), not the code.
- **Help: Context and Hint.** Both open as tabs in one Help panel, next to the preview on wide screens and above it on narrower ones, so the preview and the editor stay side by side (or one after the other) while you read. The panel stays open from card to card.
- **Context.** Lists what is hard to eyeball, such as the target's font names, sizes, margins and exact colors, and every difference between your page and the target. It updates as you type.
- **Hint.** A short reference for the topic, with a link to MDN for more. MDN refuses to load inside other sites, so the essentials are written into the app. Where the card's generator makes cards that differ enough, the hint also shows a similar card (other fill-ins) and its answer. A hint never shows your card's answer word for word: an example that would is left out.
- **Context and Hint are free.** Using them does not change the card's schedule.
- **Give up.** Asks first, then shows the answer (with a button to put it in the editor). The card can no longer be submitted: Submit becomes **Next**. It counts as a miss, so the card goes back to level 0 and stays due.
- **Submit** (or Ctrl+Enter). Grades your page against the target in both views, then moves to the next card. The result shows above the new card; **Details** shows what differed and one answer.

## Cards are generated

Each of the 61 card templates makes a fresh card every time it is shown: new colors, sizes, words and numbers. JavaScript cards are also graded with a second set of values the learner does not see, so an answer has to work in general, the way `a + b = c` works for any `a` and `b`.

Grading compares the rendered pages, not the code: element structure and text, each box's position and size, visible styles (colors, fonts, borders, shadows, transforms…), the card's focus properties, canvas pixels and console output. Different code that gives the same result passes.

## Spaced repetition

Like the [Flashcards](https://github.com/sonusario/flashcard_app) app: Leitner levels on golden-ratio intervals (1, 2, 3, 4, 7, 11, 18… days) and buckets of 7 shuffled cards. A match moves a card up a level; a miss (or giving up) sends it back to level 0. The difference is chronology: due cards are bucketed earliest-in-the-path first, and new cards are introduced strictly in path order, so later topics build on earlier ones. **Path** shows every card and its level.

Progress is stored in the browser (`localStorage`).

**About** (under the console) links to this repository and the project hub, and lists the changes merged into `main`.
