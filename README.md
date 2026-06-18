<!DOCTYPE html>
<html lang="en" data-theme="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CHANDA STUDY HUB Prototype</title>
    <style>
        :root[data-theme="light"] {
            --bg-primary: #f8f9fa;
            --bg-card: #ffffff;
            --text-main: #212529;
            --accent-color: #007bff;
            --border-color: #e3e6f0;
            --menu-hover: #f1f3f9;
        }
        :root[data-theme="dark"] {
            --bg-primary: #121212;
            --bg-card: #1e1e1e;
            --text-main: #f8f9fa;
            --accent-color: #375a7f;
            --border-color: #333333;
            --menu-hover: #2c2c2c;
        }

        body {
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
            background-color: var(--bg-primary);
            color: var(--text-main);
            margin: 0;
            transition: background-color 0.3s ease, color 0.3s ease;
            scroll-behavior: smooth;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 5%;
            background-color: var(--bg-card);
            border-bottom: 1px solid var(--border-color);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .logo { font-size: 22px; font-weight: bold; color: var(--accent-color); letter-spacing: 0.5px; }
        
        .nav-actions {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .dropdown {
            position: relative;
            display: inline-block;
        }

        .dropdown-btn {
            background-color: var(--accent-color);
            color: white;
            padding: 10px 18px;
            font-size: 15px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 500;
        }

        .dropdown-content {
            display: none;
            position: absolute;
            right: 0;
            background-color: var(--bg-card);
            min-width: 260px;
            box-shadow: 0px 8px 16px rgba(0,0,0,0.15);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            z-index: 1;
            overflow: hidden;
        }

        .dropdown-content a {
            color: var(--text-main);
            padding: 12px 16px;
            text-decoration: none;
            display: block;
            font-size: 14px;
        }

        .dropdown-content a:hover { background-color: var(--menu-hover); }
        .dropdown:hover .dropdown-content { display: block; }

        .toggle-btn {
            padding: 8px 16px;
            cursor: pointer;
            border-radius: 20px;
            border: 1px solid var(--border-color);
            background: var(--bg-primary);
            color: var(--text-main);
            font-weight: 500;
        }

        .main-container { padding: 40px 5%; max-width: 1200px; margin: 0 auto; }
        
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 50px;
        }

        .card {
            background-color: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 30px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.01);
            transition: transform 0.2s, border-color 0.2s;
        }
        .card:hover { 
            transform: translateY(-4px); 
            border-color: var(--accent-color);
        }

        .card h3 { margin-top: 0; color: var(--accent-color); font-size: 18px; }

        .tools-section {
            background-color: var(--bg-card);
            padding: 35px;
            border-radius: 12px;
            border: 1px solid var(--border-color);
        }

        .tool-box {
            margin: 25px 0;
            padding: 25px;
            border: 2px dashed var(--border-color);
            border-radius: 8px;
            background-color: var(--bg-primary);
        }

        button.action-btn {
            background-color: var(--accent-color);
            color: white;
            border: none;
            padding: 10px 22px;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 500;
        }
        
        .player-status { margin-top: 15px; font-size: 14px; font-weight: 500; color: var(--accent-color); }
    </style>
</head>
<body>

    <header>
        <div class="logo">CHANDA STUDY HUB</div>
        <div class="nav-actions">
            <div class="dropdown">
                <button class="dropdown-btn">📚 Access Books Menu ▼</button>
                <div class="dropdown-content">
                    <a href="#book-1">Auditing</a>
                    <a href="#book-2">Corporate Governance</a>
                    <a href="#book-3">IFRS and IAS Standards</a>
                    <a href="#book-4">Strategic Business Analysis</a>
                    <a href="#book-5">Financial Management</a>
                    <a href="#book-6">Financial Reporting</a>
                </div>
            </div>
            <button class="toggle-btn" onclick="toggleTheme()">🌓 Toggle Mode</button>
        </div>
    </header>

    <div class="main-container">
        <h2 style="margin-bottom: 25px;">📚 Academic Study Dashboard (Prototype)</h2>
        <div class="grid">
            <div class="card" id="book-1">
                <h3>Auditing</h3>
                <p>Access audit tracking metrics, assurance guidelines, and textbook configurations.</p>
                <button class="action-btn" style="padding: 6px 14px; font-size: 13px;">Open Modules</button>
            </div>
            <div class="card" id="book-2">
                <h3>Corporate Governance</h3>
                <p>Review compliance policies, risk assessment strategies, and regulatory boards.</p>
                <button class="action-btn" style="padding: 6px 14px; font-size: 13px;">Open Modules</button>
            </div>
            <div class="card" id="book-3">
                <h3>IFRS and IAS Standards</h3>
                <p>Explore international reporting transparency and comprehensive technical rules.</p>
                <button class="action-btn" style="padding: 6px 14px; font-size: 13px;">Open Modules</button>
            </div>
            <div class="card" id="book-4">
                <h3>Strategic Business Analysis</h3>
                <p>Analyze real-world business frameworks, metrics tables, and case examples.</p>
                <button class="action-btn" style="padding: 6px 14px; font-size: 13px;">Open Modules</button>
            </div>
            <div class="card" id="book-5">
                <h3>Financial Management</h3>
                <p>Evaluate financial forecasting tools, investment evaluations, and budgets.</p>
                <button class="action-btn" style="padding: 6px 14px; font-size: 13px;">Open Modules</button>
            </div>
            <div class="card" id="book-6">
                <h3>Financial Reporting</h3>
                <p>Construct balance sheets, income frameworks, and standard disclosures.</p>
                <button class="action-btn" style="padding: 6px 14px; font-size: 13px;">Open Modules</button>
            </div>
        </div>

        <div class="tools-section">
            <h2 style="margin-top: 0;">🎧 Study Hub AI Speech Engine</h2>
            <div class="tool-box">
                <h3 style="margin-top:0; font-size:16px;">Transform PDF Notes to Lecture Audio</h3>
                <input type="file" accept=".pdf" style="margin-bottom: 15px; display: block;">
                <button class="action-btn" onclick="simulateProcessing()">Generate Audio Lecture</button>
                <div id="statusContainer" class="player-status"></div>
            </div>
        </div>
    </div>

    <script>
        function toggleTheme() {
            const root = document.documentElement;
            const currentTheme = root.getAttribute('data-theme');
            const newTheme = currentTheme === 'dark' ? 'light' : 'dark';
            root.setAttribute('data-theme', newTheme);
        }

        function simulateProcessing() {
            const status = document.getElementById('statusContainer');
            status.innerHTML = "⏳ Prototype Simulation: Reading text lines and synthesizing natural audio accent...";
            setTimeout(() => {
                status.innerHTML = "✅ Processing complete! (Connect the Python backend script to play live files).";
            }, 2000);
        }
    </script>
</body>
</html>
