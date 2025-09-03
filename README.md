<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>قياس فرق الطول بين شخصين</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #e0f7fa, #fce4ec);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-start;
      min-height: 100vh;
      padding-top: 40px;
      margin: 0;
    }
    h1 {
      color: #333;
    }
    input {
      padding: 10px;
      margin: 10px;
      width: 150px;
      font-size: 16px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      margin-top: 10px;
      border-radius: 5px;
      border: none;
      background-color: #ff4081;
      color: white;
    }
    .result {
      margin-top: 20px;
      font-size: 18px;
      color: #222;
    }
    .characters {
      display: flex;
      justify-content: center;
      gap: 60px;
      margin-top: 40px;
      align-items: flex-end;
    }
    .character {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .character div {
      width: 80px;
      border-radius: 10px;
      margin-bottom: 10px;
      transition: height 0.3s;
    }
    .character p {
      margin: 0;
      font-weight: bold;
    }
    /* ألوان الشخصين */
    #person1 {
      background-color: #ff80ab;
    }
    #person2 {
      background-color: #4dd0e1;
    }
  </style>
</head>
<body>

  <h1>حاسبة فرق الطول بين شخصين</h1>
  <p>أدخل الطول بالسنتيمتر:</p>
  
  <input type="number" id="height1" placeholder="شخص 1">
  <input type="number" id="height2" placeholder="شخص 2"><br>
  <button onclick="calculateHeight()">احسب الفرق</button>

  <div class="result" id="result"></div>

  <div class="characters">
    <div class="character">
      <div id="person1" style="height:150px;"></div>
      <p>شخص 1</p>
    </div>
    <div class="character">
      <div id="person2" style="height:150px;"></div>
      <p>شخص 2</p>
    </div>
  </div>

  <script>
    function calculateHeight() {
      let h1 = parseFloat(document.getElementById("height1").value);
      let h2 = parseFloat(document.getElementById("height2").value);
      
      if(isNaN(h1) || isNaN(h2)) {
        document.getElementById("result").innerText = "رجاءً أدخل طول كلا الشخصين!";
        return;
      }
      
      let diff = Math.abs(h1 - h2);
      document.getElementById("result").innerText = `فرق الطول هو: ${diff} سم`;
      
      // تعديل ارتفاع المستطيلات حسب الطول
      document.getElementById("person1").style.height = `${h1 * 2}px`;
      document.getElementById("person2").style.height = `${h2 * 2}px`;
    }
  </script>

</body>
</html>
