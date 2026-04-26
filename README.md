<!DOCTYPE html>
<html>
<head>
  <title>Mobile Calculator</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      margin: 0;
      font-family: Arial;
      background: #0f0f0f;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .calculator {
      width: 320px;
      background: #1c1c1c;
      border-radius: 20px;
      padding: 15px;
      box-shadow: 0 0 20px rgba(0,0,0,0.6);
    }

    .display {
      background: #000;
      color: #0f0;
      font-size: 28px;
      padding: 20px;
      text-align: right;
      border-radius: 12px;
      min-height: 50px;
      overflow-x: auto;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
      margin-top: 15px;
    }

    button {
      padding: 18px;
      font-size: 18px;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      background: #333;
      color: white;
      transition: 0.2s;
    }

    button:hover {
      background: #555;
    }

    .operator {
      background: #ff9500;
    }

    .equal {
      background: #28a745;
      grid-column: span 2;
    }

    .clear {
      background: #dc3545;
    }

  </style>
</head>

<body>

<div class="calculator">
  <div class="display" id="display">0</div>

  <div class="buttons">
    <button onclick="clearDisplay()" class="clear">C</button>
    <button onclick="append('/')">/</button>
    <button onclick="append('*')">*</button>
    <button onclick="backspace()">⌫</button>

    <button onclick="append('7')">7</button>
    <button onclick="append('8')">8</button>
    <button onclick="append('9')">9</button>
    <button onclick="append('-')" class="operator">-</button>

    <button onclick="append('4')">4</button>
    <button onclick="append('5')">5</button>
    <button onclick="append('6')">6</button>
    <button onclick="append('+')" class="operator">+</button>

    <button onclick="append('1')">1</button>
    <button onclick="append('2')">2</button>
    <button onclick="append('3')">3</button>
    <button onclick="calculate()" class="equal">=</button>

    <button onclick="append('0')" style="grid-column: span 4;">0</button>
  </div>
</div>

<script>
  let display = document.getElementById("display");

  function append(value) {
    if (display.innerText === "0") {
      display.innerText = value;
    } else {
      display.innerText += value;
    }
  }

  function clearDisplay() {
    display.innerText = "0";
  }

  function backspace() {
    display.innerText = display.innerText.slice(0, -1);
    if (display.innerText === "") {
      display.innerText = "0";
    }
  }

  function calculate() {
    try {
      display.innerText = eval(display.innerText);
    } catch {
      display.innerText = "Error";
    }
  }
</script>

</body>
</html># calculator-project
A simple and responsive mobile calculator app using HTML, CSS, and JavaScript. Supports basic operations with a clean modern design.
