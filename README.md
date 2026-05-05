# ghana-gas-brief
<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8"/>
 <meta http-equiv="Content-Security-Policy" content="style-src 'self' 'unsafe-inline' https://fonts.googleapis.com; font-src https://fonts.gstatic.com;">

<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Ghana Gas — Site Brief</title>
<link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@300;400;600;700;800&family=Lora:ital,wght@0,400;0,600;1,400&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
/* ─────────────────────────────────────────────
   ROOT & RESET
───────────────────────────────────────────── */
:root {
  --bg:       #0b0f14;
  --surface:  #111820;
  --card:     #16202c;
  --border:   #1e2d3d;
  --line:     #253547;
  --gold:     #e8a020;
  --gold-dim: #7a530e;
  --teal:     #00c2a8;
  --teal-dim: #004d42;
  --red:      #e84040;
  --amber:    #e8900a;
  --green:    #28c97a;
  --blue:     #2090e8;
  --text:     #d4dde8;
  --muted:    #5a7080;
  --white:    #eef2f6;
  --edit-bg:  rgba(232,160,32,0.07);
  --edit-out: rgba(232,160,32,0.25);
}
*, *::before, *::after { box-sizing: border-box; margin:0; padding:0; }
html { scroll-behavior: smooth; }
body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Lora', Georgia, serif;
  font-size: 15px;
  line-height: 1.7;
  min-height: 100vh;
}

/* ─────────────────────────────────────────────
EDITABLE ELEMENTS
───────────────────────────────────────────── */
[contenteditable] {
outline: none;
border-radius: 2px;
transition: background .15s, box-shadow .15s;
cursor: text;
-webkit-user-modify: read-write;
}
[contenteditable]:hover {
background: var(–edit-bg);
}
[contenteditable]:focus {
background: var(–edit-bg);
box-shadow: 0 0 0 1px var(–edit-out);
}
.edit-hint {
position: fixed;
bottom: 20px; right: 20px;
background: var(–gold);
color: #000;
font-family: ‘JetBrains Mono’, monospace;
font-size: 11px;
padding: 8px 14px;
border-radius: 2px;
letter-spacing: 0.06em;
z-index: 999;
opacity: 0.9;
}

/* ─────────────────────────────────────────────
HEADER / MASTHEAD
───────────────────────────────────────────── */
.masthead {
background: var(–surface);
border-bottom: 1px solid var(–border);
padding: 0 48px;
display: grid;
grid-template-columns: auto 1fr auto;
align-items: stretch;
gap: 0;
min-height: 90px;
position: relative;
overflow: hidden;
}
.masthead::before {
content: ‘’;
position: absolute;
inset: 0;
background: repeating-linear-gradient(
90deg,
transparent,
transparent 60px,
rgba(232,160,32,0.03) 60px,
rgba(232,160,32,0.03) 61px
);
pointer-events: none;
}
.mast-brand {
display: flex;
align-items: center;
gap: 18px;
padding: 20px 32px 20px 0;
border-right: 1px solid var(–border);
}
.brand-icon {
width: 46px; height: 46px;
background: var(–gold);
display: flex; align-items: center; justify-content: center;
font-family: ‘Barlow Condensed’, sans-serif;
font-weight: 800;
font-size: 18px;
color: #000;
letter-spacing: -0.02em;
flex-shrink: 0;
}
.brand-text { line-height: 1.2; }
.brand-name {
font-family: ‘Barlow Condensed’, sans-serif;
font-weight: 800;
font-size: 22px;
color: var(–white);
letter-spacing: 0.04em;
text-transform: uppercase;
}
.brand-sub {
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
color: var(–muted);
letter-spacing: 0.1em;
text-transform: uppercase;
}
.mast-title {
display: flex;
align-items: center;
padding: 0 36px;
}
.mast-title h1 {
font-family: ‘Barlow Condensed’, sans-serif;
font-weight: 800;
font-size: 42px;
letter-spacing: 0.1em;
text-transform: uppercase;
color: var(–white);
display: flex;
align-items: center;
gap: 16px;
}
.mast-title h1 span {
display: inline-block;
background: var(–gold);
color: #000;
padding: 2px 12px;
font-size: 14px;
letter-spacing: 0.12em;
vertical-align: middle;
font-weight: 700;
}
.mast-meta {
display: flex;
flex-direction: column;
justify-content: center;
align-items: flex-end;
padding: 20px 0 20px 32px;
border-left: 1px solid var(–border);
gap: 4px;
}
.mast-meta .issue {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 30px;
font-weight: 700;
color: var(–gold);
letter-spacing: 0.06em;
line-height: 1;
}
.mast-meta .date {
font-family: ‘JetBrains Mono’, monospace;
font-size: 11px;
color: var(–muted);
letter-spacing: 0.08em;
}

/* ─────────────────────────────────────────────
NAV STRIP
───────────────────────────────────────────── */
.nav-strip {
background: var(–surface);
border-bottom: 2px solid var(–gold);
padding: 0 48px;
display: flex;
gap: 0;
overflow-x: auto;
}
.nav-strip a {
font-family: ‘Barlow Condensed’, sans-serif;
font-weight: 600;
font-size: 13px;
letter-spacing: 0.1em;
text-transform: uppercase;
color: var(–muted);
text-decoration: none;
padding: 12px 20px;
border-bottom: 3px solid transparent;
margin-bottom: -2px;
transition: color .2s, border-color .2s;
white-space: nowrap;
}
.nav-strip a:hover { color: var(–white); border-bottom-color: var(–gold); }

/* ─────────────────────────────────────────────
WRAPPER
───────────────────────────────────────────── */
.wrapper { max-width: 1280px; margin: 0 auto; padding: 40px 40px 100px; }

/* ─────────────────────────────────────────────
SECTION HEADER
───────────────────────────────────────────── */
.section-head {
display: flex;
align-items: center;
gap: 16px;
margin: 48px 0 24px;
}
.section-head:first-child { margin-top: 0; }
.sh-num {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 48px;
font-weight: 800;
color: var(–gold);
line-height: 1;
opacity: 0.3;
flex-shrink: 0;
}
.sh-text h2 {
font-family: ‘Barlow Condensed’, sans-serif;
font-weight: 700;
font-size: 26px;
letter-spacing: 0.08em;
text-transform: uppercase;
color: var(–white);
}
.sh-text p {
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
color: var(–muted);
letter-spacing: 0.1em;
text-transform: uppercase;
margin-top: 2px;
}
.sh-rule { flex: 1; height: 1px; background: var(–border); }

/* ─────────────────────────────────────────────
① PROJECT PROGRESS DASHBOARD
───────────────────────────────────────────── */
.project-grid {
display: grid;
grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
gap: 14px;
}
.proj-card {
background: var(–card);
border: 1px solid var(–border);
padding: 22px 22px 18px;
position: relative;
overflow: hidden;
transition: border-color .2s, transform .15s;
}
.proj-card:hover { border-color: var(–gold-dim); transform: translateY(-2px); }
.proj-card::after {
content: ‘’;
position: absolute;
top: 0; left: 0; right: 0;
height: 2px;
background: var(–gold);
transform-origin: left;
transition: transform .4s ease;
}
.proj-card .proj-name {
font-family: ‘Barlow Condensed’, sans-serif;
font-weight: 700;
font-size: 17px;
letter-spacing: 0.06em;
text-transform: uppercase;
color: var(–white);
margin-bottom: 6px;
display: block;
min-width: 10px;
}
.proj-card .proj-status {
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
color: var(–muted);
letter-spacing: 0.08em;
margin-bottom: 16px;
display: block;
min-width: 10px;
}
.proj-bar-track {
background: var(–bg);
height: 8px;
border-radius: 1px;
margin-bottom: 10px;
overflow: hidden;
cursor: pointer;
position: relative;
}
.proj-bar-fill {
height: 100%;
border-radius: 1px;
background: linear-gradient(90deg, var(–teal-dim), var(–teal));
transition: width .6s cubic-bezier(.4,0,.2,1);
}
.proj-pct-row {
display: flex;
justify-content: space-between;
align-items: center;
}
.proj-pct {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 32px;
font-weight: 700;
color: var(–teal);
line-height: 1;
}
.pct-controls {
display: flex;
gap: 6px;
align-items: center;
}
.pct-btn {
background: var(–border);
border: none;
color: var(–text);
width: 26px; height: 26px;
cursor: pointer;
font-size: 16px;
font-family: ‘Barlow Condensed’, sans-serif;
font-weight: 700;
display: flex; align-items: center; justify-content: center;
border-radius: 2px;
transition: background .15s, color .15s;
flex-shrink: 0;
}
.pct-btn:hover { background: var(–gold); color: #000; }
.proj-pct-label {
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
color: var(–muted);
letter-spacing: 0.06em;
}

/* colour variants by %  */
.fill-low { background: linear-gradient(90deg, #5c1a1a, var(–red)); }
.fill-mid { background: linear-gradient(90deg, var(–gold-dim), var(–amber)); }
.fill-hi  { background: linear-gradient(90deg, var(–teal-dim), var(–teal)); }
.fill-done { background: linear-gradient(90deg, #0d4a2a, var(–green)); }
.pct-low  { color: var(–red); }
.pct-mid  { color: var(–amber); }
.pct-hi   { color: var(–teal); }
.pct-done { color: var(–green); }

/* ─────────────────────────────────────────────
② GAS FLOW RATE TRACKER
───────────────────────────────────────────── */
.flow-table-wrap {
background: var(–card);
border: 1px solid var(–border);
overflow-x: auto;
}
.flow-table {
width: 100%;
border-collapse: collapse;
}
.flow-table thead tr {
background: var(–surface);
border-bottom: 2px solid var(–gold);
}
.flow-table th {
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
font-weight: 500;
letter-spacing: 0.1em;
text-transform: uppercase;
color: var(–gold);
padding: 14px 20px;
text-align: left;
white-space: nowrap;
}
.flow-table td {
padding: 13px 20px;
border-bottom: 1px solid var(–border);
vertical-align: middle;
font-size: 14px;
}
.flow-table tr:last-child td { border-bottom: none; }
.flow-table tr:hover td { background: rgba(232,160,32,0.04); }
.flow-table td:first-child {
font-family: ‘Barlow Condensed’, sans-serif;
font-weight: 700;
font-size: 16px;
letter-spacing: 0.04em;
color: var(–white);
white-space: nowrap;
}
.flow-val {
font-family: ‘JetBrains Mono’, monospace;
font-size: 15px;
font-weight: 500;
color: var(–teal);
min-width: 60px;
display: inline-block;
}
.flow-unit {
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
color: var(–muted);
margin-left: 4px;
}
.flow-note {
font-size: 13px;
color: var(–text);
font-family: ‘Lora’, serif;
}
.status-dot {
display: inline-block;
width: 8px; height: 8px;
border-radius: 50%;
margin-right: 6px;
}
.dot-g { background: var(–green); box-shadow: 0 0 6px var(–green); }
.dot-a { background: var(–amber); box-shadow: 0 0 6px var(–amber); }
.dot-r { background: var(–red);   box-shadow: 0 0 6px var(–red);   }
.status-txt { font-family: ‘JetBrains Mono’, monospace; font-size: 11px; letter-spacing: 0.06em; }

/* add row button */
.add-row-btn {
display: flex;
align-items: center;
gap: 8px;
background: none;
border: 1px dashed var(–border);
color: var(–muted);
font-family: ‘JetBrains Mono’, monospace;
font-size: 11px;
letter-spacing: 0.08em;
padding: 10px 20px;
cursor: pointer;
width: 100%;
transition: color .2s, border-color .2s;
text-align: left;
}
.add-row-btn:hover { color: var(–gold); border-color: var(–gold-dim); }

/* ─────────────────────────────────────────────
③ DEPARTMENT UPDATES
───────────────────────────────────────────── */
.dept-updates-grid {
display: grid;
grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
gap: 18px;
}
.dept-card {
background: var(–card);
border: 1px solid var(–border);
overflow: hidden;
transition: border-color .2s;
}
.dept-card:hover { border-color: var(–line); }
.dept-card-head {
padding: 16px 22px;
display: flex;
align-items: center;
gap: 12px;
border-bottom: 1px solid var(–border);
}
.dept-icon {
width: 34px; height: 34px;
border-radius: 2px;
display: flex; align-items: center; justify-content: center;
font-size: 16px;
flex-shrink: 0;
}
.dept-card-head .dept-name {
font-family: ‘Barlow Condensed’, sans-serif;
font-weight: 700;
font-size: 18px;
letter-spacing: 0.08em;
text-transform: uppercase;
color: var(–white);
flex: 1;
display: block;
min-width: 10px;
}
.dept-badge {
font-family: ‘JetBrains Mono’, monospace;
font-size: 9px;
letter-spacing: 0.1em;
text-transform: uppercase;
padding: 3px 8px;
border-radius: 2px;
flex-shrink: 0;
}
.badge-green { background: rgba(40,201,122,0.15); color: var(–green); }
.badge-amber { background: rgba(232,144,10,0.15); color: var(–amber); }
.badge-red   { background: rgba(232,64,64,0.15);  color: var(–red);   }
.badge-blue  { background: rgba(32,144,232,0.15); color: var(–blue);  }

.dept-card-body { padding: 18px 22px; }
.dept-card-body .update-text {
font-size: 14px;
line-height: 1.75;
color: var(–text);
min-height: 60px;
display: block;
}
.dept-card-body .update-meta {
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
color: var(–muted);
letter-spacing: 0.07em;
margin-top: 14px;
padding-top: 12px;
border-top: 1px solid var(–border);
display: flex;
justify-content: space-between;
align-items: center;
flex-wrap: wrap;
gap: 8px;
}
.update-meta span { display: block; min-width: 10px; }
.update-meta .label { color: var(–muted); font-size: 9px; letter-spacing: 0.08em; }
.update-meta .val { color: var(–text); min-width: 10px; }

/* ─────────────────────────────────────────────
PRINT / EXPORT BAR
───────────────────────────────────────────── */
.action-bar {
background: var(–surface);
border-top: 1px solid var(–border);
padding: 14px 48px;
display: flex;
justify-content: space-between;
align-items: center;
position: sticky;
bottom: 0;
z-index: 50;
}
.action-bar .hint {
font-family: ‘JetBrains Mono’, monospace;
font-size: 11px;
color: var(–muted);
letter-spacing: 0.06em;
}
.action-bar .hint strong { color: var(–gold); }
.action-btn {
background: var(–gold);
border: none;
color: #000;
font-family: ‘Barlow Condensed’, sans-serif;
font-weight: 700;
font-size: 14px;
letter-spacing: 0.1em;
text-transform: uppercase;
padding: 10px 24px;
cursor: pointer;
transition: opacity .2s;
border-radius: 2px;
}
.action-btn:hover { opacity: 0.85; }
.action-btn.secondary {
background: transparent;
border: 1px solid var(–border);
color: var(–muted);
}
.action-btn.secondary:hover { color: var(–white); border-color: var(–line); }
.btn-group { display: flex; gap: 10px; }

/* ─────────────────────────────────────────────
PRINT STYLES
───────────────────────────────────────────── */
@media print {
.action-bar, .edit-hint { display: none !important; }
body { background: white; color: #111; }
.masthead, .nav-strip { background: white; }
[contenteditable]:hover, [contenteditable]:focus { background: transparent; box-shadow: none; }
}

/* ─────────────────────────────────────────────
RESPONSIVE
───────────────────────────────────────────── */
@media (max-width: 768px) {
.masthead { grid-template-columns: 1fr; padding: 20px 24px; }
.mast-brand { border-right: none; padding-right: 0; }
.mast-meta { border-left: none; align-items: flex-start; padding-left: 0; }
.nav-strip { padding: 0 24px; }
.wrapper { padding: 28px 20px 80px; }
.project-grid { grid-template-columns: 1fr; }
.dept-updates-grid { grid-template-columns: 1fr; }
.action-bar { padding: 14px 24px; }
}
</style>

</head>
<body>

<!-- ── MASTHEAD ── -->

<div class="masthead">
  <div class="mast-brand">
    <div class="brand-icon">GG</div>
    <div class="brand-text">
      <div class="brand-name">Ghana National Gas</div>
      <div class="brand-sub">Company Limited</div>
    </div>
  </div>
  <div class="mast-title">
    <h1>SITE BRIEF <span contenteditable="true">MONTHLY</span></h1>
  </div>
  <div class="mast-meta">
    <div class="issue" contenteditable="true">ISSUE 001</div>
    <div class="date" contenteditable="true">APRIL 2026</div>
    <div class="date" style="font-size:9px; margin-top:4px;" contenteditable="true">Technical Department</div>
  </div>
</div>

<!-- ── NAV ── -->

<nav class="nav-strip">
  <a href="#section-projects">Projects</a>
  <a href="#section-flowrate">Gas Flow Rates</a>
  <a href="#section-community">Community</a>
  <a href="#section-roads">Roads</a>
  <a href="#section-pipeline">Pipeline</a>
  <a href="#section-facilities">Facilities</a>
  <a href="#section-technical">Technical Services</a>
</nav>

<div class="wrapper">

<!-- ══════════════════════════════════════════
     ① PROJECT PROGRESS DASHBOARD
══════════════════════════════════════════ -->

<div id="section-projects" class="section-head">
  <div class="sh-num">01</div>
  <div class="sh-text">
    <h2>Project Progress Dashboard</h2>
    <p>Click the name or status to edit · Use + / − to adjust completion</p>
  </div>
  <div class="sh-rule"></div>
</div>

<div class="project-grid" id="project-grid">
  <!-- Cards injected by JS -->
</div>

<!-- ══════════════════════════════════════════
     ② GAS FLOW RATE TRACKER
══════════════════════════════════════════ -->

<div id="section-flowrate" class="section-head">
  <div class="sh-num">02</div>
  <div class="sh-text">
    <h2>Gas Flow Rate Register</h2>
    <p>Click any value or remark to edit · All values in MMscfd unless specified</p>
  </div>
  <div class="sh-rule"></div>
</div>

<div class="flow-table-wrap">
  <table class="flow-table">
    <thead>
      <tr>
        <th>#</th>
        <th>Gas Stream / Line</th>
        <th>Flow Rate</th>
        <th>Unit</th>
        <th>Status</th>
        <th>Remarks</th>
        <th>Recorded</th>
      </tr>
    </thead>
    <tbody id="flow-tbody">
      <!-- rows injected by JS -->
    </tbody>
  </table>
  <button class="add-row-btn" onclick="addFlowRow()">
    ＋ &nbsp; Add Gas Stream
  </button>
</div>

<!-- ══════════════════════════════════════════
     ③ DEPARTMENT UPDATES
══════════════════════════════════════════ -->

<!-- COMMUNITY -->

<div id="section-community" class="section-head">
  <div class="sh-num">03</div>
  <div class="sh-text">
    <h2>Community Updates</h2>
    <p>Click any text field to edit</p>
  </div>
  <div class="sh-rule"></div>
</div>

<div class="dept-updates-grid">
  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(0,194,168,0.15); color:var(--teal);">🏘</div>
      <span class="dept-name" contenteditable="true">Community Liaison</span>
      <span class="dept-badge badge-green" contenteditable="true">Active</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        The quarterly Community Liaison Forum was held successfully. Key concerns raised by host community representatives centred on local content employment and the ongoing borehole project. Management responses have been formally documented and will be communicated within 14 days. The community borehole remains on track for commissioning by end of May 2026.
      </span>
      <div class="update-meta">
        <div><div class="label">Lead Officer</div><span class="val" contenteditable="true">[Name]</span></div>
        <div><div class="label">Next Forum</div><span class="val" contenteditable="true">July 2026</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>

  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(232,160,32,0.15); color:var(--gold);">🌱</div>
      <span class="dept-name" contenteditable="true">CSR / Tree Planting</span>
      <span class="dept-badge badge-amber" contenteditable="true">Ongoing</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        Tree planting exercise in collaboration with neighbouring conservation areas is progressing. A total of [number] seedlings have been planted to date as part of the company's environmental stewardship commitments. Further planting drives are scheduled for the coming month.
      </span>
      <div class="update-meta">
        <div><div class="label">Lead Officer</div><span class="val" contenteditable="true">[Name]</span></div>
        <div><div class="label">Target</div><span class="val" contenteditable="true">[Date]</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>

  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(32,144,232,0.15); color:var(--blue);">📋</div>
      <span class="dept-name" contenteditable="true">Stakeholder Engagement</span>
      <span class="dept-badge badge-blue" contenteditable="true">Scheduled</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        A Parliamentary Select Committee on Energy conducted a guided visit to the Gas Processing Plant and Automated Metering and Custody Transfer Stations. The visit highlighted key operational milestones and fostered productive policy-level dialogue between the company and parliamentary oversight.
      </span>
      <div class="update-meta">
        <div><div class="label">Lead Officer</div><span class="val" contenteditable="true">[Name]</span></div>
        <div><div class="label">Next Meeting</div><span class="val" contenteditable="true">[Date]</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>
</div>

<!-- ROADS -->

<div id="section-roads" class="section-head">
  <div class="sh-num">04</div>
  <div class="sh-text">
    <h2>Roads</h2>
    <p>Click any text field to edit</p>
  </div>
  <div class="sh-rule"></div>
</div>

<div class="dept-updates-grid">
  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(232,144,10,0.15); color:var(--amber);">🛣</div>
      <span class="dept-name" contenteditable="true">Road Works Update</span>
      <span class="dept-badge badge-amber" contenteditable="true">In Progress</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        Road construction activities are progressing on schedule. Surface dressing of the primary access route has been completed up to [KM point]. Drainage works on the secondary section are ongoing. Traffic management protocols remain in place for the duration of active works.
      </span>
      <div class="update-meta">
        <div><div class="label">Contractor</div><span class="val" contenteditable="true">[Contractor Name]</span></div>
        <div><div class="label">Completion</div><span class="val" contenteditable="true">[Target Date]</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>

  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(40,201,122,0.15); color:var(--green);">🚧</div>
      <span class="dept-name" contenteditable="true">Road Maintenance</span>
      <span class="dept-badge badge-green" contenteditable="true">Normal</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        Routine maintenance inspections were carried out this month. Pothole patching on the [specify road name] was completed. No major structural defects were identified during inspection. The next scheduled inspection is due in [Month].
      </span>
      <div class="update-meta">
        <div><div class="label">Inspector</div><span class="val" contenteditable="true">[Name]</span></div>
        <div><div class="label">Next Inspection</div><span class="val" contenteditable="true">[Date]</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>
</div>

<!-- PIPELINE -->

<div id="section-pipeline" class="section-head">
  <div class="sh-num">05</div>
  <div class="sh-text">
    <h2>Pipeline</h2>
    <p>Click any text field to edit</p>
  </div>
  <div class="sh-rule"></div>
</div>

<div class="dept-updates-grid">
  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(40,201,122,0.15); color:var(--green);">🔩</div>
      <span class="dept-name" contenteditable="true">Integrity Management</span>
      <span class="dept-badge badge-green" contenteditable="true">Satisfactory</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        Q1 pipeline integrity survey results have been reviewed. No critical anomalies were detected across the inspected segments. Two minor indications recorded at [KP location] are being tracked for trending purposes and will be re-assessed in Q3. The next IMP survey is scheduled in line with the approved integrity calendar.
      </span>
      <div class="update-meta">
        <div><div class="label">Report Ref</div><span class="val" contenteditable="true">IMP-Q1-2026</span></div>
        <div><div class="label">Next Survey</div><span class="val" contenteditable="true">Q3 2026</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>

  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(232,64,64,0.15); color:var(--red);">⚠</div>
      <span class="dept-name" contenteditable="true">Pipeline Anomaly Watch</span>
      <span class="dept-badge badge-amber" contenteditable="true">Monitoring</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        [Describe any anomaly or monitoring activity here. Include the location reference, nature of observation, current action taken, and expected resolution date. If there are no active anomalies, note "No anomalies recorded this period."]
      </span>
      <div class="update-meta">
        <div><div class="label">Location</div><span class="val" contenteditable="true">[KP Ref]</span></div>
        <div><div class="label">Resolution ETA</div><span class="val" contenteditable="true">[Date]</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>
</div>

<!-- FACILITIES -->

<div id="section-facilities" class="section-head">
  <div class="sh-num">06</div>
  <div class="sh-text">
    <h2>Facilities</h2>
    <p>Click any text field to edit</p>
  </div>
  <div class="sh-rule"></div>
</div>

<div class="dept-updates-grid">
  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(232,160,32,0.15); color:var(--gold);">🏗</div>
      <span class="dept-name" contenteditable="true">Facilities Maintenance</span>
      <span class="dept-badge badge-amber" contenteditable="true">Active Works</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        Planned upgrade works to the main site canteen commenced on April 28. The facility is operating at reduced capacity during the works period. A temporary catering arrangement is in place. Works are scheduled for completion by May 19, 2026. Inconvenience to staff is acknowledged and regretted.
      </span>
      <div class="update-meta">
        <div><div class="label">Start Date</div><span class="val" contenteditable="true">28 Apr 2026</span></div>
        <div><div class="label">End Date</div><span class="val" contenteditable="true">19 May 2026</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>

  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(0,194,168,0.15); color:var(--teal);">🏢</div>
      <span class="dept-name" contenteditable="true">Accommodation &amp; Utilities</span>
      <span class="dept-badge badge-green" contenteditable="true">Normal</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        All accommodation blocks and utility services are operating normally. Water supply, power backup systems, and general site services are within acceptable parameters. Routine cleaning and maintenance schedules are being observed. No service disruptions were recorded this period.
      </span>
      <div class="update-meta">
        <div><div class="label">Officer</div><span class="val" contenteditable="true">[Name]</span></div>
        <div><div class="label">Inspection</div><span class="val" contenteditable="true">[Last Date]</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>
</div>

<!-- TECHNICAL SERVICES -->

<div id="section-technical" class="section-head">
  <div class="sh-num">07</div>
  <div class="sh-text">
    <h2>Technical Services</h2>
    <p>Engineering, HSE, Projects &amp; other technical updates</p>
  </div>
  <div class="sh-rule"></div>
</div>

<div class="dept-updates-grid">
  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(32,144,232,0.15); color:var(--blue);">⚙</div>
      <span class="dept-name" contenteditable="true">Engineering</span>
      <span class="dept-badge badge-amber" contenteditable="true">Attention</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        Generator 2 overhaul was completed three days ahead of schedule. All inspection points were cleared and the unit has returned to full load capacity. Separately, elevated vibration readings noted on Pump Station 4 are under root cause analysis. Operational restriction on the associated line remains until clearance is issued.
      </span>
      <div class="update-meta">
        <div><div class="label">Open Items</div><span class="val" contenteditable="true">1</span></div>
        <div><div class="label">Resolution ETA</div><span class="val" contenteditable="true">22 Apr 2026</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>

  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(232,64,64,0.15); color:var(--red);">🦺</div>
      <span class="dept-name" contenteditable="true">HSE</span>
      <span class="dept-badge badge-amber" contenteditable="true">Action Required</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        Three near-miss incidents were reported and captured in the incident management system this month. Root cause analyses are underway and corrective action plans have been assigned to respective department heads. The site has recorded [X] LTI-free days. Q2 Emergency Response Drill is scheduled for May 8, 2026. All departments are required to participate.
      </span>
      <div class="update-meta">
        <div><div class="label">LTI-Free Days</div><span class="val" contenteditable="true">47</span></div>
        <div><div class="label">Drill Date</div><span class="val" contenteditable="true">08 May 2026</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>

  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(0,194,168,0.15); color:var(--teal);">📐</div>
      <span class="dept-name" contenteditable="true">Projects</span>
      <span class="dept-badge badge-blue" contenteditable="true">Procurement</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        Engineering design for the flare tip replacement has been finalised and approved by the Projects Review Board. Procurement of long-lead items is currently in progress with delivery expected in Q3 2026. Installation is planned during the next scheduled plant turnaround. All other project activities are proceeding as planned.
      </span>
      <div class="update-meta">
        <div><div class="label">Project Code</div><span class="val" contenteditable="true">PROJ-041</span></div>
        <div><div class="label">Procure ETA</div><span class="val" contenteditable="true">Q3 2026</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>

  <div class="dept-card">
    <div class="dept-card-head">
      <div class="dept-icon" style="background:rgba(232,160,32,0.15); color:var(--gold);">🔧</div>
      <span class="dept-name" contenteditable="true">Other Technical Services</span>
      <span class="dept-badge badge-green" contenteditable="true">Normal</span>
    </div>
    <div class="dept-card-body">
      <span class="update-text" contenteditable="true">
        [Add update here — describe any technical service activity, maintenance programme, or operational note relevant to the period. Replace placeholder text with actual update.]
      </span>
      <div class="update-meta">
        <div><div class="label">Lead</div><span class="val" contenteditable="true">[Name]</span></div>
        <div><div class="label">Ref</div><span class="val" contenteditable="true">[Ref No.]</span></div>
        <div><div class="label">Updated</div><span class="val" contenteditable="true">Apr 2026</span></div>
      </div>
    </div>
  </div>
</div>

</div><!-- end wrapper -->

<!-- ── ACTION BAR ── -->

<div class="action-bar">
  <div class="hint"><strong>✎ EDITING ON</strong> &nbsp;·&nbsp; Click any text to edit · Use +/− on project cards to update progress</div>
  <div class="btn-group">
    <button class="action-btn secondary" onclick="window.print()">Print / Export PDF</button>
    <button class="action-btn" onclick="saveToLocal()">💾 Save Progress</button>
  </div>
</div>

<script>
/* ─────────────────────────────────────────────
   PROJECT DATA
───────────────────────────────────────────── */
const projects = [
  { name: "Roads",              status: "In Progress",  pct: 45 },
  { name: "Gas Village",        status: "In Progress",  pct: 30 },
  { name: "Trauma Centre",      status: "In Progress",  pct: 60 },
  { name: "Trauma Centre Civil Works", status: "In Progress", pct: 25 },
  { name: "LPG Bottling Plant", status: "In Progress",  pct: 50 },
  { name: "Teachers Quarters",  status: "In Progress",  pct: 40 },
  { name: "Gas Lodge",          status: "In Progress",  pct: 70 },
  { name: "GPP Gym",            status: "In Progress",  pct: 55 },
  { name: "Astroturf",          status: "In Progress",  pct: 80 },
  { name: "Esiama Market",      status: "In Progress",  pct: 20 },
];

/* ─────────────────────────────────────────────
   GAS FLOW DATA (10 streams)
───────────────────────────────────────────── */
const gasStreams = [
  { name: "Inlet Gas Feed — GPP",           rate: "120.5", unit: "MMscfd", status: "g", remark: "Stable. Within design envelope.", date: "Apr 17" },
  { name: "Rich Gas Export — Train 1",      rate: "42.8",  unit: "MMscfd", status: "g", remark: "Normal operations.", date: "Apr 17" },
  { name: "Rich Gas Export — Train 2",      rate: "39.1",  unit: "MMscfd", status: "g", remark: "Normal operations.", date: "Apr 17" },
  { name: "Lean Gas — WAGP Delivery Point", rate: "78.4",  unit: "MMscfd", status: "a", remark: "Slight deviation. Under review.", date: "Apr 17" },
  { name: "LPG Stream — Splitter",          rate: "8.20",  unit: "MMscfd", status: "g", remark: "On spec.", date: "Apr 17" },
  { name: "Fuel Gas — Site Consumption",    rate: "3.50",  unit: "MMscfd", status: "g", remark: "Within budget.", date: "Apr 17" },
  { name: "Flare Header",                   rate: "0.80",  unit: "MMscfd", status: "a", remark: "Elevated. Flare tip investigation pending.", date: "Apr 17" },
  { name: "Gas Condensate — Recovery",      rate: "2.10",  unit: "MMscfd", status: "g", remark: "Recovering normally.", date: "Apr 17" },
  { name: "Custody Transfer — Takoradi",    rate: "55.0",  unit: "MMscfd", status: "g", remark: "Metering cross-checked. OK.", date: "Apr 17" },
  { name: "Emergency Bypass Line",          rate: "0.00",  unit: "MMscfd", status: "g", remark: "Standby. Not in service.", date: "Apr 17" },
];

/* ─────────────────────────────────────────────
   HELPERS
───────────────────────────────────────────── */
function pctClass(v) {
  if (v >= 100) return 'done';
  if (v >= 60)  return 'hi';
  if (v >= 30)  return 'mid';
  return 'low';
}
function fillClass(v) {
  if (v >= 100) return 'fill-done';
  if (v >= 60)  return 'fill-hi';
  if (v >= 30)  return 'fill-mid';
  return 'fill-low';
}
function statusLabel(s) {
  if (v >= 100) return 'Completed';
  return s;
}
function dotClass(s) {
  if (s === 'g') return 'dot-g';
  if (s === 'a') return 'dot-a';
  return 'dot-r';
}
function dotLabel(s) {
  if (s === 'g') return '<span class="status-txt" style="color:var(--green)">Normal</span>';
  if (s === 'a') return '<span class="status-txt" style="color:var(--amber)">Monitor</span>';
  return '<span class="status-txt" style="color:var(--red)">Alert</span>';
}

/* ─────────────────────────────────────────────
   RENDER PROJECTS
───────────────────────────────────────────── */
function renderProjects() {
  const grid = document.getElementById('project-grid');
  grid.innerHTML = '';
  projects.forEach((p, i) => {
    const cls = pctClass(p.pct);
    const fc  = fillClass(p.pct);
    const card = document.createElement('div');
    card.className = 'proj-card';
    card.innerHTML = `
      <span class="proj-name" contenteditable="true" oninput="projects[${i}].name=this.innerText">${p.name}</span>
      <span class="proj-status" contenteditable="true" oninput="projects[${i}].status=this.innerText">${p.status}</span>
      <div class="proj-bar-track" title="Click +/− to adjust">
        <div class="proj-bar-fill ${fc}" id="bar-fill-${i}" style="width:${p.pct}%"></div>
      </div>
      <div class="proj-pct-row">
        <span class="proj-pct pct-${cls}" id="pct-txt-${i}">${p.pct}%</span>
        <div class="pct-controls">
          <div class="proj-pct-label">completion</div>
          <button class="pct-btn" onclick="adjustPct(${i},-5)">−</button>
          <button class="pct-btn" onclick="adjustPct(${i},+5)">+</button>
        </div>
      </div>
    `;
    grid.appendChild(card);
  });
}

function adjustPct(i, delta) {
  projects[i].pct = Math.max(0, Math.min(100, projects[i].pct + delta));
  const v   = projects[i].pct;
  const cls = pctClass(v);
  const fc  = fillClass(v);
  const fill = document.getElementById(`bar-fill-${i}`);
  const txt  = document.getElementById(`pct-txt-${i}`);
  fill.style.width = v + '%';
  fill.className = 'proj-bar-fill ' + fc;
  txt.textContent = v + '%';
  txt.className = 'proj-pct pct-' + cls;
  if (v >= 100) projects[i].status = 'Completed';
}

/* ─────────────────────────────────────────────
   RENDER FLOW TABLE
───────────────────────────────────────────── */
function renderFlow() {
  const tbody = document.getElementById('flow-tbody');
  tbody.innerHTML = '';
  gasStreams.forEach((g, i) => {
    const tr = document.createElement('tr');
    tr.innerHTML = `
      <td style="color:var(--muted); font-family:'JetBrains Mono',monospace; font-size:11px;">${String(i+1).padStart(2,'0')}</td>
      <td contenteditable="true" oninput="gasStreams[${i}].name=this.innerText">${g.name}</td>
      <td>
        <span class="flow-val" contenteditable="true" oninput="gasStreams[${i}].rate=this.innerText">${g.rate}</span>
        <span class="flow-unit">${g.unit}</span>
      </td>
      <td><span class="flow-unit" contenteditable="true" oninput="gasStreams[${i}].unit=this.innerText">${g.unit}</span></td>
      <td>
        <span class="status-dot ${dotClass(g.status)}"></span>
        ${dotLabel(g.status)}
      </td>
      <td class="flow-note" contenteditable="true" oninput="gasStreams[${i}].remark=this.innerText">${g.remark}</td>
      <td style="font-family:'JetBrains Mono',monospace; font-size:10px; color:var(--muted);" contenteditable="true" oninput="gasStreams[${i}].date=this.innerText">${g.date}</td>
    `;
    tbody.appendChild(tr);
  });
}

function addFlowRow() {
  gasStreams.push({ name: "New Gas Stream", rate: "0.00", unit: "MMscfd", status: "g", remark: "Enter remarks here.", date: "—" });
  renderFlow();
  // scroll to new row
  document.getElementById('flow-tbody').lastChild.scrollIntoView({ behavior: 'smooth', block: 'center' });
}

/* ─────────────────────────────────────────────
   SAVE / LOAD (localStorage)
───────────────────────────────────────────── */
function saveToLocal() {
  // capture all contenteditable text
  const editables = document.querySelectorAll('[contenteditable]');
  const savedTexts = Array.from(editables).map(el => el.innerHTML);
  localStorage.setItem('sitebrief_projects', JSON.stringify(projects));
  localStorage.setItem('sitebrief_gas', JSON.stringify(gasStreams));
  localStorage.setItem('sitebrief_html', savedTexts.join('|||SPLIT|||'));
  const btn = document.querySelector('.action-btn:not(.secondary)');
  btn.textContent = '✓ Saved!';
  setTimeout(() => { btn.textContent = '💾 Save Progress'; }, 2000);
}

function loadFromLocal() {
  try {
    const p = localStorage.getItem('sitebrief_projects');
    const g = localStorage.getItem('sitebrief_gas');
    const h = localStorage.getItem('sitebrief_html');
    if (p) { const d = JSON.parse(p); d.forEach((x,i) => projects[i] = x); }
    if (g) { const d = JSON.parse(g); d.forEach((x,i) => gasStreams[i] = x); gasStreams.length = d.length; }
    if (h) {
      const parts = h.split('|||SPLIT|||');
      const editables = document.querySelectorAll('[contenteditable]');
      editables.forEach((el, i) => { if (parts[i] !== undefined) el.innerHTML = parts[i]; });
    }
  } catch(e) { console.log('No saved data.'); }
}

/* ─────────────────────────────────────────────
   INIT
───────────────────────────────────────────── */
renderProjects();
renderFlow();
loadFromLocal();
</script>

</body>
</html>
