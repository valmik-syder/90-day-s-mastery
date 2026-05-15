Q: What is the difference between display:flex and display:grid? When do you use each?

A: Flex is one-dimensional — use it for rows OR columns (nav, button groups, card rows). Grid is two-dimensional — use it when you need rows AND columns simultaneously (page layouts, service card grids). Rule: nav = flex, page layout = grid.

Q: What are the 12 core CSS Flexbox properties?

A: Container: display, flex-direction, flex-wrap, flex-flow, justify-content, align-items, align-content, gap. Item: flex-grow, flex-shrink, flex-basis, align-self.

Q: What does justify-content vs align-items do in Flexbox?

A: justify-content controls alignment along the MAIN axis (horizontal in row direction). align-items controls alignment along the CROSS axis (vertical in row direction). They flip when flex-direction is column.

Q: What is CSS Grid grid-template-areas and why use it?
A: Lets you name regions of a grid layout with strings and assign elements to them by name. Use it when your layout has semantically distinct regions (header, sidebar, main, footer) — much more readable than tracking row/column numbers manually.

Q: What is the difference between auto-fill and auto-fit in CSS Grid?
A: auto-fill creates as many columns as fit, keeping empty columns as placeholders. auto-fit collapses empty columns and stretches existing ones to fill the space. For responsive card grids: auto-fit + minmax() is almost always what you want.

Q: What is a CSS custom property (variable) and how do you define one?
A: Defined with -- prefix on :root. Example: :root { --primary: #0066ff; } Used with var(--primary). Useful for theming, dark mode toggle, and design tokens that need to change in one place.

Q: How does CSS dark mode toggle work with custom properties?
A: Define two sets of --color variables. On :root set light values. On [data-theme="dark"] or .dark override them. Toggle a class or attribute on <html> with JavaScript. Every element using var(--color) updates instantly.

Q: What is the JavaScript event loop and what is the difference between macrotask and microtask?
A: Call stack runs synchronous code. When async work completes, callbacks go into queues. Microtasks (Promise.then, queueMicrotask) run before the next macrotask. Macrotasks (setTimeout, setInterval, I/O) run one per event loop tick. Order: synchronous → all microtasks → one macrotask → all microtasks → repeat.

Q: What does Promise.all do vs Promise.allSettled?
A: Promise.all: runs all promises in parallel, resolves when ALL resolve, REJECTS immediately if ANY reject. Promise.allSettled: runs all in parallel, waits for ALL to finish regardless of success/failure, always resolves with array of {status, value/reason}. Use allSettled when you need results from all even if some fail.

Q: What does Promise.race do vs Promise.any?
A: Promise.race: resolves or rejects with the FIRST promise to settle (whichever finishes first, win or lose). Promise.any: resolves with the FIRST promise to SUCCEED, only rejects if ALL reject. Use race for timeouts, use any for "first successful response wins."

Q: What is a JavaScript closure?
A: A function that retains access to variables from its outer scope even after the outer function has finished executing. The inner function closes over the outer scope. Used in event handlers, factory functions, module patterns, and anywhere you need private state.

Q: What is optional chaining (?.) and when do you use it?
A: user?.address?.city safely accesses nested properties without throwing if any level is null/undefined — returns undefined instead. Use it when you are accessing properties from API responses or external data where structure is not guaranteed.

Q: What is the difference between == and === in JavaScript?
A: == does type coercion before comparing (0 == "0" is true). === compares value AND type with no coercion (0 === "0" is false). Always use === in production code. == is a source of bugs.

Q: What is async/await and what does it replace?
A: Syntactic sugar over Promises. async function always returns a Promise. await pauses execution inside the async function until the Promise resolves. Replaces .then().catch() chains with synchronous-looking code that is still non-blocking. Always wrap in try/catch for error handling.

Q: What does Array.reduce() do?
A: Takes an array and reduces it to a single value by running a callback on each element with an accumulator. reduce((acc, item) => acc + item.price, 0) sums all prices. Most powerful array method — can implement map and filter using only reduce.

Q: What is the difference between Array.map() and Array.forEach()?
A: map() creates a NEW array with transformed values — use it when you need a new array. forEach() iterates and returns undefined — use it only for side effects (logging, pushing to external array). Never use forEach when map works.

Q: What is ES6 module syntax and how does it differ from CommonJS?
A: ES6: export const x = 1 / import { x } from './file'. CommonJS: module.exports = { x } / const { x } = require('./file'). ES6 modules are static (imports resolved at parse time, tree-shakeable). CommonJS is dynamic (can require inside conditionals). Use ES6 in frontend, CommonJS is Node default (though Node now supports ES6 too).

Q: What is the Git rebase command and when do you use it vs merge?
A: git rebase main rewrites your branch's commits on top of the latest main as if you started from there. Creates clean linear history. Use rebase to update your feature branch with latest main changes. Use merge for integrating completed features (preserves history). Never rebase shared/public branches.

Q: What is git cherry-pick?
A: Applies a specific commit from one branch to your current branch. git cherry-pick abc123 copies that one commit. Use it when you need one specific fix or feature from another branch without merging everything else.

Q: What is interactive rebase (git rebase -i) used for?
A: Lets you edit, squash, reorder, or drop commits before pushing. git rebase -i HEAD~3 opens the last 3 commits for editing. Use squash to combine multiple "wip" commits into one clean commit before pushing a PR.

Q: What is Tailwind CSS JIT mode and what problem does it solve?
A: Just-In-Time mode generates only the CSS classes you actually use in your markup — scans files on demand. Solves the problem of Tailwind's full stylesheet being massive (3MB+). JIT output is typically under 10KB. Enabled by default in Tailwind v3+.

Q: What is mobile-first responsive design?
A: Writing CSS for the smallest screen first, then adding media queries for larger screens. Base styles = mobile. @media (min-width: 768px) adds tablet overrides. @media (min-width: 1024px) adds desktop. Opposite of desktop-first. Mobile-first produces cleaner, less override-heavy CSS.

Q: What is the CSS box model?
A: Every element is a box: content + padding + border + margin. box-sizing: content-box (default) — width applies to content only. box-sizing: border-box — width includes padding and border. Always set * { box-sizing: border-box } globally. It makes layout math predictable.

Q: What are HTML5 semantic elements and why do they matter?
A: Elements with meaning: header, nav, main, section, article, aside, footer, figure, figcaption, time. Matter because: screen readers use them for navigation (accessibility), search engines weight them for SEO, and they make HTML self-documenting. Use div only when no semantic element fits.

Q: What is the Intersection Observer API?
A: Browser API for detecting when an element enters/exits the viewport, without scroll event listeners. Used for: lazy loading images (observe img, set src when it enters viewport), scroll animations, infinite scroll triggers. Far more performant than scroll listeners.

Q: What is a keyframe animation in CSS?
A: @keyframes name { 0% { opacity: 0 } 100% { opacity: 1 } } then applied with animation: name 0.3s ease-in-out. Defines the intermediate states. Use transform and opacity — they are GPU-composited and don't trigger layout reflow. Avoid animating width, height, margin.

Q: What is requestAnimationFrame and when do you use it?
A: Browser API that runs a callback before the next repaint, synced to the display refresh rate (~60fps). Use for JavaScript animations where you need smooth, frame-rate-synced updates. Better than setInterval for visual updates because it pauses when tab is hidden.

Q: What is GitFlow branching strategy?
A: main (always deployable production code), develop (integration branch), feature/* (one per feature, branched from develop), release/* (prep for production), hotfix/* (emergency fixes branched from main). PRs merge feature → develop. Periodic merges develop → main for releases.

Q: What is branch protection on GitHub and what does it enforce?
A: Rules on a branch (usually main) that prevent direct pushes. Enforces: pull request required before merging, minimum number of approving reviews, status checks must pass (CI), signed commits. Protects production code from accidental direct pushes.

Q: What does the Lighthouse performance score measure?
A: Composite score of 5 metrics: LCP (Largest Contentful Paint — loading), FID/INP (interactivity), CLS (Cumulative Layout Shift — visual stability), FCP (First Contentful Paint), TTFB (Time to First Byte). Score 0–100. 90+ is the target. Each metric has specific causes and fixes.

Q: What is LCP (Largest Contentful Paint)?
A: The time it takes for the largest visible content element to render. Usually a hero image or H1. Target: under 2.5 seconds. Fix by: preloading the LCP image, using next/image with priority prop, serving WebP, reducing server response time.

Q: What is CLS (Cumulative Layout Shift)?
A: Measures unexpected layout shifts — elements moving around as page loads. Score target: under 0.1. Causes: images without explicit width/height, late-loading fonts, dynamic content injected above existing content. Fix: always set dimensions on images.

Q: What is URLSearchParams and how is it used?
A: Browser API for reading and writing URL query parameters. const params = new URLSearchParams(window.location.search). params.get('filter') reads a param. params.set('filter', 'active') sets one. Use for URL-based state (filter, sort, pagination) so state survives page refresh and is shareable.

Q: What is the difference between localStorage and sessionStorage?
A: localStorage persists until explicitly cleared — survives browser close. sessionStorage lasts only for the browser tab session — cleared when tab closes. Both store strings only (use JSON.stringify/parse). Never store sensitive data (tokens, passwords) in either — XSS can read them.

Q: What is flatMap() in JavaScript?
A: Combines map() and flat() in one step. [[1,2],[3,4]].flatMap(x => x) → [1,2,3,4]. More useful: users.flatMap(user => user.tags) returns a flat array of all tags from all users. Depth is always 1 — use flat(Infinity) for deeper nesting.

Q: What is a CSS transition vs a CSS animation?
A: Transition: triggered by a state change (hover, class toggle). Smooth interpolation between two states. transition: all 0.3s ease. Simple and declarative. Animation: runs automatically, can loop, has keyframes for multiple states. Use transition for hover effects and UI feedback. Use animation for loading spinners, entrance effects, continuous motion.

Q: What is the W3C validator and why run your HTML through it?
A: Official validator at validator.w3.org. Checks HTML for spec compliance: unclosed tags, wrong nesting, deprecated attributes, missing required attributes. Run it on every page. Invalid HTML causes browser rendering inconsistencies and accessibility failures.

Q: What does position:relative vs position:absolute do?
A: relative: positions element relative to its normal flow position. Creates a positioning context for children. absolute: removes element from flow, positions relative to nearest positioned ancestor (relative/absolute/fixed parent). Use relative on the container, absolute on the child to place it precisely within that container.

Q: What is z-index and when does it not work?
A: Controls stacking order of overlapping positioned elements. Higher number = on top. Only works on elements with position other than static (relative, absolute, fixed, sticky). z-index does not work on position:static elements — that is the most common z-index bug.

Q: What is the difference between em and rem in CSS?
A: em is relative to the font-size of the CURRENT element (or nearest parent with font-size). rem is relative to the ROOT element (html font-size, typically 16px). Use rem for consistent sizing across the page. Use em for component-local scaling (padding proportional to that component's text size).