<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Crystal Symmetry and Crossed Polarizers | Supplementary Site</title>
<style>
  :root {
    --bg: #fbfbfd; --surface: #ffffff; --text: #1d1d24; --muted: #5d5d6b;
    --accent: #5b3fd6; --accent-soft: #ece8fc; --border: #dcdce6;
    --ok: #1f7a4d; --bad: #b03a2e; --placeholder: #f1f1f6;
    color-scheme: light;
  }
  @media (prefers-color-scheme: dark) {
    :root:not([data-theme="light"]) {
      --bg: #14141a; --surface: #1d1d26; --text: #ececf3; --muted: #a4a4b5;
      --accent: #a594ff; --accent-soft: #2b2740; --border: #33334a;
      --ok: #5fd39a; --bad: #ff8a7d; --placeholder: #232334; color-scheme: dark;
    }
  }
  :root[data-theme="dark"] {
    --bg: #14141a; --surface: #1d1d26; --text: #ececf3; --muted: #a4a4b5;
    --accent: #a594ff; --accent-soft: #2b2740; --border: #33334a;
    --ok: #5fd39a; --bad: #ff8a7d; --placeholder: #232334; color-scheme: dark;
  }
  * { box-sizing: border-box; }
  html { scroll-behavior: smooth; scroll-padding-top: 4.5rem; }
  body {
    margin: 0; font-family: system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
    line-height: 1.6; color: var(--text); background: var(--bg);
    padding-top: env(safe-area-inset-top, 0px);
  }
  a { color: var(--accent); }

  /* Top bar */
  header.topbar {
    position: sticky; top: env(safe-area-inset-top, 0px); z-index: 10;
    background: var(--accent); color: #fff;
  }
  .topbar-inner {
    max-width: 1080px; margin: 0 auto; padding: 0.7rem 1rem;
    display: flex; flex-wrap: wrap; gap: 0.4rem 1.2rem; align-items: center;
  }
  .brand { font-weight: 700; margin-right: auto; font-size: 0.98rem; }
  .topbar nav a {
    color: #fff; opacity: 0.85; text-decoration: none; font-size: 0.85rem;
    padding: 0.2rem 0.3rem; border-radius: 4px;
  }
  .topbar nav a:hover, .topbar nav a:focus-visible { opacity: 1; text-decoration: underline; }

  /* Hero */
  .hero { background: var(--accent); color: #fff; padding: 2.5rem 1rem 2.8rem; }
  .hero-inner { max-width: 1080px; margin: 0 auto; }
  .hero .eyebrow-chip {
    display: inline-block; border: 1px solid rgba(255,255,255,0.5); border-radius: 999px;
    padding: 0.2rem 0.8rem; font-size: 0.78rem; letter-spacing: 0.06em; text-transform: uppercase;
  }
  .hero h1 { font-size: 2.2rem; line-height: 1.2; margin: 0.9rem 0 0.7rem; max-width: 22ch; }
  .hero p { font-size: 1.08rem; max-width: 62ch; opacity: 0.92; margin: 0; }
  .chips { display: flex; flex-wrap: wrap; gap: 0.6rem; margin-top: 1.6rem; }
  .chip {
    background: rgba(255,255,255,0.12); border: 1px solid rgba(255,255,255,0.3);
    border-radius: 10px; padding: 0.55rem 0.9rem; min-width: 120px;
  }
  .chip .n { font-size: 1.25rem; font-weight: 700; display: block; line-height: 1.2; }
  .chip .l { font-size: 0.78rem; opacity: 0.85; text-transform: uppercase; letter-spacing: 0.04em; }

  main { max-width: 1080px; margin: 0 auto; padding: 1.5rem 1rem 4rem; }
  section { margin: 3.2rem 0; scroll-margin-top: 4.5rem; }
  .section-head { margin-bottom: 1rem; }
  .step { color: var(--accent); font-weight: 700; font-size: 0.85rem; letter-spacing: 0.06em; text-transform: uppercase; }
  h2 { font-size: 1.6rem; margin: 0.2rem 0 0.4rem; line-height: 1.25; }
  h3 { font-size: 1.1rem; margin: 1.4rem 0 0.5rem; }
  p, li { max-width: 72ch; }
  .lede { font-size: 1.05rem; color: var(--muted); }
  .mono { font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace; font-size: 0.92em; }

  .card {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: 12px; padding: 1.2rem 1.3rem; margin: 1rem 0;
  }
  .card-tight { padding: 0.9rem 1rem; }
  .two-col { display: grid; grid-template-columns: 1.5fr 1fr; gap: 1.2rem; align-items: start; }
  @media (max-width: 800px) { .two-col { grid-template-columns: 1fr; } .hero h1 { font-size: 1.8rem; } }

  .equation {
    background: var(--accent-soft); border-radius: 8px; padding: 0.8rem 1rem;
    overflow-x: auto; font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;
    font-size: 0.95rem; white-space: pre; margin: 0.75rem 0;
  }

  /* Pills */
  .pills { display: flex; flex-wrap: wrap; gap: 0.5rem; margin: 0.6rem 0 0.9rem; }
  .pill-btn {
    font: inherit; font-size: 0.9rem; padding: 0.35rem 0.85rem; border-radius: 999px;
    border: 1px solid var(--border); background: var(--surface); color: var(--text); cursor: pointer;
  }
  .pill-btn:hover { border-color: var(--accent); }
  .pill-btn[aria-pressed="true"] { background: var(--accent); border-color: var(--accent); color: #fff; }
  .pill-btn:focus-visible { outline: 2px solid var(--accent); outline-offset: 2px; }

  .readout { display: grid; grid-template-columns: 1fr 1fr; gap: 0.6rem; }
  .readout div { background: var(--accent-soft); border-radius: 8px; padding: 0.6rem 0.75rem; }
  .readout .k { font-size: 0.72rem; text-transform: uppercase; letter-spacing: 0.05em; color: var(--muted); }
  .readout .v { font-size: 1.15rem; font-weight: 700; }
  .status { margin-top: 0.8rem; font-size: 0.95rem; }
  .canvas-wrap { background: var(--placeholder); border-radius: 10px; padding: 0.5rem; }
  canvas.viz { width: 100%; height: auto; display: block; border-radius: 6px; background: var(--surface); }

  .callout { border-left: 4px solid var(--accent); background: var(--accent-soft); padding: 0.8rem 1rem; border-radius: 0 8px 8px 0; margin: 1rem 0; }
  .callout.warn { border-left-color: var(--bad); }
  .callout.note { border-left-color: var(--ok); }

  .tag {
    display: inline-block; font-size: 0.72rem; font-weight: 700; padding: 0.05rem 0.45rem;
    border-radius: 4px; background: var(--placeholder); color: var(--bad); border: 1px solid var(--bad);
    vertical-align: middle; letter-spacing: 0.03em;
  }
  .pill { display: inline-block; padding: 0.1rem 0.55rem; border-radius: 999px; font-size: 0.8rem; font-weight: 600; }
  .pill.dark { background: var(--placeholder); color: var(--text); }
  .pill.bright { background: var(--accent-soft); color: var(--accent); }

  .placeholder {
    background: var(--placeholder); border: 2px dashed var(--border);
    border-radius: 10px; padding: 1.3rem 1rem; text-align: center; color: var(--muted); margin: 0.8rem 0;
  }
  .placeholder strong { color: var(--text); display: block; margin-bottom: 0.3rem; }
  .placeholder .how { font-size: 0.9rem; text-align: left; max-width: 60ch; margin: 0.5rem auto 0; }

  .grid-samples { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 0.9rem; margin-top: 1rem; }
  .sample-card { background: var(--surface); border: 1px solid var(--border); border-radius: 12px; padding: 1rem 1.1rem; }
  .sample-card h3 { margin: 0 0 0.4rem; font-size: 1.02rem; }
  .sample-card .meta { font-size: 0.9rem; color: var(--muted); margin-bottom: 0.6rem; }

  .steps { counter-reset: st; padding-left: 0; list-style: none; }
  .steps li { counter-increment: st; position: relative; padding: 0.35rem 0 0.35rem 2.2rem; }
  .steps li::before {
    content: counter(st); position: absolute; left: 0; top: 0.4rem;
    width: 1.6rem; height: 1.6rem; border-radius: 50%;
    background: var(--accent); color: #fff; display: flex; align-items: center; justify-content: center;
    font-size: 0.85rem; font-weight: 700;
  }

  .table-wrap { overflow-x: auto; margin: 1rem 0; border-radius: 12px; border: 1px solid var(--border); background: var(--surface); }
  table { width: 100%; border-collapse: collapse; font-size: 0.92rem; }
  th, td { text-align: left; padding: 0.6rem 0.7rem; border-bottom: 1px solid var(--border); vertical-align: top; }
  th { background: var(--accent-soft); font-weight: 600; white-space: nowrap; }
  tr:last-child td { border-bottom: none; }
  td.tbd { color: var(--muted); font-style: italic; }

  .refs li { margin-bottom: 0.5rem; font-size: 0.95rem; }
  .video-group { margin-top: 1rem; }
  .video-group ul { padding-left: 1.1rem; }
  .video-group li { margin-bottom: 0.35rem; }
  .quiz-option { margin: 0.35rem 0; }
  .quiz-option span.letter { font-weight: 700; margin-right: 0.4rem; color: var(--accent); }


  /* Motif */
  .motif { width: 1.1em; height: 1.1em; vertical-align: -0.18em; margin-right: 0.4em; fill: none; stroke: currentColor; stroke-width: 2; stroke-linecap: round; stroke-linejoin: round; }
  .brand .motif { width: 1.2em; height: 1.2em; }
  /* Hero wave */
  .hero { position: relative; overflow: hidden; }
  #heroWave { position: absolute; inset: 0; width: 100%; height: 100%; opacity: 0.32; pointer-events: none; z-index: 0; }
  .hero-inner { position: relative; z-index: 1; }
  .hero .motif { width: 2.2em; height: 2.2em; margin: 0 0 0.6rem; display: block; stroke: #fff; }
  /* Sections dropdown */
  details.sections { position: relative; }
  details.sections > summary {
    list-style: none; cursor: pointer; color: #fff; font-size: 0.88rem;
    padding: 0.3rem 0.85rem; border: 1px solid rgba(255,255,255,0.55); border-radius: 999px;
  }
  details.sections > summary::-webkit-details-marker { display: none; }
  details.sections > summary:focus-visible { outline: 2px solid #fff; outline-offset: 2px; }
  details.sections .panel {
    position: absolute; right: 0; top: calc(100% + 0.5rem); z-index: 30;
    background: var(--surface); color: var(--text); border: 1px solid var(--border);
    border-radius: 12px; padding: 0.5rem; min-width: 220px;
    display: grid; gap: 0.1rem; box-shadow: 0 10px 30px rgba(0,0,0,0.15);
  }
  details.sections .panel a { color: var(--text); text-decoration: none; padding: 0.4rem 0.6rem; border-radius: 8px; font-size: 0.92rem; }
  details.sections .panel a:hover, details.sections .panel a:focus-visible { background: var(--accent-soft); color: var(--accent); }


  /* ---------- Motion ---------- */
  :root { --ease: cubic-bezier(.2,.7,.2,1); }
  html.js .reveal { opacity: 0; transform: translateY(18px); transition: opacity .7s var(--ease), transform .7s var(--ease); }
  html.js .reveal.in { opacity: 1; transform: none; }
  .card, .sample-card { transition: transform .3s var(--ease), box-shadow .3s var(--ease), border-color .3s var(--ease); }
  .card:hover, .sample-card:hover { transform: translateY(-3px); box-shadow: 0 10px 28px rgba(0,0,0,0.09); border-color: var(--accent); }
  .pill-btn { transition: background .25s, color .25s, border-color .25s, transform .15s var(--ease); }
  .pill-btn:hover { transform: translateY(-1px); }
  .pill-btn:active { transform: scale(0.97); }
  details.sections > summary { transition: background .25s, color .25s; }
  details.sections > summary:hover { background: rgba(255,255,255,0.14); }
  details.sections[open] > summary { background: rgba(255,255,255,0.18); }
  details.sections[open] .panel { animation: panelIn .25s var(--ease); }
  @keyframes panelIn { from { opacity: 0; transform: translateY(-6px); } to { opacity: 1; transform: none; } }
  header.topbar { transition: box-shadow .35s var(--ease); }
  header.topbar.scrolled { box-shadow: 0 6px 18px rgba(0,0,0,0.18); }
  #progress { position: absolute; left: 0; bottom: 0; height: 3px; width: 0; background: #fff; opacity: .85; pointer-events: none; }
  .topbar-inner a, .brand { transition: opacity .2s; }
  .hero .eyebrow-chip, .hero h1, .hero p { animation: heroIn .9s var(--ease) both; }
  .hero h1 { animation-delay: .08s; }
  .hero p { animation-delay: .18s; }
  .chip { animation: heroIn .8s var(--ease) both; }
  .chip:nth-child(1) { animation-delay: .25s; } .chip:nth-child(2) { animation-delay: .32s; }
  .chip:nth-child(3) { animation-delay: .39s; } .chip:nth-child(4) { animation-delay: .46s; }
  .hero .motif { animation: heroIn .9s var(--ease) both, float 6s ease-in-out 1s infinite; }
  @keyframes heroIn { from { opacity: 0; transform: translateY(12px); } to { opacity: 1; transform: none; } }
  @keyframes float { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-4px); } }
  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after { animation: none !important; transition: none !important; scroll-behavior: auto !important; }
    html.js .reveal { opacity: 1; transform: none; }
  }


  /* ---------- Flip cards ---------- */
  .flip { perspective: 1400px; margin: 1rem 0; }
  .flip .card, .flip .callout { margin: 0; height: 100%; }
  .flip-inner { display: grid; transition: transform .8s var(--ease); transform-style: preserve-3d; }
  .flip.flipped .flip-inner { transform: rotateY(180deg); }
  .face { grid-area: 1 / 1; backface-visibility: hidden; -webkit-backface-visibility: hidden; display: flex; flex-direction: column; }
  .face > p:last-of-type, .face > ul, .face > ol { flex: 0 0 auto; }
  .face.back {
    transform: rotateY(180deg); background: var(--surface); border: 1px solid var(--accent);
    border-radius: 12px; padding: 1.1rem 1.2rem; box-shadow: 0 10px 28px rgba(0,0,0,0.08);
  }
  .flip-btn {
    align-self: flex-start; margin-top: auto; font: inherit; font-size: 0.85rem; font-weight: 600;
    padding: 0.35rem 0.9rem; border-radius: 999px; border: 1px solid var(--accent);
    background: var(--accent); color: #fff; cursor: pointer; transition: transform .15s var(--ease), opacity .2s;
  }
  .flip-btn:hover { transform: translateY(-1px); opacity: .92; }
  .flip-btn:focus-visible { outline: 2px solid var(--accent); outline-offset: 3px; }
  .flip-back { background: transparent; color: var(--accent); margin-top: 0.9rem; }
  .face.front .flip-btn { margin-top: 0.9rem; }
  .back-head .kicker { color: var(--accent); font-size: 0.72rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.06em; }
  .back-head h3 { margin: 0.2rem 0 0.6rem; font-size: 1.05rem; }
  .back-list { list-style: none; padding: 0; margin: 0; display: grid; gap: 0.55rem; }
  .back-list li { font-size: 0.9rem; line-height: 1.5; padding-left: 0.2rem; }
  .back-list .kind {
    display: inline-block; min-width: 3.6rem; font-size: 0.7rem; font-weight: 700; text-transform: uppercase;
    letter-spacing: 0.05em; color: var(--accent); background: var(--accent-soft); border-radius: 4px; padding: 0.05rem 0.35rem; margin-right: 0.35rem; text-align: center;
  }
  .back-list a { color: var(--accent); }
  .flip-hint {
    display: inline-flex; align-items: center; gap: 0.5rem; margin: 1.2rem 0 0; font-size: 0.92rem;
    background: rgba(255,255,255,0.12); border: 1px solid rgba(255,255,255,0.3); padding: 0.45rem 0.9rem; border-radius: 999px;
    animation: heroIn .9s var(--ease) .5s both;
  }
  .hint-icon { font-size: 1.05rem; }
  @media (prefers-reduced-motion: reduce) { .flip-inner { transition: none; } }

  footer { color: var(--muted); font-size: 0.85rem; text-align: center; padding: 2rem 1rem; border-top: 1px solid var(--border); }
</style>
<script>
window.MathJax = {
  tex: { inlineMath: [['\\(', '\\)']], displayMath: [['\\[', '\\]']] },
  svg: { fontCache: 'global' }
};
</script>
<script id="MathJax-script" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.2/es5/tex-svg.js"></script>
</head>
<body>
<svg width="0" height="0" style="position:absolute" aria-hidden="true">
  <symbol id="pol-motif" viewBox="0 0 64 64">
    <line x1="6" y1="48" x2="58" y2="16" stroke-opacity="0.5"/>
    <ellipse cx="20" cy="36" rx="5" ry="14" transform="rotate(-18 20 36)"/>
    <ellipse cx="32" cy="30" rx="5" ry="14" transform="rotate(-18 32 30)"/>
    <ellipse cx="44" cy="24" rx="5" ry="14" transform="rotate(-18 44 24)"/>
    <path d="M8 46 Q 32 26 56 18"/>
  </symbol>
</svg>

<header class="topbar">
  <div id="progress" aria-hidden="true"></div>
  <div class="topbar-inner">
    <span class="brand"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>MM 219 · Group 10 · Crystal Symmetry &amp; Crossed Polarizers</span>
    <details class="sections">
      <summary>Sections ▾</summary>
      <div class="panel" aria-label="Page sections">
        <a href="#theory">Theory</a>
        <a href="#method">Method</a>
        <a href="#animation">Animation</a>
        <a href="#structure">Structure</a>
        <a href="#samples">Samples</a>
        <a href="#results">Results</a>
        <a href="#concepts">Concepts</a>
        <a href="#quiz">Quiz</a>
        <a href="#references">References</a>
        <a href="#videos">Videos</a>
        <a href="#downloads">Downloads</a>
        <a href="#team">Team</a>
      </div>
    </details>
  </div>
</header>

<div class="hero">
  <canvas id="heroWave" aria-hidden="true"></canvas>
<div class="hero-inner">
    <svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>
    <span class="eyebrow-chip">MM 219 · Group 10</span>
    <h1>Does crystal symmetry decide whether light behaves the same in every direction?</h1>
    <p>We predicted, from crystal symmetry alone, which crystals should stay dark and which should brighten and darken when rotated between crossed polarizers. We then tested those predictions with a phone screen and polarized sunglasses.</p>
    <p class="flip-hint"><span class="hint-icon" aria-hidden="true">&#8634;</span> Tip: press <strong>Explore sources</strong> on any theory card to flip it and see the references and videos behind it.</p>
    <div class="chips">
      <div class="chip"><span class="n">5</span><span class="l">Samples</span></div>
      <div class="chip"><span class="n">7</span><span class="l">Crystal systems</span></div>
      <div class="chip"><span class="n">1</span><span class="l">Tensor rule</span></div>
      <div class="chip"><span class="n">4</span><span class="l">Tests per sample</span></div>
    </div>
  </div>
</div>

<main>

<!-- ============ 01 THEORY ============ -->
<section id="theory">
  <div class="section-head">
    <div class="step"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>01 · Where we start</div>
    <h2>From symmetry to tensor form</h2>
    <p class="lede">Light moves through a crystal at a speed set by the relative permittivity, a symmetric second-rank tensor \(\varepsilon_{ij}\), through \(D_i = \varepsilon_0 \varepsilon_{ij} E_j\). Neumann's principle says any physical property of a crystal must be invariant under the crystal's symmetry operations. This limits which components can be nonzero, and so how many distinct refractive indices a crystal has.</p>
  </div>

  <div class="two-col">
    <div class="flip">
  <div class="flip-inner">
  <div class="face front card">
      <h3 style="margin-top:0">Reducing the six components</h3>
      <p>A symmetric tensor has six independent components (\(\varepsilon_{11}, \varepsilon_{22}, \varepsilon_{33}, \varepsilon_{12}, \varepsilon_{23}, \varepsilon_{13}\)). Each crystal system removes some of them:</p>
      <ol class="steps">
        <li><strong>Triclinic:</strong> only inversion or no symmetry, so all 6 components are allowed.</li>
        <li><strong>Monoclinic:</strong> a single twofold axis along \(x_2\) forces \(\varepsilon_{12} = \varepsilon_{23} = 0\), leaving 4.</li>
        <li><strong>Orthorhombic:</strong> three perpendicular twofold axes remove all off-diagonal terms, leaving 3.</li>
        <li><strong>Tetragonal, hexagonal, trigonal:</strong> one threefold, fourfold or sixfold axis makes two diagonal components equal, leaving 2 (uniaxial).</li>
        <li><strong>Cubic:</strong> four threefold axes along the body diagonals force all diagonal components equal, leaving 1 (isotropic).</li>
      </ol>
    
    <button class="flip-btn" type="button" aria-expanded="false">Explore sources</button>
  </div>
  <div class="face back">
    <div class="back-head"><span class="kicker">Explore further</span><h3>Reducing the six components</h3></div>
    <ul class="back-list">
      <li><span class="kind">Book</span> J. F. Nye, <em>Physical Properties of Crystals</em> (1985), Ch. I on Neumann's principle. <span class="tag">page numbers to verify</span></li>
      <li><span class="kind">Book</span> R. E. Newnham, <em>Properties of Materials</em> (2005), Ch. 4 on symmetry and physical properties. <span class="tag">chapter to verify</span></li>
      <li><span class="kind">Table</span> W. D. Nesse, <em>Introduction to Optical Mineralogy</em>, Appendix C: uniaxial and biaxial indices (Tables C.4 to C.6).</li>
    </ul>
    <button class="flip-btn flip-back" type="button" aria-expanded="true">Flip back</button>
  </div>
  </div>
</div>

    <div class="flip">
  <div class="flip-inner">
  <div class="face front card">
      <h3 style="margin-top:0">Summary by crystal system</h3>
      <div class="table-wrap" style="margin:0.5rem 0 0">
        <table>
          <thead><tr><th>System</th><th>Independent</th><th>Optics</th></tr></thead>
          <tbody>
            <tr><td>Cubic</td><td>1</td><td>Isotropic</td></tr>
            <tr><td>Tetragonal, hex., trig.</td><td>2</td><td>Uniaxial</td></tr>
            <tr><td>Orthorhombic</td><td>3</td><td>Biaxial</td></tr>
            <tr><td>Monoclinic</td><td>4</td><td>Biaxial</td></tr>
            <tr><td>Triclinic</td><td>6</td><td>Biaxial</td></tr>
          </tbody>
        </table>
      </div>
    
    <button class="flip-btn" type="button" aria-expanded="false">Explore sources</button>
  </div>
  <div class="face back">
    <div class="back-head"><span class="kicker">Explore further</span><h3>Summary by crystal system</h3></div>
    <ul class="back-list">
      <li><span class="kind">Table</span> CRC Handbook, 97th ed., Section 10, Index of Refraction of Inorganic Crystals, pp. 10-248 to 10-251. Each entry gives its crystal system, for example \(\mathrm{CuSO_4\cdot5H_2O}\) (triclinic).</li>
      <li><span class="kind">Table</span> Nesse, Appendix C: Table C.3 (isotropic), C.4 (uniaxial), C.5 and C.6 (biaxial).</li>
    </ul>
    <button class="flip-btn flip-back" type="button" aria-expanded="true">Flip back</button>
  </div>
  </div>
</div>
  </div>

  <div class="flip">
  <div class="flip-inner">
  <div class="face front callout">
    <strong>Why cubic crystals are isotropic:</strong> the cubic group contains threefold rotations about the body diagonals, which map x, y and z onto one another. A tensor invariant under these rotations must have equal diagonal components and no off-diagonal components, so \(\varepsilon_{11} = \varepsilon_{22} = \varepsilon_{33}\) and the crystal has a single refractive index.
  
    <button class="flip-btn" type="button" aria-expanded="false">Explore sources</button>
  </div>
  <div class="face back">
    <div class="back-head"><span class="kicker">Explore further</span><h3>Why cubic crystals are isotropic</h3></div>
    <ul class="back-list">
      <li><span class="kind">Table</span> Nesse, Appendix C, Table C.3: isotropic minerals, including halite at \(n = 1.544\).</li>
      <li><span class="kind">Table</span> CRC Handbook, p. 10-249: NaCl (cubic) has a single index, \(n = 1.5441\) at 589 nm.</li>
      <li><span class="kind">Video</span> <a href="https://www.youtube.com/watch?v=5GSgji6zf00" target="_blank" rel="noopener">Reumi's world, Optic Axis and Birefringence</a></li>
    </ul>
    <button class="flip-btn flip-back" type="button" aria-expanded="true">Flip back</button>
  </div>
  </div>
</div>

  <h3>Crossed-polarizer intensity</h3>
  <p>For a plate of thickness d whose birefringence axes sit at angle \(\theta\) to the polarizer, with the analyser crossed:</p>
  <div class="equation">\[ I(\theta) = I_0 \sin^2(2\theta)\,\sin^2\!\left(\frac{\delta}{2}\right), \qquad \delta = \frac{2\pi\,\Delta n\, d}{\lambda} \]</div>
  <p>The plate is dark at \(\theta = 0^\circ, 90^\circ, 180^\circ\) and \(270^\circ\), and brightest at \(\theta = 45^\circ\). Cubic crystals have \(\Delta n = 0\), so \(\delta = 0\) and \(I = 0\) at every angle. <span class="tag">TO VERIFY</span> Derivation and sign conventions against Born &amp; Wolf, Ch. 15 (see References).</p>
</section>

<!-- ============ 02 METHOD ============ -->
<section id="method">
  <div class="section-head">
    <div class="step"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>02 · What we built</div>
    <h2>The phone-screen setup</h2>
  </div>
  <div class="two-col">
    <div class="card">
      <ol class="steps">
        <li><strong>Check the screen is an LCD.</strong> LCD screens emit polarized light; many OLED screens do not. Show a plain white image, put a polarizer in front, and rotate it. An LCD goes bright to dark and back.</li>
        <li><strong>Find the crossed position.</strong> Rotate the polarizer until the screen looks darkest.</li>
        <li><strong>Insert the sample.</strong> Place it between screen and analyser, flat and centred on the light path.</li>
        <li><strong>Rotate through 360°.</strong> Record whether it stays dark or brightens and darkens.</li>
      </ol>
    </div>
    <div>
      <div class="placeholder">
        <strong>PHOTO NEEDED: Full setup, wide shot</strong>
        Show the LCD screen, the polarizer and the sample holder.
        <div class="how"><strong>How to take it:</strong> Plain white image on the screen. Camera level with the screen, about 30 cm away, filling the frame. Save as <code>images/setup_wide.jpg</code>.</div>
      </div>
      <div class="placeholder">
        <strong>PHOTO NEEDED: Sample holder close-up</strong>
        <div class="how">Photograph from the analyser side at a slight angle to avoid reflections. Save as <code>images/holder_closeup.jpg</code>.</div>
      </div>
    </div>
  </div>
  <div class="callout warn">
    <strong>Safety:</strong> Wear gloves when handling copper sulphate, and wash your hands afterwards. It is harmful if swallowed and irritates the skin and eyes.
  </div>
</section>

<!-- ============ 03 ANIMATION ============ -->
<section id="animation">
  <div class="section-head">
    <div class="step"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>03 · Interactive · animated</div>
    <h2>Expected behaviour</h2>
    <p class="lede">Pick a sample and watch the predicted screen brightness as it rotates between crossed polarizers. The curve is \(I(\theta) = I_0 \sin^2(2\theta)\sin^2(\delta/2)\). <span class="tag">ILLUSTRATIVE</span> The \(\delta\) values are chosen to show the typical pattern. They are not measurements.</p>
  </div>
  <div class="pills" id="animPills" role="group" aria-label="Choose a sample"></div>
  <div class="two-col">
    <div class="card">
      <div class="canvas-wrap">
        <canvas id="animCanvas" class="viz" width="700" height="290"></canvas>
      </div>
      <div style="display:flex;gap:0.6rem;align-items:center;margin-top:0.8rem;flex-wrap:wrap">
        <button id="animPlay" type="button" class="pill-btn" aria-pressed="true">Pause</button>
        <label style="flex:1;min-width:180px">Angle <input id="animAngle" type="range" min="0" max="360" step="1" value="0" style="width:100%"></label>
      </div>
    </div>
    <div class="card">
      <div class="readout">
        <div><div class="k">Sample angle \(\theta\)</div><div class="v" id="rdTheta">0°</div></div>
        <div><div class="k">Relative brightness</div><div class="v" id="rdBright">0.00</div></div>
        <div><div class="k">Phase \(\delta\) (illustr.)</div><div class="v" id="rdDelta">0.0 rad</div></div>
        <div><div class="k">Dark positions / turn</div><div class="v" id="rdExt">all</div></div>
      </div>
      <p class="status" id="rdStatus"></p>
      <div class="callout note" style="margin-bottom:0"><strong>Reading the plot:</strong> the purple line is the fast axis. Where the curve touches zero the screen is dark. The bright peaks sit 45° from each dark position.</div>
    </div>
  </div>
</section>

<!-- ============ 04 STRUCTURE ============ -->
<section id="structure">
  <div class="section-head">
    <div class="step"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>04 · Interactive · 3D</div>
    <h2>Crystal structure</h2>
    <p class="lede">Drag to rotate, scroll to zoom. Table salt is drawn with its atomic positions (rock-salt structure, \(2\times2\times2\) unit cells). The other three are unit-cell shapes only, because atomic coordinates are not included. <span class="tag">TO VERIFY</span></p>
  </div>
  <div class="pills" id="crystalPills" role="group" aria-label="Choose a structure"></div>
  <div class="two-col">
    <div class="card">
      <div class="canvas-wrap">
        <canvas id="crystalCanvas" class="viz" width="700" height="420" style="touch-action:none;cursor:grab"></canvas>
      </div>
    </div>
    <div class="card">
      <h3 style="margin-top:0" id="crName">Table salt</h3>
      <p id="crInfo" class="mono" style="font-size:0.9rem"></p>
      <p style="font-size:0.9rem;color:var(--muted)">Legend: purple = \(\mathrm{Na^+}\), green = \(\mathrm{Cl^-}\), grey = unit-cell corners only.</p>
    </div>
  </div>
</section>

<!-- ============ 05 SAMPLES ============ -->
<section id="samples">
  <div class="section-head">
    <div class="step"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>05 · Predictions</div>
    <h2>The five samples</h2>
    <p class="lede">Each sample with its crystal system and the behaviour we predicted before testing. Replace the placeholders with your photos.</p>
  </div>
  <div class="grid-samples">
    <div class="sample-card">
      <h3>Table salt (NaCl)</h3>
      <div class="meta">Cubic · <span class="pill dark">Stays dark</span></div>
      <p style="font-size:0.9rem"><strong>Literature (Nesse, Table C.3):</strong> \(n = 1.544\), isotropic.</p>
      <div class="placeholder" style="margin:0.4rem 0"><strong>PHOTO: Brightest</strong><code>images/salt_bright.jpg</code></div>
      <div class="placeholder" style="margin:0.4rem 0"><strong>PHOTO: Darkest</strong><code>images/salt_dark.jpg</code></div>
    </div>
    <div class="sample-card">
      <h3>Sugar (sucrose)</h3>
      <div class="meta">Monoclinic · <span class="pill bright">Brightens and darkens</span></div>
      <div class="placeholder" style="margin:0.4rem 0"><strong>PHOTO: Brightest</strong><code>images/sugar_bright.jpg</code></div>
      <div class="placeholder" style="margin:0.4rem 0"><strong>PHOTO: Darkest</strong><code>images/sugar_dark.jpg</code></div>
      <p style="font-size:0.9rem"><strong>Prediction to test:</strong> sucrose is also chiral. Thick grains may show a colour tint and incomplete extinction.</p>
    </div>
    <div class="sample-card">
      <h3>Copper sulphate</h3>
      <div class="meta">Triclinic · <span class="pill bright">Brightens and darkens</span></div>
      <div class="placeholder" style="margin:0.4rem 0"><strong>PHOTO: Brightest</strong><code>images/copper_bright.jpg</code></div>
      <div class="placeholder" style="margin:0.4rem 0"><strong>PHOTO: Darkest</strong><code>images/copper_dark.jpg</code></div>
      <p style="font-size:0.9rem">The crystals are strongly coloured, which may affect how dark the extinction looks.</p>
    </div>
    <div class="sample-card">
      <h3>Mica sheet</h3>
      <div class="meta">Monoclinic (muscovite) · <span class="pill bright">Brightens and darkens</span></div>
      <div class="placeholder" style="margin:0.4rem 0"><strong>PHOTO: Brightest</strong><code>images/mica_bright.jpg</code></div>
      <div class="placeholder" style="margin:0.4rem 0"><strong>PHOTO: Darkest</strong><code>images/mica_dark.jpg</code></div>
      <p style="font-size:0.9rem"><strong>Literature (Nesse, Table C.5):</strong> \(n_\alpha\) 1.552–1.580, \(n_\beta\) 1.582–1.620, \(n_\gamma\) 1.587–1.623; \(2V_x\) 30–47°, negative biaxial. <strong>Why it works as a plate:</strong> mica cleaves along its basal plane. Light along the sheet normal sees mainly the small in-plane birefringence (about 0.005), which is uniform across a cleaved sheet. <span class="tag">TO VERIFY</span></p>
    </div>
    <div class="sample-card">
      <h3>Glass slide</h3>
      <div class="meta">Amorphous · <span class="pill dark">Stays dark</span></div>
      <div class="placeholder" style="margin:0.4rem 0"><strong>PHOTO: Brightest</strong><code>images/glass_bright.jpg</code></div>
      <div class="placeholder" style="margin:0.4rem 0"><strong>PHOTO: Darkest</strong><code>images/glass_dark.jpg</code></div>
      <p style="font-size:0.9rem">No crystal lattice, so Neumann's principle applies differently. It is isotropic on average. Mechanical stress can make it birefringent, so use an unstressed slide.</p>
    </div>
  </div>
</section>

<!-- ============ 06 RESULTS ============ -->
<section id="results">
  <div class="section-head">
    <div class="step"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>06 · Results</div>
    <h2>Prediction vs observation</h2>
    <p class="lede">Each row compares the prediction with the observation over a full 360° rotation. Literature values are to be taken from the References and marked to verify. Fill in the blank cells after testing.</p>
  </div>
  <div class="table-wrap">
    <table>
      <thead>
        <tr>
          <th>Sample</th><th>Crystal system</th><th>Tensor prediction</th><th>Predicted behaviour</th>
          <th>Literature indices at 589 nm (Nesse, App. C)</th>
          <th>Observed (360°)</th><th>Extinctions / 360°</th><th>Match?</th><th>Notes</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>Table salt (NaCl)</td><td>Cubic</td><td>1 independent component, isotropic</td><td>Stays dark at all angles</td><td>\(n = 1.5441\) at 589 nm (CRC p. 10-249); Nesse gives 1.544 (Table C.3)</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td></tr>
        <tr><td>Sugar (sucrose)</td><td>Monoclinic</td><td>4 independent components</td><td>Brightens and darkens; possible colour tint</td><td>\(n_\alpha = 1.5376,\ n_\beta = 1.5651,\ n_\gamma = 1.5705\) at 589.3 nm (Feynman Vol. II, Table 32-2, p. 32-9)</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td></tr>
        <tr><td>Copper sulphate</td><td>Triclinic</td><td>6 independent components</td><td>Brightens and darkens</td><td>\(n_x = 1.5140,\ n_y = 1.5367,\ n_z = 1.5436\) at 589 nm (CRC p. 10-250)</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td></tr>
        <tr><td>Mica sheet</td><td>Monoclinic</td><td>4 independent components</td><td>Brightens and darkens</td><td>\(n_\alpha\) 1.552–1.580; \(n_\beta\) 1.582–1.620; \(n_\gamma\) 1.587–1.623 (Table C.5)</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td></tr>
        <tr><td>Glass slide</td><td>Amorphous (no lattice)</td><td>Isotropic, as for a cubic medium</td><td>Stays dark at all angles</td><td>Type K crown: \(n = 1.51314\) at 546.1 nm (CRC p. 10-252). Soda-lime slide not listed.</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td><td class="tbd">[to fill]</td></tr>
      </tbody>
    </table>
  </div>
  <div class="placeholder">
    <strong>OPTIONAL PHOTO: Brightest vs darkest comparison</strong>
    <div class="how">Save as <code>images/comparison.jpg</code>.</div>
  </div>
  <h3>What did not go as expected</h3>
  <div class="placeholder">
    <strong>TEXT NEEDED</strong>
    Describe one result that differed from the prediction, or write "none". Suggest a likely cause, such as sample thickness, a tilted holder or screen glare.
  </div>
</section>

<!-- ============ 07 CONCEPTS ============ -->
<section id="concepts">
  <div class="section-head">
    <div class="step"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>07 · Concept link</div>
    <h2>The ideas behind the results</h2>
  </div>
  <div class="two-col">
    <div>
      <div class="flip">
  <div class="flip-inner">
  <div class="face front card">
        <h3 style="margin-top:0">Neumann's principle</h3>
        <p>A physical property must have at least the symmetry of the crystal's point group. For the permittivity tensor, this limits the number of independent components.</p>
      
    <button class="flip-btn" type="button" aria-expanded="false">Explore sources</button>
  </div>
  <div class="face back">
    <div class="back-head"><span class="kicker">Explore further</span><h3>Neumann's principle</h3></div>
    <ul class="back-list">
      <li><span class="kind">Book</span> J. F. Nye, <em>Physical Properties of Crystals</em> (1985), Ch. I. <span class="tag">page numbers to verify</span></li>
      <li><span class="kind">Book</span> R. E. Newnham, <em>Properties of Materials</em> (2005), Ch. 4. <span class="tag">chapter to verify</span></li>
    </ul>
    <button class="flip-btn flip-back" type="button" aria-expanded="true">Flip back</button>
  </div>
  </div>
</div>
      <div class="flip">
  <div class="flip-inner">
  <div class="face front card">
        <h3 style="margin-top:0">Second-rank tensor properties</h3>
        <p>A symmetric tensor can be diagonalised by choosing principal axes. The square roots of its eigenvalues give the principal refractive indices.</p>
        <div class="equation">\[ D_i = \varepsilon_0 \varepsilon_{ij} E_j \qquad n_i = \sqrt{\varepsilon_{ii}} \]</div>
      
    <button class="flip-btn" type="button" aria-expanded="false">Explore sources</button>
  </div>
  <div class="face back">
    <div class="back-head"><span class="kicker">Explore further</span><h3>Second-rank tensor properties</h3></div>
    <ul class="back-list">
      <li><span class="kind">Book</span> R. P. Feynman, R. B. Leighton &amp; M. Sands, <em>Lectures on Physics</em>, Vol. II, Ch. 32, Table 32-2 (p. 32-9): three principal indices of sugar crystals at 589.3 nm.</li>
      <li><span class="kind">Book</span> W. D. Nesse, p. 11: the refractive index is quoted at 589 nm, the sodium line.</li>
    </ul>
    <button class="flip-btn flip-back" type="button" aria-expanded="true">Flip back</button>
  </div>
  </div>
</div>
      <div class="flip">
  <div class="flip-inner">
  <div class="face front card">
        <h3 style="margin-top:0">Crystal systems</h3>
        <p>Each system fixes which components are allowed, so the system alone tells us how many refractive indices to expect. That is how we predicted each sample before testing.</p>
      
    <button class="flip-btn" type="button" aria-expanded="false">Explore sources</button>
  </div>
  <div class="face back">
    <div class="back-head"><span class="kicker">Explore further</span><h3>Crystal systems</h3></div>
    <ul class="back-list">
      <li><span class="kind">Table</span> CRC Handbook, p. 10-248: hexagonal, rhombohedral and tetragonal crystals have two indices; orthorhombic, monoclinic and triclinic have three.</li>
      <li><span class="kind">Table</span> Nesse, Appendix C, Tables C.4 to C.6.</li>
    </ul>
    <button class="flip-btn flip-back" type="button" aria-expanded="true">Flip back</button>
  </div>
  </div>
</div>
    </div>
    <div class="flip">
  <div class="flip-inner">
  <div class="face front card">
      <h3 style="margin-top:0">The component race: why 45° is brightest</h3>
      <p>Linearly polarized light entering a birefringent plate splits into two components, along the fast and slow axes. At 45° they have equal amplitude. Inside the plate they drift apart by the phase difference \(\delta\). On exit:</p>
      <ul>
        <li><strong>\(\delta = 0\) or whole wavelengths:</strong> still linear, blocked by the analyser (dark).</li>
        <li><strong>\(\delta = 90^\circ\) (quarter-wave):</strong> circularly polarized, half the light passes.</li>
        <li><strong>\(\delta = 180^\circ\) (half-wave):</strong> polarization flipped by 90°, so it passes fully (bright).</li>
      </ul>
      <p>At 0° or 90° one component vanishes, so there is no race and the sample stays dark. This is why an anisotropic crystal goes dark four times per turn.</p>
      <h3>Linear birefringence vs optical activity</h3>
      <p>The samples here show linear birefringence, from anisotropy. Optical activity comes from chirality and rotates the polarization plane. Sucrose is both anisotropic and chiral, so it may show both. This is a prediction to test, not a measured result.</p>
      <div class="placeholder" style="margin-bottom:0">
        <strong>DIAGRAM (optional)</strong>
        Crossed-polarizer geometry with polarizer, sample and analyser axes. Save as <code>images/crossed_polarizer_diagram.png</code>.
      </div>
    
    <button class="flip-btn" type="button" aria-expanded="false">Explore sources</button>
  </div>
  <div class="face back">
    <div class="back-head"><span class="kicker">Explore further</span><h3>The component race</h3></div>
    <ul class="back-list">
      <li><span class="kind">Video</span> <a href="https://www.youtube.com/watch?v=8YkfEft4p-w" target="_blank" rel="noopener">Eugene Khutoryansky, Polarization of Light</a></li>
      <li><span class="kind">Video</span> <a href="https://www.youtube.com/watch?v=HH58VmUbOKM" target="_blank" rel="noopener">Khan Academy, Polarization of light, linear and circular</a></li>
      <li><span class="kind">Video</span> <a href="https://www.youtube.com/watch?v=975r9a7FMqc" target="_blank" rel="noopener">Steve Mould, Why Sugar Always Twists Light To The Right</a></li>
      <li><span class="kind">Book</span> M. Born &amp; E. Wolf, <em>Principles of Optics</em>, Ch. 15. <span class="tag">section to verify</span></li>
    </ul>
    <button class="flip-btn flip-back" type="button" aria-expanded="true">Flip back</button>
  </div>
  </div>
</div>
  </div>
</section>

<!-- ============ 08 QUIZ ============ -->
<section id="quiz">
  <div class="section-head">
    <div class="step"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>08 · Audience question</div>
    <h2>Test yourself</h2>
    <p class="lede">Try this before reading the answer. It is the same question shown to the class during peer learning.</p>
  </div>
  <div class="card">
    <p><strong>[Insert the question here, exactly as submitted to the TAs.]</strong></p>
    <div class="quiz-option"><span class="letter">A.</span> [Option A]</div>
    <div class="quiz-option"><span class="letter">B.</span> [Option B]</div>
    <div class="quiz-option"><span class="letter">C.</span> [Option C]</div>
    <div class="quiz-option"><span class="letter">D.</span> [Option D]</div>
  </div>
  <div class="placeholder">
    <strong>ANSWER REVEAL (optional)</strong>
    Add the correct answer and a one-sentence explanation after the presentation.
  </div>
</section>

<!-- ============ 09 REFERENCES ============ -->
<section id="references">
  <div class="section-head">
    <div class="step"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>09 · Sources</div>
    <h2>References</h2>
    <p><span class="tag">ALL ENTRIES TO VERIFY</span> Confirm each chapter, page and value before submitting. Page numbers are left blank until checked.</p>
  </div>
  <ol class="refs">
    <li>J. F. Nye, <em>Physical Properties of Crystals: Their Representation by Tensors and Matrices</em>, Oxford University Press (1985). Neumann's principle and tensor reduction: Ch. I. Crystal optics and the indicatrix: Ch. XIII. <span class="tag">pages to verify</span></li>
    <li>M. Born &amp; E. Wolf, <em>Principles of Optics</em>, 7th ed., Cambridge University Press (1999). Optics of crystals: Ch. 15. <span class="tag">sections to verify</span></li>
    <li>W. D. Nesse, <em>Introduction to Optical Mineralogy</em>, 4th ed., Oxford University Press (2012). Table C.3 (halite, isotropic) and Table C.5 (muscovite, negative biaxial). p. 11 defines n as the 589 nm value. Sucrose and chalcanthite are not listed. <span class="tag">Appendix C page numbers to verify</span></li>
    <li>R. E. Newnham, <em>Properties of Materials: Anisotropy, Symmetry, Structure</em>, Oxford University Press (2005). Symmetry and physical properties. <span class="tag">chapter to verify</span></li>
    <li>CRC Handbook of Chemistry and Physics, 97th ed. Section 10: Index of Refraction of Inorganic Crystals (pp. 10-248 to 10-251); Refractive Index and Transmittance of Representative Glasses (p. 10-252).</li>
    <li>R. P. Feynman, R. B. Leighton &amp; M. Sands, <em>The Feynman Lectures on Physics</em>, Vol. II, New Millennium Edition, Basic Books. Refractive index of sugar crystals: Table 32-2, p. 32-9 (values taken from the CRC Handbook).</li>
  </ol>
</section>

<!-- ============ 10 VIDEOS ============ -->
<section id="videos">
  <div class="section-head">
    <div class="step"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>10 · Watch</div>
    <h2>Videos</h2>
    <p class="lede">Suggested background videos for the class.</p>
  </div>
  <div class="two-col">
    <div class="card">
      <h3 style="margin-top:0">Polarization and optical rotation</h3>
      <ul>
        <li><strong>Steve Mould, Why Sugar Always Twists Light To The Right:</strong> <a href="https://www.youtube.com/watch?v=975r9a7FMqc">youtube.com/watch?v=975r9a7FMqc</a></li>
        <li><strong>Eugene Khutoryansky, Polarization of Light:</strong> <a href="https://www.youtube.com/watch?v=8YkfEft4p-w">youtube.com/watch?v=8YkfEft4p-w</a></li>
        <li><strong>Khan Academy, Polarization of light, linear and circular:</strong> <a href="https://www.youtube.com/watch?v=HH58VmUbOKM">youtube.com/watch?v=HH58VmUbOKM</a></li>
        <li><strong>Physics and animation, Polarization of light:</strong> <a href="https://www.youtube.com/watch?v=g6Ca0tqJoPc">youtube.com/watch?v=g6Ca0tqJoPc</a></li>
        <li><strong>Rainer Heintzmann, Polarization DoubleSpar:</strong> <a href="https://www.youtube.com/watch?v=JRskpTUKW3U">youtube.com/watch?v=JRskpTUKW3U</a></li>
      </ul>
    </div>
    <div class="card">
      <h3 style="margin-top:0">Optic axes, birefringence and waveplates</h3>
      <ul>
        <li><strong>Reumi's world, Optic Axis and Birefringence:</strong> <a href="https://www.youtube.com/watch?v=5GSgji6zf00">youtube.com/watch?v=5GSgji6zf00</a></li>
        <li><strong>Reumi's world, Polarizations and Waveplates:</strong> <a href="https://www.youtube.com/watch?v=Pm5aKYIOccc">youtube.com/watch?v=Pm5aKYIOccc</a></li>
        <li><strong>Andrew MacRae, Week 9b: Dichroism and Birefringence:</strong> <a href="https://www.youtube.com/watch?v=6bui1lTEbb0">youtube.com/watch?v=6bui1lTEbb0</a></li>
      </ul>
      <h3>Refractive index and why light slows down</h3>
      <ul>
        <li><strong>3Blue1Brown, Visualizing Feynman's lecture on the refractive index:</strong> <a href="https://www.youtube.com/watch?v=KTzGBJPuJwM">youtube.com/watch?v=KTzGBJPuJwM</a></li>
        <li><strong>3Blue1Brown, The barber pole effect:</strong> <a href="https://www.youtube.com/watch?v=QCX62YJCmGk">youtube.com/watch?v=QCX62YJCmGk</a></li>
        <li><strong>Short summary of why wiggling electrons slow light:</strong> <a href="https://www.youtube.com/watch?v=XIW-2ykgVPI">youtube.com/watch?v=XIW-2ykgVPI</a></li>
        <li><strong>Looking Glass Universe, I don't know why light slows down in water:</strong> <a href="https://www.youtube.com/watch?v=uo3ds0FVpXs">youtube.com/watch?v=uo3ds0FVpXs</a></li>
        <li><strong>Follow-up Q&amp;A on refraction:</strong> <a href="https://www.youtube.com/watch?v=Cz4Q4QOuoo8">youtube.com/watch?v=Cz4Q4QOuoo8</a> and <a href="https://www.youtube.com/watch?v=DWnb2UUlqd0">youtube.com/watch?v=DWnb2UUlqd0</a></li>
      </ul>
      <h3>Malus's law and polarization states</h3>
      <ul>
        <li><strong>3Blue1Brown and MinutePhysics, Some light quantum mechanics:</strong> <a href="https://www.youtube.com/watch?v=MzRCDLre1b4">youtube.com/watch?v=MzRCDLre1b4</a></li>
        <li><strong>MinutePhysics, Bell's Theorem:</strong> <a href="https://www.youtube.com/watch?v=zcqZHYo7ONs">youtube.com/watch?v=zcqZHYo7ONs</a></li>
      </ul>
    </div>
  </div>
</section>

<!-- ============ 11 DOWNLOADS ============ -->
<section id="downloads">
  <div class="section-head">
    <div class="step"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>11 · Files</div>
    <h2>Downloads</h2>
  </div>
  <div class="card">
    <ul>
      <li><strong>Slides (PDF):</strong> <span class="mono">G[number]_[short_title].pdf</span></li>
      <li><strong>One-page summary (A4 PDF):</strong> <span class="mono">G[number]_[short_title]_summary.pdf</span></li>
    </ul>
  </div>
  <div class="placeholder">
    <strong>LINKS NEEDED</strong>
    Replace each filename with a working link once uploaded. Example: <code>G07_PolarizationSymmetry.pdf</code>.
  </div>
</section>

<!-- ============ 12 TEAM ============ -->
<section id="team">
  <div class="section-head">
    <div class="step"><svg class="motif" aria-hidden="true"><use href="#pol-motif"/></svg>12 · Group</div>
    <h2>Team · Group 10</h2>
  </div>
  <div class="two-col">
    <div class="card">
      <h3 style="margin-top:0">Group members</h3>
      <ul>
        <li>Aaditya Vichare (25b2444)</li>
        <li>Anjali Sinha (25b2427)</li>
        <li>Aryan Prasad (25b2493)</li>
        <li>Kaivalya Nimke (25b2423)</li>
        <li>Kunisetty Karthik (25b2403)</li>
        <li>Kushagra Raghuvanshi (25b2451)</li>
        <li>Lakshya Singh (25b2414)</li>
        <li>Praneesh S (25b2461)</li>
      </ul>
    </div>
    <div class="card">
      <h3 style="margin-top:0">TA guide</h3>
      <p>Sukhamoy</p>
    </div>
  </div>
</section>

</main>

<footer>
  MM 219 · Group 10 · Supplementary site · Crossed polarizers and Neumann's principle
</footer>

<script>

(function () {
  var c = document.getElementById('heroWave');
  if (!c) return;
  var ctx = c.getContext('2d');
  var reduce = window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  function size() {
    var r = c.getBoundingClientRect(), dpr = window.devicePixelRatio || 1;
    c.width = r.width * dpr; c.height = r.height * dpr;
    ctx.setTransform(dpr, 0, 0, dpr, 0, 0);
  }
  size();
  window.addEventListener('resize', size);
  var t0 = null;
  function frame(ts) {
    if (t0 === null) t0 = ts;
    var t = reduce ? 0 : (ts - t0) / 1000;
    var w = c.clientWidth, h = c.clientHeight;
    ctx.clearRect(0, 0, w, h);
    var cy = h * 0.62, amp = Math.min(h * 0.28, 120), scale = 1.0;
    var k = 2 * Math.PI / (w * 0.22), omega = 2 * Math.PI * 0.35;
    var ox = -40, oz = 0.42;
    function P(s) {
      var phi = k * s - omega * t;
      var ex = Math.cos(phi), ey = Math.sin(phi) * 0.6;
      var X = s + ox + oz * ey * amp * 0.0, Y = cy - ex * amp * 0.55;
      var Z = ey * amp;
      return { x: X + Z * 0.35, y: Y - Z * 0.22 };
    }
    ctx.strokeStyle = 'rgba(255,255,255,0.9)';
    ctx.lineWidth = 2;
    ctx.beginPath();
    for (var s = -40; s <= w + 40; s += 4) {
      var q = P(s);
      if (s === -40) ctx.moveTo(q.x, q.y); else ctx.lineTo(q.x, q.y);
    }
    ctx.stroke();
    ctx.strokeStyle = 'rgba(255,255,255,0.45)';
    ctx.lineWidth = 1.2;
    for (var s2 = 0; s2 <= w; s2 += w / 14) {
      var q2 = P(s2), base = { x: s2 + 0.35 * 0, y: cy };
      ctx.beginPath(); ctx.moveTo(base.x, base.y); ctx.lineTo(q2.x, q2.y); ctx.stroke();
    }
    ctx.strokeStyle = 'rgba(255,255,255,0.35)';
    ctx.beginPath(); ctx.moveTo(0, cy); ctx.lineTo(w, cy); ctx.stroke();
    if (!reduce) requestAnimationFrame(frame);
  }
  requestAnimationFrame(frame);
})();

(function () {
  /* ---------- helpers ---------- */
  function makePills(container, items, onPick, initialKey) {
    items.forEach(function (it) {
      var b = document.createElement('button');
      b.type = 'button';
      b.className = 'pill-btn';
      b.textContent = it.label;
      b.setAttribute('aria-pressed', it.key === initialKey ? 'true' : 'false');
      b.addEventListener('click', function () {
        Array.prototype.forEach.call(container.children, function (c) { c.setAttribute('aria-pressed', 'false'); });
        b.setAttribute('aria-pressed', 'true');
        onPick(it.key);
      });
      container.appendChild(b);
    });
  }

  /* ---------- Expected-behaviour animation ---------- */
  var SAMPLES = {
    salt:   { name: 'Table salt (NaCl), cubic', delta: 0, note: 'Stays dark at every angle.', dark: 'all' },
    sugar:  { name: 'Sugar (sucrose), monoclinic', delta: 3.2, note: 'Four dark and four bright positions per turn.', dark: '4' },
    copper: { name: 'Copper sulphate, triclinic', delta: 2.6, note: 'Four dark and four bright positions per turn.', dark: '4' },
    mica:   { name: 'Mica sheet, monoclinic', delta: 3.8, note: 'Four sharp extinctions per turn.', dark: '4' },
    glass:  { name: 'Glass slide, amorphous', delta: 0, note: 'Stays dark at every angle.', dark: 'all' }
  };
  var cur = 'salt', theta = 0, playing = true, lastTs = null;
  var acv = document.getElementById('animCanvas');
  var actx = acv.getContext('2d');
  var slider = document.getElementById('animAngle');
  var btn = document.getElementById('animPlay');
  var rdTheta = document.getElementById('rdTheta');
  var rdBright = document.getElementById('rdBright');
  var rdDelta = document.getElementById('rdDelta');
  var rdExt = document.getElementById('rdExt');
  var rdStatus = document.getElementById('rdStatus');

  function inten(deg, delta) {
    var t = deg * Math.PI / 180;
    return Math.pow(Math.sin(2 * t), 2) * Math.pow(Math.sin(delta / 2), 2);
  }

  function drawAnim() {
    var W = acv.width, H = acv.height;
    actx.clearRect(0, 0, W, H);
    var s = SAMPLES[cur], b = inten(theta, s.delta), g = Math.round(255 * b);
    actx.fillStyle = 'rgb(' + g + ',' + g + ',' + g + ')';
    actx.fillRect(30, 50, 200, 200);
    actx.strokeStyle = '#888'; actx.lineWidth = 1; actx.strokeRect(30, 50, 200, 200);
    actx.fillStyle = '#888'; actx.font = '14px system-ui, sans-serif';
    actx.fillText('Screen brightness', 30, 36);
    var cx = 130, cy = 150, r = 85, a = theta * Math.PI / 180;
    actx.strokeStyle = '#5b3fd6'; actx.lineWidth = 3;
    actx.beginPath();
    actx.moveTo(cx - r * Math.cos(a), cy + r * Math.sin(a));
    actx.lineTo(cx + r * Math.cos(a), cy - r * Math.sin(a));
    actx.stroke();
    var px = 290, py = 50, pw = 380, ph = 200;
    actx.fillStyle = '#888';
    actx.fillText('Relative intensity vs sample angle', px, 36);
    actx.strokeStyle = '#888'; actx.lineWidth = 1; actx.strokeRect(px, py, pw, ph);
    actx.strokeStyle = '#5b3fd6'; actx.lineWidth = 2;
    actx.beginPath();
    for (var i = 0; i <= 360; i += 2) {
      var x = px + pw * i / 360, y = py + ph * (1 - inten(i, s.delta));
      if (i === 0) actx.moveTo(x, y); else actx.lineTo(x, y);
    }
    actx.stroke();
    actx.fillStyle = '#b03a2e';
    actx.beginPath();
    actx.arc(px + pw * theta / 360, py + ph * (1 - b), 6, 0, 2 * Math.PI);
    actx.fill();
    actx.fillStyle = '#888';
    actx.fillText('0°', px, py + ph + 18);
    actx.fillText('180°', px + pw / 2 - 14, py + ph + 18);
    actx.fillText('360°', px + pw - 30, py + ph + 18);

    rdTheta.textContent = Math.round(theta) + '°';
    rdBright.textContent = b.toFixed(2);
    rdDelta.textContent = s.delta.toFixed(1) + ' rad';
    rdExt.textContent = s.dark === 'all' ? 'all angles' : '4';
    rdStatus.textContent = s.name + '. ' + s.note;
  }

  function loopAnim(ts) {
    if (lastTs !== null && playing) {
      theta = (theta + (ts - lastTs) * 0.04) % 360;
      slider.value = Math.round(theta);
    }
    lastTs = ts;
    drawAnim();
    requestAnimationFrame(loopAnim);
  }

  makePills(document.getElementById('animPills'), [
    { key: 'salt', label: 'Table salt' },
    { key: 'sugar', label: 'Sugar' },
    { key: 'copper', label: 'Copper sulphate' },
    { key: 'mica', label: 'Mica' },
    { key: 'glass', label: 'Glass' }
  ], function (k) { cur = k; drawAnim(); }, 'salt');

  slider.addEventListener('input', function () { theta = Number(slider.value); drawAnim(); });
  btn.addEventListener('click', function () {
    playing = !playing;
    btn.textContent = playing ? 'Pause' : 'Play';
    btn.setAttribute('aria-pressed', playing ? 'true' : 'false');
    lastTs = null;
  });
  requestAnimationFrame(loopAnim);

  /* ---------- 3D crystal structure viewer ---------- */
  var CRYSTALS = {
    nacl: { name: 'Table salt (NaCl)', detail: 'Rock-salt structure, \\(2\\times2\\times2\\) unit cells. \\(a = b = c = 5.64\\ \\text{Å}\\), \\(\\alpha = \\beta = \\gamma = 90^\\circ\\). Approximate; to verify.', p: [5.64, 5.64, 5.64, 90, 90, 90], rocksalt: true },
    sucrose: { name: 'Sugar (sucrose)', detail: 'Monoclinic unit-cell shape only. Approximate cell parameters, to verify against a crystallography database.', p: [10.86, 8.71, 7.76, 90, 102.9, 90] },
    cuso4: { name: 'Copper sulphate', detail: 'Triclinic unit-cell shape only. Approximate cell parameters, to verify against a crystallography database.', p: [6.12, 10.7, 5.98, 82.3, 107.4, 102.6] },
    mica: { name: 'Muscovite mica', detail: 'Monoclinic unit-cell shape only. Approximate cell parameters, to verify against a crystallography database.', p: [5.19, 9.03, 20.1, 90, 95.8, 90] }
  };
  var ROCKSALT = [
    [0, 0, 0, 0], [0.5, 0.5, 0, 0], [0.5, 0, 0.5, 0], [0, 0.5, 0.5, 0],
    [0.5, 0, 0, 1], [0, 0.5, 0, 1], [0, 0, 0.5, 1], [0.5, 0.5, 0.5, 1]
  ];

  function latticeVecs(p, mult) {
    var a = p[0], b = p[1], c = p[2];
    var d = Math.PI / 180;
    var ca = Math.cos(p[3] * d), cb = Math.cos(p[4] * d), cg = Math.cos(p[5] * d), sg = Math.sin(p[5] * d);
    var cz = (ca - cb * cg) / sg;
    var a1 = [a, 0, 0];
    var a2 = [b * cg, b * sg, 0];
    var a3 = [c * cb, c * cz, c * Math.sqrt(Math.max(0, 1 - cb * cb - cz * cz))];
    return [a1, a2, a3].map(function (v) { return v.map(function (x) { return x * mult; }); });
  }

  function buildScene(key) {
    var c = CRYSTALS[key];
    var V = latticeVecs(c.p, c.rocksalt ? 2 : 1);
    function cart(u, v, w) {
      return [0, 1, 2].map(function (k) { return u * V[0][k] + v * V[1][k] + w * V[2][k]; });
    }
    var corners = [];
    [0, 1].forEach(function (u) {
      [0, 1].forEach(function (v) {
        [0, 1].forEach(function (w) { corners.push([u, v, w]); });
      });
    });
    var cp = corners.map(function (f) { return cart(f[0], f[1], f[2]); });
    var g = [0, 1, 2].map(function (k) {
      return cp.reduce(function (s, q) { return s + q[k]; }, 0) / 8;
    });
    var m = 0;
    cp.forEach(function (q) {
      [0, 1, 2].forEach(function (k) { m = Math.max(m, Math.abs(q[k] - g[k])); });
    });
    function norm(q) { return q.map(function (x, k) { return (x - g[k]) / m; }); }

    var edges = [];
    for (var i = 0; i < 8; i++) {
      for (var j = i + 1; j < 8; j++) {
        var diff = 0;
        for (var k = 0; k < 3; k++) if (corners[i][k] !== corners[j][k]) diff++;
        if (diff === 1) edges.push([i, j]);
      }
    }
    var atoms = [];
    if (c.rocksalt) {
      for (var ii = 0; ii < 2; ii++) {
        for (var jj = 0; jj < 2; jj++) {
          for (var kk = 0; kk < 2; kk++) {
            ROCKSALT.forEach(function (q) {
              atoms.push({ p: norm(cart((ii + q[0]) / 2, (jj + q[1]) / 2, (kk + q[2]) / 2)), t: q[3] });
            });
          }
        }
      }
    } else {
      cp.forEach(function (q) { atoms.push({ p: norm(q), t: 2 }); });
    }
    return { corners: cp.map(norm), edges: edges, atoms: atoms };
  }

  var scv = document.getElementById('crystalCanvas');
  var sx = scv.getContext('2d');
  var crName = document.getElementById('crName');
  var crInfo = document.getElementById('crInfo');
  var geo = null;
  var rx = -0.35, ry = 0.6, zoom = 1, dragging = false, lx = 0, ly = 0;

  function proj(p) {
    var x = p[0], y = p[1], z = p[2];
    var cy = Math.cos(ry), sy = Math.sin(ry);
    var x1 = x * cy + z * sy, z1 = -x * sy + z * cy;
    var cxr = Math.cos(rx), sxr = Math.sin(rx);
    var y2 = y * cxr - z1 * sxr, z2 = y * sxr + z1 * cxr;
    var k = 4 / (4 + z2);
    return { x: scv.width / 2 + x1 * k * 160 * zoom, y: scv.height / 2 - y2 * k * 160 * zoom, z: z2 };
  }

  function drawCrystal() {
    var W = scv.width, H = scv.height;
    sx.clearRect(0, 0, W, H);
    sx.strokeStyle = '#888'; sx.lineWidth = 2;
    geo.edges.forEach(function (e) {
      var A = proj(geo.corners[e[0]]), B = proj(geo.corners[e[1]]);
      sx.beginPath(); sx.moveTo(A.x, A.y); sx.lineTo(B.x, B.y); sx.stroke();
    });
    var pts = geo.atoms.map(function (at) { return { t: at.t, q: proj(at.p) }; });
    pts.sort(function (A, B) { return B.q.z - A.q.z; });
    pts.forEach(function (at) {
      var col = at.t === 0 ? '#5b3fd6' : (at.t === 1 ? '#1f7a4d' : '#999');
      var rad = (at.t === 2 ? 5 : 9) * (4 / (4 + at.q.z));
      sx.beginPath(); sx.arc(at.q.x, at.q.y, rad, 0, 2 * Math.PI);
      sx.fillStyle = col; sx.fill();
    });
    sx.fillStyle = '#888'; sx.font = '14px system-ui, sans-serif';
    sx.fillText('Drag to rotate, scroll to zoom', 16, H - 16);
  }

  function loopCrystal() {
    if (!dragging) ry += 0.004;
    drawCrystal();
    requestAnimationFrame(loopCrystal);
  }

  function setCrystal(k) {
    geo = buildScene(k);
    crName.textContent = CRYSTALS[k].name;
    crInfo.innerHTML = CRYSTALS[k].detail;
    if (window.MathJax && MathJax.typesetPromise) { MathJax.typesetPromise([crInfo]); }
  }

  makePills(document.getElementById('crystalPills'), [
    { key: 'nacl', label: 'Table salt (NaCl)' },
    { key: 'sucrose', label: 'Sugar (sucrose)' },
    { key: 'cuso4', label: 'Copper sulphate' },
    { key: 'mica', label: 'Muscovite mica' }
  ], setCrystal, 'nacl');

  scv.addEventListener('pointerdown', function (e) {
    dragging = true; lx = e.clientX; ly = e.clientY;
    scv.setPointerCapture(e.pointerId);
    scv.style.cursor = 'grabbing';
  });
  scv.addEventListener('pointermove', function (e) {
    if (!dragging) return;
    ry += (e.clientX - lx) * 0.01;
    rx += (e.clientY - ly) * 0.01;
    lx = e.clientX; ly = e.clientY;
  });
  function endDrag() { dragging = false; scv.style.cursor = 'grab'; }
  scv.addEventListener('pointerup', endDrag);
  scv.addEventListener('pointercancel', endDrag);
  scv.addEventListener('wheel', function (e) {
    e.preventDefault();
    zoom = Math.min(2.5, Math.max(0.5, zoom * (e.deltaY < 0 ? 1.08 : 0.92)));
  }, { passive: false });

  setCrystal('nacl');
  requestAnimationFrame(loopCrystal);
})();
</script>

<script>
(function () {
  var doc = document.documentElement;
  doc.classList.add('js');
  var reduce = window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches;

  /* Scroll reveals */
  var targets = document.querySelectorAll('main section, main .card, main .sample-card, main .placeholder, main .callout');
  Array.prototype.forEach.call(targets, function (el, i) {
    el.classList.add('reveal');
    el.style.transitionDelay = ((i % 3) * 70) + 'ms';
  });
  if (reduce || !('IntersectionObserver' in window)) {
    Array.prototype.forEach.call(targets, function (el) { el.classList.add('in'); });
  } else {
    var io = new IntersectionObserver(function (entries) {
      entries.forEach(function (e) {
        if (e.isIntersecting) { e.target.classList.add('in'); io.unobserve(e.target); }
      });
    }, { threshold: 0.12, rootMargin: '0px 0px -40px 0px' });
    Array.prototype.forEach.call(targets, function (el) { io.observe(el); });
  }

  /* Reading progress and header shadow */
  var bar = document.getElementById('progress');
  var header = document.querySelector('header.topbar');
  function onScroll() {
    var max = doc.scrollHeight - window.innerHeight;
    var pct = max > 0 ? (window.scrollY / max) * 100 : 0;
    bar.style.width = pct + '%';
    header.classList.toggle('scrolled', window.scrollY > 8);
  }
  window.addEventListener('scroll', onScroll, { passive: true });
  onScroll();

  /* Count-up for hero stat chips */
  if (!reduce) {
    var nums = document.querySelectorAll('.chip .n');
    Array.prototype.forEach.call(nums, function (el) {
      var target = parseInt(el.textContent, 10);
      if (isNaN(target)) return;
      var start = null, dur = 900;
      el.textContent = '0';
      function step(ts) {
        if (start === null) start = ts;
        var t = Math.min(1, (ts - start) / dur);
        el.textContent = Math.round(target * (1 - Math.pow(1 - t, 3)));
        if (t < 1) requestAnimationFrame(step);
      }
      setTimeout(function () { requestAnimationFrame(step); }, 400);
    });
  }
})();
</script>

<script>
(function () {
  var flips = document.querySelectorAll('.flip');
  Array.prototype.forEach.call(flips, function (f) {
    var front = f.querySelector('.face.front');
    var back = f.querySelector('.face.back');
    back.inert = true;
    f.addEventListener('click', function (e) {
      var btn = e.target.closest('.flip-btn');
      if (!btn) return;
      var on = !f.classList.contains('flipped');
      f.classList.toggle('flipped', on);
      front.inert = on;
      back.inert = !on;
      var frontBtn = front.querySelector('.flip-btn');
      frontBtn.setAttribute('aria-expanded', on ? 'true' : 'false');
      if (!on) frontBtn.focus({ preventScroll: true });
      else back.querySelector('.flip-back').focus({ preventScroll: true });
    });
  });
})();
</script>
</body>
</html>
