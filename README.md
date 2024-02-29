<!DOCTYPE html>
<html>
<head>
    <title>حساب العمر والبرج</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        
        h1 {
            color: #333;
        }
        
        .input-container {
            margin: 20px auto;
            max-width: 300px;
        }
        
        .input-container input {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            margin-bottom: 10px;
            box-sizing: border-box;
        }
        
        .btn {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        
        .result {
            margin: 20px auto;
            max-width: 300px;
            padding: 10px;
            background-color: #f1f1f1;
        }
    </style>
</head>
<body>
    <h1>حساب العمر والبرج</h1>
    <div class="input-container">
        <input type="date" id="birthdate" required>
        <button class="btn" onclick="calculateAgeAndZodiac()">احسب</button>
    </div>
    <div class="result" id="result"></div>

    <script>
        function calculateAgeAndZodiac() {
            var birthdate = document.getElementById("birthdate").value;
            var today = new Date();
            var birthdateObj = new Date(birthdate);
            var age = today.getFullYear() - birthdateObj.getFullYear();
            var monthDiff = today.getMonth() - birthdateObj.getMonth();
            if (monthDiff < 0 || (monthDiff === 0 && today.getDate() < birthdateObj.getDate())) {
                age--;
            }
            
            var zodiac = getZodiac(birthdateObj.getMonth() + 1, birthdateObj.getDate());
            
            var result = "عمرك: " + age + " سنة<br>";
            result += "برجك الفلكي: " + zodiac;
            
            document.getElementById("result").innerHTML = result;
        }
        
        function getZodiac(month, day) {
            // قم بتعريف البرج الفلكي هنا بناءً على الشهر واليوم المعطيين
            // قم بإرجاع اسم البرج الفلكي المطابق
            
            // مثال بسيط للبرج الفلكي
            if ((month === 1 && day >= 20) || (month === 2 && day <= 18)) {
                return "برج الدلو";
            } else if ((month === 2 && day >= 19) || (month === 3 && day <= 20)) {
                return "برج الحوت";
            } else {
                return "برج غير معروف";
            }
        }
    </script>
</body>
</html>
