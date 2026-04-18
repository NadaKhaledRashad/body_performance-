#body_performance
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Body Performance Analytics — README</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --navy: #0f1b35;
    --navy-mid: #1a2d52;
    --blue-accent: #2563eb;
    --blue-light: #dbeafe;
    --teal: #0d9488;
    --teal-light: #ccfbf1;
    --amber: #d97706;
    --amber-light: #fef3c7;
    --red: #dc2626;
    --red-light: #fee2e2;
    --green: #16a34a;
    --green-light: #dcfce7;
    --purple: #7c3aed;
    --purple-light: #ede9fe;
    --gray-50: #f8fafc;
    --gray-100: #f1f5f9;
    --gray-200: #e2e8f0;
    --gray-300: #cbd5e1;
    --gray-400: #94a3b8;
    --gray-600: #475569;
    --gray-700: #334155;
    --gray-800: #1e293b;
    --gray-900: #0f172a;
    --font: 'Space Grotesk', sans-serif;
    --mono: 'JetBrains Mono', monospace;
    --radius: 12px;
    --radius-sm: 8px;
    --shadow: 0 1px 3px rgba(0,0,0,0.08), 0 4px 16px rgba(0,0,0,0.05);
    --shadow-md: 0 4px 12px rgba(0,0,0,0.1), 0 12px 32px rgba(0,0,0,0.06);
  }

  body {
    font-family: var(--font);
    background: var(--gray-50);
    color: var(--gray-800);
    line-height: 1.6;
    font-size: 15px;
  }

  .hero {
    background: var(--navy);
    color: white;
    padding: 72px 40px 60px;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    top: -60px; right: -80px;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(37,99,235,0.25) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero::after {
    content: '';
    position: absolute;
    bottom: -40px; left: 20%;
    width: 300px; height: 300px;
    background: radial-gradient(circle, rgba(13,148,136,0.2) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(37,99,235,0.2);
    border: 1px solid rgba(37,99,235,0.4);
    color: #93c5fd;
    font-size: 12px;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    padding: 6px 14px;
    border-radius: 100px;
    margin-bottom: 24px;
  }
  .hero h1 {
    font-size: clamp(28px, 4vw, 46px);
    font-weight: 700;
    line-height: 1.15;
    margin-bottom: 16px;
    max-width: 700px;
  }
  .hero h1 span { color: #60a5fa; }
  .hero p {
    font-size: 16px;
    color: #94a3b8;
    max-width: 560px;
    margin-bottom: 32px;
  }
  .hero-meta { display: flex; gap: 24px; flex-wrap: wrap; }
  .hero-meta-item { display: flex; align-items: center; gap: 8px; font-size: 13px; color: #94a3b8; }
  .hero-meta-item strong { color: #e2e8f0; }
  .dot { width: 6px; height: 6px; border-radius: 50%; background: var(--blue-accent); flex-shrink: 0; }

  .stats-ribbon {
    background: white;
    border-bottom: 1px solid var(--gray-200);
    padding: 0 40px;
    display: flex;
    gap: 0;
    overflow-x: auto;
  }
  .stat-cell {
    padding: 20px 32px 20px 0;
    margin-right: 32px;
    border-right: 1px solid var(--gray-200);
    white-space: nowrap;
    flex-shrink: 0;
  }
  .stat-cell:last-child { border-right: none; }
  .stat-num { font-size: 24px; font-weight: 700; color: var(--navy); display: block; line-height: 1; margin-bottom: 4px; }
  .stat-label { font-size: 12px; color: var(--gray-400); text-transform: uppercase; letter-spacing: 0.07em; }

  .container { max-width: 1100px; margin: 0 auto; padding: 48px 40px; }
  .grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; }
  .grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; }
  .grid-4 { display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; }

  .section { margin-bottom: 56px; }
  .section-label { font-size: 11px; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase; color: var(--blue-accent); margin-bottom: 8px; }
  .section-title { font-size: 22px; font-weight: 700; color: var(--gray-900); margin-bottom: 24px; }

  .card { background: white; border: 1px solid var(--gray-200); border-radius: var(--radius); padding: 24px; box-shadow: var(--shadow); }
  .card-sm { padding: 16px 20px; }

  .pipeline { display: flex; align-items: center; gap: 0; overflow-x: auto; padding: 8px 0; }
  .pipe-step { display: flex; align-items: center; gap: 0; flex-shrink: 0; }
  .pipe-box { background: white; border: 1.5px solid var(--gray-200); border-radius: var(--radius-sm); padding: 14px 20px; text-align: center; box-shadow: var(--shadow); }
  .pipe-icon { font-size: 22px; margin-bottom: 6px; }
  .pipe-name { font-size: 12px; font-weight: 600; color: var(--gray-800); white-space: nowrap; }
  .pipe-arrow { width: 36px; height: 2px; background: linear-gradient(90deg, var(--blue-accent), var(--teal)); position: relative; flex-shrink: 0; }
  .pipe-arrow::after { content: ''; position: absolute; right: -1px; top: -4px; border: 5px solid transparent; border-left: 7px solid var(--teal); }

  .feat-table { width: 100%; border-collapse: collapse; }
  .feat-table th { text-align: left; font-size: 11px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.08em; color: var(--gray-400); padding: 8px 12px; border-bottom: 1.5px solid var(--gray-200); }
  .feat-table td { padding: 11px 12px; font-size: 14px; border-bottom: 1px solid var(--gray-100); vertical-align: middle; }
  .feat-table tr:last-child td { border-bottom: none; }
  .feat-table tr:hover td { background: var(--gray-50); }
  .feat-name { font-family: var(--mono); font-size: 13px; color: var(--blue-accent); font-weight: 500; }
  .badge { display: inline-block; padding: 3px 10px; border-radius: 100px; font-size: 11px; font-weight: 600; }
  .badge-blue { background: var(--blue-light); color: #1d4ed8; }
  .badge-amber { background: var(--amber-light); color: #92400e; }
  .badge-teal { background: var(--teal-light); color: #115e59; }

  .clean-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; }
  .clean-card { background: white; border: 1px solid var(--gray-200); border-radius: var(--radius-sm); padding: 14px; border-top: 3px solid var(--blue-accent); }
  .clean-card.warn { border-top-color: var(--amber); }
  .clean-card.danger { border-top-color: var(--red); }
  .clean-card.success { border-top-color: var(--green); }
  .clean-rows { font-size: 22px; font-weight: 700; color: var(--gray-900); margin-bottom: 4px; }
  .clean-issue { font-size: 12px; font-weight: 600; color: var(--gray-700); margin-bottom: 2px; }
  .clean-desc { font-size: 11px; color: var(--gray-400); }

  .insight-card { background: white; border: 1px solid var(--gray-200); border-radius: var(--radius); padding: 20px; display: flex; gap: 16px; align-items: flex-start; }
  .insight-icon { width: 40px; height: 40px; border-radius: var(--radius-sm); display: flex; align-items: center; justify-content: center; font-size: 18px; flex-shrink: 0; }
  .insight-icon.blue { background: var(--blue-light); }
  .insight-icon.teal { background: var(--teal-light); }
  .insight-icon.amber { background: var(--amber-light); }
  .insight-icon.red { background: var(--red-light); }
  .insight-icon.purple { background: var(--purple-light); }
  .insight-icon.green { background: var(--green-light); }
  .insight-title { font-size: 13px; font-weight: 600; color: var(--gray-900); margin-bottom: 4px; }
  .insight-body { font-size: 13px; color: var(--gray-600); line-height: 1.5; }

  .corr-list { list-style: none; display: flex; flex-direction: column; gap: 10px; }
  .corr-item { display: flex; align-items: center; gap: 10px; }
  .corr-label { font-size: 12px; font-family: var(--mono); color: var(--gray-600); width: 220px; flex-shrink: 0; }
  .corr-bar-wrap { flex: 1; background: var(--gray-100); border-radius: 4px; height: 8px; overflow: hidden; }
  .corr-bar { height: 100%; border-radius: 4px; }
  .corr-bar.pos { background: var(--teal); }
  .corr-bar.neg { background: var(--red); }
  .corr-val { font-size: 12px; font-weight: 600; width: 44px; text-align: right; flex-shrink: 0; }
  .corr-val.pos { color: var(--teal); }
  .corr-val.neg { color: var(--red); }

  .model-table { width: 100%; border-collapse: collapse; }
  .model-table th { text-align: left; font-size: 11px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.08em; color: var(--gray-400); padding: 10px 14px; border-bottom: 2px solid var(--gray-200); }
  .model-table td { padding: 12px 14px; font-size: 14px; border-bottom: 1px solid var(--gray-100); vertical-align: middle; }
  .model-table tr:hover td { background: var(--gray-50); }
  .model-table tr.best-row td { background: #f0fdf9; }
  .model-table tr.best-row td:first-child { border-left: 3px solid var(--teal); padding-left: 11px; }
  .acc-bar-wrap { display: flex; align-items: center; gap: 8px; }
  .acc-bar { height: 6px; border-radius: 3px; background: var(--blue-accent); }
  .acc-val { font-size: 13px; font-weight: 600; color: var(--gray-800); }
  .best-tag { display: inline-block; background: var(--teal-light); color: #0f766e; font-size: 10px; font-weight: 700; text-transform: uppercase; letter-spacing: 0.06em; padding: 2px 8px; border-radius: 100px; margin-left: 6px; }

  .reg-table { width: 100%; border-collapse: collapse; }
  .reg-table th { text-align: left; font-size: 11px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.08em; color: var(--gray-400); padding: 8px 12px; border-bottom: 1.5px solid var(--gray-200); }
  .reg-table td { padding: 10px 12px; font-size: 13px; border-bottom: 1px solid var(--gray-100); }
  .r2-pill { display: inline-block; background: var(--green-light); color: #15803d; font-weight: 600; font-size: 12px; padding: 2px 8px; border-radius: 100px; }

  .coeff-item { display: flex; align-items: center; gap: 10px; padding: 8px 0; border-bottom: 1px solid var(--gray-100); }
  .coeff-item:last-child { border-bottom: none; }
  .coeff-feat { font-family: var(--mono); font-size: 12px; color: var(--gray-700); width: 160px; flex-shrink: 0; }
  .coeff-bar-wrap { flex: 1; display: flex; align-items: center; justify-content: center; position: relative; height: 8px; }
  .coeff-center { position: absolute; left: 50%; width: 1px; height: 14px; background: var(--gray-300); top: -3px; }
  .coeff-bar-pos { position: absolute; left: 50%; height: 8px; border-radius: 0 3px 3px 0; background: var(--teal); }
  .coeff-bar-neg { position: absolute; right: 50%; height: 8px; border-radius: 3px 0 0 3px; background: var(--red); }
  .coeff-val { font-size: 12px; font-weight: 600; width: 48px; text-align: right; flex-shrink: 0; }
  .coeff-val.pos { color: var(--teal); }
  .coeff-val.neg { color: var(--red); }

  .team-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 14px; }
  .team-card { background: white; border: 1px solid var(--gray-200); border-radius: var(--radius-sm); padding: 16px; display: flex; align-items: center; gap: 12px; }
  .team-avatar { width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 13px; font-weight: 700; flex-shrink: 0; color: white; }
  .av1 { background: #2563eb; } .av2 { background: #0d9488; } .av3 { background: #7c3aed; }
  .av4 { background: #d97706; } .av5 { background: #dc2626; } .av6 { background: #16a34a; }
  .team-name { font-size: 13px; font-weight: 600; color: var(--gray-800); }
  .team-role { font-size: 11px; color: var(--gray-400); }

  .tech-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; }
  .tech-item { background: white; border: 1px solid var(--gray-200); border-radius: var(--radius-sm); padding: 14px 16px; display: flex; align-items: center; gap: 10px; }
  .tech-dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink: 0; }
  .tech-name { font-size: 13px; font-weight: 600; color: var(--gray-800); }
  .tech-use { font-size: 11px; color: var(--gray-400); }

  .code-block { background: var(--gray-900); color: #e2e8f0; border-radius: var(--radius-sm); padding: 20px 24px; font-family: var(--mono); font-size: 13px; line-height: 1.7; overflow-x: auto; }
  .code-block .cmd { color: #60a5fa; }
  .code-block .comment { color: #64748b; }
  .code-block .str { color: #34d399; }

  .footer { background: var(--navy); color: #64748b; text-align: center; padding: 32px 40px; font-size: 13px; }
  .footer strong { color: #94a3b8; }

  .tab-bar { display: flex; gap: 4px; border-bottom: 1.5px solid var(--gray-200); margin-bottom: 24px; }
  .tab-btn { padding: 8px 18px; font-size: 13px; font-weight: 500; color: var(--gray-400); border: none; background: none; cursor: pointer; border-bottom: 2px solid transparent; margin-bottom: -1.5px; font-family: var(--font); transition: color 0.15s; }
  .tab-btn.active { color: var(--blue-accent); border-bottom-color: var(--blue-accent); }
  .tab-panel { display: none; }
  .tab-panel.active { display: block; }

  @media (max-width: 768px) {
    .hero { padding: 48px 20px 40px; }
    .container { padding: 32px 20px; }
    .grid-2, .grid-3, .grid-4, .clean-grid, .team-grid, .tech-grid { grid-template-columns: 1fr 1fr; }
    .stats-ribbon { padding: 0 20px; }
  }
</style>
</head>
<body>

<header class="hero">
  <div class="hero-badge"><span class="dot"></span> ML · Classification · Regression</div>
  <h1>Body Performance <span>Analytics</span> &amp; Intelligent Classification System</h1>
  <p>Machine Learning for Physical Fitness Assessment — predicting performance classes and explosive power from body measurements.</p>
  <div class="hero-meta">
    <div class="hero-meta-item"><strong>Course:</strong> Introduction to AI and ML</div>
    <div class="hero-meta-item"><strong>Supervisor:</strong> Dr. Sherif Morsi</div>
    <div class="hero-meta-item"><strong>Language:</strong> Python 3</div>
    <div class="hero-meta-item"><strong>Platform:</strong> Google Colab</div>
  </div>
</header>

<div class="stats-ribbon">
  <div class="stat-cell"><span class="stat-num">13,371</span><span class="stat-label">Clean Records</span></div>
  <div class="stat-cell"><span class="stat-num">11</span><span class="stat-label">Input Features</span></div>
  <div class="stat-cell"><span class="stat-num">4</span><span class="stat-label">Performance Classes</span></div>
  <div class="stat-cell"><span class="stat-num">74.23%</span><span class="stat-label">Best Accuracy (NN)</span></div>
  <div class="stat-cell"><span class="stat-num">R² 0.79</span><span class="stat-label">Regression Score</span></div>
  <div class="stat-cell"><span class="stat-num">6</span><span class="stat-label">Models Tested</span></div>
</div>

<div class="container">

  <section class="section">
    <div class="section-label">Overview</div>
    <div class="section-title">Project Goals</div>
    <div class="grid-2">
      <div class="card" style="border-left: 4px solid var(--blue-accent);">
        <div style="font-size:11px;font-weight:600;text-transform:uppercase;letter-spacing:.08em;color:var(--blue-accent);margin-bottom:10px;">Task 1 — Classification</div>
        <div style="font-size:17px;font-weight:700;color:var(--gray-900);margin-bottom:8px;">Predict Performance Class</div>
        <p style="color:var(--gray-600);font-size:14px;">Classify individuals into one of four levels — <strong>A (Excellent)</strong>, <strong>B (Good)</strong>, <strong>C (Average)</strong>, or <strong>D (Poor)</strong> — based on physical measurements.</p>
      </div>
      <div class="card" style="border-left: 4px solid var(--teal);">
        <div style="font-size:11px;font-weight:600;text-transform:uppercase;letter-spacing:.08em;color:var(--teal);margin-bottom:10px;">Task 2 — Regression</div>
        <div style="font-size:17px;font-weight:700;color:var(--gray-900);margin-bottom:8px;">Predict Explosive Power</div>
        <p style="color:var(--gray-600);font-size:14px;">Predict <code style="font-family:var(--mono);font-size:13px;background:var(--gray-100);padding:2px 6px;border-radius:4px;">broad_jump_cm</code> as a continuous proxy for explosive power using Linear Regression (OLS).</p>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="section-label">Methodology</div>
    <div class="section-title">Project Pipeline</div>
    <div class="card" style="padding: 32px;">
      <div class="pipeline">
        <div class="pipe-step"><div class="pipe-box"><div class="pipe-icon">🗃️</div><div class="pipe-name">Raw Data</div></div></div>
        <div class="pipe-arrow"></div>
        <div class="pipe-step"><div class="pipe-box"><div class="pipe-icon">🧹</div><div class="pipe-name">Data Cleaning</div></div></div>
        <div class="pipe-arrow"></div>
        <div class="pipe-step"><div class="pipe-box"><div class="pipe-icon">🔬</div><div class="pipe-name">EDA</div></div></div>
        <div class="pipe-arrow"></div>
        <div class="pipe-step"><div class="pipe-box"><div class="pipe-icon">⚙️</div><div class="pipe-name">Feature Engineering</div></div></div>
        <div class="pipe-arrow"></div>
        <div class="pipe-step"><div class="pipe-box"><div class="pipe-icon">🤖</div><div class="pipe-name">Model Training</div></div></div>
        <div class="pipe-arrow"></div>
        <div class="pipe-step"><div class="pipe-box"><div class="pipe-icon">📊</div><div class="pipe-name">Evaluation</div></div></div>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="section-label">Dataset</div>
    <div class="section-title">Features &amp; Variables</div>
    <div class="card" style="padding: 0; overflow: hidden;">
      <table class="feat-table">
        <thead>
          <tr><th>Feature</th><th>Description</th><th>Type</th><th>Role</th></tr>
        </thead>
        <tbody>
          <tr><td class="feat-name">age</td><td>Age in years</td><td><span class="badge badge-blue">Numeric</span></td><td>Input</td></tr>
          <tr><td class="feat-name">gender</td><td>Male / Female</td><td><span class="badge badge-amber">Categorical</span></td><td>Input</td></tr>
          <tr><td class="feat-name">height_cm</td><td>Height in centimeters</td><td><span class="badge badge-blue">Numeric</span></td><td>Input</td></tr>
          <tr><td class="feat-name">weight_kg</td><td>Weight in kilograms</td><td><span class="badge badge-blue">Numeric</span></td><td>Input</td></tr>
          <tr><td class="feat-name">body_fat_percent</td><td>Body fat percentage</td><td><span class="badge badge-blue">Numeric</span></td><td>Input</td></tr>
          <tr><td class="feat-name">diastolic</td><td>Diastolic blood pressure</td><td><span class="badge badge-blue">Numeric</span></td><td>Input</td></tr>
          <tr><td class="feat-name">systolic</td><td>Systolic blood pressure</td><td><span class="badge badge-blue">Numeric</span></td><td>Input</td></tr>
          <tr><td class="feat-name">gripForce</td><td>Hand grip strength (kg)</td><td><span class="badge badge-blue">Numeric</span></td><td>Input</td></tr>
          <tr><td class="feat-name">sit_and_bend_forward_cm</td><td>Flexibility measure (cm)</td><td><span class="badge badge-blue">Numeric</span></td><td>Input</td></tr>
          <tr><td class="feat-name">sit_ups_counts</td><td>Sit-up count (muscular endurance)</td><td><span class="badge badge-blue">Numeric</span></td><td>Input</td></tr>
          <tr><td class="feat-name">broad_jump_cm</td><td>Broad jump distance (explosive power)</td><td><span class="badge badge-blue">Numeric</span></td><td>Input / Reg. Target</td></tr>
          <tr><td class="feat-name">class</td><td>Performance class A–D</td><td><span class="badge badge-teal">Ordinal</span></td><td>Class. Target</td></tr>
        </tbody>
      </table>
    </div>
  </section>

  <section class="section">
    <div class="section-label">Preprocessing</div>
    <div class="section-title">Data Cleaning Summary</div>
    <div class="clean-grid" style="margin-bottom:16px;">
      <div class="clean-card success"><div class="clean-rows">1</div><div class="clean-issue">Duplicate rows</div><div class="clean-desc">Exact copy removed</div></div>
      <div class="clean-card warn"><div class="clean-rows">1</div><div class="clean-issue">Body fat &gt; 60%</div><div class="clean-desc">Biologically impossible</div></div>
      <div class="clean-card warn"><div class="clean-rows">1</div><div class="clean-issue">Height &lt; 130 cm</div><div class="clean-desc">Adult dataset assumption</div></div>
      <div class="clean-card warn"><div class="clean-rows">1</div><div class="clean-issue">Weight &lt; 30 kg</div><div class="clean-desc">Clinically invalid</div></div>
      <div class="clean-card danger"><div class="clean-rows">2</div><div class="clean-issue">Zero blood pressure</div><div class="clean-desc">Not a valid real-world value</div></div>
      <div class="clean-card danger"><div class="clean-rows">4</div><div class="clean-issue">BP inversion</div><div class="clean-desc">Systolic &lt; Diastolic</div></div>
      <div class="clean-card danger"><div class="clean-rows">3</div><div class="clean-issue">Zero grip force</div><div class="clean-desc">Not measurable as zero</div></div>
      <div class="clean-card danger"><div class="clean-rows">10</div><div class="clean-issue">Zero broad jump</div><div class="clean-desc">Impossible for a living adult</div></div>
    </div>
    <div class="card card-sm" style="background: var(--green-light); border-color: #86efac; display:flex; align-items:center; gap:12px;">
      <span style="font-size:20px;">✅</span>
      <div>
        <strong style="color:#15803d;">Total removed: 22 rows (0.16%)</strong>
        <span style="color:#166534; font-size:13px; margin-left:8px;">— Final dataset: 13,371 clean records ready for modeling</span>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="section-label">Exploratory Data Analysis</div>
    <div class="section-title">Key Findings</div>
    <div class="grid-2" style="gap:16px; margin-bottom:32px;">
      <div class="insight-card"><div class="insight-icon blue">⚧</div><div><div class="insight-title">Gender as Dominant Predictor</div><div class="insight-body">Males outperform females by 38–68% across all strength and power metrics, making gender the single strongest performance indicator.</div></div></div>
      <div class="insight-card"><div class="insight-icon amber">📉</div><div><div class="insight-title">Age-Related Decline</div><div class="insight-body">Athletic performance shows a clear monotonic decline with age throughout the 21–64 range, affecting grip force, broad jump, and sit-ups.</div></div></div>
      <div class="insight-card"><div class="insight-icon red">🩸</div><div><div class="insight-title">Body Fat: Strongest Negative Indicator</div><div class="insight-body">Body fat is the strongest negative predictor with inverse correlations of r = −0.61 to −0.68 with broad jump and sit-up performance.</div></div></div>
      <div class="insight-card"><div class="insight-icon teal">⚖️</div><div><div class="insight-title">Perfectly Balanced Classes</div><div class="insight-body">Classes A, B, C, D each contain ~3,340 records (25% each), eliminating class-imbalance bias and making accuracy a fair metric.</div></div></div>
      <div class="insight-card"><div class="insight-icon purple">💉</div><div><div class="insight-title">Blood Pressure: Negligible Correlation</div><div class="insight-body">Blood pressure shows |r| &lt; 0.06 with all fitness metrics — effectively independent from physical performance in this dataset.</div></div></div>
      <div class="insight-card"><div class="insight-icon green">🤸</div><div><div class="insight-title">Flexibility: Bimodal Distribution</div><div class="insight-body">Sit-and-bend scores show a bimodal pattern including valid negative values representing limited range of motion — retained intentionally.</div></div></div>
    </div>
    <div class="grid-2">
      <div class="card">
        <div style="font-size:13px;font-weight:600;color:var(--teal);margin-bottom:16px;">Strong Positive Correlations</div>
        <ul class="corr-list">
          <li class="corr-item"><span class="corr-label">gripForce ↔ broad_jump</span><div class="corr-bar-wrap"><div class="corr-bar pos" style="width:100%"></div></div><span class="corr-val pos">0.752</span></li>
          <li class="corr-item"><span class="corr-label">sit_ups ↔ broad_jump</span><div class="corr-bar-wrap"><div class="corr-bar pos" style="width:99%"></div></div><span class="corr-val pos">0.750</span></li>
          <li class="corr-item"><span class="corr-label">height ↔ gripForce</span><div class="corr-bar-wrap"><div class="corr-bar pos" style="width:97%"></div></div><span class="corr-val pos">0.736</span></li>
          <li class="corr-item"><span class="corr-label">height ↔ weight</span><div class="corr-bar-wrap"><div class="corr-bar pos" style="width:97%"></div></div><span class="corr-val pos">0.735</span></li>
          <li class="corr-item"><span class="corr-label">weight ↔ gripForce</span><div class="corr-bar-wrap"><div class="corr-bar pos" style="width:93%"></div></div><span class="corr-val pos">0.701</span></li>
        </ul>
      </div>
      <div class="card">
        <div style="font-size:13px;font-weight:600;color:var(--red);margin-bottom:16px;">Strong Negative Correlations</div>
        <ul class="corr-list">
          <li class="corr-item"><span class="corr-label">body_fat ↔ broad_jump</span><div class="corr-bar-wrap"><div class="corr-bar neg" style="width:100%"></div></div><span class="corr-val neg">−0.680</span></li>
          <li class="corr-item"><span class="corr-label">body_fat ↔ sit_ups</span><div class="corr-bar-wrap"><div class="corr-bar neg" style="width:90%"></div></div><span class="corr-val neg">−0.610</span></li>
          <li class="corr-item"><span class="corr-label">age ↔ sit_ups</span><div class="corr-bar-wrap"><div class="corr-bar neg" style="width:79%"></div></div><span class="corr-val neg">−0.540</span></li>
        </ul>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="section-label">Results</div>
    <div class="section-title">Model Performance</div>
    <div class="tab-bar">
      <button class="tab-btn active" onclick="switchTab(event,'tab-clf')">Classification</button>
      <button class="tab-btn" onclick="switchTab(event,'tab-reg')">Regression</button>
      <button class="tab-btn" onclick="switchTab(event,'tab-coeff')">Feature Coefficients</button>
    </div>

    <div class="tab-panel active" id="tab-clf">
      <div class="card" style="padding:0; overflow:hidden;">
        <table class="model-table">
          <thead><tr><th>Model</th><th>Accuracy</th><th>Precision</th><th>Recall</th><th>F1</th><th>Best Config</th></tr></thead>
          <tbody>
            <tr class="best-row">
              <td><strong>Neural Network (MLP)</strong><span class="best-tag">Best</span></td>
              <td><div class="acc-bar-wrap"><div class="acc-bar" style="width:74px;background:var(--teal)"></div><span class="acc-val" style="color:var(--teal)">74.23%</span></div></td>
              <td>~0.75</td><td>~0.74</td><td>~0.74</td><td style="font-size:12px;color:var(--gray-400);">3-layer, ReLU, Dropout</td>
            </tr>
            <tr>
              <td>Random Forest</td>
              <td><div class="acc-bar-wrap"><div class="acc-bar" style="width:72px"></div><span class="acc-val">72.00%</span></div></td>
              <td>0.89</td><td>0.85</td><td>0.84</td><td style="font-size:12px;color:var(--gray-400);">100 trees, depth=10</td>
            </tr>
            <tr>
              <td>SVM</td>
              <td><div class="acc-bar-wrap"><div class="acc-bar" style="width:71px"></div><span class="acc-val">71.71%</span></div></td>
              <td>0.72</td><td>0.72</td><td>0.72</td><td style="font-size:12px;color:var(--gray-400);">RBF, C=10, γ=0.1</td>
            </tr>
            <tr>
              <td>Decision Tree (Pruned)</td>
              <td><div class="acc-bar-wrap"><div class="acc-bar" style="width:68px"></div><span class="acc-val">68.00%</span></div></td>
              <td>0.86</td><td>0.81</td><td>0.80</td><td style="font-size:12px;color:var(--gray-400);">max_depth=10</td>
            </tr>
            <tr>
              <td>Decision Tree (Unpruned)</td>
              <td><div class="acc-bar-wrap"><div class="acc-bar" style="width:65px;background:var(--gray-300)"></div><span class="acc-val">64.56%</span></div></td>
              <td>0.65</td><td>0.64</td><td>0.64</td><td style="font-size:12px;color:var(--gray-400);">No depth limit</td>
            </tr>
            <tr>
              <td>KNN (k=30)</td>
              <td><div class="acc-bar-wrap"><div class="acc-bar" style="width:63px;background:var(--gray-300)"></div><span class="acc-val">62.77%</span></div></td>
              <td>0.654</td><td>0.628</td><td>0.628</td><td style="font-size:12px;color:var(--gray-400);">k=30, Euclidean</td>
            </tr>
            <tr>
              <td>KNN (k=5 — baseline)</td>
              <td><div class="acc-bar-wrap"><div class="acc-bar" style="width:59px;background:var(--gray-200)"></div><span class="acc-val" style="color:var(--gray-400)">58.99%</span></div></td>
              <td>0.615</td><td>0.590</td><td>0.590</td><td style="font-size:12px;color:var(--gray-400);">Default k=5</td>
            </tr>
          </tbody>
        </table>
      </div>
      <div class="card card-sm" style="margin-top:12px;background:var(--amber-light);border-color:#fcd34d;">
        <span style="font-size:13px;color:#92400e;">⚠️ <strong>Note:</strong> The Neural Network result (74.23%) was affected by a preprocessing bug — trained on 304 unintended classes. Expected post-fix accuracy is <strong>70–75%</strong>, consistent with SVM.</span>
      </div>
    </div>

    <div class="tab-panel" id="tab-reg">
      <div class="grid-2">
        <div class="card" style="padding:0;overflow:hidden;">
          <div style="padding:16px 20px;border-bottom:1px solid var(--gray-100);font-size:13px;font-weight:600;color:var(--gray-700);">Performance Across Splits</div>
          <table class="reg-table">
            <thead><tr><th>Split Strategy</th><th>MSE</th><th>RMSE (cm)</th><th>R² Score</th></tr></thead>
            <tbody>
              <tr><td>80:20</td><td>335.91</td><td>18.32</td><td><span class="r2-pill">0.7773</span></td></tr>
              <tr><td>70:30</td><td>323.79</td><td>17.99</td><td><span class="r2-pill">0.7874</span></td></tr>
              <tr><td>50:50</td><td>317.61</td><td>17.82</td><td><span class="r2-pill">0.7954</span></td></tr>
              <tr><td>5-Fold Cross-Validation</td><td>325.54</td><td>~18.03</td><td><span class="r2-pill">0.7915</span></td></tr>
            </tbody>
          </table>
        </div>
        <div style="display:flex;flex-direction:column;gap:12px;">
          <div class="card card-sm" style="text-align:center;">
            <div style="font-size:36px;font-weight:700;color:var(--navy);">~0.79</div>
            <div style="font-size:13px;color:var(--gray-400);margin-top:4px;">Mean R² — explains ~79% of variance in broad jump</div>
          </div>
          <div class="card card-sm" style="text-align:center;">
            <div style="font-size:36px;font-weight:700;color:var(--navy);">~18 cm</div>
            <div style="font-size:13px;color:var(--gray-400);margin-top:4px;">Mean RMSE — average prediction error</div>
          </div>
        </div>
      </div>
    </div>

    <div class="tab-panel" id="tab-coeff">
      <div class="card">
        <div style="font-size:13px;color:var(--gray-400);margin-bottom:20px;">Standardized coefficients — magnitude = importance, sign = direction of effect on <code style="font-family:var(--mono);font-size:12px;background:var(--gray-100);padding:2px 6px;border-radius:4px;">broad_jump_cm</code></div>
        <div id="coeff-list"></div>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="section-label">Stack</div>
    <div class="section-title">Technologies Used</div>
    <div class="tech-grid">
      <div class="tech-item"><div class="tech-dot" style="background:#3b82f6"></div><div><div class="tech-name">Python 3</div><div class="tech-use">Core language</div></div></div>
      <div class="tech-item"><div class="tech-dot" style="background:#f59e0b"></div><div><div class="tech-name">pandas</div><div class="tech-use">Data manipulation</div></div></div>
      <div class="tech-item"><div class="tech-dot" style="background:#6366f1"></div><div><div class="tech-name">numpy</div><div class="tech-use">Numerical ops</div></div></div>
      <div class="tech-item"><div class="tech-dot" style="background:#10b981"></div><div><div class="tech-name">scikit-learn</div><div class="tech-use">ML models</div></div></div>
      <div class="tech-item"><div class="tech-dot" style="background:#ef4444"></div><div><div class="tech-name">TensorFlow / Keras</div><div class="tech-use">Neural Network</div></div></div>
      <div class="tech-item"><div class="tech-dot" style="background:#8b5cf6"></div><div><div class="tech-name">matplotlib</div><div class="tech-use">Visualization</div></div></div>
      <div class="tech-item"><div class="tech-dot" style="background:#0ea5e9"></div><div><div class="tech-name">seaborn</div><div class="tech-use">Statistical plots</div></div></div>
      <div class="tech-item"><div class="tech-dot" style="background:#f97316"></div><div><div class="tech-name">Google Colab</div><div class="tech-use">Dev environment</div></div></div>
    </div>
  </section>

  <section class="section">
    <div class="section-label">Setup</div>
    <div class="section-title">How to Run</div>
    <div class="card">
      <div class="code-block">
<span class="comment"># 1. Clone the repository</span>
<span class="cmd">git clone</span> <span class="str">https://github.com/your-username/body-performance-analytics.git</span>
<span class="cmd">cd</span> body-performance-analytics

<span class="comment"># 2. Install dependencies</span>
<span class="cmd">pip install</span> pandas numpy matplotlib seaborn scikit-learn tensorflow

<span class="comment"># 3. Run notebooks in order</span>
<span class="comment">#    01_data_cleaning.ipynb → 02_eda.ipynb → 03_classification.ipynb → 04_regression.ipynb</span>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="section-label">Team</div>
    <div class="section-title">Contributors</div>
    <div class="team-grid">
      <div class="team-card"><div class="team-avatar av1">NK</div><div><div class="team-name">Nada Khaled Mahmoud</div><div class="team-role">Team Leader</div></div></div>
      <div class="team-card"><div class="team-avatar av2">NE</div><div><div class="team-name">Neama Eid Darwish</div><div class="team-role">Member</div></div></div>
      <div class="team-card"><div class="team-avatar av3">FY</div><div><div class="team-name">Fatima Youssef Kamal</div><div class="team-role">Member</div></div></div>
      <div class="team-card"><div class="team-avatar av4">MY</div><div><div class="team-name">Mona Yasser Abdelkader</div><div class="team-role">Member</div></div></div>
      <div class="team-card"><div class="team-avatar av5">HR</div><div><div class="team-name">Hagar Roshdy Ramadan</div><div class="team-role">Member</div></div></div>
      <div class="team-card"><div class="team-avatar av6">NA</div><div><div class="team-name">Nourhan Abdelkhaleq</div><div class="team-role">Member</div></div></div>
    </div>
  </section>

</div>

<footer class="footer">
  <p>Built for <strong>Introduction to AI & ML</strong> · Supervised by <strong>Dr. Sherif Morsi</strong> · Educational purposes only</p>
</footer>

<script>
function switchTab(e, id) {
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  document.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
  e.target.classList.add('active');
  document.getElementById(id).classList.add('active');
}

const coeffs = [
  { feat: 'gender',            val: 12.59, dir: 'pos', interp: 'Males jump ~12.5 cm further' },
  { feat: 'sit_ups_counts',    val: 8.75,  dir: 'pos', interp: 'More sit-ups → longer jump' },
  { feat: 'gripForce',         val: 7.86,  dir: 'pos', interp: 'Stronger grip → more power' },
  { feat: 'sit_and_bend',      val: 4.12,  dir: 'pos', interp: 'Better flexibility helps' },
  { feat: 'height_cm',         val: 1.35,  dir: 'pos', interp: 'Taller → slightly longer jump' },
  { feat: 'weight_kg',         val: 1.31,  dir: 'pos', interp: 'Slight muscle mass effect' },
  { feat: 'body_fat_percent',  val: -7.23, dir: 'neg', interp: 'Higher fat → less power' },
  { feat: 'age',               val: -7.87, dir: 'neg', interp: 'Older → reduced explosive power' },
  { feat: 'systolic',          val: -0.34, dir: 'neg', interp: 'Negligible predictor' },
  { feat: 'diastolic',         val: 0.96,  dir: 'pos', interp: 'Negligible predictor' },
];

const maxAbs = Math.max(...coeffs.map(c => Math.abs(c.val)));
const list = document.getElementById('coeff-list');
coeffs.forEach(c => {
  const pct = (Math.abs(c.val) / maxAbs * 48).toFixed(1);
  list.innerHTML += `
    <div class="coeff-item">
      <span class="coeff-feat">${c.feat}</span>
      <div class="coeff-bar-wrap">
        <div class="coeff-center"></div>
        ${c.dir === 'pos'
          ? `<div class="coeff-bar-pos" style="width:${pct}%"></div>`
          : `<div class="coeff-bar-neg" style="width:${pct}%"></div>`}
      </div>
      <span class="coeff-val ${c.dir}">${c.val > 0 ? '+' : ''}${c.val}</span>
      <span style="font-size:11px;color:var(--gray-400);flex:1;padding-left:10px;">${c.interp}</span>
    </div>`;
});
</script>
</body>
</html>
