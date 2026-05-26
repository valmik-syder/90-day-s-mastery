What This Week Builds
By end of Day 7 you will have the ClientSide.in landing page fully built, styled, interactive, and deployed to GitHub Pages. This is not a tutorial project. This is version zero of your actual agency website — the first URL you will send to a foreign client.
The week has one build target that grows every day. You do not start a new project each day. You layer on top of yesterday's file.

Technologies Covered
TechnologyWhere It AppearsHTML5 Semantic ElementsDay 1CSS Flexbox (all 12 properties)Day 1CSS Grid + grid-template-areasDay 2CSS Custom Properties + Keyframe AnimationsDay 2Dark Mode Toggle with CSS VariablesDay 2Tailwind CSS (utility-first, JIT, dark mode)Day 3JavaScript ClosuresDay 4Event Loop + Microtask QueueDay 4Promises (.all .race .allSettled .any)Day 4async/awaitDay 4Array Methods (map, filter, reduce, flatMap)Day 5ES6 ModulesDay 5URLSearchParamsDay 5Git (branching, rebase, cherry-pick, GitFlow)Day 6GitHub (PRs, branch protection, Actions basics)Day 6Lighthouse + performance optimizationDay 7GitHub Pages deploymentDay 7

Daily Build Targets
Day 1 — Figma Sketch + Semantic HTML + CSS Flexbox
Goal written before editor opens:

"I will build the ClientSide.in landing page with a nav, hero section, 6 service cards, and footer using only semantic HTML and CSS Flexbox. No Tailwind. No JavaScript."

What you build:

Figma wireframe sketch before writing one line of CSS
Semantic HTML structure: <header>, <nav>, <main>, <section>, <footer>
CSS Flexbox nav with logo left, links right
Hero section with heading, subheading, CTA button
Services grid with 6 cards using flex-wrap
W3C validation — zero errors before committing

Depth check before Day 2:

Delete justify-content: space-between from navbar. What breaks?
Delete flex-wrap: wrap from services-grid. What breaks?
Delete min-height: 70vh from hero. What breaks?
Restore all three. Now explain what each property does in your own words.


Day 2 — CSS Grid + Animations + Dark Mode
Goal written before editor opens:

"I will add a CSS Grid services section, hover animations with keyframes, CSS custom properties for the entire color system, and a dark mode toggle."

Copy forward: cp Day-1/index.html Day-2/ and cp Day-1/style.css Day-2/
What you add:

Rebuild services section using CSS Grid with grid-template-areas
CSS custom properties on :root for all colors — no hardcoded hex values anywhere
Keyframe animations on service cards (entrance fade or hover lift)
Dark mode toggle: [data-theme="dark"] overrides CSS variables
JavaScript button that toggles data-theme on <html>

Depth check before Day 3:

Change grid-template-columns to repeat(2, 1fr). What changes?
Remove the :root variables and hardcode one color. What breaks when you toggle dark mode?
Explain: why CSS custom properties make dark mode possible in 10 lines vs 100.


Day 3 — Tailwind CSS Rebuild
Goal written before editor opens:

"I will delete all custom CSS and rebuild the entire layout using only Tailwind utility classes. Then compare Lighthouse scores between both versions."

Copy forward: Both files from Day-2.
What you do:

Install Tailwind via CDN first (for speed): <script src="https://cdn.tailwindcss.com"></script>
Delete style.css entirely
Rebuild every section using only Tailwind classes — no custom CSS
Run Lighthouse on Day-2 version and Day-3 version — compare scores and screenshot both
Understand what Tailwind is compiling under the hood (inspect the generated CSS in DevTools)

Depth check before Day 4:

Why did you use flex for the nav but grid for the services section?
Open DevTools → Elements → Styles. Find a Tailwind class. What CSS property did it generate?
What is JIT mode and why does it matter for production bundle size?


Day 4 — JavaScript Part 1
Goal written before editor opens:

"I will add a live character counter using closures, async form submission with Promise simulation, smooth scroll, and lazy image loading."

Copy forward: Both files from Day-3.
What you add:

Contact form with character counter using a closure (the counter function closes over the max value)
Async form submit: simulate API call with new Promise(resolve => setTimeout(resolve, 1500)), show loading state
Smooth scroll to sections using requestAnimationFrame
Lazy image loading with IntersectionObserver on service card images

Depth check before Day 5:

Explain the JavaScript event loop out loud without Googling. Microtask vs macrotask queue — which runs first?
Write Promise.all, Promise.race, Promise.allSettled, Promise.any from memory. What does each do differently?
What is a closure? Write one from scratch in the sandbox folder.


Day 5 — JavaScript Part 2
Goal written before editor opens:

"I will add service card filtering using filter/map/reduce on a JSON array, URL-based filter state with URLSearchParams, and split all JS into ES6 modules."

Copy forward: Both files from Day-4.
What you add:

Move all 15 ClientSide services into a services.js data file as a JSON array
Filter and render cards dynamically using array.filter() → array.map() → innerHTML
URL-based filter: when you click a filter button, URLSearchParams updates the URL so the state survives refresh
Split JS into 3 ES6 modules: data.js (services array), render.js (DOM rendering), filter.js (filter logic)

Depth check before Day 6:

What is the difference between map() and forEach()? When would you never use forEach()?
What does flatMap() do that map() cannot?
Explain ES6 module import/export vs CommonJS require/module.exports. Which is tree-shakeable and why?


Day 6 — Git + GitHub Mastery
Goal written before editor opens:

"I will set up GitFlow with main, develop, and 3 feature branches. Practice interactive rebase, cherry-pick, and set up branch protection on main."

What you do:

Set up GitFlow: main, develop, feature/hero, feature/services, feature/dark-mode
Make 3 messy "wip" commits on a feature branch then squash them into 1 clean commit with git rebase -i HEAD~3
Cherry-pick one specific commit from feature/services onto feature/hero
Set up branch protection on main on GitHub: require PR before merge, no direct push
Write a proper README (this file) in the repo root

Depth check before Day 7:

What is the difference between git merge and git rebase? When do you use each?
What does git cherry-pick abc123 do exactly?
What does interactive rebase squash do and why does it matter for PRs?


Day 7 — Polish + Lighthouse + GitHub Pages Deploy
Goal written before editor opens:

"I will fix every responsive breakpoint from 320px to 1440px, hit Lighthouse 90+ on all metrics, and deploy to GitHub Pages."

Copy forward: All files from Day-6.
What you do:

Test at every breakpoint in Chrome DevTools: 320px, 375px, 768px, 1024px, 1440px. Fix every layout break.
Run Lighthouse. Fix every issue it flags. Target: 90+ on Performance, Accessibility, Best Practices, SEO.
Add alt attributes to every image (accessibility + SEO)
Add meta description tag (SEO)
Deploy to GitHub Pages: Settings → Pages → Deploy from branch → main

Depth check — Week 1 complete:

Rebuild the Tailwind service card grid from memory in 20 minutes. No notes.
Explain the JavaScript event loop (microtask vs macrotask) without Googling.
Why flexbox for nav, grid for services — not the other way around?
What is LCP? What is CLS? What caused your lowest Lighthouse score?
