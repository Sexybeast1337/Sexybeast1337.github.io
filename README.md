<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minecraft Virtual Computer</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #2e2e2e;
            color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .computer {
            width: 800px;
            background-color: #1e1e1e;
            border: 3px solid #00ff00;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 0 20px #00ff00;
        }

        .screen {
            background-color: #000000;
            color: #00ff00;
            padding: 20px;
            font-family: "Courier New", Courier, monospace;
            height: 400px;
            overflow-y: auto;
            border: 2px solid #00ff00;
            margin-bottom: 10px;
        }

        textarea {
            width: 100%;
            height: 200px;
            background-color: #1e1e1e;
            color: #ffffff;
            border: 2px solid #00ff00;
            font-family: "Courier New", Courier, monospace;
            padding: 10px;
            resize: none;
        }

        button {
            background-color: #00ff00;
            color: #1e1e1e;
            border: none;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            border-radius: 5px;
        }

        button:hover {
            background-color: #1aff1a;
        }
    </style>
</head>
<body>
    <div class="computer">
        <div class="screen" id="screen">
            Welcome to the Minecraft Virtual Computer!<br>
            Type your report below and click "Save Report."
        </div>
        <textarea id="report" placeholder="Write your report here..."></textarea>
        <button onclick="saveReport()">Save Report</button>
    </div>

    <script>
        function saveReport() {
            const reportText = document.getElementById('report').value;
            if (reportText.trim() === '') {
                alert('Please write something before saving.');
                return;
            }

            const screen = document.getElementById('screen');
            const reportEntry = document.createElement('div');
            reportEntry.textContent = `> ${reportText}`;
            screen.appendChild(reportEntry);

            // Clear the text area
            document.getElementById('report').value = '';

            // Scroll to the bottom of the screen
            screen.scrollTop = screen.scrollHeight;
        }
    </script>
</body>
</html>
