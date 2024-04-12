<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Page</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
        }
        .container {
            text-align: center;
        }
        input[type="text"], input[type="password"], input[type="submit"] {
            padding: 10px;
            margin: 5px;
            width: 200px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        input[type="submit"] {
            cursor: pointer;
            background-color: #007bff;
            color: #fff;
            border: none;
        }
        .error-message {
            color: red;
            font-size: 12px;
            margin-top: -10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Login</h2>
        <form id="loginForm" onsubmit="return validateForm()">
            <input type="text" id="username" placeholder="Username">
            <div id="usernameError" class="error-message"></div>
            <input type="password" id="password" placeholder="Password">
            <div id="passwordError" class="error-message"></div>
            <input type="submit" value="Login">
        </form>
    </div>

    <script>
        function validateForm() {
            var username = document.getElementById("username").value;
            var password = document.getElementById("password").value;
            var usernameError = document.getElementById("usernameError");
            var passwordError = document.getElementById("passwordError");

            // 임의로 지정된 ID/PW
            var correctUsername = "user123";
            var correctPassword = "pass456";

            if (username !== correctUsername || password !== correctPassword) {
                if (username !== correctUsername) {
                    usernameError.innerHTML = "Username is incorrect";
                } else {
                    usernameError.innerHTML = "";
                }

                if (password !== correctPassword) {
                    passwordError.innerHTML = "Password is incorrect";
                } else {
                    passwordError.innerHTML = "";
                }

                return false; // 폼 제출을 막음
            }

            // 로그인이 성공할 경우
            alert("로그인이 되었습니다!");
            return true;
        }
    </script>
</body>
</html>
