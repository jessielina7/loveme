
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Do You Love Me?</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Poppins', Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: linear-gradient(135deg, #ffdee2, #ffc0cb); /* Soft baby pink */
      color: #333;
    }

    .wrapper {
      position: relative;
      width: 90%;
      max-width: 500px;
      text-align: center;
      background: white;
      padding: 30px 20px;
      border-radius: 15px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
    }

    .question {
      font-size: 24px;
      font-weight: bold;
      margin-bottom: 20px;
      color: #333;
    }

    .gif {
      max-width: 100%;
      height: auto;
      margin-bottom: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }

    .btn-group {
      display: flex;
      justify-content: center;
      gap: 20px;
      position: relative;
    }

    button {
      padding: 12px 30px;
      font-size: 18px;
      font-weight: bold;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      transition: transform 0.3s ease, background-color 0.3s ease;
    }

    button:focus {
      outline: none;
    }

    .yes-btn {
      background-color: #4caf50;
      color: white;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }

    .yes-btn:hover {
      background-color: #45a049;
      transform: scale(1.05);
    }

    .no-btn {
      background-color: #ff4d4d;
      color: white;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
    }

    .no-btn:hover {
      background-color: #e43e3e;
      transform: scale(1.05);
    }
  </style>
</head>
<body>
<div class="wrapper">
  <h2 class="question">Do you love me?</h2>
  <img class="gif" alt="gif" src="https://media.giphy.com/media/6zI0KUEik37Jm/giphy.gif" />
  <div class="btn-group">
    <button class="yes-btn">Yes</button>
    <button class="no-btn">No</button>
  </div>
</div>

<script>
  const yesBtn = document.querySelector(".yes-btn");
  const noBtn = document.querySelector(".no-btn");
  const question = document.querySelector(".question");
  const gif = document.querySelector(".gif");

  let moveNoBtn = true;

  yesBtn.addEventListener("click", () => {
    question.innerHTML = "Love you toooo ❤️";
    gif.src = "https://media.giphy.com/media/Vcwi2ZdTTDtv2kS889/giphy.gif";
    yesBtn.style.display = "none";  // Hide Yes button
    noBtn.style.display = "none";   // Hide No button
    moveNoBtn = false;  // Stop moving the No button
  });

  noBtn.addEventListener("mouseover", () => {
    if (moveNoBtn) {
      let maxX = window.innerWidth - noBtn.offsetWidth - 20; // Prevent overflow
      let maxY = window.innerHeight - noBtn.offsetHeight - 20;

      let x = Math.random() * maxX;
      let y = Math.random() * maxY;
      
      noBtn.style.left = `${x}px`;
      noBtn.style.top = `${y}px`;
    }
  });
</script>
</body>
</html>
