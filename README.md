<!DOCTYPE html>
<html lang="km">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>វត្តមានគ្រូបង្រៀន - សាលាបឋមសិក្សាហ៊ុនសែនមិត្តភាព</title>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        :root {
            --primary-color: #2481cc;
            --success-color: #28a745;
            --bg-color: #f4f7f6;
            --card-bg: #ffffff;
            --text-color: #333333;
        }
        body {
            font-family: 'Khmer OS Siemreap', Arial, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            padding: 12px;
            margin: 0;
        }
        .header {
            text-align: center;
            background: linear-gradient(135deg, #2481cc, #1e5b88);
            color: white;
            padding: 20px 10px;
            border-radius: 12px;
            margin-bottom: 15px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        .header h2 {
            margin: 5px 0;
            font-size: 18px;
        }
        .header p {
            margin: 0;
            font-size: 13px;
            opacity: 0.9;
        }
        .card {
            background: var(--card-bg);
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 2px 6px rgba(0,0,0,0.05);
            margin-bottom: 12px;
        }
        .card h3 {
            font-size: 15px;
            margin-top: 0;
            color: var(--primary-color);
            border-bottom: 2px solid #f0f0f0;
            padding-bottom: 8px;
        }
        /* ទម្រង់តារាងវត្តមាន */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 5px;
            font-size: 13px;
        }
        th, td {
            border: 1px solid #e0e0e0;
            padding: 8px 6px;
            text-align: center;
        }
        th {
            background-color: #f8f9fa;
            color: #555;
            font-weight: bold;
        }
        .status-present {
            color: var(--success-color);
            font-weight: bold;
        }
        .status-absent {
            color: #dc3545;
            font-weight: bold;
        }
        /* ប៊ូតុងផ្ញើវត្តមាន */
        .btn-submit {
            background-color: var(--success-color);
            color: white;
            border: none;
            width: 100%;
            padding: 12px;
            font-size: 15px;
            font-family: 'Khmer OS Siemreap', Arial, sans-serif;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            box-shadow: 0 4px 6px rgba(40, 167, 69, 0.2);
            margin-top: 10px;
        }
        .btn-submit:active {
            transform: scale(0.98);
        }
    </style>
</head>
<body>

    <!-- ផ្នែកក្បាលកម្មវិធី -->
    <div class="header">
        <h2>សាលាបឋមសិក្សាហ៊ុនសែនមិត្តភាព</h2>
        <p>ប្រព័ន្ធគ្រប់គ្រងវត្តមានគ្រូបង្រៀនប្រចាំថ្ងៃ</p>
    </div>

    <!-- ផ្នែកព័ត៌មានថ្ងៃខែ -->
    <div class="card">
        <h3>📅 កាលបរិច្ឆេទថ្ងៃនេះ</h3>
        <p id="current-date" style="margin: 5px 0; font-weight: bold; color: #555;"></p>
    </div>

    <!-- ផ្នែកតារាងវត្តមានគ្រូ -->
    <div class="card">
        <h3>📝 បញ្ជីវត្តមានគ្រូประจำកម្រិត</h3>
        <table>
            <thead>
                <tr>
                    <th>ឈ្មោះលោកគ្រូ/អ្នកគ្រូ</th>
                    <th>ថ្នាក់ទី</th>
                    <th>វត្តមាន</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>លោកគ្រូ នាយក</td>
                    <td>រដ្ឋបាល</td>
                    <td><span class="status-present">វត្តមាន</span></td>
                </tr>
                <tr>
                    <td>អ្នកគ្រូ <s>ក</s></td>
                    <td>ទី១</td>
                    <td><span class="status-present">វត្តមាន</span></td>
                </tr>
                <tr>
                    <td>លោកគ្រូ <s>ខ</s></td>
                    <td>ទី២</td>
                    <td><span class="status-absent">អវត្តមាន</span></td>
                </tr>
            </tbody>
        </table>

        <!-- ប៊ូតុងបញ្ជាក់វត្តមាន -->
        <button class="btn-submit" onclick="submitAttendance()">ចុះឈ្មោះវត្តមានថ្ងៃនេះ</button>
    </div>

    <script>
        // បើក Telegram Web App ឱ្យពេញអេក្រង់
        let tg = window.Telegram.WebApp;
        tg.expand();

        // បង្ហាញកាលបរិច្ឆេទបច្ចុប្បន្នជាភាសាខ្មែរ
        const options = { year: 'numeric', month: 'long', day: 'numeric', weekday: 'long' };
        document.getElementById('current-date').innerText = new Date().toLocaleDateString('km-KH', options);

        // פונក្សនពេលចុចប៊ូតុង
        function submitAttendance() {
            alert("✅ វត្តមានត្រូវបានបញ្ជូនដោយជោគជ័យ!");
        }
    </script>

</body>
</html>
