<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    input[type="text"] {
      width: 100%;
      padding: 10px;
      font-size: 24px;
      text-align: right;
      margin-bottom: 10px;
    }
    .buttons button {
      width: 60px;
      height: 60px;
      margin: 5px;
      font-size: 20px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    .buttons button:hover {
      background: #e0e0e0;
    }
    .equal {
      background-color: #4CAF50;
      color: white;
    }
  </style>
</head>
<body>

<div class="calculator">
  <input type="text" id="display" readonly>
  <div class="buttons">
    <button onclick="clearDisplay()">C</button>
    <button onclick="appendValue('/')">/</button>
    <button onclick="appendValue('')"></button>
    <button onclick="appendValue('-')">-</button><br>
    <button onclick="appendValue('7')">7</button>
    <button onclick="appendValue('8')">8</button>
    <button onclick="appendValue('9')">9</button>
    <button onclick="appendValue('+')">+</button><br>
    <button onclick="appendValue('4')">4</button>
    <button onclick="appendValue('5')">5</button>
    <button onclick="appendValue('6')">6</button>
    <button onclick="calculateResult()" class="equal">=</button><br>
    <button onclick="appendValue('1')">1</button>
    <button onclick="appendValue('2')">2</button>
    <button onclick="appendValue('3')">3</button>
    <button onclick="appendValue('0')">0</button>
    <button onclick="appendValue('.')">.</button>
  </div>
</div>

<script>
  function appendValue(value) {
    document.getElementById('display').value += value;
  }

  function clearDisplay() {
    document.getElementById('display').value = '';
  }

  function calculateResult() {
    try {
      document.getElementById('display').value = eval(document.getElementById('display').value);
    } catch {
      document.getElementById('display').value = 'Error';
    }
  }
</script>

</body>
</html>
