# codealpha_age_calculator
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Age Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
        }
        .container {
            max-width: 400px;
            margin: auto;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 10px;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
        }
        input, button {
            margin: 10px;
            padding: 10px;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Age Calculator</h2>
        <label for="dob">Enter your date of birth:</label>
        <input type="date" id="dob">
        <button onclick="calculateAge()">Calculate Age</button>
        <h3 id="result"></h3>
    </div>

    <script>
        function calculateAge() {
            let dob = document.getElementById('dob').value;
            if (!dob) {
                document.getElementById('result').innerText = "Please select a valid date.";
                return;
            }
            let dobDate = new Date(dob);
            let today = new Date();
            let age = today.getFullYear() - dobDate.getFullYear();
            let monthDiff = today.getMonth() - dobDate.getMonth();
            let dayDiff = today.getDate() - dobDate.getDate();
            
            if (monthDiff < 0 || (monthDiff === 0 && dayDiff < 0)) {
                age--;
            }
            
            document.getElementById('result').innerText = `You are ${age} years old.`;
        }
    </script>
</body>
</html>
