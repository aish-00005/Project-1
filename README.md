<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #f2f2f2;
    }
    .calculator {
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
      width: 250px;
      text-align: center;
    }
    input, select, button {
      margin: 10px 0;
      padding: 10px;
      width: 100%;
      font-size: 16px;
    }
    #result {
      font-weight: bold;
      margin-top: 15px;
    }
  </style>
</head>
<body>

<div class="calculator">
  <h2>Simple Calculator</h2>
  <input type="number" id="num1" placeholder="Enter first number">
  <input type="number" id="num2" placeholder="Enter second number">
  
  <select id="operation">
    <option value="add">Add (+)</option>
    <option value="subtract">Subtract (-)</option>
    <option value="multiply">Multiply (*)</option>
    <option value="divide">Divide (/)</option>
  </select>
  
  <button onclick="calculate()">Calculate</button>
  
  <div id="result"></div>
</div>

<script>
  function calculate() {
    const num1 = parseFloat(document.getElementById("num1").value);
    const num2 = parseFloat(document.getElementById("num2").value);
    const op = document.getElementById("operation").value;
    let result = "";

    if (isNaN(num1) || isNaN(num2)) {
      result = "Please enter valid numbers.";
    } else {
      switch (op) {
        case "add": result = num1 + num2; break;
        case "subtract": result = num1 - num2; break;
        case "multiply": result = num1 * num2; break;
        case "divide":
          result = num2 !== 0 ? num1 / num2 : "Cannot divide by zero";
          break;
      }
    }

    document.getElementById("result").innerText = "Result: " + result;
  }
</script>

</body>
</html>
