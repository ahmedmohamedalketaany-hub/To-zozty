<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>حاجة بسيطة لـ زوزتي ❤️</title>
    <style>
        body { 
            font-family: 'Arial', sans-serif; 
            background-color: #fce4ec; 
            display: flex; 
            justify-content: center; 
            align-items: center; 
            min-height: 100vh; 
            margin: 0; 
            padding: 20px; 
            box-sizing: border-box; 
            overflow-x: hidden;
        }
        .card { 
            background: white; 
            padding: 30px; 
            border-radius: 20px; 
            box-shadow: 0 15px 30px rgba(0,0,0,0.15); 
            text-align: center; 
            width: 100%; 
            max-width: 400px; 
            border: 3px solid #f06292; 
        }
        h1 { color: #ad1457; font-size: 24px; margin-bottom: 10px; }
        p.hint { color: #888; font-size: 16px; margin-bottom: 20px; font-weight: bold; }
        
        input { width: 90%; padding: 12px; margin: 15px 0; border: 2px solid #f8bbd0; border-radius: 10px; text-align: center; font-size: 18px; outline: none; transition: 0.3s; }
        input:focus { border-color: #f06292; box-shadow: 0 0 8px rgba(240, 98, 146, 0.2); }
        
        button { background-color: #f06292; color: white; border: none; padding: 15px 25px; border-radius: 10px; cursor: pointer; font-size: 18px; font-weight: bold; width: 90%; transition: 0.3s; margin-top: 10px; }
        button:hover { background-color: #d81b60; transform: scale(1.02); }

        #message, #page2, #page3 { display: none; margin-top: 20px; }
        
        #finalText { color: #ad1457; font-size: 19px; font-weight: bold; line-height: 1.8; white-space: pre-wrap; text-align: right; }
        
        .timer-container { display: flex; justify-content: space-around; margin-top: 20px; }
        .timer-box { background: #fff0f3; padding: 10px; border-radius: 10px; width: 65px; border: 1px solid #f8bbd0; }
        .timer-num { font-size: 18px; color: #ad1457; font-weight: bold; display: block; }
        .timer-label { font-size: 12px; color: #888; }

        .promise-card { background: #fff0f3; border: 1px solid #f8bbd0; padding: 12px; margin: 10px 0; border-radius: 10px; cursor: pointer; transition: 0.3s; font-weight: bold; color: #ad1457; font-size: 15px; }
        .promise-card.active { background: #f06292; color: white; }

        .heart-particle { position: fixed; pointer-events: none; z-index: 100; animation: floatUp 2s ease-out forwards; font-size: 20px; }
        @keyframes floatUp { 0% { transform: translateY(0) scale(1); opacity: 1; } 100% { transform: translateY(-100px) scale(1.5); opacity: 0; } }
        
        .animate-pop { animation: popIn 0.5s ease-out; }
        @keyframes popIn { from { opacity: 0; transform: scale(0.8); } to { opacity: 1; transform: scale(1); } }
    </style>
</head>
<body onclick="spawnHeart(event)">

<div class="card">
    <div id="login-section">
        <h1>كلام من قلب حمودك 😝💗</h1>
        <p class="hint">اكتبي الباسورد ي زعتوره 😑</p>
        <input type="text" id="passwordInput" placeholder="التاريخ السري.."> 
        <button onclick="checkPassword()">افتحي ي زفوته 😝💗💗💗</button>
    </div>

    <div id="message" class="animate-pop">
        <div id="finalText"></div>
        <button id="nextBtn1" style="display:none; margin-top:20px;" onclick="goToPage2()">شوفي اللي بعده ي زوزتي ➡️</button>
    </div>

    <div id="page2" class="animate-pop">
        <h1>إحنا مع بعض بقالنا.. 💖</h1>
        <div class="timer-container">
            <div class="timer-box"><span id="days" class="timer-num">0</span><span class="timer-label">يوم</span></div>
            <div class="timer-box"><span id="hours" class="timer-num">0</span><span class="timer-label">ساعة</span></div>
            <div class="timer-box"><span id="minutes" class="timer-num">0</span><span class="timer-label">دقيقة</span></div>
            <div class="timer-box"><span id="seconds" class="timer-num">0</span><span class="timer-label">ثانية</span></div>
        </div>
        <p style="color: #ad1457; font-weight: bold; margin-top: 20px;">
        من يوم ما وشنا جه في وش بعض والزلزال حصل وحياتي اتشقلبت وبقت أجمل يا أحلى زوزة في الدنيا 😝❤️
        </p>
        <button onclick="goToPage3()">آخر حاجة بقا 💍</button>
    </div>

    <div id="page3" class="animate-pop">
        <h1>وعودي ليكي ي زوزتي 💍</h1>
        <div class="promise-card" onclick="showP(this, 'أوعدك إني عمري ما هبعد عنك تاني ولا هسيبك مهما حصل ❤️')">وعد رقم 1</div>
        <div class="promise-card" onclick="showP(this, 'أوعدك إني عمري ما هخونك، وهتفضلي أنتي الوحيدة اللي في قلبي وعيني ❤️')">وعد رقم 2</div>
        <div class="promise-card" onclick="showP(this, 'أوعدك إننا هنفضل سوا لأخر العمر وتكوني مراتي وأم عيالي ❤️')">وعد رقم 3</div>
        <div id="displayP" style="margin-top:15px; color:#ad1457; font-weight:bold; font-size:17px; min-height:50px"></div>
        <button style="background-color:#888; font-size:14px;" onclick="location.reload()">ابدأ من جديد 🔄</button>
    </div>
</div>

<script>
    function spawnHeart(e) {
        const heart = document.createElement('div');
        heart.innerHTML = '❤️'; heart.className = 'heart-particle';
        heart.style.left = e.clientX + 'px'; heart.style.top = e.clientY + 'px';
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 2000);
    }

    function typeWriter(text, i) {
        if (i < text.length) {
            document.getElementById("finalText").innerHTML += text.charAt(i);
            setTimeout(() => typeWriter(text, i + 1), 50);
        } else {
            document.getElementById('nextBtn1').style.display = 'block';
        }
    }

    function checkPassword() {
        const pass = document.getElementById('passwordInput').value;
        const correctPass = "24/9/2010"; 
        
        // المسافات تم ضبطها هنا بدقة
        const secretMessage = "Happy Valentine's Day يا أحلى زوزه في الدنيا ❤️\n\nبحبك يا زوزتي يا روحي يا حياتي، وبعشقك وبموت فيكي وبدمنك.. كل سنة وأنتي معايا يا حبيبتي وربنا ما يحرمني منك أبدًا يا رب.\n\nوخليكي فاكرة إنك مهما كبرتي أو غلستي هتفضلي أنتي طفلتي وزوزتي الوحيدة اللي ماليش غيرها.. هفضل أحبك لحد ما نعجز سوا يا زعتورتي 😝💗";

        if (pass === correctPass) {
            document.getElementById('login-section').style.display = 'none';
            document.getElementById('message').style.display = 'block';
            typeWriter(secretMessage, 0);
        } else {
            alert("غلط يا حبيبتيييي 😝💗");
        }
    }

    function goToPage2() {
        document.getElementById('message').style.display = 'none';
        document.getElementById('page2').style.display = 'block';
        startTimer();
    }

    function goToPage3() {
        document.getElementById('page2').style.display = 'none';
        document.getElementById('page3').style.display = 'block';
    }

    function startTimer() {
        const startDate = new Date(2025, 4, 23); 
        setInterval(() => {
            const diff = new Date() - startDate;
            document.getElementById('days').innerText = Math.floor(diff / 86400000);
            document.getElementById('hours').innerText = Math.floor((diff / 3600000) % 24);
            document.getElementById('minutes').innerText = Math.floor((diff / 60000) % 60);
            document.getElementById('seconds').innerText = Math.floor((diff / 1000) % 60);
        }, 1000);
    }

    function showP(el, txt) {
        document.querySelectorAll('.promise-card').forEach(c => c.classList.remove('active'));
        el.classList.add('active');
        document.getElementById('displayP').innerText = txt;
    }
</script>

</body>
</html>
