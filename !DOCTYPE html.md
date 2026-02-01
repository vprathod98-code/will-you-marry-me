<!DOCTYPE html>  
<html lang="en">  
<head>  
  <meta charset="UTF-8" />  
  <title>Will You Marry Me?</title>  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  
  <style>  
    * {  
      box-sizing: border-box;  
      font-family: "Poppins", system-ui, -apple-system, BlinkMacSystemFont, sans-serif;  
    }  
  
    body {  
      margin: 0;  
      height: 100vh;  
      background: linear-gradient(135deg, #fbd3e9, #bb377d);  
      display: flex;  
      align-items: center;  
      justify-content: center;  
    }  
  
    .card {  
      background: #fff;  
      width: 90%;  
      max-width: 420px;  
      padding: 40px 20px;  
      border-radius: 20px;  
      text-align: center;  
      box-shadow: 0 20px 40px rgba(0,0,0,0.15);  
      position: relative;  
    }  
  
    .emoji {  
      font-size: 70px;  
      margin-bottom: 10px;  
    }  
  
    h1 {  
      font-size: 24px;  
      margin-bottom: 30px;  
      color: #333;  
    }  
  
    .buttons {  
      display: flex;  
      justify-content: center;  
      gap: 20px;  
      position: relative;  
    }  
  
    button {  
      padding: 12px 26px;  
      font-size: 18px;  
      border-radius: 999px;  
      border: none;  
      cursor: pointer;  
      transition: transform 0.2s ease;  
    }  
  
    #yesBtn {  
      background: #ff4d6d;  
      color: white;  
      box-shadow: 0 10px 20px rgba(255,77,109,0.4);  
    }  
  
    #yesBtn:hover {  
      transform: scale(1.08);  
    }  
  
    #noBtn {  
      background: #e0e0e0;  
      color: #333;  
      position: absolute;  
      left: 0;  
    }  
  
    .message {  
      display: none;  
      margin-top: 20px;  
      font-size: 22px;  
      color: #ff4d6d;  
      font-weight: 600;  
    }  
  </style>  
</head>  
<body>  
  
  <div class="card" id="card">  
    <div class="emoji">💖</div>  
    <h1>Soundarya, will you marry me?</h1>  
  
    <div class="buttons">  
      <button id="noBtn">No</button>  
      <button id="yesBtn">Yes</button>  
    </div>  
  
    <div class="message" id="message">  
      🎉 Congratulations Soundarya! 💍<br>  
      You just made me the happiest person alive ❤️  
    </div>  
  </div>  
  
  <script>  
    const noBtn = document.getElementById("noBtn");  
    const yesBtn = document.getElementById("yesBtn");  
    const message = document.getElementById("message");  
    const card = document.getElementById("card");  
  
    function moveNoButton() {  
      const cardRect = card.getBoundingClientRect();  
      const btnRect = noBtn.getBoundingClientRect();  
  
      const maxX = cardRect.width - btnRect.width - 20;  
      const maxY = cardRect.height - btnRect.height - 20;  
  
      const x = Math.random() * maxX;  
      const y = Math.random() * maxY;  
  
      noBtn.style.left = `${x}px`;  
      noBtn.style.top = `${y}px`;  
    }  
  
    noBtn.addEventListener("mouseenter", moveNoButton);  
    noBtn.addEventListener("touchstart", moveNoButton);  
  
    yesBtn.addEventListener("click", () => {  
      document.querySelector(".buttons").style.display = "none";  
      message.style.display = "block";  
    });  
  </script>  
  
</body>  
</html>  
