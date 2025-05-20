# moetikkrabben.nl
moetikkrabben.nl
<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Moet ik krabben?</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="container">
    <h1>Moet ik krabben?</h1>
    <input type="text" id="locationInput" placeholder="Vul je woonplaats of postcode in" />
    <button onclick="checkWeather()">Check</button>
    <div id="result"></div>
  </div>
  <script src="script.js"></script>
</body>
</html>
body {
  margin: 0;
  font-family: 'Arial', sans-serif;
  background: linear-gradient(to bottom, #cceeff, #ffffff);
  color: #003366;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.container {
  text-align: center;
  padding: 20px;
  background: white;
  border-radius: 15px;
  box-shadow: 0 0 20px rgba(0,0,0,0.1);
}
input {
  padding: 10px;
  width: 80%;
  margin-top: 10px;
  border-radius: 5px;
  border: 1px solid #003366;
}
button {
  margin-top: 10px;
  padding: 10px 20px;
  background-color: #00aaff;
  border: none;
  color: white;
  border-radius: 5px;
  cursor: pointer;
}
#result {
  margin-top: 20px;
  font-size: 24px;
  font-weight: bold;
}
function checkWeather() {
  const location = document.getElementById("locationInput").value;
  const result = document.getElementById("result");

  const today = new Date();
  const month = today.getMonth(); // 0 = januari
  const hour = today.getHours();

  if ([10, 11, 0, 1, 2].includes(month) && hour < 9) {
    result.innerText = "JA, je moet krabben! ❄️";
  } else {
    result.innerText = "NEE, geen zorgen. 🚗";
  }
}
