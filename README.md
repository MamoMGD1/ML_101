<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>ML_101 • Open Learning Journey</title>
  <!-- Fonts & Icons -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css" integrity="sha512-SnH5WK+bZxgPHs44uWIX+LLJAJ9/2PkfF6rW0E8DhiL1ZsV1MZ9YxFvG6v7Qw4Qf7qX8C0t3bS8JrjV+LQe5xg==" crossorigin="anonymous" referrerpolicy="no-referrer" />
  <style>
    :root{
      --bg: #0b0f16;
      --bg-accent: #0f1521;
      --card: #121a27;
      --card-2: #0e1624;
      --text: #e6edf3;
      --muted: #9fb0c2;
      --brand: #7cacf8;
      --brand-2: #8b5cf6;
      --ok: #4ade80;
      --warn: #f59e0b;
      --danger: #ef4444;
      --ring: rgba(124,172,248,.25);
      --shadow: 0 10px 30px rgba(0,0,0,.35);
      --radius-xl: 22px;
      --radius-lg: 16px;
    }
    *{box-sizing:border-box}
    html,body{margin:0;padding:0;background:radial-gradient(1200px 800px at 10% -10%, rgba(124,172,248,.08), transparent 50%), radial-gradient(800px 600px at 100% 0%, rgba(139,92,246,.08), transparent 40%), var(--bg);color:var(--text);font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial,"Noto Sans",sans-serif;}
    a{color:var(--brand);text-decoration:none}
    a:hover{opacity:.95}
    .wrapper{max-width:1100px;margin:0 auto;padding:28px}

    /* Hero */
    .hero{margin:24px 0 28px;display:grid;grid-template-columns:1.3fr 1fr;gap:24px;align-items:center}
    .hero-card{background:linear-gradient(180deg, rgba(20,27,41,.8), rgba(14,22,36,.85));border:1px solid rgba(255,255,255,.06);box-shadow:var(--shadow);border-radius:var(--radius-xl);padding:28px;position:relative;overflow:hidden}
    .hero h1{font-size:44px;line-height:1.05;margin:0 0 10px;letter-spacing:.2px}
    .hero p.lead{font-size:17px;color:var(--muted);margin:0 0 18px}

    .chipbar{display:flex;flex-wrap:wrap;gap:10px;margin:8px 0 20px}
    .chip{display:inline-flex;align-items:center;gap:8px;padding:8px 12px;border-radius:999px;background:rgba(124,172,248,.08);border:1px solid rgba(124,172,248,.25);color:#cfe0ff;font-weight:600;font-size:12px}
    .chip i{font-size:13px;opacity:.9}

    .cta{display:flex;flex-wrap:wrap;gap:12px}
    .btn{display:inline-flex;align-items:center;gap:10px;padding:12px 16px;border-radius:12px;border:1px solid rgba(255,255,255,.08);background:linear-gradient(180deg, rgba(124,172,248,.18), rgba(124,172,248,.12));backdrop-filter: blur(4px);color:#eaf2ff;font-weight:700;letter-spacing:.2px;transition:transform .12s ease, box-shadow .12s ease}
    .btn:hover{transform:translateY(-1px);box-shadow:0 10px 16px var(--ring)}
    .btn.secondary{background:linear-gradient(180deg, rgba(139,92,246,.18), rgba(139,92,246,.12));}
    .btn.ghost{background:rgba(255,255,255,.03)}

    .hero-side{display:grid;gap:12px}
    .stat{background:linear-gradient(180deg, rgba(18,26,39,.9), rgba(14,22,36,.9));border:1px solid rgba(255,255,255,.06);border-radius:18px;padding:16px 18px;display:flex;align-items:center;gap:14px}
    .stat i{font-size:18px;color:#cfe0ff}
    .stat strong{font-size:14px}
    .stat span{color:var(--muted);font-size:13px}

    /* Grid sections */
    .grid{display:grid;grid-template-columns:repeat(12,1fr);gap:20px;margin:26px 0}
    .card{grid-column:span 12;background:linear-gradient(180deg, rgba(16,23,35,.6), rgba(12,18,29,.75));border:1px solid rgba(255,255,255,.06);border-radius:var(--radius-lg);padding:22px;box-shadow:var(--shadow)}
    .card h2{margin:0 0 12px;font-size:22px}
    .card p{color:var(--muted);margin:8px 0}

    .twocol .card{grid-column:span 6}
    .threecol .card{grid-column:span 4}

    /* Lists */
    ul.clean{list-style:none;padding:0;margin:10px 0}
    ul.clean li{padding:8px 0;display:flex;gap:12px;align-items:flex-start}
    ul.clean li i{opacity:.9;margin-top:2px}

    /* Roadmap */
    .roadmap{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:14px}
    .step{background:linear-gradient(180deg, rgba(19,28,43,.6), rgba(13,19,31,.8));border:1px solid rgba(255,255,255,.06);border-radius:14px;padding:14px}
    .step .meta{display:flex;justify-content:space-between;align-items:center;margin-bottom:6px}
    .badge{display:inline-flex;align-items:center;gap:6px;font-size:11px;padding:6px 10px;border-radius:999px;background:rgba(74,222,128,.1);border:1px solid rgba(74,222,128,.35);color:#b7f7c9;font-weight:700}
    .badge.wip{background:rgba(245,158,11,.08);border-color:rgba(245,158,11,.35);color:#ffe1a8}
    .badge.todo{background:rgba(255,255,255,.04);border-color:rgba(255,255,255,.08);color:#c8d6e5}

    details{border:1px solid rgba(255,255,255,.06);background:linear-gradient(180deg, rgba(16,23,35,.5), rgba(13,19,31,.65));border-radius:12px;padding:14px}
    details summary{cursor:pointer;font-weight:700}

    /* Footer */
    footer{margin:40px 0 10px;color:var(--muted);font-size:13px;display:flex;flex-wrap:wrap;gap:8px;justify-content:space-between;align-items:center}
    .social{display:flex;gap:10px}
    .social a{display:inline-flex;align-items:center;justify-content:center;width:36px;height:36px;border-radius:12px;background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.06)}

    /* Responsive */
    @media (max-width: 920px){
      .hero{grid-template-columns:1fr}
      .twocol .card{grid-column:span 12}
      .threecol .card{grid-column:span 12}
      .roadmap{grid-template-columns:1fr}
    }
  </style>
</head>
<body>
  <div class="wrapper">
    <!-- HERO -->
    <section class="hero">
      <div class="hero-card">
        <div class="chipbar">
          <span class="chip"><i class="fa-solid fa-code"></i> Built from Scratch</span>
          <span class="chip"><i class="fa-solid fa-scale-balanced"></i> Math-First</span>
          <span class="chip"><i class="fa-solid fa-rocket"></i> Beginner-Friendly</span>
          <span class="chip"><i class="fa-solid fa-handshake-angle"></i> Open to Contributions</span>
        </div>
        <h1>ML_101 — Open Learning Journey</h1>
        <p class="lead">An open-source, community-driven course to learn Machine Learning step by step — with the math, intuition, and code <em>built from first principles</em>. The goal isn’t to just run a model, but to understand why it works.</p>
        <div class="cta">
          <a class="btn" href="#getting-started"><i class="fa-solid fa-play"></i> Start Here</a>
          <a class="btn secondary" href="#roadmap"><i class="fa-solid fa-route"></i> Roadmap</a>
          <a class="btn ghost" href="#contribute"><i class="fa-solid fa-people-group"></i> Contribute</a>
        </div>
      </div>
      <div class="hero-side">
        <div class="stat"><i class="fa-solid fa-screwdriver-wrench"></i> <div><strong>Work in Progress</strong><br/><span>New notebooks published weekly.</span></div></div>
        <div class="stat"><i class="fa-solid fa-cloud"></i> <div><strong>Colab-Ready</strong><br/><span>Every chapter runnable in Google Colab.</span></div></div>
        <div class="stat"><i class="fa-solid fa-scale-balanced"></i> <div><strong>Math & Mechanisms</strong><br/><span>We derive and implement, not just import.</span></div></div>
      </div>
    </section>

    <!-- PHILOSOPHY / ABOUT -->
    <section class="grid twocol" id="about">
      <article class="card">
        <h2><i class="fa-solid fa-lightbulb"></i> Philosophy</h2>
        <p>This course is for learners who want to <strong>truly understand</strong> Machine Learning — not just use it. We focus on intuition, math, and mechanisms first, with code written from scratch to reveal how things work under the hood.</p>
        <ul class="clean">
          <li><i class="fa-solid fa-check"></i> Plain-language explanations + math where it matters</li>
          <li><i class="fa-solid fa-check"></i> Minimal dependencies; we implement core pieces ourselves</li>
          <li><i class="fa-solid fa-check"></i> Practical notebooks you can run and modify</li>
        </ul>
      </article>
      <article class="card" id="status">
        <h2><i class="fa-solid fa-hourglass-half"></i> Course Status</h2>
        <p>🔨 <strong>Actively updated</strong>. Chapters release week by week. You can follow along and contribute as we go.</p>
        <details>
          <summary>What’s included now?</summary>
          <ul class="clean">
            <li><i class="fa-solid fa-circle-check" style="color:#86efac"></i> Building Foundations</li>
            <li><i class="fa-solid fa-circle-check" style="color:#86efac"></i> Supervised Learning</li>
            <li><i class="fa-solid fa-circle-check" style="color:#86efac"></i> Unsupervised Learning</li>
            <li><i class="fa-solid fa-circle-check" style="color:#86efac"></i> Reinforcement Learning</li>
            <li><i class="fa-solid fa-circle-check" style="color:#86efac"></i> Neural Networks</li>
            <li><i class="fa-solid fa-circle-check" style="color:#86efac"></i> Computer Vision</li>
            <li><i class="fa-solid fa-person-digging" style="color:#fde68a"></i> Natural Language Processing (in progress)</li>
          </ul>
        </details>
      </article>
    </section>

    <!-- ROADMAP -->
    <section class="grid" id="roadmap">
      <article class="card">
        <h2><i class="fa-solid fa-route"></i> Roadmap</h2>
        <div class="roadmap">
          <div class="step">
            <div class="meta"><strong>1) Building Foundations</strong> <span class="badge"><i class="fa-solid fa-check"></i> Done</span></div>
            <p>Python refreshers, math recap, data handling, metrics, and ML workflow.</p>
          </div>
          <div class="step">
            <div class="meta"><strong>2) Supervised Learning</strong> <span class="badge"><i class="fa-solid fa-check"></i> Done</span></div>
            <p>Linear/Logistic regression, regularization, SVMs, trees, ensembles, model selection.</p>
          </div>
          <div class="step">
            <div class="meta"><strong>3) Unsupervised Learning</strong> <span class="badge"><i class="fa-solid fa-check"></i> Done</span></div>
            <p>K-means, GMM, PCA/ICA, dimensionality reduction, anomaly detection.</p>
          </div>
          <div class="step">
            <div class="meta"><strong>4) Reinforcement Learning</strong> <span class="badge"><i class="fa-solid fa-check"></i> Done</span></div>
            <p>MDPs, value iteration, Q-learning and policy gradient intuition.</p>
          </div>
          <div class="step">
            <div class="meta"><strong>5) Neural Networks</strong> <span class="badge"><i class="fa-solid fa-check"></i> Done</span></div>
            <p>Backprop from scratch, activations, regularization, optimization strategies.</p>
          </div>
          <div class="step">
            <div class="meta"><strong>6) Computer Vision</strong> <span class="badge"><i class="fa-solid fa-check"></i> Done</span></div>
            <p>Convolutions, pooling, classic CNNs, and modern training tips.</p>
          </div>
          <div class="step">
            <div class="meta"><strong>7) Natural Language Processing</strong> <span class="badge wip"><i class="fa-solid fa-person-digging"></i> In Progress</span></div>
            <p>Text preprocessing, embeddings, RNNs/LSTMs, attention, Transformers (from scratch).</p>
          </div>
        </div>
      </article>
    </section>

    <!-- GETTING STARTED / HOW TO USE -->
    <section class="grid twocol" id="getting-started">
      <article class="card">
        <h2><i class="fa-solid fa-terminal"></i> How to Use</h2>
        <ol>
          <li>Open any chapter folder and click the notebook you want to run.</li>
          <li>Use the <strong>Colab badge</strong> at the top of the notebook to launch it in Google Colab (no setup needed).</li>
          <li>Alternatively, clone the repo and run locally:</li>
        </ol>
        <pre style="background:var(--card-2); padding:14px; border-radius:12px; overflow:auto; border:1px solid rgba(255,255,255,.06)"><code>git clone https://github.com/&lt;your-username&gt;/ML_101.git
cd ML_101
# (Optional) create and activate a virtual env
pip install -r requirements.txt
jupyter lab</code></pre>
        <p style="margin-top:10px;color:var(--muted)">Each section will also have its own README with a Colab badge and details specific to that topic.</p>
      </article>
      <article class="card">
        <h2><i class="fa-solid fa-list-check"></i> Prerequisites</h2>
        <ul class="clean">
          <li><i class="fa-solid fa-code"></i> Python basics with <strong>NumPy</strong>, <strong>Pandas</strong>, <strong>Matplotlib</strong></li>
          <li><i class="fa-solid fa-diagram-project"></i> Familiarity with algorithms & data structures</li>
          <li><i class="fa-solid fa-square-root-variable"></i> High-school math: linear algebra, probability, and a bit of calculus</li>
        </ul>
        <p class="muted">No prior ML experience required — we build from the ground up.</p>
      </article>
    </section>

    <!-- CONTRIBUTION -->
    <section class="grid" id="contribute">
      <article class="card">
        <h2><i class="fa-solid fa-people-group"></i> Contributing & Community</h2>
        <p>I’m always open to <strong>questions</strong>, <strong>reviews</strong>, <strong>troubleshooting</strong>, and <strong>pull requests</strong>. This project is designed to be collaborative — let’s learn together and make it better each week.</p>
        <ul class="clean">
          <li><i class="fa-solid fa-comment-dots"></i> Start a discussion or ask anything in Issues</li>
          <li><i class="fa-solid fa-bug"></i> Report a bug with steps to reproduce</li>
          <li><i class="fa-solid fa-wand-magic-sparkles"></i> Suggest improvements or add examples</li>
          <li><i class="fa-solid fa-pen-to-square"></i> Submit a PR with clear description and notebook diffs</li>
        </ul>
        <p class="muted"><em>Code of Conduct</em> and <em>Contributing Guide</em> coming soon.</p>
      </article>
    </section>

    <!-- ACKNOWLEDGEMENT & LICENSE -->
    <section class="grid threecol" id="credits">
      <article class="card">
        <h2><i class="fa-solid fa-school"></i> Acknowledgement</h2>
        <p>This course is motivated by the <strong>Introduction to Machine Learning</strong> course at <strong>Sharif University of Technology</strong>, instructed by <a href="https://www.sharifml.ir/" target="_blank" rel="noopener">Dr. Ali Sharifi Zarchi</a>.</p>
      </article>
      <article class="card">
        <h2><i class="fa-solid fa-id-badge"></i> License</h2>
        <p>Released under the <strong>MIT License</strong>. You’re free to use, modify, and share with attribution.</p>
      </article>
      <article class="card">
        <h2><i class="fa-solid fa-info-circle"></i> Who is this for?</h2>
        <p>Students, self-learners, and practitioners who want to build a <em>deep</em> understanding of ML — beyond just calling library functions.</p>
      </article>
    </section>

    <footer>
      <div>© <span id="year"></span> ML_101 — Learn by Building</div>
      <div class="social">
        <a href="#" title="GitHub"><i class="fa-brands fa-github"></i></a>
        <a href="#" title="LinkedIn"><i class="fa-brands fa-linkedin"></i></a>
        <a href="#" title="X / Twitter"><i class="fa-brands fa-x-twitter"></i></a>
      </div>
    </footer>
  </div>
  <script>
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
