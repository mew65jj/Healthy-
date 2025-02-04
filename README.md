<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>เว็บให้ข้อมูลยาและการรักษา</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>แนะนำการรักษาอาการเบื้องต้น</h1>
        <label for="symptom">เลือกอาการ:</label>
        <select id="symptom" onchange="showTreatment()">
            <option value="">-- กรุณาเลือกอาการ --</option>
            <option value="period_pain">ปวดท้องเมน</option>
            <option value="headache">ปวดหัว</option>
            <option value="leg_pain">ปวดขา</option>
            <option value="seizure">ชัก</option>
            <option value="choking">อาหารติดคอ</option>
        </select>

        <div id="result" class="hidden">
            <h2>วิธีรักษาและยา</h2>
            <p id="treatment"></p>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>