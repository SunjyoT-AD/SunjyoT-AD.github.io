<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ESP32 LED Control</title>
  <style>
    body { text-align: center; font-family: Arial, sans-serif; }
    .button { padding: 15px 30px; font-size: 16px; margin: 10px; cursor: pointer; }
    .on { background-color: #4CAF50; color: white; }
    .off { background-color: #f44336; color: white; }
  </style>
</head>
<body>
  <h1>Control LEDs on ESP32</h1>
  <button class="button on" onclick="turnOn(1)">Turn LED 1 ON</button>
  <button class="button off" onclick="turnOff(1)">Turn LED 1 OFF</button><br>

  <button class="button on" onclick="turnOn(2)">Turn LED 2 ON</button>
  <button class="button off" onclick="turnOff(2)">Turn LED 2 OFF</button><br>

  <button class="button on" onclick="turnOn(3)">Turn LED 3 ON</button>
  <button class="button off" onclick="turnOff(3)">Turn LED 3 OFF</button><br>

  <button class="button on" onclick="turnOn(4)">Turn LED 4 ON</button>
  <button class="button off" onclick="turnOff(4)">Turn LED 4 OFF</button><br>

  <script>
    const ESP32_IP = "http://192.168.108.152"; // Replace with your ESP32 IP address

    function turnOn(led) {
      fetch(`${ESP32_IP}/turnon?led=${led}`)
        .then(response => response.text())
        .then(data => alert(data))
        .catch(error => alert("Error: " + error));
    }

    function turnOff(led) {
      fetch(`${ESP32_IP}/turnoff?led=${led}`)
        .then(response => response.text())
        .then(data => alert(data))
        .catch(error => alert("Error: " + error));
    }
  </script>
</body>
</html>
