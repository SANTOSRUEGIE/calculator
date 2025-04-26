<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #f4f4f4;
    }
    .calculator {
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
    }
    input, button {
      font-size: 18px;
      margin: 5px;
      padding: 10px;
    }
    #result {
      margin-top: 10px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="number" id="num1" placeholder="First number" />
    <input type="number" id="num2" placeholder="Second number" /><br/>
    <button onclick="calculate('+')">+</button>
    <button onclick="calculate('-')">-</button>
    <button onclick="calculate('*')">*</button>
    <button onclick="calculate('/')">/</button>
    <div id="result"></div>
  </div>

  <script>
    function calculate(op) {
      const num1 = parseFloat(document.getElementById('num1').value);
      const num2 = parseFloat(document.getElementById('num2').value);
      let result;

      if (isNaN(num1) || isNaN(num2)) {
        result = "Please enter valid numbers.";
      } else {
        switch (op) {
          case '+': result = num1 + num2; break;
          case '-': result = num1 - num2; break;
          case '*': result = num1 * num2; break;
          case '/': 
            result = num2 !== 0 ? num1 / num2 : "Cannot divide by zero.";
            break;
        }
      }

      document.getElementById('result').textContent = "Result: " + result;
    }
  </script>
</body>
</html>

