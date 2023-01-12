<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MadeByZzerud^-^</title>
</head>
<body>
  <textarea id = "username" placeholder="Введите имя"></textarea>
  <textarea id = "password" placeholder="Введите пароль"></textarea>
  <button onclick="register()">Register</button>
  <button onclick="login()">Login</button>

  <script type="text/javascript">

  let usernames = JSON.parse(localStorage.getItem("usernames"))  [];
    let passwords = JSON.parse(localStorage.getItem("passwords"))  [];

  function register() {
    let username = document.getElementById("username").value;
    let password = document.getElementById("password").value;

  //проверяем, взят ли юзернейм
    let isUsernameTaken = usernames.includes(username);
  //проверяем, валидный ли пароль
    let isPasswordValid = password.length >= 4 && password.length <= 12;

    if (!isUsernameTaken && isPasswordValid) {
      usernames.push(username);
      passwords.push(password);
      localStorage.setItem("usernames", JSON.stringify(usernames));
      localStorage.setItem("passwords", JSON.stringify(passwords));
      alert("Регистрация завершена!");
    } 
  else {
    if(isUsernameTaken){
      alert("Регистрация не завершена. Ваше имя уже занято.");
    }
    else{
      alert("Регистрация не завершена. Пароль не соответствует правильности, проверьте чтобы он был не меньше 4 и не больше 12 символов!");
    }
    }
  }

  function login() {
    let username = document.getElementById("username").value;
    let password = document.getElementById("password").value;

    let bool = 0;

  for(let i = 0; i <= usernames.length && i <= passwords.length; i++){
    if(username === usernames[i] && password === passwords[i]){
      bool = 1;
    }
  }


    if (bool === 1) {
      alert("Успешный вход!");
    } else {
      alert("Вход не удался. Проверьте своё имя и пароль, возможно вам придется регистрироваться.");
    }
  }
  </script>
</body>
</html>
