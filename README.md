<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Sacred Anniversary Blessing</title>
    <style>
        :root {
            --parchment: #f4e4bc;
            --gold: #d4af37;
            --crimson: #8b0000;
            --border-style: 8px double var(--gold);
        }

        body {
            background-color: #1a1a1a;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            font-family: 'Georgia', serif;
            overflow-x: hidden;
        }

        /* The Diya Animation */
        .diya-container {
            position: fixed;
            bottom: 20px;
            text-align: center;
        }

        .flame {
            width: 15px;
            height: 25px;
            background: linear-gradient(to bottom, #ffea00, #ff7b00);
            border-radius: 50% 50% 20% 20%;
            margin: 0 auto;
            box-shadow: 0 0 20px #ff7b00;
            animation: flicker 0.1s infinite alternate;
        }

        @keyframes flicker {
            0% { transform: scale(1); opacity: 0.9; }
            100% { transform: scale(1.1); opacity: 1; }
        }

        .lamp-base {
            width: 60px;
            height: 25px;
            background: #8b4513;
            border-radius: 0 0 50px 50px;
            border-top: 4px solid #5d2e0a;
        }

        /* The Scroll Container */
        .scroll-wrapper {
            position: relative;
            width: 90%;
            max-width: 500px;
            perspective: 1000px;
        }

        /* The Seal (Button) */
        #seal {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 100px;
            height: 100px;
            background: var(--crimson);
            border-radius: 50%;
            border: 4px solid #5e0000;
            color: var(--gold);
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            box-shadow: 0 0 15px rgba(0,0,0,0.5);
            z-index: 10;
            font-weight: bold;
            transition: all 0.5s ease;
            text-align: center;
            font-size: 0.9rem;
            padding: 10px;
        }

        #seal:hover {
            transform: translate(-50%, -50%) scale(1.1);
            box-shadow: 0 0 25px var(--crimson);
        }

        /* The Scroll Paper */
        .parchment {
            background-color: var(--parchment);
            background-image: url('https://www.transparenttextures.com/patterns/paper-fibers.png');
            border: var(--border-style);
            padding: 0 40px;
            max-height: 0;
            overflow: hidden;
            transition: max-height 2s ease-in-out, padding 1s ease;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            position: relative;
            border-radius: 5px;
        }

        .parchment.open {
            max-height: 1000px;
            padding: 60px 40px;
        }

        .content {
            opacity: 0;
            transition: opacity 1.5s ease 1s;
            text-align: center;
            color: #332b1a;
        }

        .parchment.open .content {
            opacity: 1;
        }

        h1 {
            color: var(--crimson);
            font-variant: small-caps;
            border-bottom: 1px solid var(--gold);
            padding-bottom: 10px;
        }

        .main-message {
            font-size: 1.2rem;
            line-height: 1.6;
            font-style: italic;
            margin: 20px 0;
        }

        .blessing {
            font-size: 1rem;
            color: #5d4a26;
            margin-top: 30px;
            padding: 15px;
            border-top: 1px solid var(--gold);
        }

        .ornament {
            font-size: 2rem;
            color: var(--gold);
            display: block;
            margin: 10px 0;
        }
    </style>
</head>
<body>

    <div class="scroll-wrapper">
        <div id="seal" onclick="openScroll()">Break the Seal</div>
        
        <div class="parchment" id="parchment">
            <div class="content">
                <span class="ornament">❧</span>
                <h1>Happy Anniversary</h1>
                <p class="main-message">
                    "To the pillars of our family—may your union be blessed by the heavens with the same strength and grace you show us every day."
                </p>
                <div class="blessing">
                    <strong>Traditional Blessing:</strong><br>
                    May your home be filled with the light of prosperity (Lakshmi) and the wisdom of peace. May the coming years bring you boundless health and shared laughter.
                </div>
                <span class="ornament">❧</span>
            </div>
        </div>
    </div>

    <div class="diya-container">
        <div class="flame"></div>
        <div class="lamp-base"></div>
    </div>

    <script>
        function openScroll() {
            const seal = document.getElementById('seal');
            const parchment = document.getElementById('parchment');
            
            // Fade out the seal
            seal.style.opacity = '0';
            seal.style.pointerEvents = 'none';
            
            // Open the parchment
            parchment.classList.add('open');
        }
    </script>
</body>
</html>
