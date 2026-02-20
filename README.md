# student-mark

# Coding
<!DOCTYPE html>
<html>
<head>
    <title>Student Marks Manager</title>

    <style>
        body {
            font-family: 'Segoe UI', sans-serif;
            margin: 0;
            padding: 30px;
            background: linear-gradient(135deg, #1d2671, #c33764);
        }

        h1 {
            text-align: center;
            color: white;
            margin-bottom: 30px;
        }

        .container {
            background: white;
            max-width: 900px;
            margin: auto;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.4);
        }

        .section {
            margin-bottom: 25px;
            padding: 20px;
            border-radius: 10px;
            background: #f4f6f9;
        }

        .section h3 {
            margin-top: 0;
            color: #c33764;
        }

        input {
            width: 100%;
            padding: 10px;
            margin: 8px 0;
            border-radius: 8px;
            border: 1px solid #ccc;
            outline: none;
            transition: 0.3s;
        }

        input:focus {
            border-color: #c33764;
            box-shadow: 0 0 5px #c33764;
        }

        button {
            padding: 10px 20px;
            background: #c33764;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            margin-top: 10px;
            transition: 0.3s;
        }

        button:hover {
            background: #8e2450;
            transform: scale(1.05);
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 30px;
        }

        th {
            background: #1d2671;
            color: white;
            padding: 10px;
        }

        td {
            padding: 10px;
            text-align: center;
        }

        tr:nth-child(even) {
            background: #f2f2f2;
        }

        tr:hover {
            background: #ffe3ec;
        }

        .pass {
            color: green;
            font-weight: bold;
        }

        .fail {
            color: red;
            font-weight: bold;
        }
    </style>
</head>

<body>

<h1>📊 Student Marks Entry</h1>

<div class="container">

    <!-- Section 1 -->
    <div class="section">
        <h3>Student Details</h3>
        <input type="text" id="name" placeholder="Student Name">
        <input type="text" id="roll" placeholder="Roll No">
    </div>

    <!-- Section 2 -->
    <div class="section">
        <h3>Science Subjects</h3>
        <input type="number" id="maths" placeholder="Maths">
        <input type="number" id="python" placeholder="Python">
        <input type="number" id="or" placeholder="Operation Research">
    </div>

    <!-- Section 3 -->
    <div class="section">
        <h3>Language Subjects</h3>
        <input type="number" id="tamil" placeholder="Tamil">
        <input type="number" id="english" placeholder="English">
    </div>

    <button onclick="addStudent()">Save</button>

    <table id="marksTable">
        <tr>
            <th>Name</th>
            <th>Roll No</th>
            <th>Maths</th>
            <th>Python</th>
            <th>Operation Research</th>
            <th>Tamil</th>
            <th>English</th>
            <th>Total</th>
            <th>Result</th>
        </tr>
    </table>

</div>

<script>
function addStudent() {

    let name = document.getElementById("name").value;
    let roll = document.getElementById("roll").value;
    let maths = parseInt(document.getElementById("maths").value);
    let python = parseInt(document.getElementById("python").value);
    let or = parseInt(document.getElementById("or").value);
    let tamil = parseInt(document.getElementById("tamil").value);
    let english = parseInt(document.getElementById("english").value);

    if(name === "" || roll === "" ||
       isNaN(maths) || isNaN(python) || isNaN(or) ||
       isNaN(tamil) || isNaN(english)) {
        alert("Please fill all fields properly!");
        return;
    }

    let total = maths + python + or + tamil + english;

    let result = (maths>=35 && python>=35 && or>=35 && tamil>=35 && english>=35)
        ? "Pass" : "Fail";

    let table = document.getElementById("marksTable");
    let row = table.insertRow();

    row.insertCell(0).innerHTML = name;
    row.insertCell(1).innerHTML = roll;
    row.insertCell(2).innerHTML = maths;
    row.insertCell(3).innerHTML = python;
    row.insertCell(4).innerHTML = or;
    row.insertCell(5).innerHTML = tamil;
    row.insertCell(6).innerHTML = english;
    row.insertCell(7).innerHTML = total;

    let resultCell = row.insertCell(8);
    resultCell.innerHTML = result;
    resultCell.className = result === "Pass" ? "pass" : "fail";

    document.querySelectorAll("input").forEach(input => input.value = "");
}
</script>

</body>
</html>

# Website
<img width="1314" height="508" alt="image" src="https://github.com/user-attachments/assets/fe433563-b2c2-4311-a386-27f8999f739f" />
<img width="1341" height="769" alt="image" src="https://github.com/user-attachments/assets/eb207fa5-32e6-4f7d-bed9-a1b22a1a6169" />



# Output
https://rajeshwari69514-boop.github.io/student-mark/
