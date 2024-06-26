<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تسجيل الدخول</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .login-container {
            width: 300px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        input, select {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            width: 100%;
            padding: 10px;
            background-color: blue;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
        }
        button:hover {
            background-color: darkblue;
        }
    </style>
</head>
<body>
    <div class="login-container">
        <h2>تسجيل الدخول</h2>
        <form onsubmit="handleLogin(event)">
            <input type="email" id="email" placeholder="البريد الإلكتروني" required>
            <input type="text" id="name" placeholder="الاسم" required>
            <input type="number" id="age" placeholder="السن" required>
            <select id="role" required>
                <option value="" disabled selected>اختر الدور</option>
                <option value="owner">المالك</option>
                <option value="manager">المدير</option>
                <option value="inquiry">استعلام</option>
            </select>
            <button type="submit">تسجيل الدخول</button>
        </form>
    </div>
    <script>
        function handleLogin(event) {
            event.preventDefault();
            const email = document.getElementById('email').value;
            const name = document.getElementById('name').value;
            const age = document.getElementById('age').value;
            const role = document.getElementById('role').value;

            // إرسال إشعار للمالك والمدير عبر البريد الإلكتروني
            if (role === 'owner' || role === 'manager') {
                alert('تم تسجيل الدخول كـ ' + (role === 'owner' ? 'مالك' : 'مدير'));
                // نقل المستخدم إلى الصفحة الرئيسية
                window.location.href = 'index.html';
            } else if (role === 'inquiry') {
                alert('تم تسجيل الدخول كـ استعلام');
                window.location.href = 'index.html';
            }
        }
    </script>
</body>
</html>
