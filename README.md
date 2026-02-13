<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Welcome</title>
  <style>
    :root {
      --bg: #0b0f1a;
      --card: rgba(255, 255, 255, 0.06);
      --border: rgba(255, 255, 255, 0.12);
      --glow: 0 0 40px rgba(99, 102, 241, 0.25);
      --accent: #6366f1;
      --accent2: #22d3ee;
      --text: #e5e7eb;
      --muted: #9ca3af;
    }

    * { box-sizing: border-box; }
    html, body { height: 100%; }
    body {
      margin: 0;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial;
      background:
        radial-gradient(1200px 600px at 20% 10%, rgba(34,211,238,.15), transparent 40%),
        radial-gradient(900px 500px at 80% 20%, rgba(99,102,241,.18), transparent 45%),
        radial-gradient(700px 400px at 50% 90%, rgba(236,72,153,.12), transparent 45%),
        var(--bg);
      color: var(--text);
      overflow: hidden;
    }

    .noise {
      pointer-events: none;
      position: fixed;
      inset: 0;
      background: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='140' height='140'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='0.8' numOctaves='2'/></filter><rect width='100%' height='100%' filter='url(%23n)' opacity='0.04'/></svg>");
      mix-blend-mode: overlay;
    }

    .orbs span {
      position: absolute;
      width: 280px;
      height: 280px;
      filter: blur(40px);
      opacity: .35;
      animation: float 16s ease-in-out infinite alternate;
      border-radius: 50%;
    }
    .orbs .a { background: #6366f1; left: 10%; top: 20%; animation-delay: 0s; }
    .orbs .b { background: #22d3ee; right: 10%; top: 10%; animation-delay: 2s; }
    .orbs .c { background: #ec4899; left: 50%; bottom: 10%; animation-delay: 4s; }

    @keyframes float {
      0% { transform: translateY(0) translateX(0) scale(1); }
      100% { transform: translateY(-30px) translateX(20px) scale(1.1); }
    }

    .wrap {
      position: relative;
      height: 100%;
      display: grid;
      place-items: center;
      padding: 24px;
    }

    .card {
      position: relative;
      max-width: 720px;
      width: 100%;
      padding: 48px 40px;
      border-radius: 24px;
      background: linear-gradient(180deg, rgba(255,255,255,.08), rgba(255,255,255,.02)) , var(--card);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      border: 1px solid var(--border);
      box-shadow: var(--glow), inset 0 1px 0 rgba(255,255,255,.08);
      animation: enter 900ms cubic-bezier(.2,.9,.2,1) both;
    }

    @keyframes enter {
      from { opacity: 0; transform: translateY(16px) scale(.98); }
      to   { opacity: 1; transform: translateY(0) scale(1); }
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 8px 12px;
      border-radius: 999px;
      border: 1px solid var(--border);
      background: rgba(255,255,255,.06);
      color: var(--muted);
      font-size: 12px;
      letter-spacing: .08em;
      text-transform: uppercase;
    }

    .title {
      margin: 18px 0 6px;
      font-size: clamp(36px, 6vw, 56px);
      line-height: 1.05;
      letter-spacing: -0.02em;
      background: linear-gradient(90deg, #fff, #c7d2fe 40%, #67e8f9 80%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .subtitle {
      color: var(--muted);
      max-width: 52ch;
      font-size: 16px;
      line-height: 1.6;
    }

    .cta {
      margin-top: 28px;
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }

    .btn {
      position: relative;
      border: 1px solid var(--border);
      background: rgba(255,255,255,.06);
      color: var(--text);
      padding: 12px 16px;
      border-radius: 12px;
      cursor: pointer;
      transition: transform .15s ease, box-shadow .15s ease, border-color .15s ease;
      overflow: hidden;
    }
    .btn.primary {
      border-color: transparent;
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      box-shadow: 0 10px 30px rgba(99,102,241,.35);
    }
    .btn:hover { transform: translateY(-1px); box-shadow: 0 12px 40px rgba(0,0,0,.35); }
    .btn:active { transform: translateY(0); }

    .scanline {
      position: absolute;
      inset: 0;
      background: linear-gradient(transparent 49%, rgba(255,255,255,.04) 50%, transparent 51%);
      background-size: 100% 6px;
      mix-blend-mode: overlay;
      opacity: .25;
      pointer-events: none;
    }

    .grid {
      position: fixed;
      inset: 0;
      background:
        linear-gradient(transparent 95%, rgba(255,255,255,.04) 96%) 0 0 / 100% 28px,
        linear-gradient(90deg, transparent 95%, rgba(255,255,255,.04) 96%) 0 0 / 28px 100%;
      opacity: .25;
      pointer-events: none;
    }

    footer {
      position: fixed;
      bottom: 16px;
      width: 100%;
      text-align: center;
      color: #9ca3af;
      font-size: 12px;
      opacity: .7;
    }
  </style>
</head>
<body>
  <div class="grid"></div>
  <div class="orbs">
    <span class="a"></span>
    <span class="b"></span>
    <span class="c"></span>
  </div>
  <div class="noise"></div>

  <main class="wrap">
    <section class="card">
      <span class="badge">WELCOME</span>
      <h1 class="title">Enter the Lab</h1>
      <p class="subtitle">
        A modern, minimal landing. Clean motion. Subtle glow. Zero noise.
      </p>
      <div class="cta">
        <button class="btn primary" onclick="pulse()">Explore</button>
        <button class="btn" onclick="toggleGrid()">Toggle Grid</button>
      </div>
      <div class="scanline"></div>
    </section>
  </main>

  <footer>© Modern Welcome</footer>

  <script>
    const grid = document.querySelector('.grid');

    function toggleGrid() {
      grid.style.display = grid.style.display === 'none' ? 'block' : 'none';
    }

    function pulse() {
      const card = document.querySelector('.card');
      card.animate([
        { boxShadow: getComputedStyle(card).boxShadow },
        { boxShadow: '0 0 80px rgba(34,211,238,.6)' },
        { boxShadow: getComputedStyle(card).boxShadow }
      ], { duration: 600, easing: 'ease-out' });
    }
  </script>
</body>
</html>
