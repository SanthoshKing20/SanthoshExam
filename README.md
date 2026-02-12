# SanthoshExam
<!DOCTYPE html>
<html>
<head>
    <title>Employee Compensation Management</title>

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

        .displayResult {
            margin-top: 20px;
            font-weight: bold;
            color: green;
        }
    </style>
</head>

<body>

    <div class="container">
        <h2>Employee Compensation Management</h2>

        <input type="text" id="workerName" placeholder="Employee Full Name">
        <input type="number" id="baseSalary" placeholder="Monthly Earnings">

        <button id="salaryBtn">Generate Payroll</button>

        <div class="displayResult" id="salaryOutput"></div>
    </div>

    <script>
        document.getElementById("salaryBtn").addEventListener("click", generatePayrollDetails);

        function generatePayrollDetails() {

            let workerName = document.getElementById("workerName").value.trim();
            let baseSalary = parseFloat(document.getElementById("baseSalary").value);

            if (workerName === "" || isNaN(baseSalary)) {
                alert("Please enter valid employee details!");
                return;
            }

            if (baseSalary < 0) {
                alert("Earnings cannot be negative!");
                return;
            }

            let totalAnnualEarnings = baseSalary * 12;
            let deductionAmount = totalAnnualEarnings * 0.10;  
            let netAnnualIncome = totalAnnualEarnings - deductionAmount;

            document.getElementById("salaryOutput").innerHTML =
                "Employee Name: " + workerName + "<br>" +
                "Total Annual Earnings: ₹" + totalAnnualEarnings.toFixed(2) + "<br>" +
                "Tax Deduction (10%): ₹" + deductionAmount.toFixed(2) + "<br>" +
                "Net Annual Income: ₹" + netAnnualIncome.toFixed(2);
        }
    </script>

</body>
</html>

