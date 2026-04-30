# pickaxe
Are u ok?
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Player Stats | Sporshyo</title>
    <style>
        :root {
            --bg: #e0e0e0;
            --card-bg: #c6c6c6;
            --text: #333;
            --mc-border: #373737;
            --accent: #3f76e4;
            --header-overlay: rgba(0,0,0,0.3);
        }

        /* Dark Mode Variables */
        [data-theme="dark"] {
            --bg: #1a1a1a;
            --card-bg: #2d2d2d;
            --text: #f0f0f0;
            --mc-border: #000;
            --accent: #00f3e3;
            --header-overlay: rgba(0,0,0,0.7);
        }

        body {
            margin: 0; background: var(--bg); color: var(--text);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; 
            transition: background 0.4s, color 0.4s;
            display: flex; flex-direction: column; align-items: center;
            -webkit-tap-highlight-color: transparent;
        }

        /* Header Section */
        header {
            width: 100%; height: 280px;
            background: linear-gradient(var(--header-overlay), var(--header-overlay)), 
                        url('https://wallpaperaccess.com/full/223161.jpg');
            background-size: cover; background-position: center;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            border-bottom: 6px solid var(--mc-border);
        }

        .avatar-frame {
            width: 90px; height: 90px; background: #5da037;
            border: 4px solid #fff; box-shadow: 0 5px 15px rgba(0,0,0,0.4);
            image-rendering: pixelated; margin-bottom: 10px;
            background-image: url('https://mc-heads.net/avatar/steve'); /* Placeholder for a skin */
            background-size: cover;
        }

        /* Fixed Theme Toggle */
        .theme-toggle {
            position: absolute; top: 20px; right: 20px;
            padding: 10px 15px; background: var(--card-bg); 
            border: 3px solid var(--mc-border); color: var(--text);
            cursor: pointer; font-weight: bold; border-radius: 4px;
            font-size: 14px; z-index: 100;
        }

        .container { width: 92%; max-width: 550px; margin-top: -40px; }

        .card {
            background: var(--card-bg); padding: 25px; border: 4px solid var(--mc-border);
            border-top: 4px solid rgba(255,255,255,0.4); border-left: 4px solid rgba(255,255,255,0.4);
            margin-bottom: 20px; box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }

        .card h2 { margin: 0 0 15px 0; font-size: 1.1rem; text-transform: uppercase; letter-spacing: 1px; color: var(--accent); }

        .stats-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
        .stat-box { background: rgba(0,0,0,0.05); padding: 12px; border: 2px solid rgba(0,0,0,0.1); border-radius: 4px; text-align: center; }
        .stat-val { display: block; font-size: 1.2rem; font-weight: bold; color: var(--accent); }

        .btn {
            display: block; width: 100%; padding: 15px; margin-top: 15px;
            background: #8b8b8b; border: 4px solid #000;
            border-top-color: #fff; border-left-color: #fff;
            color: white; text-align: center; text-decoration: none;
            font-weight: bold; text-shadow: 2px 2px #000; cursor: pointer;
            box-sizing: border-box;
        }

        .btn:active {
            border: 4px solid #fff; border-top-color: #000; border-left-color: #000;
            transform: translateY(2px);
        }

        .dedication {
            text-align: center; margin-top: 25px; font-style: italic;
            color: var(--accent); font-weight: 600; font-size: 0.95rem;
            border-top: 1px solid rgba(0,0,0,0.1); padding-top: 15px;
        }

        footer { margin: 50px 0; color: #777; font-size: 0.8rem; text-align: center; line-height: 1.5; }
    </style>
</head>
<body data-theme="dark">

    <button class="theme-toggle" onclick="toggleTheme()" id="themeBtn">☀️ Mode</button>

    <header>
        <div class="avatar-frame"></div>
        <h1 style="text-shadow: 3px 3px #000; margin: 0; color: #fff; letter-spacing: 2px;">SPORSHYO</h1>
        <p style="color: #ddd; font-weight: 300;" id="greeting">Elite Minecraft Builder</p>
    </header>

    <div class="container">
        <!-- Stats Card -->
        <div class="card">
            <h2>Server Statistics</h2>
            <div class="stats-grid">
                <div class="stat-box"><span class="stat-val">∞</span> IQ Plays</div>
                <div class="stat-box"><span class="stat-val">10/10</span> Building</div>
                <div class="stat-box"><span class="stat-val">MVP</span> Friendship</div>
                <div class="stat-box"><span class="stat-val">Active</span> Survivor</div>
            </div>
        </div>

        <!-- Quest Log Card -->
        <div class="card">
            <h2>Quest Log</h2>
            <p style="line-height: 1.6; margin-bottom: 10px;">
                একসাথে গেম খেলা আর সেই রাতভর আড্ডাগুলো সত্যিই সেরা। এই ওয়েবসাইটটা বানালাম আমাদের গেমিং মেমোরিগুলো সেলিব্রেট করার জন্য। GG, Player 1!
            </p>
            <div class="dedication">A website made by Rupom for Sporshyo</div>
        </div>

        <!-- Actions Card -->
        <div class="card">
            <h2>Quick Actions</h2>
            <button class="btn" onclick="alert('Coordinate Leak! Shared Base at 404, 64, -200')">View Base Coords</button>
            <a href="https://github.com" class="btn">Source Code</a>
        </div>
    </div>

    <footer>
        &copy; 2026 Developed with HTML/CSS/JS <br>
        Built on GitHub Mobile <br>
        Version 2.1.0 - Stable Build
    </footer>

    <script>
        // Theme Toggle Logic
        function toggleTheme() {
            const body = document.body;
            const btn = document.getElementById('themeBtn');
            if (body.getAttribute('data-theme') === 'dark') {
                body.setAttribute('data-theme', 'light');
                btn.innerText = "🌙 Mode";
            } else {
                body.setAttribute('data-theme', 'dark');
                btn.innerText = "☀️ Mode";
            }
        }

        // Bonus: Dynamic Greeting based on time
        const hour = new Date().getHours();
        const greetElement = document.getElementById('greeting');
        if (hour < 12) greetElement.innerText = "Good Morning, Elite Builder";
        else if (hour < 18) greetElement.innerText = "Good Afternoon, Elite Builder";
        else greetElement.innerText = "Good Evening, Elite Builder";
    </script>
</body>
</html>
