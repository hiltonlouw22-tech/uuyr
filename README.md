<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>M2Y Boss - Africa's Secure Commerce Revolution</title>
    <meta name="description" content="Secure marketplace with verified deliveries, carpool, live tracking, and escrow payments">
    <meta name="theme-color" content="#1877F2" media="(prefers-color-scheme: light)">
    <meta name="theme-color" content="#0d1117" media="(prefers-color-scheme: dark)">

    <!-- Enhanced PWA Manifest -->
    <link rel="manifest" href="data:application/manifest+json,{
        %22name%22:%22M2Y%20Boss%22,
        %22short_name%22:%22M2Y%22,
        %22start_url%22:%22.%22,
        %22display%22:%22standalone%22,
        %22background_color%22:%22#F0F2F5%22,
        %22theme_color%22:%22#1877F2%22,
        %22icons%22:[
            {%22src%22:%22data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20192%20192'%3E%3Ctext%20y='160'%20font-size='140'%3E🚘%3C/text%3E%3C/svg%3E%22,%22sizes%22:%22192x192%22,%22type%22:%22image/svg+xml%22},
            {%22src%22:%22data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20512%20512'%3E%3Ctext%20y='440'%20font-size='380'%3E🚘%3C/text%3E%3C/svg%3E%22,%22sizes%22:%22512x512%22,%22type%22:%22image/svg+xml%22}
        ]
    }">

    <style>
        /* === M2Y BOSS EDITION - COMBINED & UPGRADED === */
        :root {
            --bg: #F0F2F5;
            --card: white;
            --text: #1C1E21;
            --text-light: #65676B;
            --primary: #1877F2;
            --success: #42B72A;
            --gold: #FFD700;
            --gradient: linear-gradient(135deg, #1877F2, #8A2BE2, #FF6B35);
        }

        @media (prefers-color-scheme: dark) {
            :root {
                --bg: #0d1117;
                --card: #161b22;
                --text: #f0f6fc;
                --text-light: #8b949e;
            }
            body { background: var(--bg); color: var(--text); }
            .card, .item-card, .nav-tabs, .bottom-nav { background: var(--card); }
            .form-control { background: #161b22; color: var(--text); border-color: #30363d; }
        }

        * { margin:0; padding:0; box-sizing:border-box; }
        body { font-family: 'Segoe UI', sans-serif; background: var(--bg); color: var(--text); min-height: 100vh; transition: background 0.3s, color 0.3s; }

        .container { max-width: 100%; padding: 0 16px; margin: 0 auto; }

        .header {
            background: var(--gradient);
            color: white;
            padding: 60px 20px 28px;
            text-align: center;
            border-bottom-left-radius: 30px;
            border-bottom-right-radius: 30px;
            position: relative;
        }

        .logo { font-size: 56px; animation: float 4s ease-in-out infinite; }
        @keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-12px)} }

        .security-badge {
            position: fixed;
            top: 12px;
            right: 12px;
            background: var(--success);
            color: white;
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 800;
            z-index: 10000;
            display: flex;
            align-items: center;
            gap: 6px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.2);
        }

        .loading-overlay {
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.85);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 10000;
            color: white;
            backdrop-filter: blur(4px);
        }

        .spinner {
            width: 48px;
            height: 48px;
            border: 4px solid rgba(255,255,255,0.3);
            border-top: 4px solid white;
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin-bottom: 20px;
        }

        @keyframes spin { to { transform: rotate(360deg); } }

        /* Dark Mode Toggle */
        .dark-toggle {
            position: fixed;
            top: 16px;
            left: 16px;
            background: rgba(0,0,0,0.3);
            color: white;
            width: 44px;
            height: 44px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            z-index: 10000;
            cursor: pointer;
        }

        /* Bottom Nav */
        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(255,255,255,0.95);
            backdrop-filter: blur(12px);
            display: flex;
            padding: 8px 0 16px;
            box-shadow: 0 -4px 20px rgba(0,0,0,0.1);
            z-index: 1000;
        }

        .nav-item {
            flex: 1;
            text-align: center;
            padding: 8px;
            font-size: 10px;
            font-weight: 800;
            color: var(--text-light);
            cursor: pointer;
        }

        .nav-item.active { color: var(--primary); }
        .nav-item span { font-size: 24px; display: block; margin-bottom: 4px; }

        /* Live Activity Feed */
        .activity-feed { margin: 20px 0; }
        .activity-item {
            display: flex;
            align-items: center;
            padding: 14px;
            background: var(--card);
            border-radius: 14px;
            margin-bottom: 10px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.06);
            animation: slideIn 0.6s ease;
        }

        @keyframes slideIn { from { opacity: 0; transform: translateX(-30px); } }

        /* Cards & Buttons (kept from first version) */
        .card {
            background: var(--card);
            border-radius: 20px;
            padding: 20px;
            margin-bottom: 16px;
            box-shadow: 0 4px 16px rgba(0,0,0,0.08);
            border-left: 4px solid var(--primary);
            transition: transform 0.25s ease;
        }

        .card:hover { transform: translateY(-6px); }

        .btn {
            background: var(--gradient);
            color: white;
            border: none;
            padding: 16px;
            border-radius: 14px;
            font-weight: 800;
            cursor: pointer;
            transition: all 0.25s;
        }

        .btn:hover { transform: translateY(-3px); }

        /* Install Prompt */
        .install-prompt {
            position: fixed;
            bottom: 80px;
            left: 16px;
            right: 16px;
            background: var(--card);
            padding: 18px;
            border-radius: 16px;
            box-shadow: 0 8px 30px rgba(0,0,0,0.3);
            text-align: center;
            z-index: 999;
            display: none;
        }

        .section { display: none; padding-bottom: 80px; }
        .section.active { display: block; animation: fadeIn 0.4s; }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    </style>
</head>
<body>

    <!-- Dark Mode Toggle -->
    <div class="dark-toggle" onclick="toggleDark()">🌙</div>

    <!-- Security Badge -->
    <div class="security-badge">🔒 SECURE CONNECTION</div>

    <!-- Loading Overlay -->
    <div class="loading-overlay" id="loadingOverlay">
        <div class="spinner"></div>
        <div>Initializing M2Y Boss...</div>
    </div>

    <!-- Install Prompt -->
    <div class="install-prompt" id="installPrompt">
        <strong>🚀 Install M2Y Boss</strong><br>
        <small>Add to home screen for instant access & offline mode</small><br><br>
        <button class="btn" onclick="promptInstall()">Install Now</button>
    </div>

    <!-- Login Section -->
    <div id="login" class="section active">
        <div class="header">
            <div class="logo">🚘</div>
            <div style="font-size:28px;font-weight:800;">M2Y BOSS</div>
            <div style="font-size:16px;opacity:0.9;">Secure African Commerce</div>
        </div>

        <div class="container">
            <div class="card">
                <div style="font-size:20px;font-weight:800;text-align:center;margin-bottom:20px;">🔐 Secure Login</div>
                <button class="btn btn-success" onclick="quickLogin('buyer')">👤 Buyer Demo</button>
                <button class="btn btn-warning" onclick="quickLogin('driver')">🚗 Driver Demo</button>
                <button class="btn" style="background:var(--gold);color:black;" onclick="quickLogin('seller')">🏪 Seller Demo</button>
            </div>
        </div>
    </div>

    <!-- Main App Section -->
    <div id="mainApp" class="section">
        <div class="header">
            <div class="logo">🚘</div>
            <div style="font-size:28px;font-weight:800;" id="userGreeting">M2Y BOSS</div>
            <div style="font-size:16px;opacity:0.9;">Secure. Fast. Live.</div>
        </div>

        <div class="container">
            <!-- Live Activity Feed -->
            <div class="card">
                <div style="font-size:20px;font-weight:800;margin-bottom:16px;">🔥 LIVE ACTIVITY</div>
                <div class="activity-feed" id="activityFeed"></div>
            </div>

            <!-- Quick Actions -->
            <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin:24px 0;">
                <div class="card" style="text-align:center;padding:20px;cursor:pointer;" onclick="vibrate();showNotification('Opening Marketplace','info')">
                    <div style="font-size:40px;">🛍️</div>
                    <div style="font-weight:800;margin-top:8px;">Shop</div>
                </div>
                <div class="card" style="text-align:center;padding:20px;cursor:pointer;" onclick="vibrate();showNotification('Requesting Driver','success')">
                    <div style="font-size:40px;">📦</div>
                    <div style="font-weight:800;margin-top:8px;">Deliver</div>
                </div>
                <div class="card" style="text-align:center;padding:20px;cursor:pointer;" onclick="vibrate();showNotification('Finding Carpool','info')">
                    <div style="font-size:40px;">👥</div>
                    <div style="font-weight:800;margin-top:8px;">Carpool</div>
                </div>
            </div>

            <!-- Live Tracking Card -->
            <div class="card">
                <div style="font-size:20px;font-weight:800;margin-bottom:16px;">📍 LIVE TRACKING</div>
                <div style="height:220px;background:#87CEEB;border-radius:14px;position:relative;overflow:hidden;">
                    <div style="position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);font-size:50px;">📍</div>
                    <div id="driverCar" style="position:absolute;top:80%;left:10%;font-size:44px;transition:all 10s ease;">🚗</div>
                </div>
                <div style="padding:16px 0;text-align:center;">
                    <strong>John arriving in 6 min</strong><br>
                    <small>Toyota Hilux • 1.8km away • Verified Driver</small>
                </div>
            </div>
        </div>
    </div>

    <!-- Bottom Navigation -->
    <div class="bottom-nav">
        <div class="nav-item active" onclick="loadSection('home')"><span>🏠</span>Home</div>
        <div class="nav-item" onclick="loadSection('marketplace')"><span>🛍️</span>Shop</div>
        <div class="nav-item" onclick="loadSection('deliver')"><span>📦</span>Deliver</div>
        <div class="nav-item" onclick="loadSection('wallet')"><span>💰</span>Wallet</div>
        <div class="nav-item" onclick="secureLogout()"><span>👤</span>Me</div>
    </div>

    <script>
        // M2Y BOSS COMBINED EDITION
        let darkMode = window.matchMedia('(prefers-color-scheme: dark)').matches;
        let deferredPrompt;

        function toggleDark() {
            darkMode = !darkMode;
            document.body.style.background = darkMode ? '#0d1117' : '#F0F2F5';
            vibrate();
        }

        function vibrate() {
            if (navigator.vibrate) navigator.vibrate(40);
        }

        function showNotification(msg, type='info') {
            const n = document.createElement('div');
            n.style.cssText = `position:fixed;top:90px;right:16px;background:white;padding:16px;border-radius:12px;box-shadow:0 8px 30px rgba(0,0,0,0.2);border-left:5px solid ${type==='success'?'#27ae60':type==='error'?'#e74c3c':'#1877F2'};z-index:10000;max-width:300px;transform:translateX(120%);transition:0.4s;`;
            n.innerHTML = `<strong>${type==='success'?'✅':type==='error'?'❌':'ℹ️'} ${type.toUpperCase()}</strong><div style="margin-top:6px;">${msg}</div>`;
            document.body.appendChild(n);
            setTimeout(()=>n.style.transform='translateX(0)',100);
            setTimeout(()=> { n.style.transform='translateX(120%)'; setTimeout(()=>n.remove(),400); },4500);
        }

        // Live Activity
        const activities = [
            "💸 Thabo bought iPhone 13 Pro (R600)",
            "🚗 Sarah accepted delivery – R200",
            "✅ Lerato received package safely",
            "👥 Carpool Sandton → Rosebank (R45)",
            "🤑 FashionHub earned R1,200 today",
            "📦 Mike completed 5 deliveries"
        ];

        function addActivity() {
            const feed = document.getElementById('activityFeed');
            const item = document.createElement('div');
            item.className = 'activity-item';
            const act = activities[Math.floor(Math.random()*activities.length)];
            item.innerHTML = `<span style="font-size:28px;margin-right:14px;">${act.split(' ')[0]}</span><div>${act}<br><small style="color:var(--text-light);">Just now • Verified</small></div>`;
            feed.insertBefore(item, feed.firstChild);
            if (feed.children.length > 7) feed.removeChild(feed.lastChild);
        }

        // Driver Animation
        function moveDriver() {
            const car = document.getElementById('driverCar');
            car.style.transition = 'all 12s ease-in-out';
            car.style.left = '85%';
            car.style.top = '25%';
            setTimeout(() => {
                car.style.left = '50%';
                car.style.top = '50%';
                showNotification('🚗 Driver arrived!', 'success');
            }, 12000);
        }

        // Quick Login
        function quickLogin(role) {
            document.getElementById('loadingOverlay').style.display = 'flex';
            setTimeout(() => {
                document.getElementById('login').classList.remove('active');
                document.getElementById('mainApp').classList.add('active');
                document.getElementById('userGreeting').textContent = `Welcome, ${role.toUpperCase()}!`;
                addActivity(); addActivity(); addActivity();
                moveDriver();
                document.getElementById('loadingOverlay').style.display = 'none';
                showNotification('Logged in – Boss Mode Activated', 'success');
            }, 1500);
        }

        function secureLogout() {
            showNotification('Securely logging out...', 'info');
            setTimeout(() => location.reload(), 1000);
        }

        function loadSection(sec) {
            showNotification(`Loading ${sec}...`, 'info');
        }

        // Install Prompt
        window.addEventListener('beforeinstallprompt', (e) => {
            e.preventDefault();
            deferredPrompt = e;
            setTimeout(() => document.getElementById('installPrompt').style.display = 'block', 8000);
        });

        function promptInstall() {
            if (deferredPrompt) {
                deferredPrompt.prompt();
                deferredPrompt.userChoice.then(() => {
                    document.getElementById('installPrompt').style.display = 'none';
                });
            }
        }

        // Init
        setInterval(addActivity, 6000);
        setInterval(moveDriver, 20000);
        document.getElementById('loadingOverlay').style.display = 'none';
    </script>
</body>
</html>
