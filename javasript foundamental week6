
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SpendWise - Budget Manager</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background: #f1f5f9;
            padding: 30px 15px;
        }

        .container {
            max-width: 600px;
            margin: 30px auto;
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        h1 {
            text-align: center;
            color: #16a34a;
            margin-bottom: 10px;
        }

        .subtitle {
            text-align: center;
            color: #64748b;
            margin-bottom: 25px;
        }

        label {
            display: block;
            margin: 15px 0 8px;
            font-weight: bold;
        }

        input {
            width: 100%;
            padding: 13px;
            border: 1px solid #cbd5e1;
            border-radius: 8px;
            font-size: 16px;
        }

        button {
            width: 100%;
            padding: 14px;
            background: #16a34a;
            color: white;
            border: none;
            border-radius: 8px;
            margin-top: 20px;
            font-size: 16px;
            cursor: pointer;
        }

        button:hover {
            background: #15803d;
        }

        .results {
            margin-top: 25px;
            padding: 20px;
            background: #f0fdf4;
            border-radius: 10px;
            display: none;
        }

        .results h2 {
            color: #166534;
            margin-bottom: 15px;
        }

        .results p {
            margin: 12px 0;
            font-size: 16px;
        }

        .balance {
            font-size: 22px;
            font-weight: bold;
            color: #16a34a;
        }

        .warning {
            color: #dc2626;
            font-weight: bold;
        }

        footer {
            text-align: center;
            margin-top: 25px;
            color: #64748b;
            font-size: 13px;
        }
    </style>
</head>

<body>

    <div class="container">

        <h1>SpendWise</h1>

        <p class="subtitle">
            Manage your budget and track your spending.
        </p>

        <!-- User Input -->
        <label for="budget">Enter Your Total Budget (Ksh)</label>
        <input type="number" id="budget"
               placeholder="e.g. 50000" min="0" step="any">

        <label for="expenses">Enter Your Total Expenses (Ksh)</label>
        <input type="number" id="expenses"
               placeholder="e.g. 15000" min="0" step="any">

        <button onclick="displayResults()">
            Calculate Balance
        </button>

        <!-- Results -->
        <div class="results" id="results">

            <h2>Budget Summary</h2>

            <p>Total Budget:
                <strong id="totalBudget"></strong>
            </p>

            <p>Total Expenses:
                <strong id="totalExpenses"></strong>
            </p>

            <p>Remaining Balance:</p>

            <p class="balance" id="remainingBalance"></p>

            <p id="message"></p>

        </div>

        <footer>
            © 2026 SpendWise. Budget smarter, spend wiser.
        </footer>

    </div>

    <script>

        // 1. Store application data
        let budget;
        let expenses;

        // 2. Function to calculate remaining balance
        function calculateBalance(budget, expenses) {
            return budget - expenses;
        }

        // 3. Function to display results
        function displayResults() {

            // Collect user input
            let budgetInput = document.getElementById("budget").value;
            let expensesInput = document.getElementById("expenses").value;

            // Check for valid input
            if (budgetInput.trim() === "" ||
                expensesInput.trim() === "") {

                alert("Please enter both your budget and expenses.");
                return;
            }

            // Convert input into numbers
            budget = Number(budgetInput);
            expenses = Number(expensesInput);

            if (!Number.isFinite(budget) ||
                !Number.isFinite(expenses) ||
                budget < 0 || expenses < 0) {

                alert("Please enter valid, non-negative amounts.");
                return;
            }

            // Perform budget calculation
            let balance = calculateBalance(budget, expenses);

            // Display results on the webpage
            document.getElementById("totalBudget").textContent =
                "Ksh " + budget.toLocaleString();

            document.getElementById("totalExpenses").textContent =
                "Ksh " + expenses.toLocaleString();

            document.getElementById("remainingBalance").textContent =
                "Ksh " + balance.toLocaleString();

            // Display budget status
            let message = document.getElementById("message");

            if (balance < 0) {
                message.textContent =
                    "Warning! You have exceeded your budget.";

                message.className = "warning";
            } else {
                message.textContent =
                    "Great! You are within your budget.";

                message.className = "";
            }

            // Show results section
            document.getElementById("results").style.display = "block";

            // Display results in browser console
            console.log("===== SPENDWISE BUDGET SUMMARY =====");
            console.log("Total Budget: Ksh " + budget);
            console.log("Total Expenses: Ksh " + expenses);
            console.log("Remaining Balance: Ksh " + balance);
            console.log("===================================");
        }

    </script>

</body>
</html>
