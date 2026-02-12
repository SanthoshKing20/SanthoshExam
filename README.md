# SanthoshExam
<!DOCTYPE html>
<html>
<head>
    <title>Employee Payroll System</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(to right, #4facfe, #00f2fe);
            margin: 0;
            padding: 0;
        }

        .container {
            width: 400px;
            margin: 100px auto;
            padding: 25px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0,0,0,0.3);
            text-align: center;
        }

        h2 {
            margin-bottom: 20px;
        }

        input {
            width: 90%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #ccc;
        }

        button {
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #0056b3;
        }

        .result {
            margin-top: 20px;
            font-weight: bold;
            color: green;
        }
    </style>
</head>

<body>

    <div class="container">
        <h2>Employee Payroll System</h2>

        <input type="text" id="name" placeholder="Enter Employee Name">
        <input type="number" id="salary" placeholder="Enter Monthly Salary">

        <button id="calcBtn">Calculate Payroll</button>

        <div class="result" id="result"></div>
    </div>

    <script>
        document.getElementById("calcBtn").addEventListener("click", calculatePayroll);

        function calculatePayroll() {

            let name = document.getElementById("name").value.trim();
            let salary = parseFloat(document.getElementById("salary").value);

            if (name === "" || isNaN(salary)) {
                alert("Please fill all details correctly!");
                return;
            }

            if (salary < 0) {
                alert("Salary cannot be negative!");
                return;
            }

            let annualSalary = salary * 12;
            let tax = annualSalary * 0.10;   // 10% tax
            let netSalary = annualSalary - tax;

            document.getElementById("result").innerHTML =
                "Employee Name: " + name + "<br>" +
                "Annual Salary: ₹" + annualSalary.toFixed(2) + "<br>" +
                "Tax (10%): ₹" + tax.toFixed(2) + "<br>" +
                "Net Salary: ₹" + netSalary.toFixed(2);
        }
    </script>

</body>
</html>
