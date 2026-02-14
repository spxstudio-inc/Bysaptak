<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>
      forkushiiiii
    </title>
    <style>
      @import url(&#39;https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&amp;family=Dancing+Script:wght@700&amp;family=Great+Vibes&amp;display=swap&#39;);

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: &#39;Poppins&#39;, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 99%, #fecfef 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
            overflow: hidden;
            position: relative;
        }

        .card {
            background: rgba(255, 255, 255, 0.95);
            padding: 2.5rem;
            border-radius: 25px;
            box-shadow: 0 15px 35px rgba(255, 75, 110, 0.15);
            width: 100%;
            max-width: 450px;
            text-align: center;
            position: relative;
            min-height: 400px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            transition: all 0.5s ease;
            z-index: 10;
        }

        h1 {
            color: #ff4b6e;
            font-size: 2.2rem;
            margin-bottom: 0.5rem;
            font-family: &#39;Dancing Script&#39;, cursive;
        }

        #proposalMsg {
            font-family: &#39;Great Vibes&#39;, cursive;
            font-size: 3rem;
            color: #d6335c;
            line-height: 1.2;
            margin-bottom: 2rem;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
            font-weight: 400;
        }

        p {
            color: #555;
            font-size: 1.1rem;
            line-height: 1.6;
            margin-bottom: 2rem;
        }

        .btn-group {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
        }

        button {
            padding: 12px 30px;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            outline: none;
        }

        .btn-yes {
            background: #ff4b6e;
            color: white;
            box-shadow: 0 5px 15px rgba(255, 75, 110, 0.3);
        }

        .btn-yes:hover {
            transform: scale(1.05);
            background: #e63e5d;
        }

        .btn-no {
            background: #f1f1f1;
            color: #666;
        }

        .hidden {
            display: none !important;
        }

        /* Animations */
        .fade-in {
            animation: fadeIn 0.8s ease-out;
        }

        .pop-in {
            animation: popIn 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes popIn {
            from {
                opacity: 0;
                transform: scale(0.8);
            }

            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        /* Floating Hearts */
        .floating-heart {
            position: absolute;
            color: #ff4b6e;
            opacity: 0.6;
            top: 100vh;
            animation: floatUp linear forwards;
            z-index: 1;
            pointer-events: none;
        }

        @keyframes floatUp {
            to {
                transform: translateY(-120vh) rotate(360deg);
            }
        }

        /* Loading */
        .loader {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #ff4b6e;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% {
                transform: rotate(0deg);
            }

            100% {
                transform: rotate(360deg);
            }
        }

        .shayari-box {
            background: #fff0f3;
            padding: 1.5rem;
            border-radius: 15px;
            border: 1px dashed #ff4b6e;
            margin-bottom: 2rem;
            font-style: italic;
            color: #d6335c;
        }

        .heart-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
            animation: heartbeat 1.5s infinite;
        }

        @keyframes heartbeat {
            0% {
                transform: scale(1);
            }

            50% {
                transform: scale(1.1);
            }

            100% {
                transform: scale(1);
            }
        }

        .valentine-media {
            max-width: 150px;
            width: 100%;
            border-radius: 15px;
            margin-bottom: 1rem;
            animation: popIn 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .plead-msg {
            display: block;
            width: 100%;
            margin-top: 15px;
            color: #ff4b6e;
            font-size: 0.95rem;
            font-weight: 500;
            min-height: 24px;
            /* Prevent layout jump */
            transition: opacity 0.3s;
        }

        .no-bg {
            box-shadow: none !important;
            background: transparent !important;
            border-radius: 0 !important;
        }

        .emoji-icon {
            height: 1.2em;
            vertical-align: sub;
            margin: 0 4px;
            display: inline-block;
        }
    </style>
  </head>
  <body>
    <div class="card" id="mainCard">
      <div class="loader" id="loader">
      </div>
      <!-- Error State -->
      <div id="errorState" class="hidden">
        <h1>
          Oops! 💔
        </h1>
        <p id="errorMsg">
          Something went wrong...
        </p>
      </div>
      <!-- Stage 1: Proposal -->
      <div id="stage1" class="hidden fade-in">
        <h1>
          Hey
          <span id="partnerName"></span>
          <img src="https://em-content.zobj.net/source/apple/391/sparkling-heart_1f496.png" class="emoji-icon" alt="💖" />
        </h1>
        <p id="proposalMsg">
           Will you be my Valentine?
        </p>
        <div class="btn-group">
          <button class="btn-yes" onclick="nextStage()">
            Hanji
            <img src="https://em-content.zobj.net/source/apple/391/red-heart_2764-fe0f.png" class="emoji-icon" alt="❤️" />
          </button>
          <button class="btn-no" id="noBtn" onmouseover="moveNoButton()" onclick="moveNoButton()">
            Nahi
            <img src="https://em-content.zobj.net/source/apple/391/see-no-evil-monkey_1f648.png" class="emoji-icon" alt="🙈" />
          </button>
        </div>
        <p id="pleadMessage" class="plead-msg">
        </p>
      </div>
      <!-- Stage 2: Confirmation -->
      <div id="stage2" class="hidden">
        <video src="kiss.mp4" autoplay="" loop="" muted="" playsinline="" class="valentine-media">
        </video>
        <h1>
          I Knew It!
          <img src="https://em-content.zobj.net/source/apple/391/red-heart_2764-fe0f.png" class="emoji-icon" alt="❤️" />
        </h1>
        <p>
          Aap mujhse pyaar karte ho! hehe
          <img src="https://em-content.zobj.net/source/apple/391/see-no-evil-monkey_1f648.png" class="emoji-icon" alt="🙈" />
          <br />
          accha ab niche button pe click karo
        </p>
        <button class="btn-yes" onclick="goToShayari()">
          For you
          <img src="https://em-content.zobj.net/source/apple/391/love-letter_1f48c.png" class="emoji-icon" alt="💌" />
        </button>
      </div>
      <!-- Stage 3: Shayari -->
      <div id="stage3" class="hidden">
        <img src="doggy.png" alt="Cute Doggy" class="valentine-media no-bg" />
        <div class="shayari-box" id="shayariText">
        </div>
        <button class="btn-yes" onclick="nextShayari()">
          Next
          <img src="https://em-content.zobj.net/source/apple/391/sparkling-heart_1f496.png" class="emoji-icon" alt="💖" />
        </button>
      </div>
    </div>
   <script>
    function createFloatingHeart() {
        const heart = document.createElement('div');
        heart.classList.add('floating-heart');
        heart.innerHTML = '❤';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.animationDuration = Math.random() * 3 + 2 + 's';
        heart.style.fontSize = Math.random() * 1.5 + 0.5 + 'rem';
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 5000);
    }

    setInterval(createFloatingHeart, 800);

    const shayaris = [
        "Aap hi ke bina hoon kyun bechain?<br>Aap hi kyun meri zaroorat hain?<br>Wehm itna haseen nahi hota,<br>Waakai aap khoobsurat hain ❤️",
        "Teri dhadkan hi zindagi ka kissa hai mera,<br>Tu zindagi ka ek ahem hissa hai mera,<br>Meri mohabbat tujhse sirf lafzon ki nahi,<br>Teri rooh se rooh ka rishta hai mera. 💕",
        "Kitna Pyar Hai Tumse Yeh Jan Lo,<br>Tum Hi Zindagi Ho Meri Yeh Man Lo,<br>Tumhe Dene Ko Mere Paas Kuchh Nahi,<br>Bas Ek Jaan Hai Jab Ji Chaye Mang Lo! 🌹"
    ];

    const noMessages = [
        "Soch lo na please 😢",
        "Ek baar aur soch lo 💔",
        "Man jao na... 🥺",
        "Please... 🥺❤️",
        "Mera dil toot jayega... 💔"
    ];

    let currentShayariParams = 0;
    let noCount = 0;

    document.addEventListener('DOMContentLoaded', () => {

        const urlParams = new URLSearchParams(window.location.search);
        const name = urlParams.get('name') || "Kushi";
        const message = urlParams.get('message');

        document.getElementById('loader').classList.add('hidden');
        document.getElementById('stage1').classList.remove('hidden');

        document.getElementById('partnerName').innerText = name;

        if (message && message.trim() !== "") {
            document.getElementById('proposalMsg').innerText = message;
        }
    });

    function moveNoButton() {
        const btn = document.getElementById('noBtn');
        const pleadMsg = document.getElementById('pleadMessage');

        pleadMsg.innerHTML = noMessages[noCount % noMessages.length];
        noCount++;

        const maxX = window.innerWidth - btn.offsetWidth - 20;
        const maxY = window.innerHeight - btn.offsetHeight - 20;

        btn.style.position = 'fixed';
        btn.style.left = Math.random() * maxX + 'px';
        btn.style.top = Math.random() * maxY + 'px';
        btn.style.zIndex = '1000';
    }

    function nextStage() {
        for (let i = 0; i < 30; i++)
            setTimeout(createFloatingHeart, i * 50);

        document.getElementById('stage1').classList.add('hidden');
        document.getElementById('stage2').classList.remove('hidden');
    }

    function goToShayari() {
        document.getElementById('stage2').classList.add('hidden');
        document.getElementById('stage3').classList.remove('hidden');
        document.getElementById('shayariText').innerHTML = shayaris[0];
    }

    function nextShayari() {
        currentShayariParams++;
        document.getElementById('shayariText').innerHTML =
            shayaris[currentShayariParams % shayaris.length];
    }
</script>

  </body>
</html>