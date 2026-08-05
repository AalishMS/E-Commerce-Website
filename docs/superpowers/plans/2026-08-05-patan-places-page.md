# Places to Visit in Patan Page Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Rebuild `places.html` and `stylesheet.css` into a simple, responsive "Places to Visit in Patan" page (HTML + CSS only).

**Architecture:** A single semantic HTML page in `places.html` styled entirely by `stylesheet.css`. The page is split into three layout regions — hero, attraction cards grid, and a tips section — plus a footer. The card grid uses CSS Grid's `auto-fill/minmax` for responsiveness, so no media queries are required for the main layout; one small media query handles the tips section. There is no build step and no JavaScript.

**Tech Stack:** HTML5, CSS3, Google Fonts (Yatra), no frameworks.

## Global Constraints

- No JavaScript, no frameworks, no external assets beyond the Yatra Google Font.
- Patan = Patan (Lalitpur), Nepal.
- Yatra font applied throughout; fallback `serif`.
- Palette: beige background `#f6efe1`; deep red accent `#9a1b2e`; warm brown text `#3d2f23`; cream card surface `#fffdf6`.
- Cards: `border-radius: 16px`, subtle layered shadow; hover = lift + deeper shadow only.
- Grid: `repeat(auto-fill, minmax(280px, 1fr))`.
- Fluid type via `clamp()`.
- Image placeholders must be easily replaceable by changing `<img src>`.

---

### Task 1: Rebuild `places.html`

**Files:**
- Modify: `places.html` (whole file, currently a stub)

**Interfaces:**
- Consumes: nothing
- Produces: the semantic page structure that `stylesheet.css` (Task 2) styles via these class names — `.hero`, `.hero-title`, `.hero-text`, `.btn-primary`, `.attractions`, `.section-title`, `.grid`, `.card`, `.card-image`, `.card-title`, `.card-text`, `.card-location`, `.card-link`, `.tips`, `.tips-list`, `.footer`.

- [ ] **Step 1: Replace `places.html` contents**

Replace the entire file with:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset='utf-8'>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <title>Places to Visit in Patan</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Yatra+One&display=swap" rel="stylesheet">
    <link rel='stylesheet' href='stylesheet.css'>
</head>
<body>
    <header class="hero">
        <h1 class="hero-title">Places to Visit in Patan</h1>
        <p class="hero-text">
            Step into the ancient Newari city of Patan — a living museum of
            carved temples, palace squares, and courtyard shrines nestled in the
            Kathmandu Valley.
        </p>
        <a class="btn-primary" href="#attractions">Plan Your Visit</a>
    </header>

    <main>
        <section class="attractions" id="attractions">
            <h2 class="section-title">Iconic Attractions</h2>

            <div class="grid">
                <article class="card">
                    <figure class="card-image">
                        <img src="" alt="Patan Durbar Square">
                        <figcaption>Patan Durbar Square</figcaption>
                    </figure>
                    <h3 class="card-title">Patan Durbar Square</h3>
                    <p class="card-text">
                        The heart of the old royal city, lined with the palace
                        complex, ornate temples, and courtyard squares dating
                        back to the Malla dynasty.
                    </p>
                    <p class="card-location">Location: Mangal Bazar, Patan</p>
                    <a class="card-link" href="#">Learn More</a>
                </article>

                <article class="card">
                    <figure class="card-image">
                        <img src="" alt="Krishna Mandir">
                        <figcaption>Krishna Mandir</figcaption>
                    </figure>
                    <h3 class="card-title">Krishna Mandir</h3>
                    <p class="card-text">
                        A masterpiece of stone carving, this three-tiered
                        Shikhara-style temple was built by King Siddhi Narsingh
                        Malla in the 17th century.
                    </p>
                    <p class="card-location">Location: Patan Durbar Square</p>
                    <a class="card-link" href="#">Learn More</a>
                </article>

                <article class="card">
                    <figure class="card-image">
                        <img src="" alt="Golden Temple (Hiranya Varna Mahavihar)">
                        <figcaption>Hiranya Varna Mahavihar</figcaption>
                    </figure>
                    <h3 class="card-title">Golden Temple</h3>
                    <p class="card-text">
                        A gilded Buddhist monastery hidden in a courtyard of the
                        old town, shining with gold-plated roofs and intricate
                        statues of the Buddha.
                    </p>
                    <p class="card-location">Location: Kwa Bahal, Patan</p>
                    <a class="card-link" href="#">Learn More</a>
                </article>

                <article class="card">
                    <figure class="card-image">
                        <img src="" alt="Patan Museum">
                        <figcaption>Patan Museum</figcaption>
                    </figure>
                    <h3 class="card-title">Patan Museum</h3>
                    <p class="card-text">
                        Housed in a restored wing of the royal palace, this
                        museum displays some of the finest bronze and wooden art
                        in South Asia.
                    </p>
                    <p class="card-location">Location: Patan Durbar Square</p>
                    <a class="card-link" href="#">Learn More</a>
                </article>

                <article class="card">
                    <figure class="card-image">
                        <img src="" alt="Mahabouddha Temple">
                        <figcaption>Mahabouddha Temple</figcaption>
                    </figure>
                    <h3 class="card-title">Mahabouddha Temple</h3>
                    <p class="card-text">
                        A terracotta temple crowned by thousands of small Buddha
                        images, earning it the nickname the "Temple of a
                        Thousand Buddhas".
                    </p>
                    <p class="card-location">Location: Oku Bahal, Patan</p>
                    <a class="card-link" href="#">Learn More</a>
                </article>

                <article class="card">
                    <figure class="card-image">
                        <img src="" alt="Kumbeshwar Temple">
                        <figcaption>Kumbeshwar Temple</figcaption>
                    </figure>
                    <h3 class="card-title">Kumbeshwar Temple</h3>
                    <p class="card-text">
                        A five-tiered pagoda temple raised on a stone plinth,
                        dedicated to Shiva and surrounded by ancient waterspouts
                        and shrine courtyards.
                    </p>
                    <p class="card-location">Location: Kumbeshwar Tole, Patan</p>
                    <a class="card-link" href="#">Learn More</a>
                </article>
            </div>
        </section>

        <section class="tips">
            <h2 class="section-title">Visitor Tips</h2>
            <ul class="tips-list">
                <li>Carry cash — most ticket counters and local shops in Patan do not accept cards.</li>
                <li>Dress modestly and remove shoes before entering temples and courtyards.</li>
                <li>Visit in the early morning or late afternoon to avoid crowds and the midday heat.</li>
                <li>Patan is compact — explore the old town on foot or by rickshaw to soak up the details.</li>
                <li>Hire a local guide to bring the carvings and history of the squares to life.</li>
            </ul>
        </section>
    </main>

    <footer class="footer">
        <p>Discover the heritage of Patan &mdash; an open-air museum of the Kathmandu Valley.</p>
    </footer>
</body>
</html>
```

- [ ] **Step 2: Verify structure**

Open `places.html` in a browser (or run: `start places.html`). Expected: page renders unstyled (plain text + unstyled lists) because `stylesheet.css` still holds the old stub rules. Do not worry about the missing images — the empty `src` is intentional for now.

- [ ] **Step 3: Commit**

```bash
git add places.html
git commit -m "feat: build semantic structure for Places to Visit in Patan"
```

---

### Task 2: Write `stylesheet.css`

**Files:**
- Modify: `stylesheet.css` (whole file, currently the `.Heading` stub)

**Interfaces:**
- Consumes: class names produced in Task 1 (see Task 1 Interfaces)
- Produces: the completed responsive styling for the page

- [ ] **Step 1: Replace `stylesheet.css` contents**

Replace the entire file with:

```css
:root {
    --beige: #f6efe1;
    --deep-red: #9a1b2e;
    --deep-red-dark: #7c1424;
    --text: #3d2f23;
    --cream: #fffdf6;
    --shadow: 0 2px 6px rgba(61, 47, 35, 0.12), 0 10px 24px rgba(61, 47, 35, 0.08);
}

* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: "Yatra One", serif;
    color: var(--text);
    background-color: var(--beige);
    line-height: 1.7;
}

.hero {
    text-align: center;
    padding: clamp(4rem, 12vw, 7rem) 1.5rem;
    background: linear-gradient(180deg, #fbf6ec 0%, var(--beige) 100%);
}

.hero-title {
    margin: 0 auto 1rem;
    max-width: 20ch;
    font-size: clamp(2rem, 6vw, 3.5rem);
    line-height: 1.2;
    color: var(--deep-red);
    letter-spacing: 0.02em;
}

.hero-text {
    margin: 0 auto 2.5rem;
    max-width: 46rem;
    font-size: clamp(1rem, 2.5vw, 1.25rem);
}

.btn-primary {
    display: inline-block;
    padding: 0.9rem 2.2rem;
    background-color: var(--deep-red);
    color: var(--cream);
    text-decoration: none;
    border-radius: 999px;
    letter-spacing: 0.05em;
    box-shadow: var(--shadow);
    transition: background-color 0.2s ease, transform 0.2s ease;
}

.btn-primary:hover {
    background-color: var(--deep-red-dark);
    transform: translateY(-2px);
}

main {
    padding: 0 1.5rem;
}

.attractions,
.tips {
    max-width: 72rem;
    margin: 0 auto;
    padding: clamp(2.5rem, 6vw, 4rem) 0;
}

.section-title {
    margin: 0 0 2rem;
    font-size: clamp(1.5rem, 4vw, 2.25rem);
    color: var(--deep-red);
    text-align: center;
    letter-spacing: 0.03em;
}

.grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 2rem;
}

.card {
    display: flex;
    flex-direction: column;
    background-color: var(--cream);
    border-radius: 16px;
    overflow: hidden;
    box-shadow: var(--shadow);
    transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.card:hover {
    transform: translateY(-6px);
    box-shadow: 0 6px 14px rgba(61, 47, 35, 0.14), 0 18px 36px rgba(61, 47, 35, 0.12);
}

.card-image {
    margin: 0;
    height: 200px;
    background: linear-gradient(135deg, #e8dcc4 0%, #d9c8a6 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
}

.card-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.card-image figcaption {
    position: absolute;
    inset: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--deep-red);
    font-size: 1.1rem;
    text-align: center;
    padding: 1rem;
}

.card-title {
    margin: 0;
    padding: 1.25rem 1.5rem 0;
    font-size: 1.35rem;
    color: var(--deep-red);
    letter-spacing: 0.02em;
}

.card-text {
    margin: 0;
    padding: 0.75rem 1.5rem;
    flex: 1;
}

.card-location {
    margin: 0;
    padding: 0 1.5rem;
    font-size: 0.9rem;
    color: var(--deep-red);
}

.card-link {
    display: inline-block;
    margin: 1rem 1.5rem 1.5rem;
    color: var(--deep-red);
    text-decoration: none;
    border-bottom: 2px solid transparent;
    transition: border-color 0.2s ease, color 0.2s ease;
    align-self: flex-start;
}

.card-link:hover {
    color: var(--deep-red-dark);
    border-bottom-color: var(--deep-red);
}

.tips {
    background-color: #f1e6d2;
    border-radius: 16px;
    padding: clamp(2.5rem, 6vw, 4rem) clamp(1.5rem, 4vw, 3rem);
    margin-bottom: 3rem;
}

.tips-list {
    margin: 0 auto;
    max-width: 46rem;
    padding-left: 1.25rem;
}

.tips-list li {
    margin-bottom: 0.75rem;
}

@media (min-width: 48rem) {
    .tips-list {
        columns: 2;
        column-gap: 3rem;
    }
}

.footer {
    text-align: center;
    padding: 2rem 1.5rem;
    background-color: var(--deep-red);
    color: var(--cream);
    font-size: 0.95rem;
}
```

- [ ] **Step 2: Verify visually in a browser**

Open `places.html` (or run: `start places.html`). Expected:
- Yatra font applied throughout; heading and section titles deep red.
- Hero centered with CTA button; button darkens on hover.
- 6 cards in a responsive grid — 3 columns on a wide window, shrinking to 1 column as the window narrows.
- Each card shows a beige gradient placeholder where its image will go, name, description, location, and "Learn More" link.
- Tips section styled as a rounded panel (tips list becomes two columns when the window is wider than 48rem); footer deep red with cream text.
- Hovering a card lifts it slightly with a deeper shadow.

- [ ] **Step 3: Commit**

```bash
git add stylesheet.css
git commit -m "feat: style Places to Visit in Patan page"
```

---

