# VigilantPath
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VigilantPath — Security For Everyone</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@300;400;500&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #04080f;
  --surface: #0a1220;
  --surface2: #0f1a2e;
  --border: #162540;
  --accent: #00d4ff;
  --accent2: #0af5a0;
  --danger: #ff3d5a;
  --warn: #ffb020;
  --text: #e8f4ff;
  --muted: #4a6f8a;
  --glow: 0 0 30px rgba(0,212,255,0.25);
  --glow-green: 0 0 20px rgba(10,245,160,0.25);
  --glow-red: 0 0 20px rgba(255,61,90,0.3);
}
* { margin:0; padding:0; box-sizing:border-box; }
html { scroll-behavior: smooth; }
body {
  font-family: 'DM Sans', sans-serif;
  background: var(--bg);
  color: var(--text);
  overflow-x: hidden;
}
body::before {
  content:'';
  position:fixed; inset:0;
  background-image:
    linear-gradient(rgba(0,212,255,0.025) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0,212,255,0.025) 1px, transparent 1px);
  background-size: 50px 50px;
  pointer-events:none; z-index:0;
}

/* ── NAV ── */
nav {
  position: fixed; top:0; left:0; right:0; z-index:200;
  background: rgba(4,8,15,0.85);
  backdrop-filter: blur(16px);
  border-bottom: 1px solid var(--border);
  padding: 0 60px;
  display: flex; align-items: center; height: 64px;
}
.nav-logo {
  font-family:'Syne',sans-serif; font-weight:800; font-size:20px;
  color: var(--accent); display:flex; align-items:center; gap:10px;
  text-decoration:none; flex-shrink:0;
}
.nav-logo-icon {
  width:34px; height:34px; border-radius:8px;
  background: linear-gradient(135deg,var(--accent),var(--accent2));
  display:flex; align-items:center; justify-content:center;
  font-size:17px; box-shadow:var(--glow);
}
.nav-links { display:flex; gap:4px; margin-left:40px; flex:1; }
.nav-link {
  padding:8px 16px; border-radius:6px;
  font-size:13.5px; color:var(--muted); cursor:pointer;
  border:none; background:none; transition:all 0.2s;
  font-family:'DM Sans',sans-serif;
}
.nav-link:hover, .nav-link.active { color:var(--text); background:var(--surface2); }
.nav-cta {
  background: var(--accent); color:#000;
  border:none; border-radius:8px;
  padding:9px 22px; font-size:13px; font-weight:700;
  font-family:'Syne',sans-serif; cursor:pointer;
  box-shadow:var(--glow); transition:all 0.2s;
  margin-left:auto;
}
.nav-cta:hover { background:#33ddff; transform:translateY(-1px); }

/* ── SECTIONS ── */
section { position:relative; z-index:1; }
.section-inner { max-width:1200px; margin:0 auto; padding:0 40px; }

/* ── HERO ── */
#home {
  min-height: 100vh;
  display:flex; align-items:center;
  padding-top:64px;
  overflow:hidden;
}
.hero-wrap {
  max-width:1200px; margin:0 auto; padding:80px 40px;
  display:grid; grid-template-columns:1fr 1fr; gap:60px; align-items:center;
}
.hero-tag {
  display:inline-flex; align-items:center; gap:8px;
  background:rgba(0,212,255,0.08); border:1px solid rgba(0,212,255,0.2);
  border-radius:20px; padding:5px 14px; margin-bottom:24px;
  font-size:11px; font-family:'DM Mono',monospace; color:var(--accent);
  letter-spacing:1px; text-transform:uppercase;
}
.hero-tag-dot { width:6px; height:6px; border-radius:50%; background:var(--accent2); animation:pulse 1.5s infinite; }
@keyframes pulse { 0%,100%{opacity:1;box-shadow:0 0 0 0 rgba(10,245,160,0.6);}50%{opacity:.8;box-shadow:0 0 0 5px rgba(10,245,160,0);} }
.hero-title {
  font-family:'Syne',sans-serif; font-size:58px; font-weight:800;
  line-height:1.05; letter-spacing:-2px; margin-bottom:16px;
}
.hero-title .hl { color:var(--accent); }
.hero-title .hl2 { color:var(--accent2); }
.hero-motto {
  font-family:'DM Mono',monospace; font-size:13px;
  color:var(--accent2); letter-spacing:3px; text-transform:uppercase;
  margin-bottom:24px; display:flex; align-items:center; gap:10px;
}
.hero-motto::before, .hero-motto::after {
  content:''; flex:1; max-width:40px; height:1px; background:var(--accent2); opacity:0.4;
}
.hero-desc {
  font-size:16px; color:var(--muted); line-height:1.75;
  margin-bottom:36px; max-width:480px;
}
.hero-btns { display:flex; gap:12px; flex-wrap:wrap; }
.btn-primary {
  background:var(--accent); color:#000; border:none;
  border-radius:10px; padding:14px 28px;
  font-family:'Syne',sans-serif; font-size:14px; font-weight:700;
  cursor:pointer; box-shadow:var(--glow); transition:all 0.2s;
}
.btn-primary:hover { background:#33ddff; transform:translateY(-2px); box-shadow:0 0 40px rgba(0,212,255,0.4); }
.btn-outline {
  background:transparent; color:var(--text);
  border:1px solid var(--border); border-radius:10px;
  padding:14px 28px; font-family:'Syne',sans-serif;
  font-size:14px; font-weight:600; cursor:pointer; transition:all 0.2s;
}
.btn-outline:hover { border-color:var(--accent); color:var(--accent); }
.hero-stats { display:flex; gap:32px; margin-top:48px; }
.hero-stat-val { font-family:'Syne',sans-serif; font-size:28px; font-weight:800; }
.hero-stat-label { font-size:11px; color:var(--muted); font-family:'DM Mono',monospace; margin-top:2px; }

/* Hero right — live threat widget */
.hero-visual {
  background:var(--surface); border:1px solid var(--border);
  border-radius:16px; padding:20px; position:relative;
  box-shadow: 0 0 60px rgba(0,212,255,0.05);
}
.hero-visual-title {
  font-family:'DM Mono',monospace; font-size:11px; color:var(--muted);
  text-transform:uppercase; letter-spacing:1px; margin-bottom:16px;
  display:flex; align-items:center; justify-content:space-between;
}
.live-pill {
  background:rgba(255,61,90,0.15); color:var(--danger);
  border:1px solid rgba(255,61,90,0.3); border-radius:20px;
  padding:2px 10px; font-size:10px; animation:badge-pulse 2s infinite;
}
@keyframes badge-pulse{0%,100%{box-shadow:0 0 0 0 rgba(255,61,90,.4);}50%{box-shadow:0 0 0 5px rgba(255,61,90,0);}}
.global-counter {
  text-align:center; padding:16px 0;
  border-bottom:1px solid var(--border); margin-bottom:16px;
}
.counter-val {
  font-family:'Syne',sans-serif; font-size:52px; font-weight:800;
  color:var(--danger); letter-spacing:-2px; line-height:1;
}
.counter-label { font-size:11px; color:var(--muted); font-family:'DM Mono',monospace; margin-top:6px; }
.mini-feed { display:flex; flex-direction:column; gap:7px; }
.mini-feed-item {
  display:flex; align-items:center; gap:10px;
  padding:8px 10px; border-radius:8px;
  background:var(--surface2); font-size:11.5px;
  border-left:3px solid var(--border);
  animation:feedIn 0.5s ease;
}
@keyframes feedIn{from{opacity:0;transform:translateY(-12px);}to{opacity:1;transform:translateY(0);}}
.mini-feed-item.c { border-left-color:var(--danger); }
.mini-feed-item.w { border-left-color:var(--warn); }
.mini-feed-item.g { border-left-color:var(--accent2); }
.feed-flag { font-size:16px; flex-shrink:0; }
.feed-info { flex:1; }
.feed-info-title { font-size:12px; font-weight:500; }
.feed-info-sub { font-size:10px; color:var(--muted); font-family:'DM Mono',monospace; }
.feed-sev {
  font-size:9px; padding:2px 7px; border-radius:3px;
  font-family:'DM Mono',monospace; flex-shrink:0;
}
.feed-sev.c { background:rgba(255,61,90,.15); color:var(--danger); }
.feed-sev.w { background:rgba(255,176,32,.15); color:var(--warn); }
.feed-sev.g { background:rgba(10,245,160,.1); color:var(--accent2); }

/* ── GLOBAL THREAT SECTION ── */
#threats {
  padding: 100px 0;
  background: linear-gradient(180deg, var(--bg) 0%, var(--surface) 50%, var(--bg) 100%);
}
.section-tag {
  display:inline-flex; align-items:center; gap:8px;
  background:rgba(255,61,90,0.08); border:1px solid rgba(255,61,90,0.2);
  border-radius:20px; padding:5px 14px; margin-bottom:20px;
  font-size:11px; font-family:'DM Mono',monospace; color:var(--danger);
  letter-spacing:1px; text-transform:uppercase;
}
.section-title {
  font-family:'Syne',sans-serif; font-size:42px; font-weight:800;
  line-height:1.1; letter-spacing:-1px; margin-bottom:12px;
}
.section-sub { font-size:15px; color:var(--muted); line-height:1.7; max-width:600px; margin-bottom:48px; }

.threat-cards { display:grid; grid-template-columns:repeat(3,1fr); gap:20px; margin-bottom:40px; }
.threat-card {
  background:var(--surface); border:1px solid var(--border);
  border-radius:14px; padding:24px; position:relative; overflow:hidden;
  transition:transform 0.3s, box-shadow 0.3s;
}
.threat-card:hover { transform:translateY(-4px); }
.threat-card::before { content:''; position:absolute; top:0; left:0; right:0; height:2px; }
.tc-red::before { background:var(--danger); box-shadow:var(--glow-red); }
.tc-yellow::before { background:var(--warn); }
.tc-blue::before { background:var(--accent); box-shadow:var(--glow); }
.threat-card-icon { font-size:28px; margin-bottom:12px; }
.threat-card-title { font-family:'Syne',sans-serif; font-size:16px; font-weight:700; margin-bottom:6px; }
.threat-card-stat { font-family:'Syne',sans-serif; font-size:32px; font-weight:800; margin-bottom:4px; }
.threat-card-desc { font-size:12px; color:var(--muted); line-height:1.6; }

/* World map */
.world-wrap {
  background:var(--surface); border:1px solid var(--border);
  border-radius:16px; padding:24px; margin-bottom:20px;
}
.world-header { display:flex; align-items:center; justify-content:space-between; margin-bottom:16px; }
.world-title { font-family:'Syne',sans-serif; font-size:16px; font-weight:700; }
#worldMap { width:100%; height:300px; }

/* Country ranking */
.country-grid { display:grid; grid-template-columns:1fr 1fr; gap:20px; }
.country-panel {
  background:var(--surface); border:1px solid var(--border);
  border-radius:14px; padding:20px;
}
.country-title { font-family:'Syne',sans-serif; font-size:14px; font-weight:700; margin-bottom:16px; display:flex; align-items:center; gap:8px; }
.country-row { display:flex; align-items:center; gap:12px; margin-bottom:10px; }
.country-rank { font-family:'DM Mono',monospace; font-size:11px; color:var(--muted); width:24px; }
.country-flag { font-size:18px; }
.country-name { flex:1; font-size:13px; }
.country-bar-wrap { width:100px; height:6px; background:var(--surface2); border-radius:3px; }
.country-bar { height:100%; border-radius:3px; }
.country-pct { font-family:'DM Mono',monospace; font-size:11px; color:var(--muted); width:36px; text-align:right; }

/* Rising trend chart */
.trend-wrap {
  background:var(--surface); border:1px solid var(--border);
  border-radius:16px; padding:24px;
}
.trend-header { display:flex; align-items:center; justify-content:space-between; margin-bottom:20px; }
.trend-title { font-family:'Syne',sans-serif; font-size:16px; font-weight:700; }
.trend-tabs { display:flex; gap:6px; }
.trend-tab {
  padding:5px 12px; border-radius:6px; border:1px solid var(--border);
  font-size:11px; font-family:'DM Mono',monospace; color:var(--muted);
  cursor:pointer; background:none; transition:all 0.2s;
}
.trend-tab.active { border-color:var(--accent); color:var(--accent); background:rgba(0,212,255,0.06); }
#trendChart { width:100%; height:180px; }

/* ── WHY VIGILANTPATH ── */
#why { padding:100px 0; }
.why-grid { display:grid; grid-template-columns:1fr 1fr; gap:60px; align-items:center; }
.why-text .section-tag { background:rgba(10,245,160,0.08); border-color:rgba(10,245,160,0.2); color:var(--accent2); }
.feature-list { display:flex; flex-direction:column; gap:20px; margin-top:36px; }
.feature-item { display:flex; gap:16px; align-items:flex-start; }
.feature-icon-wrap {
  width:44px; height:44px; border-radius:10px; flex-shrink:0;
  display:flex; align-items:center; justify-content:center; font-size:20px;
  background:rgba(0,212,255,0.08); border:1px solid rgba(0,212,255,0.15);
}
.feature-title { font-family:'Syne',sans-serif; font-size:15px; font-weight:700; margin-bottom:4px; }
.feature-desc { font-size:13px; color:var(--muted); line-height:1.65; }

/* workflow visual */
.workflow-visual {
  display:flex; flex-direction:column; gap:0;
}
.wf-step {
  display:flex; gap:20px; align-items:flex-start;
  position:relative;
}
.wf-step:not(:last-child)::after {
  content:''; position:absolute;
  left:21px; top:44px; width:2px;
  height:calc(100% - 4px);
  background: linear-gradient(var(--accent), transparent);
}
.wf-num {
  width:44px; height:44px; border-radius:50%; flex-shrink:0;
  background:var(--surface2); border:2px solid var(--accent);
  display:flex; align-items:center; justify-content:center;
  font-family:'Syne',sans-serif; font-weight:800; font-size:16px;
  color:var(--accent); box-shadow:var(--glow); z-index:1;
}
.wf-content { padding:10px 0 32px; }
.wf-title { font-family:'Syne',sans-serif; font-size:15px; font-weight:700; margin-bottom:4px; }
.wf-desc { font-size:13px; color:var(--muted); line-height:1.6; }

/* ── SERVICES ── */
#services { padding:100px 0; background: linear-gradient(180deg,var(--bg) 0%,var(--surface) 100%); }
.services-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:20px; }
.service-card {
  background:var(--surface2); border:1px solid var(--border);
  border-radius:14px; padding:28px;
  transition:transform 0.3s, border-color 0.3s, box-shadow 0.3s;
}
.service-card:hover { transform:translateY(-4px); border-color:var(--accent); box-shadow:var(--glow); }
.service-icon { font-size:32px; margin-bottom:16px; }
.service-title { font-family:'Syne',sans-serif; font-size:17px; font-weight:700; margin-bottom:8px; }
.service-desc { font-size:13px; color:var(--muted); line-height:1.7; margin-bottom:16px; }
.service-tag {
  display:inline-block; padding:3px 10px; border-radius:20px;
  font-size:10px; font-family:'DM Mono',monospace;
  background:rgba(0,212,255,0.08); color:var(--accent);
  border:1px solid rgba(0,212,255,0.2);
}

/* ── DASHBOARD PREVIEW ── */
#dashboard { padding:100px 0; }
.dash-preview {
  background:var(--surface); border:1px solid var(--border);
  border-radius:20px; overflow:hidden;
  box-shadow: 0 40px 100px rgba(0,0,0,0.5), var(--glow);
}
.dash-bar {
  background:var(--surface2); padding:10px 16px;
  border-bottom:1px solid var(--border);
  display:flex; align-items:center; gap:8px;
}
.dash-dot { width:10px; height:10px; border-radius:50%; }
.dash-title-bar { margin-left:auto; font-size:11px; color:var(--muted); font-family:'DM Mono',monospace; }
.dash-content { padding:20px; display:grid; grid-template-columns:1fr 1fr 1fr 1fr; gap:12px; }
.dash-mini-card {
  background:var(--surface2); border:1px solid var(--border);
  border-radius:10px; padding:14px;
}
.dash-mini-label { font-size:9px; text-transform:uppercase; letter-spacing:1px; color:var(--muted); font-family:'DM Mono',monospace; }
.dash-mini-val { font-family:'Syne',sans-serif; font-size:24px; font-weight:800; margin-top:6px; }
.dash-bottom { padding:0 20px 20px; display:grid; grid-template-columns:2fr 1fr; gap:12px; }
.dash-chart-area {
  background:var(--surface2); border:1px solid var(--border);
  border-radius:10px; padding:14px; height:130px;
}
.dash-chart-label { font-size:9px; color:var(--muted); font-family:'DM Mono',monospace; margin-bottom:8px; text-transform:uppercase; letter-spacing:1px; }
.dash-list-area {
  background:var(--surface2); border:1px solid var(--border);
  border-radius:10px; padding:14px;
}
.dash-list-item {
  display:flex; align-items:center; gap:8px;
  padding:5px 0; border-bottom:1px solid var(--border);
  font-size:11px;
}
.dash-list-item:last-child { border:none; }
.dash-dot2 { width:6px; height:6px; border-radius:50%; flex-shrink:0; }

/* ── PLANS ── */
#plans { padding:100px 0; background:linear-gradient(180deg,var(--bg) 0%,var(--surface) 100%); }
.plans-tag { background:rgba(0,212,255,0.08); border-color:rgba(0,212,255,0.2); color:var(--accent); }
.plan-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:20px; margin-top:48px; }
.plan-card {
  background:var(--surface2); border:1px solid var(--border);
  border-radius:16px; padding:28px; position:relative; overflow:hidden;
  transition:transform 0.3s, box-shadow 0.3s;
}
.plan-card:hover { transform:translateY(-4px); }
.plan-card.featured { border-color:var(--accent); box-shadow:var(--glow), inset 0 0 80px rgba(0,212,255,0.03); }
.plan-card.featured::after {
  content:'MOST POPULAR';
  position:absolute; top:0; right:0;
  background:var(--accent); color:#000;
  font-size:9px; font-family:'DM Mono',monospace; font-weight:700; letter-spacing:1px;
  padding:5px 14px; border-bottom-left-radius:8px;
}
.plan-name { font-family:'Syne',sans-serif; font-size:20px; font-weight:800; margin-bottom:4px; }
.plan-tagline { font-size:12px; color:var(--muted); margin-bottom:20px; }
.plan-price { font-family:'Syne',sans-serif; font-size:40px; font-weight:800; }
.plan-price small { font-size:14px; color:var(--muted); font-weight:400; }
.plan-divider { border:none; border-top:1px solid var(--border); margin:20px 0; }
.plan-feat { display:flex; align-items:center; gap:10px; font-size:13px; margin-bottom:10px; color:var(--muted); }
.plan-feat.y { color:var(--text); }
.plan-feat .ck { color:var(--accent2); font-size:14px; }
.plan-feat .xk { color:var(--border); }
.plan-btn2 {
  display:block; width:100%; margin-top:24px;
  padding:13px; border-radius:10px;
  font-family:'Syne',sans-serif; font-size:14px; font-weight:700;
  cursor:pointer; transition:all 0.2s; border:none; text-align:center;
}
.pb-filled { background:var(--accent); color:#000; box-shadow:var(--glow); }
.pb-filled:hover { background:#33ddff; }
.pb-outline { background:transparent; color:var(--accent); border:1px solid rgba(0,212,255,0.3); }
.pb-outline:hover { background:rgba(0,212,255,0.06); }
.pb-dark { background:var(--surface); color:var(--text); border:1px solid var(--border); }
.pb-dark:hover { border-color:var(--accent); color:var(--accent); }

/* ── TEAM ── */
#team { padding:100px 0; }
.team-tag { background:rgba(10,245,160,0.08); border-color:rgba(10,245,160,0.2); color:var(--accent2); }
.team-grid { display:grid; grid-template-columns:repeat(4,1fr); gap:16px; margin-top:48px; }
.team-card {
  background:var(--surface); border:1px solid var(--border);
  border-radius:14px; padding:20px; text-align:center;
  transition:transform 0.2s, box-shadow 0.2s;
}
.team-card:hover { transform:translateY(-4px); box-shadow:0 12px 40px rgba(0,0,0,0.3); }
.team-av {
  width:60px; height:60px; border-radius:50%; margin:0 auto 12px;
  display:flex; align-items:center; justify-content:center;
  font-family:'Syne',sans-serif; font-size:20px; font-weight:800;
}
.team-nm { font-family:'Syne',sans-serif; font-size:14px; font-weight:700; }
.team-rl { font-size:11px; color:var(--muted); font-family:'DM Mono',monospace; margin-top:3px; }
.team-tg {
  display:inline-block; margin-top:10px;
  padding:3px 10px; border-radius:20px; font-size:10px;
  font-family:'DM Mono',monospace;
  background:rgba(0,212,255,0.08); color:var(--accent);
  border:1px solid rgba(0,212,255,0.15);
}

/* ── MOTTO BANNER ── */
.motto-banner {
  padding:80px 0;
  background:linear-gradient(135deg, rgba(0,212,255,0.06), rgba(10,245,160,0.04));
  border-top:1px solid rgba(0,212,255,0.1);
  border-bottom:1px solid rgba(0,212,255,0.1);
  text-align:center; position:relative; overflow:hidden;
}
.motto-text {
  font-family:'Syne',sans-serif; font-size:56px; font-weight:800;
  letter-spacing:-2px;
  background: linear-gradient(135deg, var(--accent), var(--accent2));
  -webkit-background-clip:text; -webkit-text-fill-color:transparent;
  background-clip:text;
  margin-bottom:12px;
}
.motto-sub { font-size:16px; color:var(--muted); font-family:'DM Mono',monospace; letter-spacing:2px; }

/* ── FOOTER ── */
footer {
  background:var(--surface); border-top:1px solid var(--border);
  padding:48px 60px 32px;
}
.footer-grid { display:grid; grid-template-columns:2fr 1fr 1fr 1fr; gap:40px; margin-bottom:40px; }
.footer-logo { font-family:'Syne',sans-serif; font-size:20px; font-weight:800; color:var(--accent); display:flex; align-items:center; gap:10px; margin-bottom:12px; }
.footer-desc { font-size:13px; color:var(--muted); line-height:1.7; }
.footer-col-title { font-family:'Syne',sans-serif; font-size:13px; font-weight:700; margin-bottom:16px; }
.footer-link { display:block; font-size:13px; color:var(--muted); margin-bottom:8px; cursor:pointer; transition:color 0.2s; text-decoration:none; }
.footer-link:hover { color:var(--accent); }
.footer-bottom { border-top:1px solid var(--border); padding-top:24px; display:flex; align-items:center; justify-content:space-between; }
.footer-copy { font-size:12px; color:var(--muted); font-family:'DM Mono',monospace; }
.footer-badges { display:flex; gap:10px; }
.footer-badge {
  font-size:10px; padding:4px 12px; border-radius:20px;
  font-family:'DM Mono',monospace; border:1px solid var(--border); color:var(--muted);
}

/* ── SCROLLBAR ── */
::-webkit-scrollbar { width:6px; }
::-webkit-scrollbar-track { background:var(--bg); }
::-webkit-scrollbar-thumb { background:var(--border); border-radius:3px; }

/* ── TOAST ── */
.toast {
  position:fixed; bottom:28px; right:28px;
  background:var(--surface2); border:1px solid var(--danger);
  border-radius:12px; padding:16px 18px; z-index:999;
  display:flex; align-items:center; gap:12px;
  max-width:320px; box-shadow:var(--glow-red);
  transform:translateY(80px); opacity:0;
  transition:all 0.4s cubic-bezier(.175,.885,.32,1.275);
}
.toast.show { transform:translateY(0); opacity:1; }
.toast-close { margin-left:auto; cursor:pointer; color:var(--muted); font-size:18px; line-height:1; background:none; border:none; }

/* ── ANIMATIONS ── */
.fade-up {
  opacity:0; transform:translateY(30px);
  transition:opacity 0.7s ease, transform 0.7s ease;
}
.fade-up.visible { opacity:1; transform:translateY(0); }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#home">
    <div class="nav-logo-icon">🛡</div>
    VigilantPath
  </a>
  <div class="nav-links">
    <button class="nav-link active" onclick="scrollTo('home',this)">Home</button>
    <button class="nav-link" onclick="scrollTo('threats',this)">Global Threats</button>
    <button class="nav-link" onclick="scrollTo('why',this)">Why Us</button>
    <button class="nav-link" onclick="scrollTo('services',this)">Services</button>
    <button class="nav-link" onclick="scrollTo('dashboard',this)">Dashboard</button>
    <button class="nav-link" onclick="scrollTo('plans',this)">Pricing</button>
    <button class="nav-link" onclick="scrollTo('team',this)">Team</button>
  </div>
  <button class="nav-cta" onclick="scrollTo('plans',null)">Get Protected →</button>
</nav>

<!-- ═══ HERO ═══ -->
<section id="home">
  <div class="hero-wrap">
    <div class="hero-left">
      <div class="hero-tag"><div class="hero-tag-dot"></div> Now protecting 1,284 clients across Africa</div>
      <h1 class="hero-title">
        Continuous<br>
        <span class="hl">Security.</span><br>
        Real-Time<br>
        <span class="hl2">Protection.</span>
      </h1>
      <div class="hero-motto">Security For Everyone</div>
      <p class="hero-desc">
        VigilantPath is a subscription-based cybersecurity service that monitors your digital environment 24/7, detects threats the moment they emerge, and neutralizes them before damage is done — so you never have to worry about what's lurking in your network.
      </p>
      <div class="hero-btns">
        <button class="btn-primary" onclick="scrollTo('plans',null)">Start Free Trial →</button>
        <button class="btn-outline" onclick="scrollTo('threats',null)">See Global Threats</button>
      </div>
      <div class="hero-stats">
        <div>
          <div class="hero-stat-val" style="color:var(--danger)" id="heroCounter">2,847,193</div>
          <div class="hero-stat-label">Attacks Today (Global)</div>
        </div>
        <div>
          <div class="hero-stat-val" style="color:var(--accent2)">99.97%</div>
          <div class="hero-stat-label">Platform Uptime</div>
        </div>
        <div>
          <div class="hero-stat-val" style="color:var(--accent)">4.2m</div>
          <div class="hero-stat-label">Avg Response Time</div>
        </div>
      </div>
    </div>

    <!-- Hero Live Widget -->
    <div class="hero-visual">
      <div class="hero-visual-title">
        Global Threat Feed
        <span class="live-pill">● LIVE</span>
      </div>
      <div class="global-counter">
        <div class="counter-val" id="liveCount">2,847,193</div>
        <div class="counter-label">Cyberattacks detected globally today</div>
      </div>
      <div class="mini-feed" id="miniFeed"></div>
    </div>
  </div>
</section>

<!-- ═══ GLOBAL THREATS ═══ -->
<section id="threats">
  <div class="section-inner">
    <div class="fade-up">
      <div class="section-tag">⚠ Global Threat Intelligence</div>
      <h2 class="section-title">The World Is Under Attack.<br>Is Your Organization Ready?</h2>
      <p class="section-sub">Cyberattacks are rising at an alarming rate globally — targeting businesses, governments, hospitals, and individuals. The question is not if you will be attacked, but when. VigilantPath exists to ensure you're always prepared.</p>
    </div>

    <div class="threat-cards fade-up">
      <div class="threat-card tc-red">
        <div class="threat-card-icon">🦠</div>
        <div class="threat-card-title">Ransomware Attacks</div>
        <div class="threat-card-stat" style="color:var(--danger)" id="ransomCount">4,200+</div>
        <div class="threat-card-desc">Ransomware incidents reported globally in 2024. Average ransom demand has risen to $2.73M per incident, with healthcare and finance sectors most targeted.</div>
      </div>
      <div class="threat-card tc-yellow">
        <div class="threat-card-icon">🎣</div>
        <div class="threat-card-title">Phishing Campaigns</div>
        <div class="threat-card-stat" style="color:var(--warn)">3.4B</div>
        <div class="threat-card-desc">Phishing emails are sent every single day globally. 36% of all data breaches in 2024 involved phishing — the #1 attack vector targeting African SMEs.</div>
      </div>
      <div class="threat-card tc-blue">
        <div class="threat-card-icon">💸</div>
        <div class="threat-card-title">Global Cost of Cybercrime</div>
        <div class="threat-card-stat" style="color:var(--accent)">$9.5T</div>
        <div class="threat-card-desc">Projected global cybercrime cost in 2024. By 2025, this figure is expected to exceed $10.5 trillion — greater than the GDP of every country except the US and China.</div>
      </div>
    </div>

    <!-- World Map -->
    <div class="world-wrap fade-up">
      <div class="world-header">
        <div class="world-title">🌍 Live Global Attack Origins</div>
        <span style="font-size:11px;color:var(--muted);font-family:'DM Mono',monospace">Attacks per second: <span style="color:var(--danger)" id="apsCount">32</span></span>
      </div>
      <svg id="worldMap" viewBox="0 0 900 400" style="background:var(--surface2);border-radius:10px;">
        <!-- Simplified world landmass shapes -->
        <!-- North America -->
        <path d="M 80 80 L 200 70 L 220 100 L 240 90 L 260 110 L 250 140 L 230 160 L 200 170 L 190 200 L 170 220 L 150 210 L 130 190 L 110 180 L 90 160 L 75 130 Z" fill="#0f1a2e" stroke="#162540" stroke-width="1"/>
        <!-- South America -->
        <path d="M 180 230 L 220 220 L 240 240 L 250 280 L 240 320 L 220 350 L 200 355 L 185 340 L 175 310 L 170 280 L 175 250 Z" fill="#0f1a2e" stroke="#162540" stroke-width="1"/>
        <!-- Europe -->
        <path d="M 400 60 L 460 55 L 480 70 L 490 90 L 470 110 L 450 115 L 430 110 L 410 120 L 390 110 L 385 90 Z" fill="#0f1a2e" stroke="#162540" stroke-width="1"/>
        <!-- Africa -->
        <path d="M 410 130 L 470 125 L 490 150 L 495 200 L 490 250 L 470 290 L 450 310 L 430 310 L 410 295 L 395 260 L 390 220 L 395 175 L 400 150 Z" fill="#0f1a2e" stroke="#162540" stroke-width="1"/>
        <!-- Asia -->
        <path d="M 490 60 L 650 50 L 700 70 L 720 100 L 700 130 L 680 150 L 650 160 L 620 155 L 590 165 L 560 150 L 530 140 L 505 125 L 495 100 Z" fill="#0f1a2e" stroke="#162540" stroke-width="1"/>
        <!-- Australia -->
        <path d="M 680 230 L 750 220 L 780 240 L 790 270 L 775 295 L 750 305 L 720 300 L 700 280 L 690 255 Z" fill="#0f1a2e" stroke="#162540" stroke-width="1"/>

        <!-- Attack pulse dots - positions mapped to real cities -->
        <g id="attackDots"></g>
        <!-- Static reference dots -->
        <circle cx="155" cy="125" r="3" fill="var(--accent2)" opacity="0.6"/> <!-- New York -->
        <circle cx="440" cy="80" r="3" fill="var(--accent2)" opacity="0.6"/>  <!-- London -->
        <circle cx="560" cy="100" r="3" fill="var(--accent2)" opacity="0.6"/> <!-- Moscow -->
        <circle cx="650" cy="110" r="3" fill="var(--accent2)" opacity="0.6"/> <!-- Beijing -->
        <circle cx="435" cy="175" r="3" fill="var(--accent2)" opacity="0.6"/> <!-- Lagos -->
        <circle cx="530" cy="130" r="3" fill="var(--accent2)" opacity="0.6"/> <!-- Mumbai -->

        <!-- City labels -->
        <text x="157" y="120" fill="var(--muted)" font-size="8" font-family="DM Mono">NYC</text>
        <text x="442" y="76" fill="var(--muted)" font-size="8" font-family="DM Mono">LDN</text>
        <text x="562" y="96" fill="var(--muted)" font-size="8" font-family="DM Mono">MSC</text>
        <text x="652" y="106" fill="var(--muted)" font-size="8" font-family="DM Mono">BEI</text>
        <text x="437" y="170" fill="var(--accent2)" font-size="8" font-family="DM Mono" font-weight="bold">LAGOS ★</text>
        <text x="532" y="126" fill="var(--muted)" font-size="8" font-family="DM Mono">MUM</text>
      </svg>
    </div>

    <!-- Country Rankings + Rising Trend -->
    <div class="country-grid fade-up">
      <div class="country-panel">
        <div class="country-title">🔴 Top Attack Source Countries</div>
        <div id="sourceList"></div>
      </div>
      <div class="country-panel">
        <div class="country-title">🎯 Most Targeted Sectors</div>
        <div id="targetList"></div>
      </div>
    </div>

    <div style="height:20px"></div>

    <!-- Rising Trend Chart -->
    <div class="trend-wrap fade-up">
      <div class="trend-header">
        <div class="trend-title">📈 Global Cyberattack Growth Trend</div>
        <div class="trend-tabs">
          <button class="trend-tab active" onclick="setTrend('monthly',this)">Monthly</button>
          <button class="trend-tab" onclick="setTrend('yearly',this)">Yearly</button>
        </div>
      </div>
      <svg id="trendChart" viewBox="0 0 800 180" preserveAspectRatio="none">
        <defs>
          <linearGradient id="trendGrad" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0%" stop-color="var(--danger)" stop-opacity="0.35"/>
            <stop offset="100%" stop-color="var(--danger)" stop-opacity="0"/>
          </linearGradient>
        </defs>
        <path id="trendArea" fill="url(#trendGrad)"/>
        <path id="trendLine" fill="none" stroke="var(--danger)" stroke-width="2.5"/>
        <g id="trendLabels"></g>
      </svg>
    </div>
  </div>
</section>

<!-- ═══ WHY VIGILANTPATH ═══ -->
<section id="why">
  <div class="section-inner">
    <div class="why-grid">
      <div class="why-text fade-up">
        <div class="section-tag" style="background:rgba(10,245,160,0.08);border-color:rgba(10,245,160,0.2);color:var(--accent2)">✦ Why VigilantPath</div>
        <h2 class="section-title">Proactive.<br>Not Reactive.</h2>
        <p class="section-sub" style="margin-bottom:0">Traditional cybersecurity waits for an attack to happen, then responds. VigilantPath never sleeps — our AI engine is always watching, always learning, always one step ahead of threats.</p>
        <div class="feature-list">
          <div class="feature-item">
            <div class="feature-icon-wrap">🤖</div>
            <div>
              <div class="feature-title">AI-Powered Threat Detection</div>
              <div class="feature-desc">Machine learning models trained on millions of threat signatures continuously monitor your environment, detecting anomalies that would slip past traditional tools.</div>
            </div>
          </div>
          <div class="feature-item">
            <div class="feature-icon-wrap">⚡</div>
            <div>
              <div class="feature-title">Real-Time Automated Response</div>
              <div class="feature-desc">When a threat is confirmed, automated countermeasures deploy in seconds — blocking IPs, isolating endpoints, and neutralizing attacks before damage occurs.</div>
            </div>
          </div>
          <div class="feature-item">
            <div class="feature-icon-wrap">📊</div>
            <div>
              <div class="feature-title">Full Visibility Dashboard</div>
              <div class="feature-desc">See your entire security posture in real time. Track threats, view incident history, and monitor compliance status from one intuitive dashboard.</div>
            </div>
          </div>
          <div class="feature-item">
            <div class="feature-icon-wrap">🌍</div>
            <div>
              <div class="feature-title">Built for Africa, Global Standards</div>
              <div class="feature-desc">Fully NDPR-compliant with deep understanding of the Nigerian and African threat landscape — backed by global threat intelligence feeds and world-class infrastructure.</div>
            </div>
          </div>
        </div>
      </div>

      <!-- Workflow -->
      <div class="workflow-visual fade-up">
        <div style="font-family:'Syne',sans-serif;font-size:15px;font-weight:700;margin-bottom:28px;color:var(--muted)">How VigilantPath Works</div>
        <div class="wf-step">
          <div class="wf-num">1</div>
          <div class="wf-content">
            <div class="wf-title">Onboard in Minutes</div>
            <div class="wf-desc">Sign up, choose your plan, and connect your infrastructure via our lightweight agent or API. Setup takes less than 30 minutes.</div>
          </div>
        </div>
        <div class="wf-step">
          <div class="wf-num">2</div>
          <div class="wf-content">
            <div class="wf-title">24/7 Continuous Monitoring</div>
            <div class="wf-desc">Our AI engine scans your network traffic, endpoints, and cloud environments around the clock — never sleeping, never missing a signal.</div>
          </div>
        </div>
        <div class="wf-step">
          <div class="wf-num">3</div>
          <div class="wf-content">
            <div class="wf-title">Instant Threat Detection</div>
            <div class="wf-desc">Anomalies are flagged in real time and classified by severity. Your dashboard lights up the moment something needs attention.</div>
          </div>
        </div>
        <div class="wf-step">
          <div class="wf-num">4</div>
          <div class="wf-content">
            <div class="wf-title">Automated Mitigation</div>
            <div class="wf-desc">Confirmed threats trigger instant countermeasures. Our SOC team backs up the AI for complex incidents requiring human expertise.</div>
          </div>
        </div>
        <div class="wf-step" style="margin-bottom:0">
          <div class="wf-num">5</div>
          <div class="wf-content" style="padding-bottom:0">
            <div class="wf-title">Reports & Continuous Improvement</div>
            <div class="wf-desc">Regular security reports keep you informed. Our models continuously learn from new threats to stay ahead of attackers.</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ SERVICES ═══ -->
<section id="services">
  <div class="section-inner">
    <div class="fade-up" style="text-align:center;margin-bottom:48px;">
      <div class="section-tag" style="display:inline-flex;background:rgba(255,176,32,0.08);border-color:rgba(255,176,32,0.2);color:var(--warn)">◈ Our Services</div>
      <h2 class="section-title">Everything You Need.<br>One Subscription.</h2>
      <p class="section-sub" style="margin:0 auto">From endpoint protection to enterprise-grade SOC operations, VigilantPath delivers a complete security stack — without the enterprise price tag.</p>
    </div>
    <div class="services-grid fade-up">
      <div class="service-card">
        <div class="service-icon">🔍</div>
        <div class="service-title">Continuous Monitoring</div>
        <div class="service-desc">24/7 AI-driven monitoring of your network, endpoints, cloud workloads, and user activity. No gaps, no blind spots, no time off.</div>
        <span class="service-tag">Core Service</span>
      </div>
      <div class="service-card">
        <div class="service-icon">⚡</div>
        <div class="service-title">Real-Time Threat Response</div>
        <div class="service-desc">Automated countermeasures deploy within seconds of threat confirmation. Block, isolate, neutralize — all without manual intervention.</div>
        <span class="service-tag">Automated</span>
      </div>
      <div class="service-card">
        <div class="service-icon">🧠</div>
        <div class="service-title">Threat Intelligence</div>
        <div class="service-desc">Continuously updated global and local threat feeds keep our detection engine current with the latest attack techniques and indicators of compromise.</div>
        <span class="service-tag">AI-Powered</span>
      </div>
      <div class="service-card">
        <div class="service-icon">📋</div>
        <div class="service-title">Compliance Reporting</div>
        <div class="service-desc">Automated NDPR and security compliance reports. Know your posture, prove your compliance, and stay ahead of regulatory requirements with zero manual effort.</div>
        <span class="service-tag">NDPR Ready</span>
      </div>
      <div class="service-card">
        <div class="service-icon">🛡</div>
        <div class="service-title">Security Operations Center</div>
        <div class="service-desc">Our expert SOC team provides human oversight and handles complex incident response — a dedicated security team available to every subscriber, not just enterprises.</div>
        <span class="service-tag">24/7 SOC</span>
      </div>
      <div class="service-card">
        <div class="service-icon">📊</div>
        <div class="service-title">Security Dashboard</div>
        <div class="service-desc">A real-time, intuitive dashboard giving full visibility into your security posture, active threats, blocked attacks, and system health — accessible from anywhere.</div>
        <span class="service-tag">Real-Time</span>
      </div>
    </div>
  </div>
</section>

<!-- ═══ DASHBOARD PREVIEW ═══ -->
<section id="dashboard">
  <div class="section-inner">
    <div class="fade-up" style="text-align:center;margin-bottom:40px;">
      <div class="section-tag" style="display:inline-flex;background:rgba(0,212,255,0.08);border-color:rgba(0,212,255,0.2);color:var(--accent)">⬡ Platform Preview</div>
      <h2 class="section-title">Your Security,<br>Always in View</h2>
      <p class="section-sub" style="margin:0 auto">The VigilantPath dashboard gives you complete, real-time visibility into your security environment from a single, easy-to-use interface.</p>
    </div>
    <div class="dash-preview fade-up">
      <div class="dash-bar">
        <div class="dash-dot" style="background:#ff5f57"></div>
        <div class="dash-dot" style="background:#febc2e"></div>
        <div class="dash-dot" style="background:#28c840"></div>
        <div class="dash-title-bar">VigilantPath Security Dashboard — Professional Plan</div>
      </div>
      <div class="dash-content">
        <div class="dash-mini-card">
          <div class="dash-mini-label">Threats Blocked</div>
          <div class="dash-mini-val" style="color:var(--accent)" id="dashCount">247</div>
        </div>
        <div class="dash-mini-card">
          <div class="dash-mini-label">Security Score</div>
          <div class="dash-mini-val" style="color:var(--accent2)">94/100</div>
        </div>
        <div class="dash-mini-card">
          <div class="dash-mini-label">Critical Alerts</div>
          <div class="dash-mini-val" style="color:var(--danger)">3</div>
        </div>
        <div class="dash-mini-card">
          <div class="dash-mini-label">Response Time</div>
          <div class="dash-mini-val" style="color:var(--warn)">4.2m</div>
        </div>
      </div>
      <div class="dash-bottom">
        <div class="dash-chart-area">
          <div class="dash-chart-label">7-Day Threat Activity</div>
          <svg width="100%" height="85" viewBox="0 0 400 85">
            <defs><linearGradient id="dg" x1="0" y1="0" x2="0" y2="1">
              <stop offset="0%" stop-color="var(--accent)" stop-opacity="0.4"/>
              <stop offset="100%" stop-color="var(--accent)" stop-opacity="0"/>
            </linearGradient></defs>
            <path d="M0 70 L57 55 L114 62 L171 38 L228 45 L285 30 L342 20 L400 15 L400 85 L0 85 Z" fill="url(#dg)"/>
            <path d="M0 70 L57 55 L114 62 L171 38 L228 45 L285 30 L342 20 L400 15" fill="none" stroke="var(--accent)" stroke-width="2"/>
            <text x="0" y="82" fill="var(--muted)" font-size="8" font-family="DM Mono">Mon</text>
            <text x="55" y="82" fill="var(--muted)" font-size="8" font-family="DM Mono">Tue</text>
            <text x="112" y="82" fill="var(--muted)" font-size="8" font-family="DM Mono">Wed</text>
            <text x="169" y="82" fill="var(--muted)" font-size="8" font-family="DM Mono">Thu</text>
            <text x="226" y="82" fill="var(--muted)" font-size="8" font-family="DM Mono">Fri</text>
            <text x="283" y="82" fill="var(--muted)" font-size="8" font-family="DM Mono">Sat</text>
            <text x="340" y="82" fill="var(--muted)" font-size="8" font-family="DM Mono">Sun</text>
          </svg>
        </div>
        <div class="dash-list-area">
          <div style="font-size:9px;color:var(--muted);font-family:'DM Mono',monospace;text-transform:uppercase;letter-spacing:1px;margin-bottom:8px;">Recent Alerts</div>
          <div class="dash-list-item"><div class="dash-dot2" style="background:var(--danger)"></div>Ransomware blocked</div>
          <div class="dash-list-item"><div class="dash-dot2" style="background:var(--warn)"></div>SSH brute force halted</div>
          <div class="dash-list-item"><div class="dash-dot2" style="background:var(--accent)"></div>Port scan detected</div>
          <div class="dash-list-item"><div class="dash-dot2" style="background:var(--accent2)"></div>System health: 97%</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ MOTTO BANNER ═══ -->
<div class="motto-banner">
  <div class="motto-text">" Security For Everyone "</div>
  <div class="motto-sub">// VigilantPath — Continuous Security · Real-Time Protection · Zero Compromise</div>
</div>

<!-- ═══ PLANS ═══ -->
<section id="plans">
  <div class="section-inner">
    <div class="fade-up" style="text-align:center;">
      <div class="section-tag" style="display:inline-flex;background:rgba(0,212,255,0.08);border-color:rgba(0,212,255,0.2);color:var(--accent)">◈ Pricing Plans</div>
      <h2 class="section-title">Protection for<br>Every Budget</h2>
      <p class="section-sub" style="margin:0 auto">From individual users to large enterprises — VigilantPath's subscription tiers make world-class cybersecurity accessible to everyone. Our motto isn't just a slogan; it's our pricing philosophy.</p>
    </div>
    <div class="plan-grid fade-up">
      <div class="plan-card">
        <div class="plan-name">Basic</div>
        <div class="plan-tagline">For individuals & remote workers</div>
        <div class="plan-price">₦5,000 <small>/month</small></div>
        <hr class="plan-divider">
        <div class="plan-feat y"><span class="ck">✓</span> Device monitoring (up to 3)</div>
        <div class="plan-feat y"><span class="ck">✓</span> Real-time threat alerts</div>
        <div class="plan-feat y"><span class="ck">✓</span> Email support</div>
        <div class="plan-feat y"><span class="ck">✓</span> Weekly security reports</div>
        <div class="plan-feat"><span class="xk">✗</span> Network monitoring</div>
        <div class="plan-feat"><span class="xk">✗</span> 24/7 SOC team access</div>
        <div class="plan-feat"><span class="xk">✗</span> Compliance reporting</div>
        <button class="plan-btn2 pb-outline">Get Started Free →</button>
      </div>
      <div class="plan-card featured">
        <div class="plan-name">Professional</div>
        <div class="plan-tagline">For SMBs & growing businesses</div>
        <div class="plan-price">₦35,000 <small>/month</small></div>
        <hr class="plan-divider">
        <div class="plan-feat y"><span class="ck">✓</span> Unlimited device monitoring</div>
        <div class="plan-feat y"><span class="ck">✓</span> Full network monitoring</div>
        <div class="plan-feat y"><span class="ck">✓</span> 24/7 chat & phone support</div>
        <div class="plan-feat y"><span class="ck">✓</span> Real-time dashboard</div>
        <div class="plan-feat y"><span class="ck">✓</span> Automated threat response</div>
        <div class="plan-feat y"><span class="ck">✓</span> Monthly compliance reports</div>
        <div class="plan-feat"><span class="xk">✗</span> Dedicated account manager</div>
        <button class="plan-btn2 pb-filled">Start 14-Day Free Trial →</button>
      </div>
      <div class="plan-card">
        <div class="plan-name">Enterprise</div>
        <div class="plan-tagline">For large corporations & government</div>
        <div class="plan-price" style="font-size:26px;padding:6px 0">Custom Pricing</div>
        <hr class="plan-divider">
        <div class="plan-feat y"><span class="ck">✓</span> Everything in Professional</div>
        <div class="plan-feat y"><span class="ck">✓</span> Dedicated SOC team</div>
        <div class="plan-feat y"><span class="ck">✓</span> Dedicated account manager</div>
        <div class="plan-feat y"><span class="ck">✓</span> SLA — 99.9% uptime guarantee</div>
        <div class="plan-feat y"><span class="ck">✓</span> Custom API integrations</div>
        <div class="plan-feat y"><span class="ck">✓</span> Quarterly security reviews</div>
        <div class="plan-feat y"><span class="ck">✓</span> On-site support available</div>
        <button class="plan-btn2 pb-dark">Contact Sales →</button>
      </div>
    </div>
    <div style="text-align:center;margin-top:24px;color:var(--muted);font-size:12px;font-family:'DM Mono',monospace;">
      All plans · AES-256 encryption · NDPR compliant · No contracts · Cancel anytime
    </div>
  </div>
</section>

<!-- ═══ TEAM ═══ -->
<section id="team">
  <div class="section-inner">
    <div class="fade-up" style="text-align:center;margin-bottom:0">
      <div class="section-tag" style="display:inline-flex;background:rgba(10,245,160,0.08);border-color:rgba(10,245,160,0.2);color:var(--accent2)">◎ Our Team</div>
      <h2 class="section-title">11 Founders.<br>One Mission.</h2>
      <p class="section-sub" style="margin:0 auto 0">VigilantPath was founded by a team of 11 driven students and technologists from Akure, Nigeria, united by a single belief: that world-class cybersecurity should not be a luxury. Our headquarters is in Lagos, Nigeria's commercial capital, where we serve and grow alongside Africa's most ambitious businesses.</p>
    </div>

    <!-- Office info -->
    <div style="display:grid;grid-template-columns:1fr 1fr;gap:16px;margin:32px 0;" class="fade-up">
      <div style="background:linear-gradient(135deg,rgba(0,212,255,0.06),rgba(10,245,160,0.03));border:1px solid rgba(0,212,255,0.15);border-radius:14px;padding:24px;display:flex;gap:16px;align-items:center;">
        <div style="font-size:36px">🏢</div>
        <div>
          <div style="font-family:'Syne',sans-serif;font-size:15px;font-weight:700;margin-bottom:4px">Lagos Headquarters</div>
          <div style="font-size:13px;color:var(--muted)">Lagos, Nigeria — Nigeria's commercial capital, home to our client-facing operations, enterprise sales, and customer success teams.</div>
        </div>
      </div>
      <div style="background:linear-gradient(135deg,rgba(10,245,160,0.06),rgba(0,212,255,0.03));border:1px solid rgba(10,245,160,0.15);border-radius:14px;padding:24px;display:flex;gap:16px;align-items:center;">
        <div style="font-size:36px">🎓</div>
        <div>
          <div style="font-family:'Syne',sans-serif;font-size:15px;font-weight:700;margin-bottom:4px">Founded in Akure</div>
          <div style="font-size:13px;color:var(--muted)">Our founding team hails from Akure, Ondo State — proof that world-changing technology companies can be built anywhere in Nigeria.</div>
        </div>
      </div>
    </div>

    <div class="team-grid fade-up" id="teamGrid"></div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-grid">
    <div>
      <div class="footer-logo"><div class="nav-logo-icon" style="width:28px;height:28px;font-size:14px">🛡</div>VigilantPath</div>
      <div class="footer-desc">A subscription-based continuous security and real-time threat mitigation service. Security For Everyone — from individuals to enterprises across Africa and beyond.</div>
    </div>
    <div>
      <div class="footer-col-title">Platform</div>
      <a class="footer-link" href="#threats">Global Threats</a>
      <a class="footer-link" href="#dashboard">Dashboard</a>
      <a class="footer-link" href="#services">Services</a>
      <a class="footer-link" href="#plans">Pricing</a>
    </div>
    <div>
      <div class="footer-col-title">Company</div>
      <a class="footer-link" href="#why">Why VigilantPath</a>
      <a class="footer-link" href="#team">Our Team</a>
      <a class="footer-link" href="#">Careers</a>
      <a class="footer-link" href="#">Blog</a>
    </div>
    <div>
      <div class="footer-col-title">Legal</div>
      <a class="footer-link" href="#">Privacy Policy</a>
      <a class="footer-link" href="#">Terms of Service</a>
      <a class="footer-link" href="#">NDPR Compliance</a>
      <a class="footer-link" href="#">Security Policy</a>
    </div>
  </div>
  <div class="footer-bottom">
    <div class="footer-copy">© 2026 VigilantPath. All rights reserved. Lagos, Nigeria.</div>
    <div class="footer-badges">
      <div class="footer-badge">NDPR Compliant</div>
      <div class="footer-badge">AES-256 Encrypted</div>
      <div class="footer-badge">99.97% Uptime</div>
    </div>
  </div>
</footer>

<!-- TOAST -->
<div class="toast" id="toast">
  <div style="font-size:20px">🚨</div>
  <div>
    <div style="font-size:13px;font-weight:600;margin-bottom:2px">Critical Threat Detected</div>
    <div style="font-size:11px;color:var(--muted)">Ransomware blocked on client network — Lagos, NG</div>
  </div>
  <button class="toast-close" onclick="document.getElementById('toast').classList.remove('show')">✕</button>
</div>

<script>
// ── NAV SCROLL ──
function scrollTo(id, btn) {
  document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
  if (btn) {
    document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));
    btn.classList.add('active');
  }
}

// Update active nav on scroll
const sections = ['home','threats','why','services','dashboard','plans','team'];
window.addEventListener('scroll', () => {
  let cur = 'home';
  sections.forEach(id => {
    const el = document.getElementById(id);
    if (el && el.getBoundingClientRect().top < 120) cur = id;
  });
  document.querySelectorAll('.nav-link').forEach((l, i) => {
    l.classList.toggle('active', sections[i] === cur);
  });
});

// ── LIVE COUNTER ──
let globalCount = 2847193;
function formatNum(n) { return n.toLocaleString(); }
function tickCounter() {
  globalCount += Math.floor(Math.random() * 80) + 20;
  const el1 = document.getElementById('liveCount');
  const el2 = document.getElementById('heroCounter');
  if (el1) el1.textContent = formatNum(globalCount);
  if (el2) el2.textContent = formatNum(globalCount);
}
setInterval(tickCounter, 1200);

// APS counter
let aps = 32;
setInterval(() => {
  aps = 28 + Math.floor(Math.random() * 18);
  const el = document.getElementById('apsCount');
  if (el) el.textContent = aps;
}, 2000);

// Dashboard counter
let dc = 247;
setInterval(() => {
  if (Math.random() > 0.5) {
    dc += Math.floor(Math.random() * 2) + 1;
    const el = document.getElementById('dashCount');
    if (el) el.textContent = dc;
  }
}, 3500);

// ── MINI FEED ──
const feedData = [
  { cls:'c', flag:'🇨🇳', title:'Brute Force SSH', sub:'Source: 182.61.xx.xx → Target: API Gateway', sev:'CRITICAL' },
  { cls:'w', flag:'🇷🇺', title:'Phishing Domain Detected', sub:'dns: secure-gtb.fakesite.ru flagged', sev:'HIGH' },
  { cls:'c', flag:'🇧🇷', title:'Ransomware Payload Blocked', sub:'Signature: LockBit 3.0 variant', sev:'CRITICAL' },
  { cls:'g', flag:'🇳🇬', title:'Threat Neutralized', sub:'VigilantPath auto-mitigated Lagos client', sev:'RESOLVED' },
  { cls:'w', flag:'🇰🇵', title:'DDoS Traffic Spike', sub:'1.4Gbps attack on web server', sev:'HIGH' },
  { cls:'c', flag:'🇮🇷', title:'Zero-Day Exploit Attempt', sub:'CVE-2024-4877 attempted on SMB', sev:'CRITICAL' },
  { cls:'g', flag:'🇳🇬', title:'Client Protected', sub:'VigilantPath blocked intrusion attempt', sev:'RESOLVED' },
  { cls:'w', flag:'🇺🇸', title:'Credential Stuffing Attack', sub:'12,000 login attempts/min detected', sev:'HIGH' },
];
let fi = 0;
const mf = document.getElementById('miniFeed');
function addMiniItem() {
  const d = feedData[fi % feedData.length]; fi++;
  if (mf.children.length >= 5) mf.removeChild(mf.lastChild);
  const el = document.createElement('div');
  el.className = `mini-feed-item ${d.cls}`;
  const sevColor = d.cls === 'c' ? 'var(--danger)' : d.cls === 'w' ? 'var(--warn)' : 'var(--accent2)';
  el.innerHTML = `
    <div class="feed-flag">${d.flag}</div>
    <div class="feed-info">
      <div class="feed-info-title">${d.title}</div>
      <div class="feed-info-sub">${d.sub}</div>
    </div>
    <span class="feed-sev ${d.cls}" style="color:${sevColor}">${d.sev}</span>
  `;
  mf.insertBefore(el, mf.firstChild);
}
addMiniItem(); addMiniItem(); addMiniItem();
setInterval(addMiniItem, 2800);

// ── WORLD MAP ATTACK PULSES ──
const mapAttacks = [
  {x:155,y:125,c:'var(--danger)'}, {x:440,y:80,c:'var(--warn)'},
  {x:560,y:100,c:'var(--danger)'}, {x:650,y:110,c:'var(--danger)'},
  {x:530,y:130,c:'var(--warn)'}, {x:200,y:250,c:'var(--warn)'},
  {x:720,y:260,c:'var(--accent)'}, {x:470,y:195,c:'var(--accent)'},
];
const dotsG = document.getElementById('attackDots');
function spawnAttack() {
  const a = mapAttacks[Math.floor(Math.random() * mapAttacks.length)];
  const jx = a.x + (Math.random()-0.5)*30;
  const jy = a.y + (Math.random()-0.5)*20;
  const g = document.createElementNS('http://www.w3.org/2000/svg','g');
  const c1 = document.createElementNS('http://www.w3.org/2000/svg','circle');
  c1.setAttribute('cx', jx); c1.setAttribute('cy', jy);
  c1.setAttribute('r', '3'); c1.setAttribute('fill', a.c);
  c1.style.animation = 'none';
  const c2 = document.createElementNS('http://www.w3.org/2000/svg','circle');
  c2.setAttribute('cx', jx); c2.setAttribute('cy', jy);
  c2.setAttribute('r', '3'); c2.setAttribute('fill', 'none');
  c2.setAttribute('stroke', a.c); c2.setAttribute('stroke-width','1');
  g.appendChild(c1); g.appendChild(c2);
  dotsG.appendChild(g);
  // Animate expand and fade
  let r = 3, op = 1;
  const step = () => {
    r += 0.6; op -= 0.04;
    c2.setAttribute('r', r);
    c2.setAttribute('opacity', op);
    c1.setAttribute('opacity', op + 0.3);
    if (op > 0) requestAnimationFrame(step);
    else dotsG.removeChild(g);
  };
  requestAnimationFrame(step);
}
setInterval(spawnAttack, 600);

// ── COUNTRY RANKINGS ──
const sources = [
  { flag:'🇨🇳', name:'China', pct:24, color:'var(--danger)' },
  { flag:'🇷🇺', name:'Russia', pct:19, color:'var(--danger)' },
  { flag:'🇺🇸', name:'United States', pct:12, color:'var(--warn)' },
  { flag:'🇧🇷', name:'Brazil', pct:8, color:'var(--warn)' },
  { flag:'🇰🇵', name:'North Korea', pct:7, color:'var(--accent)' },
];
const targets = [
  { flag:'🏥', name:'Healthcare', pct:22, color:'var(--danger)' },
  { flag:'🏦', name:'Finance & Banking', pct:20, color:'var(--danger)' },
  { flag:'🏛', name:'Government', pct:17, color:'var(--warn)' },
  { flag:'🛒', name:'Retail / E-Commerce', pct:14, color:'var(--warn)' },
  { flag:'🎓', name:'Education', pct:11, color:'var(--accent)' },
];
function renderList(id, data) {
  const el = document.getElementById(id);
  data.forEach((d, i) => {
    el.innerHTML += `
      <div class="country-row">
        <div class="country-rank">#${i+1}</div>
        <div class="country-flag">${d.flag}</div>
        <div class="country-name">${d.name}</div>
        <div class="country-bar-wrap"><div class="country-bar" style="width:${d.pct*4}px;background:${d.color}"></div></div>
        <div class="country-pct">${d.pct}%</div>
      </div>`;
  });
}
renderList('sourceList', sources);
renderList('targetList', targets);

// ── TREND CHART ──
const monthlyData = { labels:['Jul','Aug','Sep','Oct','Nov','Dec','Jan','Feb','Mar','Apr','May','Jun'], values:[62,68,71,79,85,90,95,103,112,120,131,147] };
const yearlyData = { labels:['2018','2019','2020','2021','2022','2023','2024','2025'], values:[30,42,58,75,95,118,145,172] };
let currentTrend = 'monthly';

function drawTrend(data) {
  const svg = document.getElementById('trendChart');
  const w=800, h=160, pad=30;
  const vals = data.values;
  const labels = data.labels;
  const min=Math.min(...vals)-5, max=Math.max(...vals)+10;
  const x=(i)=> pad + (i/(vals.length-1))*(w-pad*2);
  const y=(v)=> h - pad - ((v-min)/(max-min))*(h-pad*2);
  const lineD = vals.map((v,i)=>`${i===0?'M':'L'} ${x(i)} ${y(v)}`).join(' ');
  const areaD = `M ${x(0)} ${h} ${vals.map((v,i)=>`L ${x(i)} ${y(v)}`).join(' ')} L ${x(vals.length-1)} ${h} Z`;
  document.getElementById('trendLine').setAttribute('d', lineD);
  document.getElementById('trendArea').setAttribute('d', areaD);
  const lg = document.getElementById('trendLabels');
  lg.innerHTML = '';
  labels.forEach((l,i) => {
    const tx = document.createElementNS('http://www.w3.org/2000/svg','text');
    tx.setAttribute('x', x(i)); tx.setAttribute('y', h-4);
    tx.setAttribute('text-anchor','middle'); tx.setAttribute('fill','#4a6f8a');
    tx.setAttribute('font-size','10'); tx.setAttribute('font-family','DM Mono');
    tx.textContent = l; lg.appendChild(tx);
    // value label on top
    const tv = document.createElementNS('http://www.w3.org/2000/svg','text');
    tv.setAttribute('x', x(i)); tv.setAttribute('y', y(vals[i])-8);
    tv.setAttribute('text-anchor','middle'); tv.setAttribute('fill','var(--danger)');
    tv.setAttribute('font-size','9'); tv.setAttribute('font-family','DM Mono');
    tv.textContent = vals[i]+'M'; lg.appendChild(tv);
    // dot
    const c = document.createElementNS('http://www.w3.org/2000/svg','circle');
    c.setAttribute('cx', x(i)); c.setAttribute('cy', y(vals[i]));
    c.setAttribute('r','4'); c.setAttribute('fill','var(--danger)');
    c.setAttribute('stroke','var(--bg)'); c.setAttribute('stroke-width','2');
    lg.appendChild(c);
  });
}
drawTrend(monthlyData);

function setTrend(type, btn) {
  document.querySelectorAll('.trend-tab').forEach(t => t.classList.remove('active'));
  btn.classList.add('active');
  drawTrend(type === 'monthly' ? monthlyData : yearlyData);
}

// ── TEAM ──
const team = [
  { name:'Adebayo A.', role:'CEO', tag:'Strategy', g:'#00d4ff,#004080' },
  { name:'Chisom O.',  role:'CTO', tag:'Engineering', g:'#0af5a0,#005040' },
  { name:'Emeka N.',   role:'CISO', tag:'Security', g:'#ff3d5a,#600010' },
  { name:'Fatima L.',  role:'CFO', tag:'Finance', g:'#ffb020,#604000' },
  { name:'Gbenga T.',  role:'CMO', tag:'Marketing', g:'#a855f7,#400080' },
  { name:'Halima B.',  role:'Head of Product', tag:'Product', g:'#00d4ff,#002040' },
  { name:'Ibrahim K.', role:'Lead Engineer', tag:'Dev', g:'#0af5a0,#002030' },
  { name:'Joy A.',     role:'SOC Analyst', tag:'Operations', g:'#ff3d5a,#500010' },
  { name:'Kunle R.',   role:'SOC Analyst', tag:'Operations', g:'#ffb020,#503000' },
  { name:'Lola M.',    role:'Sales & BizDev', tag:'Growth', g:'#00d4ff,#001030' },
  { name:'Moses E.',   role:'Legal & Compliance', tag:'Legal', g:'#0af5a0,#001020' },
];
const tg = document.getElementById('teamGrid');
team.forEach(m => {
  const init = m.name.split(' ').map(p=>p[0]).join('');
  tg.innerHTML += `
    <div class="team-card">
      <div class="team-av" style="background:linear-gradient(135deg,${m.g})">${init}</div>
      <div class="team-nm">${m.name}</div>
      <div class="team-rl">${m.role}</div>
      <span class="team-tg">${m.tag}</span>
    </div>`;
});

// ── SCROLL ANIMATIONS ──
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
}, { threshold: 0.1 });
document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

// ── TOAST ──
setTimeout(() => {
  document.getElementById('toast').classList.add('show');
  setTimeout(() => document.getElementById('toast').classList.remove('show'), 7000);
}, 5000);
</script>
</body>
</html>
