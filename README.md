# LIBRARY-MANGEMENT-

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SJC Library Portal - Book Entry Form</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #f5f0ed;
            color: #35212a;
        }

        header {
            background: #6b1730;
            color: white;
            padding: 22px;
            text-align: center;
            border-bottom: 5px solid #d5a44d;
        }

        header h1 {
            margin: 0 0 8px;
        }

        header p {
            margin: 0;
            color: #f4d58a;
        }

        .container {
            max-width: 1000px;
            margin: 30px auto;
            padding: 25px;
            background: white;
            border-radius: 14px;
            box-shadow: 0 8px 25px #32151d15;
        }

        h2 {
            color: #6b1730;
            border-bottom: 2px solid #d5a44d;
            padding-bottom: 10px;
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(2, minmax(0, 1fr));
            gap: 18px;
        }

        .field label {
            display: block;
            margin-bottom: 7px;
            font-weight: bold;
            font-size: 14px;
        }

        .field input,
        .field select,
        .field textarea {
            width: 100%;
            padding: 11px;
            border: 1px solid #d8cbd0;
            border-radius: 7px;
            font-size: 14px;
            background: white;
        }

        .field textarea {
            resize: vertical;
            min-height: 42px;
        }

        .full-width {
            grid-column: 1 / -1;
        }

        .buttons {
            display: flex;
            gap: 12px;
            margin-top: 22px;
            flex-wrap: wrap;
        }

        button {
            padding: 12px 20px;
            border: none;
            border-radius: 7px;
            cursor: pointer;
            font-weight: bold;
        }

        .save-btn {
            background: #6b1730;
            color: white;
        }

        .reset-btn {
            background: #eee5e8;
            color: #6b1730;
        }

        .table-wrapper {
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 15px;
            font-size: 13px;
        }

        th, td {
            padding: 11px;
            border: 1px solid #e1d7db;
            text-align: left;
        }

        th {
            background: #6b1730;
            color: white;
        }

        tr:nth-child(even) {
            background: #faf6f7;
        }

        #statusMessage {
            color: #167344;
            font-weight: bold;
        }

        @media (max-width: 650px) {
            .form-grid {
                grid-template-columns: 1fr;
            }

            .full-width {
                grid-column: auto;
            }

            .container {
                margin: 15px;
                padding: 18px;
            }
        }
    </style>
</head>

<body>

<header>
    <h1>SJC Library Portal</h1>
    <p>Student Book Entry and Tracking Form</p>
</header>

<main class="container">

    <h2>Student Details</h2>

    <form id="bookForm">

        <div class="form-grid">

            <div class="field">
                <label for="dno">D.NO</label>
                <input
                    type="text"
                    id="dno"
                    placeholder="Enter student D.NO"
                    pattern="25UCS(50[1-9]|5[1-5][0-9]|56[0-5])"
                    title="Enter D.NO from 25UCS501 to 25UCS565"
                    required
                >
            </div>

            <div class="field">
                <label for="studentName">Student Name</label>
                <input type="text" id="studentName" required>
            </div>

            <div class="field">
                <label for="department">Department</label>
                <select id="department" required>
                    <option value="B.Sc. Computer Science">
                        B.Sc. Computer Science
                    </option>
                    <option value="BCA">BCA</option>
                    <option value="B.Sc. Mathematics">
                        B.Sc. Mathematics
                    </option>
                    <option value="B.Com">B.Com</option>
                    <option value="Other">Other</option>
                </select>
            </div>

            <div class="field">
                <label for="year">Year</label>
                <select id="year" required>
                    <option value="I Year">I Year</option>
                    <option value="II Year" selected>II Year</option>
                    <option value="III Year">III Year</option>
                </select>
            </div>

            <div class="field">
                <label for="phone">Phone Number</label>
                <input
                    type="tel"
                    id="phone"
                    pattern="[0-9]{10}"
                    title="Enter a 10-digit phone number"
                >
            </div>

            <div class="field">
                <label for="email">Email Address</label>
                <input type="email" id="email">
            </div>

        </div>

        <h2>Book Details</h2>

        <div class="form-grid">

            <div class="field">
                <label for="bookId">Book ID / Accession Number</label>
                <input type="text" id="bookId" required>
            </div>

            <div class="field">
                <label for="bookTitle">Book Title</label>
                <input type="text" id="bookTitle" required>
            </div>

            <div class="field">
                <label for="author">Author Name</label>
                <input type="text" id="author" required>
            </div>

            <div class="field">
                <label for="issueDate">Date of Issue</label>
                <input type="date" id="issueDate" required>
            </div>

            <div class="field">
                <label for="dueDate">Expected Return Date</label>
                <input type="date" id="dueDate" required>
            </div>

            <div class="field">
                <label for="actualReturn">Actual Return Date</label>
                <input type="date" id="actualReturn">
            </div>

            <div class="field">
                <label for="bookStatus">Book Status</label>
                <select id="bookStatus" required>
                    <option value="Issued">Issued</option>
                    <option value="Returned">Returned</option>
                    <option value="Overdue">Overdue</option>
                </select>
            </div>

            <div class="field">
                <label for="fine">Fine Amount (₹)</label>
                <input
                    type="number"
                    id="fine"
                    min="0"
                    step="0.01"
                    value="0"
                    required
                >
            </div>

            <div class="field full-width">
                <label for="remarks">Remarks</label>
                <textarea id="remarks"></textarea>
            </div>

        </div>

        <div class="buttons">
            <button class="save-btn" type="submit">
                Save Book Record
            </button>

            <button class="reset-btn" type="reset">
                Clear Form
            </button>
        </div>

        <p id="statusMessage" role="status" aria-live="polite"></p>

    </form>

    <h2>Book Records</h2>

    <div class="table-wrapper">
        <table>
            <thead>
                <tr>
                    <th>D.NO</th>
                    <th>Student Name</th>
                    <th>Book ID</th>
                    <th>Book Title</th>
                    <th>Issue Date</th>
                    <th>Due Date</th>
                    <th>Status</th>
                    <th>Fine (₹)</th>
                </tr>
            </thead>

            <tbody id="recordsTable">
                <tr id="emptyRow">
                    <td colspan="8" style="text-align:center">
                        No book records added yet.
                    </td>
                </tr>
            </tbody>
        </table>
    </div>

</main>

<script>
    const form = document.getElementById("bookForm");
    const recordsTable = document.getElementById("recordsTable");
    const statusMessage = document.getElementById("statusMessage");

    const issueDate = document.getElementById("issueDate");
    const dueDate = document.getElementById("dueDate");
    const actualReturn = document.getElementById("actualReturn");

    issueDate.addEventListener("change", function () {
        dueDate.min = issueDate.value;
        actualReturn.min = issueDate.value;

        if (dueDate.value && dueDate.value < issueDate.value) {
            dueDate.value = "";
        }

        if (actualReturn.value &&
            actualReturn.value < issueDate.value) {
            actualReturn.value = "";
        }
    });

    dueDate.addEventListener("change", function () {
        actualReturn.max = "";
    });

    form.addEventListener("submit", function (event) {
        event.preventDefault();

        const dno = document.getElementById("dno").value.trim().toUpperCase();
        const match = /^25UCS(\d{3})$/.exec(dno);

        if (!match ||
            Number(match[1]) < 501 ||
            Number(match[1]) > 565) {
            alert("Enter a D.NO between 25UCS501 and 25UCS565.");
            return;
        }

        if (dueDate.value < issueDate.value) {
            alert("Expected return date cannot be before the issue date.");
            return;
        }

        if (actualReturn.value &&
            actualReturn.value < issueDate.value) {
            alert("Actual return date cannot be before the issue date.");
            return;
        }

        const values = [
            dno,
            document.getElementById("studentName").value.trim(),
            document.getElementById("bookId").value.trim(),
            document.getElementById("bookTitle").value.trim(),
            issueDate.value,
            dueDate.value,
            document.getElementById("bookStatus").value,
            Number(document.getElementById("fine").value).toFixed(2)
        ];

        const emptyRow = document.getElementById("emptyRow");
        if (emptyRow) {
            emptyRow.remove();
        }

        const row = document.createElement("tr");

        values.forEach(function (value) {
            const cell = document.createElement("td");
            cell.textContent = value;
            row.appendChild(cell);
        });

        recordsTable.appendChild(row);

        statusMessage.textContent = "Book record added successfully!";
        form.reset();

        document.getElementById("department").value =
            "B.Sc. Computer Science";
        document.getElementById("year").value = "II Year";
        document.getElementById("fine").value = "0";

        dueDate.min = "";
        actualReturn.min = "";
    });
</script>

</body>
</html>
