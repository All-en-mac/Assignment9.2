HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Typography & Images — Article</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Main Content Container with Controlled Max-Width -->
    <main class="article-container">
        
        <!-- Article Header -->
        <header class="article-header">
            <span class="category">Design & Architecture</span>
            <h1>The Evolution of Modern Web Typography and Responsive Layouts</h1>
            <p class="article-meta">Published by Alex Rivera • October 24, 2026 • 5 min read</p>
        </header>

        <!-- Primary Feature Image -->
        <div class="image-wrapper">
            <img src="https://images.unsplash.com/photo-1507238691740-187a5b1d37b8?auto=format&fit=crop&w=1200&q=80" alt="Workspace with design drafts and laptop">
            <figcaption>Clean typography relies on precise scale and fluid sizing.</figcaption>
        </div>

        <!-- Article Body Content -->
        <section class="article-content">
            <p class="lead">Crafting a truly responsive reading experience requires more than just scaling screen grids. It demands careful attention to typography, scalable media assets, and comfortable line lengths that prevent eye fatigue.</p>
            
            <h2>Why Line Length Matters</h2>
            <p>When text blocks stretch too wide across desktop monitors, readers struggle to track lines from the end of one sentence to the beginning of the next. Conversely, lines that are too narrow break reading rhythm. The golden rule of web typography is maintaining an average of <strong>60 to 75 characters per line</strong>.</p>
            
            <p>By pairing a controlled container `max-width` with fluid font units like `clamp()`, typography scales organically without requiring dozens of hardcoded media query breakpoints.</p>

            <!-- Secondary Image -->
            <div class="image-wrapper">
                <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?auto=format&fit=crop&w=1200&q=80" alt="Developer coding on dual screens">
                <figcaption>Modern CSS gives developers unprecedented control over layout behavior.</figcaption>
            </div>

            <h2>Embracing Fluid Scalability</h2>
            <p>Using relative units like <code>rem</code> for spacing and font sizes ensures accessibility, respecting user browser preferences (such as custom default font sizes). When combined with responsive images (`max-width: 100%`), your content remains robust, crisp, and overflow-free on everything from compact smartphones to ultra-wide displays.</p>
        </section>

        <!-- Article Footer -->
        <footer class="article-footer">
            <p>&copy; 2026 Typography & Web Standards Journal. All rights reserved.</p>
        </footer>

    </main>

</body>
</html>


CSS
/* ==========================================================
   Global Resets & Box-Sizing
   ========================================================== */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box; /* Prevents padding/borders from causing horizontal overflow */
}

body {
    background-color: #f8fafc;
    color: #1e293b;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.7;
    padding: 1.5rem 1rem; /* Responsive padding for mobile */
}

/* ==========================================================
   Step 5 & 6: Controlled Container Max-Width & Line Length
   ========================================================== */
.article-container {
    max-width: 720px; /* Ideal width to maintain 60-75 characters per line */
    margin: 0 auto;   /* Centers the article container on the screen */
    background-color: #ffffff;
    padding: 2rem 1.5rem;
    border-radius: 12px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
    border: 1px solid #e2e8f0;
}

/* ==========================================================
   Step 3: Responsive Typography (rem & clamp())
   ========================================================== */
.category {
    font-size: 0.85rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: #2563eb;
    display: block;
    margin-bottom: 0.75rem;
}

/* Fluid Heading using clamp() (Min: 1.75rem, Ideal: 4vw + 1rem, Max: 2.5rem) */
.article-header h1 {
    font-size: clamp(1.75rem, 3.5vw + 1rem, 2.6rem);
    font-weight: 800;
    color: #0f172a;
    line-height: 1.25;
    margin-bottom: 1rem;
}

.article-meta {
    font-size: 0.9rem;
    color: #64748b;
    margin-bottom: 2rem;
    padding-bottom: 1.5rem;
    border-bottom: 1px solid #e2e8f0;
}

.article-content h2 {
    font-size: clamp(1.3rem, 2vw + 0.8rem, 1.75rem);
    font-weight: 700;
    color: #0f172a;
    margin-top: 2.5rem;
    margin-bottom: 1rem;
}

.article-content p {
    font-size: 1.05rem; /* Scales comfortably using rem */
    color: #334155;
    margin-bottom: 1.25rem;
}

.lead {
    font-size: 1.15rem;
    font-weight: 500;
    color: #0f172a;
    line-height: 1.6;
}

/* ==========================================================
   Step 4 & 7: Responsive Images (max-width & height: auto)
   ========================================================== */
.image-wrapper {
    margin: 2rem 0;
    text-align: center;
}

.image-wrapper img {
    width: 100%;             /* Ensures image spans container width */
    max-width: 100%;         /* Step 4: Prevents image from exceeding container */
    height: auto;            /* Step 4: Maintains natural aspect ratio without stretching */
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
    display: block;
}

.image-wrapper figcaption {
    font-size: 0.85rem;
    color: #64748b;
    margin-top: 0.5rem;
    font-style: italic;
}

/* Article Footer */
.article-footer {
    margin-top: 3rem;
    padding-top: 1.5rem;
    border-top: 1px solid #e2e8f0;
    text-align: center;
    color: #64748b;
    font-size: 0.85rem;
}

/* ==========================================================
   Step 6: Tablet & Desktop Spacing Enhancements
   ========================================================== */
@media (min-width: 768px) {
    body {
        padding: 3rem 2rem;
    }

    .article-container {
        padding: 3rem 3.5rem;
    }
}