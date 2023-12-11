<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lessons in ITWS-01</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f2f2f2;
        }

        #container {
            width: 80%;
            margin: 20px auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align:  center;
            margin: 0 auto;
        }

        h1, h2, h3 {
            text-align: center;
            color: #333;
        }

        p {
            color: #666;
        }

        select, input, button {
            margin: 10px 0;
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        button {
            cursor: pointer;
            background-color: #4caf50;
            color: #fff;
        }

        button:hover {
            background-color: #45a049;
        }
    </style>
</head>

<body>
    <div id="container">
        <h1>Lessons in ITWS-01</h1>
        <button onclick="permutation()">Permutation</button>
        <button onclick="fibonacciSeries()">Fibonacci Series</button>
        <button onclick="lucasSeries()">Lucas Series</button>
        <button onclick="tribonacciSeries()">Tribonacci Series</button>
        <div id="output"></div>
    </div>

    <script>
        function clearScreen() {
            document.getElementById('output').innerHTML = '';
        }

        function displayOutput(outputText) {
            document.getElementById('output').innerHTML = outputText;
        }

        function permutation() {
            let n = prompt("Enter the value of n:");
            let r = prompt("Enter the value of r:");

            // Implement permutation logic here
            if (n < r || n < 0 || r < 0) {
                displayOutput("Invalid input. Please ensure n >= r >= 0.");
            } else {
                let result = nPr(n, r);
                displayOutput(`Permutation P(${n}, ${r}) = ${result}`);
            }
        }

        function nPr(n, r) {
            // Implement permutation calculation
            let result = 1;
            for (let i = 0; i < r; i++) {
                result *= (n - i);
            }
            return result;
        }

        function fibonacciSeries() {
            let n = prompt("Enter the number of terms in the series:");

            // Implement fibonacci series logic here
            if (n < 1) {
                displayOutput("Invalid input. Please enter a positive integer.");
            } else {
                let series = [];
                for (let i = 0; i < n; i++) {
                    series.push(fibonacci(i));
                }
                displayOutput(`Fibonacci Series: ${series.join(" ")}`);
            }
        }

        function fibonacci(n) {
            // Implement fibonacci calculation
            if (n <= 1) {
                return n;
            } else {
                return fibonacci(n - 1) + fibonacci(n - 2);
            }
        }

        function lucasSeries() {
            let n = prompt("Enter the number of terms in the series:");

            // Implement lucas series logic here
            if (n < 1) {
                displayOutput("Invalid input. Please enter a positive integer.");
            } else {
                let series = [];
                for (let i = 0; i < n; i++) {
                    series.push(lucas(i));
                }
                displayOutput(`Lucas Series: ${series.join(" ")}`);
            }
        }

        function lucas(n) {
            // Implement lucas calculation
            if (n == 0) {
                return 2;
            } else if (n == 1) {
                return 1;
            } else {
                return lucas(n - 1) + lucas(n - 2);
            }
        }

        function tribonacciSeries() {
            let n = prompt("Enter the number of terms in the series:");

            // Implement tribonacci series logic here
            if (n < 1) {
                displayOutput("Invalid input. Please enter a positive integer.");
            } else {
                let series = [];
                for (let i = 0; i < n; i++) {
                    series.push(tribonacci(i));
                }
                displayOutput(`Tribonacci Series: ${series.join(" ")}`);
            }
        }

        function tribonacci(n) {
            // Implement tribonacci calculation
            if (n == 0) {
                return 0;
            } else if (n == 1 || n == 2) {
                return 1;
            } else {
                return tribonacci(n - 1) + tribonacci(n - 2) + tribonacci(n - 3);
            }
        }
    </script>
</body>
</html>
