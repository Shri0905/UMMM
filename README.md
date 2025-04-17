<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Birthday Countdown</title>
  <style>
    body {
      background: #ffe3e3;
      font-family: 'Arial', sans-serif;
      text-align: center;
      padding-top: 50px;
    }
    h1 {
      font-size: 3em;
      color: #ff4b5c;
    }
    #countdown {
      font-size: 2em;
      color: #333;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>Countdown to Her Birthday 🎉</h1>
  <div id="countdown"></div>

  <script>
    const birthday = new Date("July 25, 2025 00:00:00").getTime();

    const updateCountdown = () => {
      const now = new Date().getTime();
      const distance = birthday - now;

      if (distance < 0) {
        document.getElementById("countdown").innerHTML = "Happy Birthday! 🎂🎈";
        return;
      }

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      document.getElementById("countdown").innerHTML =
        `${days}d ${hours}h ${minutes}m ${seconds}s`;
    };

    setInterval(updateCountdown, 1000);
    updateCountdown();
  </script>
</body>
</html>

