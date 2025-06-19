<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bana Kızgın mısın?</title>
  <style>
    body {
      font-family: "Comic Sans MS", cursive, sans-serif;
      background-color: #ffe6e6;
      text-align: center;
      padding-top: 80px;
      margin: 0;
      overflow: hidden;
    }

    h1 {
      font-size: 1.8em;
      color: #cc3366;
      margin: 0 20px 20px;
    }

    #runawayBtn {
      padding: 12px 24px;
      font-size: 1em;
      background-color: #ff6699;
      color: white;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      position: absolute;
    }
  </style>
</head>
<body>
  <h1 id="mainText">bana kızgın mısın?</h1>
  <button id="runawayBtn">evet</button>

  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
  <script>
    const btn = document.getElementById('runawayBtn');
    const title = document.getElementById('mainText');
    let canClick = false;

    function moveButton() {
      if (!canClick) {
        const x = Math.random() * (window.innerWidth - btn.offsetWidth);
        const y = Math.random() * (window.innerHeight - btn.offsetHeight);
        btn.style.left = `${x}px`;
        btn.style.top = `${y}px`;
      }
    }

    btn.addEventListener('mouseover', moveButton);

    setTimeout(() => {
      title.textContent = "beni çokk mu seviyorsun?";
      btn.textContent = "evet asskım";
      canClick = true;
      btn.style.position = "static";
      btn.style.marginTop = "20px";
    }, 15000);

    btn.addEventListener('click', () => {
      if (canClick) {
        confetti({
          particleCount: 150,
          spread: 70,
          origin: { y: 0.6 }
        });
      }
    });

    window.addEventListener('resize', moveButton);
    moveButton(); // ilk konumlandırma
  </script>
</body>
</html>
