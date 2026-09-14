<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>For You ☆</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      min-height: 100vh;
      background: #a03838;
      font-family: Georgia, serif;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
    }

    .page {
      display: none;
      width: 100%;
      max-width: 500px;
      min-height: 100vh;
      padding: 40px 25px;
      text-align: center;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      animation: fade 0.6s ease;
    }

    .page.active {
      display: flex;
    }

    h1 {
      color: #e36262;
      font-size: 38px;
      margin-bottom: 20px;
    }

    h2 {
      color: #e14b4b;
      margin-bottom: 15px;
    }

    p {
      color: #6c2c2c;
      font-size: 18px;
      line-height: 1.7;
    }

    button {
      border: none;
      border-radius: 25px;
      padding: 13px 28px;
      margin-top: 25px;
      font-size: 16px;
      cursor: pointer;
      background: #e45555;
      color: white;
      transition: 0.2s;
    }

    button:hover {
      transform: scale(1.05);
      background: #d96c6c;
    }

   .heart {
  font-size: 75px;
  color: gold;
  animation: heartbeat 1.3s infinite;
  margin-bottom: 20px;
}
    .photo {
      width: 230px;
      height: 280px;
      object-fit: cover;
      border-radius: 15px;
      box-shadow: 0 8px 25px rgba(0,0,0,.15);
      margin: 10px;
    }

    .photos {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
    }

    .letter {
      background: white;
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 5px 20px rgba(0,0,0,.1);
      text-align: left;
      max-height: 60vh;
      overflow-y: auto;
    }

    .buttons {
      display: flex;
      gap: 15px;
      justify-content: center;
    }

    #noBtn {
      background: #aaa;
    }

  .floating-heart {
  position: fixed;
  bottom: -50px;
  left: 50%;
  font-size: 25px;
  color: gold;
  pointer-events: none;
  z-index: 9999;
  animation: floatUp 5s linear forwards;
}

@keyframes floatUp {
  0% {
    transform: translateY(0) rotate(0deg);
    opacity: 1;
  }

  100% {
    transform: translateY(-110vh) rotate(360deg);
    opacity: 0;
  }
}
  </style>
</head>

<body>

  <!-- PAGE 1 -->
  <section class="page active" id="page1">
    <div class="star">☆</div>

    <h1>Waddup!</h1>

    <p>
      I made a little somethingsomething<br>
      happi beryrtdayay
    </p>

    <button onclick="nextPage()">Next →</button>
  </section>


  <!-- PAGE 2 -->
  <section class="page" id="page2">

    <h1>Happy Birthday! ♡</h1>

    <p>
      Today is your special day,<br>
      so I wanted to make something<br>
      a little different for you since different ka talaga.
    </p>

    <button onclick="nextPage()">Next →</button>
  </section>


  <!-- PAGE 3 -->
  <section class="page" id="page3">

    <h2>Pictures📸 (YUNG MGA PHOTOS KO SAYO PALAGING MAY KASAMA OK) </h2>

    <div class="photos">
      <!-- CHANGE THESE TO YOUR PHOTOS -->
      <img src="525C710C-9FB5-46B9-B724-305CD209C1A2.jpg" class="photo">
      <img src="IMG_8984.jpeg" class="photo">
    </div>

    <button onclick="nextPage()">Next →</button>
  </section>


  <!-- PAGE 4 -->
  <section class="page" id="page4">

    <h1>For you</h1>

    <div class="letter">
      <p>
        Dear liway,<br><br>

        I just wanted to say how grateful I am
        to have you in my life. You deserve all
        the happiness in the world, and I hope
        this year brings you lots of good memories,
        laughter, and moments you'll never forget. 
        (seryoso yarn??) joke sorry but fr,
        you've been so wonderful and a supportive friend to me
        and I can't thank you enough for that. Side note : gaga tama na 
        sa mga bobong lalaki na yan umayos ka.
        <br><br>

        Thank you for being you. ☆
        <br><br>

        Happy birthday!
      </p>
    </div>

    <button onclick="nextPage()">Next →</button>
  </section>


  <!-- PAGE 5 -->
  <section class="page" id="page5">

    <div class="heart">☆</div>

    <h1>One last thing...</h1>

    <p>
      Open mo to..♡ pramis wala tong virus. ata
    </p>

    <div class="buttons">
      <button onclick="yes()">Open it ☆</button>
      <button id="noBtn" onclick="moveNo()">No ty</button>
    </div>
  </section>


  <!-- PAGE 6 -->
  <section class="page" id="page6">

    <div class="star">☆</div>

    <h1>YAY!</h1>

    <p>
      I hope you liked it. ☆<br><br>
      Happy birthday once again!
      oo pinapress ko lang sayo para sa wala or may virus na talaga...
    </p>

    <button onclick="restart()">Start again</button>
  </section>


  <script>
    let currentPage = 1;

    function nextPage() {
  document.getElementById("page" + currentPage)
    .classList.remove("active");

  currentPage++;

  document.getElementById("page" + currentPage)
    .classList.add("active");

  createHearts();
}
    function yes() {
      document.getElementById("page5")
        .classList.remove("active");

      document.getElementById("page6")
        .classList.add("active");

      currentPage = 6;

      createHearts();
    }

    function restart() {
      document.getElementById("page6")
        .classList.remove("active");

      document.getElementById("page1")
        .classList.add("active");

      currentPage = 1;
    }

    function moveNo() {
      const btn = document.getElementById("noBtn");

      const x = Math.random() * 200 - 100;
      const y = Math.random() * 150 - 75;

      btn.style.transform =
        `translate(${x}px, ${y}px)`;
    }

    function createHearts() {
  for (let i = 0; i < 15; i++) {
    const star = document.createElement("div");

    star.className = "floating-heart";
    star.innerHTML = "★";

    star.style.left = Math.random() * 100 + "vw";
    star.style.fontSize = (15 + Math.random() * 25) + "px";
    star.style.animationDuration = (3 + Math.random() * 4) + "s";

    document.body.appendChild(star);

    setTimeout(() => {
      star.remove();
    }, 7000);
  }
}
  </script>

</body>
</html>
