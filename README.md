<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CGPA Calculator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            text-align: center;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 450px;
            margin: 50px auto;
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        h2 {
            color: #333;
        }
        input {
            width: 90%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
        }
        button {
            width: 95%;
            padding: 12px;
            background: #007BFF;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 18px;
            cursor: pointer;
            transition: background 0.3s;
        }
        button:hover {
            background: #0056b3;
        }
        #result {
            margin-top: 15px;
            font-size: 20px;
            font-weight: bold;
            color: #333;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>CGPA Calculator</h2>
        <p>Enter your grades separated by commas to calculate your CGPA.</p>
        <input type="text" id="grades" placeholder="e.g. 3.5, 3.8, 4.0">
        <button onclick="calculateCGPA()">Calculate CGPA</button>
        <p id="result"></p>
    </div>

    <script>
        function calculateCGPA() {
            let gradesInput = document.getElementById('grades').value;
            let grades = gradesInput.split(',').map(num => parseFloat(num.trim()));
            
            if (grades.length === 0 || grades.some(isNaN)) {
                document.getElementById('result').innerText = "Please enter valid grades.";
                return;
            }
            
            let sum = grades.reduce((a, b) => a + b, 0);
            let cgpa = sum / grades.length;
            
            document.getElementById('result').innerText = `Your CGPA is: ${cgpa.toFixed(2)}`;
        }
    </script>
</body>
</html> 
