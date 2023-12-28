- 👋 Hi, I’m @Pankazyt
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Pankazyt/Pankazyt is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<html>
<head>
  <style>
    * {
      box-sizing: border-box;
    }

    .calculator {
      width: 300px;
      margin: 50px auto;
      border: 1px solid black;
      padding: 10px;
    }

    .display {
      width: 100%;
      height: 50px;
      font-size: 24px;
      text-align: right;
      border: none;
      outline: none;
      padding: 10px;
    }

    .button {
      width: 25%;
      height: 50px;
      font-size: 18px;
      background-color: lightgray;
      border: none;
      outline: none;
      cursor: pointer;
    }

    .button:hover {
      background-color: gray;
    }

    .button:active {
      background-color: darkgray;
    }

    .operator {
      background-color: orange;
    }

    .operator:hover {
      background-color: darkorange;
    }

    .operator:active {
      background-color: orangered;
    }

    .clear {
      width: 50%;
    }

    .equal {
      width: 50%;
      background-color: green;
    }

    .equal:hover {
      background-color: limegreen;
    }

    .equal:active {
      background-color: darkgreen;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" class="display" value="0" disabled>
    <div>
      <button id="clear" class="button clear">C</button>
      <button id="divide" class="button operator">/</button>
      <button id="multiply" class="button operator">*</button>
      <button id="seven" class="button">7</button>
      <button id="eight" class="button">8</button>
      <button id="nine" class="button">9</button>
      <button id="subtract" class="button operator">-</button>
      <button id="four" class="button">4</button>
      <button id="five" class="button">5</button>
      <button id="six" class="button">6</button>
      <button id="add" class="button operator">+</button>
      <button id="one" class="button">1</button>
      <button id="two" class="button">2</button>
      <button id="three" class="button">3</button>
      <button id="equal" class="button equal">=</button>
      <button id="zero" class="button">0</button>
      <button id="decimal" class="button">.</button>
    </div>
  </div>
  <script>
    // Get the display element
    var display = document.getElementById("display");

    // Get all the buttons
    var buttons = document.getElementsByClassName("button");

    // Add click event listener to each button
    for (var i = 0; i < buttons.length; i++) {
      buttons[i].addEventListener("click", function() {
        // Get the button value
        var value = this.innerHTML;

        // If the button is clear, reset the display
        if (value == "C") {
          display.value = "0";
        }

        // If the button is equal, evaluate the expression
        else if (value == "=") {
          display.value = eval(display.value);
        }

        // If the button is an operator, append it to the display
        else if (value == "+" || value == "-" || value == "*" || value == "/") {
          display.value += value;
        }

        // If the button is a number or decimal, append it to the display
        else {
          // If the display is zero, replace it with the value
          if (display.value == "0") {
            display.value = value;
          }

          // Otherwise, append the value to the display
          else {
            display.value += value;
          }
        }
      });
    }
  </script>
</body>
</html>
