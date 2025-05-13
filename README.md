# HTML Calculator Code

Here's a complete HTML code for a functional calculator with basic operations (addition, subtraction, multiplication, division) and a clean interface:

html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f5f5f5;
        }
        
        .calculator {
            border: 1px solid #ccc;
            border-radius: 10px;
            width: 300px;
            background-color: #fff;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }
        
        .display {
            width: 100%;
            height: 80px;
            border: none;
            background-color: #252525;
            color: white;
            text-align: right;
            padding-right: 20px;
            padding-left: 10px;
            font-size: 2rem;
            border-top-left-radius: 10px;
            border-top-right-radius: 10px;
            box-sizing: border-box;
        }
        
        .keys {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap: 10px;
            padding: 20px;
        }
        
        button {
            height: 60px;
            border-radius: 5px;
            border: none;
            background-color: #f0f0f0;
            font-size: 1.5rem;
            color: #333;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        
        button:hover {
            background-color: #ddd;
        }
        
        .operator {
            background-color: #f39c12;
            color: white;
        }
        
        .operator:hover {
            background-color: #e67e22;
        }
        
        .equal {
            background-color: #2ecc71;
            color: white;
            grid-column: span 2;
        }
        
        .equal:hover {
            background-color: #27ae60;
        }
        
        .clear {
            background-color: #e74c3c;
            color: white;
        }
        
        .clear:hover {
            background-color: #c0392b;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" class="display" id="display" disabled>
        <div class="keys">
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('/')" class="operator">/</button>
            
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('*')" class="operator">×</button>
            
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="appendToDisplay('-')" class="operator">-</button>
            
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="appendToDisplay('.')">.</button>
            <button onclick="clearDisplay()" class="clear">C</button>
            <button onclick="appendToDisplay('+')" class="operator">+</button>
            
            <button onclick="calculate()" class="equal">=</button>
        </div>
    </div>

    <script>
        let currentDisplay = '';
        
        function appendToDisplay(value) {
            currentDisplay += value;
            document.getElementById('display').value = currentDisplay;
        }
        
        function clearDisplay() {
            currentDisplay = '';
            document.getElementById('display').value = '';
        }
        
        function calculate() {
            try {
                // Replace × with * for calculation
                let expression = currentDisplay.replace(/×/g, '*');
                const result = eval(expression);
                document.getElementById('display').value = result;
                currentDisplay = result.toString();
            } catch (error) {
                document.getElementById('display').value = 'Error';
                currentDisplay = '';
            }
        }
    </script>
</body>
</html>

