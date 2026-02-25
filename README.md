<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VigilantPath — Enterprise Security</title>
    <link href="https://fonts.googleapis.com/css2?family=Syne:wght@700;800&family=DM+Sans:wght@400;500;700&family=DM+Mono&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg: #030712;
            --surface: #0f172a;
            --surface-light: #1e293b;
            --border: #334155;
            --accent: #6366f1;
            --accent-glow: rgba(99, 102, 241, 0.3);
            --success: #10b981;
            --danger: #ef4444;
            --text: #f8fafc;
            --muted: #94a3b8;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }
        html { scroll-behavior: smooth; }
        body { 
            background: var(--bg); 
            color: var(--text); 
            font-family: 'DM Sans', sans-serif; 
            overflow-x: hidden; 
            line-height: 1.6;
        }

        /* --- NAVIGATION --- */
        nav {
            position: fixed; top: 0; width: 100%; height: 70px;
            background: rgba(3, 7, 18, 0.8); backdrop-filter: blur(12px);
            border-bottom: 1px solid var(--border);
            display: flex; align-items: center; justify-content: space-between;
            padding: 0 5%; z-index: 1000;
        }
        .logo { display: flex; align-items: center; gap: 10px; text-decoration: none; }
        .logo-box {
            width: 35px; height: 35px; background: var(--accent);
            border-radius: 8px; display: flex; align-items: center; justify-content: center;
            box-shadow: 0 0 15px var(--accent-glow);
        }
        .logo-text { font-family: 'Syne', sans-serif; font-weight: 800; font-size: 22px; color: var(--text); }
        .nav-links { display: flex; gap: 25px; }
        .nav-links a { text-decoration: none; color: var(--muted); font-size: 14px; font-weight: 500; transition: 0.3s; cursor: pointer; }
        .nav-links a:hover { color: var(--accent); }
        .nav-btn { background: var(--accent); color: white; padding: 10px 22px; border-radius: 50px; border: none; font-weight: 700; cursor: pointer; transition: 0.3s; }
        .nav-btn:hover { transform: scale(1.05); box-shadow: 0 0 20px var(--accent-glow); }

        /* --- SECTIONS --- */
        section { padding: 100px 5%; max-width: 1300px; margin: 0 auto; }
        .section-header { text-align: center; margin-bottom: 60px; }
        .section-header h2 { font-family: 'Syne', sans-serif; font-size: 42px; margin-bottom: 10px; }
        .section-header p { color: var(--muted); font-size: 18px; }

        /* --- HERO --- */
        .hero { min-height: 100vh; display: flex; align-items: center; padding-top: 120px; }
        .hero-grid { display: grid; grid-template-columns: 1.2fr 0.8fr; gap: 60px; align-items: center; }
        .tag { background: rgba(99, 102, 241, 0.1); color: var(--accent); padding: 6px 15px; border-radius: 50px; font-size: 12px; font-family: 'DM Mono'; border: 1px solid var(--accent-glow); display: inline-block; margin-bottom: 20px; }
        h1 { font-family: 'Syne', sans-serif; font-size: clamp(40px, 5vw, 68px); line-height: 1.1; margin-bottom: 25px; }
        
        /* --- LIVE WIDGET --- */
        .threat-widget { background: var(--surface); border: 1px solid var(--border); border-radius: 24px; padding: 30px; box-shadow: 0 20px 50px rgba(0,0,0,0.5); }
        .live-indicator { color: var(--danger); font-family: 'DM Mono'; font-size: 12px; display: flex; align-items: center; gap: 8px; margin-bottom: 10px; }
        .dot { width: 8px; height: 8px; background: var(--danger); border-radius: 50%; animation: blink 1s infinite; }
        @keyframes blink { 50% { opacity: 0; } }
        .counter { font-family: 'Syne', sans-serif; font-size: 48px; font-weight: 800; color: var(--text); }

        /* --- PRICING TABS --- */
        .pricing-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 25px; }
        .price-card { 
            background: var(--surface); border: 1px solid var(--border); border-radius: 24px; padding: 40px; 
            display: flex; flex-direction: column; transition: 0.3s; position: relative;
        }
        .price-card.featured { border-color: var(--accent); transform: scale(1.05); z-index: 2; background: #111827; }
        .popular-badge { 
            position: absolute; top: -15px; left: 50%; transform: translateX(-50%);
            background: var(--accent); color: white; padding: 5px 15px; border-radius: 50px; 
            font-size: 12px; font-weight: 700;
        }
        .price-val { font-family: 'Syne', sans-serif; font-size: 42px; font-weight: 800; margin: 20px 0; }
        .price-val span { font-size: 16px; color: var(--muted); font-weight: 400; }
        .feat-list { list-style: none; margin-bottom: 30px; flex-grow: 1; }
        .feat-list li { margin-bottom: 12px; font-size: 14px; display: flex; align-items: center; gap: 10px; }
        .feat-list li::before { content: '✓'; color: var(--accent); font-weight: bold; }

        footer { text-align: center; padding: 60px; border-top: 1px solid var(--border); color: var(--muted); font-size: 14px; }

        @media (max-width: 900px) {
            .hero-grid { grid-template-columns: 1fr; text-align: center; }
            .hero p { margin: 0 auto 30px; }
            .price-card.featured { transform: scale(1); }
        }
    </style>
</head>
<body>

<nav>
    <a href="#" class="logo">
        <div class="logo-box">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2.5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
        </div>
        <span class="logo-text">VigilantPath</span>
    </a>
    <div class="nav-links">
        <a onclick="scrollSection('home')">Intelligence</a>
        <a onclick="scrollSection('solutions')">Solutions</a>
        <a onclick="scrollSection('pricing')">Pricing</a>
    </div>
    <button class="nav-btn">Get Started</button>
</nav>

<section class="hero" id="home">
    <div class="hero-grid">
        <div>
            <div class="tag">#1 Cybersecurity Platform in Africa</div>
            <h1>Elite Security <br><span style="color: var(--accent);">For Every Asset.</span></h1>
            <p>VigilantPath provides autonomous, real-time threat detection and response, ensuring your digital infrastructure remains impenetrable 24/7.</p>
            <div style="display: flex; gap: 15px; justify-content: inherit;">
                <button class="nav-btn" style="padding: 15px 35px;">Deploy Now</button>
                <button class="nav-btn" style="background: transparent; border: 1px solid var(--border);">Documentation</button>
            </div>
        </div>
        
        <div class="threat-widget">
            <div class="live-indicator"><div class="dot"></div> LIVE GLOBAL THREAT FEED</div>
            <div class="counter" id="mainCounter">2,847,193</div>
            <p style="font-size: 12px; margin-top: 5px; font-family: 'DM Mono';">Attacks mitigated today</p>
            <hr style="margin: 20px 0; border: 0; border-top: 1px solid var(--border);">
            <div id="log" style="font-family: 'DM Mono'; font-size: 11px; color: var(--success); height: 80px; overflow: hidden;">
                > [SYSTEM]: Monitoring Active...<br>
                > [STATUS]: No breaches detected in Lagos Node.
            </div>
        </div>
    </div>
</section>

<section id="solutions">
    <div class="section-header">
        <h2>Defensive Architecture</h2>
        <p>Next-generation solutions for the modern enterprise.</p>
    </div>
    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px;">
        <div style="background: var(--surface); border: 1px solid var(--border); padding: 40px; border-radius: 20px;">
            <h3 style="font-family: 'Syne'; margin-bottom: 15px;">Autonomous Defense</h3>
            <p style="color: var(--muted); font-size: 14px;">Our AI engines identify and neutralize zero-day exploits before they reach your network perimeter.</p>
        </div>
        <div style="background: var(--surface); border: 1px solid var(--border); padding: 40px; border-radius: 20px;">
            <h3 style="font-family: 'Syne'; margin-bottom: 15px;">Global Intelligence</h3>
            <p style="color: var(--muted); font-size: 14px;">Direct feed from global threat databases ensuring you are protected against international actors.</p>
        </div>
        <div style="background: var(--surface); border: 1px solid var(--border); padding: 40px; border-radius: 20px;">
            <h3 style="font-family: 'Syne'; margin-bottom: 15px;">Real-time Analytics</h3>
            <p style="color: var(--muted); font-size: 14px;">Comprehensive dashboarding providing a bird's eye view of your entire digital footprint.</p>
        </div>
    </div>
</section>

<section id="pricing">
    <div class="section-header">
        <h2>Flexible Protection</h2>
        <p>Secure your scale with our transparent pricing models.</p>
    </div>
    <div class="pricing-grid">
        <div class="price-card">
            <h3>Startup</h3>
            <p style="color: var(--muted); font-size: 13px;">For small teams & MVPs</p>
            <div class="price-val">$49<span>/mo</span></div>
            <ul class="feat-list">
                <li>Up to 5 Network Nodes</li>
                <li>Real-time Threat Feed</li>
                <li>Standard Support</li>
                <li>Weekly Security Audit</li>
            </ul>
            <button class="nav-btn" style="background: transparent; border: 1px solid var(--border);">Choose Plan</button>
        </div>

        <div class="price-card featured">
            <div class="popular-badge">RECOMMENDED</div>
            <h3>Enterprise</h3>
            <p style="color: var(--muted); font-size: 13px;">For growing tech businesses</p>
            <div class="price-val">$199<span>/mo</span></div>
            <ul class="feat-list">
                <li>Unlimited Network Nodes</li>
                <li>AI Autonomous Response</li>
                <li>24/7 Dedicated Support</li>
                <li>Advanced DDoS Protection</li>
            </ul>
            <button class="nav-btn">Start Free Trial</button>
        </div>

        <div class="price-card">
            <h3>Custom</h3>
            <p style="color: var(--muted); font-size: 13px;">For large scale infrastructure</p>
            <div class="price-val">Talk<span> to Us</span></div>
            <ul class="feat-list">
                <li>Full Governance Control</li>
                <li>On-Premise Deployment</li>
                <li>Custom Threat Models</li>
                <li>White-glove Onboarding</li>
            </ul>
            <button class="nav-btn" style="background: transparent; border: 1px solid var(--border);">Contact Sales</button>
        </div>
    </div>
</section>

<footer>
    &copy; 2026 VigilantPath Security. Built for Enterprise Excellence.
</footer>

<script>
    function scrollSection(id) {
        document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
    }

    let count = 2847193;
    const counterEl = document.getElementById('mainCounter');
    const logEl = document.getElementById('log');

    setInterval(() => {
        count += Math.floor(Math.random() * 7) + 1;
        counterEl.innerText = count.toLocaleString();
        
        if(Math.random() > 0.7) {
            const actions = ["BLOCK", "SCAN", "SYNC", "QUERY"];
            const action = actions[Math.floor(Math.random() * actions.length)];
            const time = new Date().toLocaleTimeString([], { hour12: false, hour: '2-digit', minute: '2-digit', second: '2-digit' });
            logEl.innerHTML = `> [${time}] ${action}: Incoming packet filtered...<br>` + logEl.innerHTML;
        }
    }, 2000);
</script>

</body>
</html>
