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
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
    text-align: center;
}

.container {
    background: white;
    max-width: 500px;
    margin: 50px auto;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h1 {
    font-size: 24px;
    color: #333;
}

label {
    font-size: 18px;
}

select {
    margin: 10px 0;
    padding: 8px;
    font-size: 16px;
}

.hidden {
    display: none;
}

#result {
    margin-top: 20px;
    padding: 10px;
    background: #dff0d8;
    border-radius: 5px;
}
function showTreatment() {
    const symptom = document.getElementById("symptom").value;
    const treatmentText = document.getElementById("treatment");
    const resultDiv = document.getElementById("result");

    let treatmentInfo = "";

    switch(symptom) {
        case "period_pain":
            treatmentInfo = "วิธีรักษา: ประคบร้อน ทานน้ำอุ่น ออกกำลังกายเบาๆ <br> ยาที่ใช้ได้: ไอบูโพรเฟน (Ibuprofen), พาราเซตามอล (Paracetamol)";
            break;
        case "headache":
            treatmentInfo = "วิธีรักษา: ดื่มน้ำมากๆ นอนพัก หลีกเลี่ยงเสียงดัง <br> ยาที่ใช้ได้: พาราเซตามอล (Paracetamol), ไอบูโพรเฟน (Ibuprofen)";
            break;
        case "leg_pain":
            treatmentInfo = "วิธีรักษา: ประคบเย็น นวดเบาๆ พักขาให้สูง <br> ยาที่ใช้ได้: ไอบูโพรเฟน (Ibuprofen), นาโปรเซน (Naproxen)";
            break;
        case "seizure":
            treatmentInfo = "วิธีรักษา: พยุงร่างกายให้นอนตะแคง เคลียร์พื้นที่รอบตัว ห้ามใส่อะไรเข้าปาก <br> ควรพบแพทย์ทันที";
            break;
        case "choking":
            treatmentInfo = "วิธีรักษา: ใช้วิธี Heimlich Maneuver (กดท้องดันอากาศออก) หรือให้ผู้ป่วยก้มหัวลงแล้วตบหลัง";
            break;
        default:
            treatmentInfo = "";
    }

    if (treatmentInfo) {
        treatmentText.innerHTML = treatmentInfo;
        resultDiv.classList.remove("hidden");
    } else {
        resultDiv.classList.add("hidden");
    }
}