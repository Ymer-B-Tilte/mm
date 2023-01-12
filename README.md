<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <form action="action_page.php">
        <div class="container">
          <h1>Регистрация</h1>

          <label for="email"><b></b></label>
          <input type="text" placeholder="Введите электронную почту" name="email" required>
      
          <label for="psw"><b>Пароль</b></label>
          <input type="Пароль" placeholder="Ввести пароль" name="psw" required>
      
          <label for="psw-repeat"><b>Повторите пароль</b></label>
          <input type="Пароль" placeholder="Повторите пароль" name="psw-repeat" required>
      
          <button type="submit" class="registerbtn">Регистрация</button>
        </div>
      
        <div class="container signin">
          <p>Имеете уже аккаунт? <a href="#">Войти</a>.</p>
        </div>
      </form>
      <script>
        let usernames = [];
        let userpasswords = [];

        function Argister(){
            let username = document.getElementById("username");
            let userpassword = document.getElementById("password").value;
            
            let truefalse = 1;
            let passwoedtrue = 0;

            //username seiting
            for(let i = 0; i <= usernames.length; i++){
                if(username.value === usernames[i]){
                    truefalse = 0;
                }
            }

            //password seiting
            if(userpassword.length >= 4 && userpasswoed.length <= 12){
                passwordtrue = 1;
                
            }
            

            if(truefalse == 1 && passwordtrue == 1){
                usernames.push(username.value);
                userpassword.push(userpassword);
            }
            else{
                alert("Ошибка регистрации")
            }
            console.log(usernames, userpasswoeds)
        }

        function login(){
            let username = document.getElementById("username");
            let userpassword = document.getElementById("password").value;

            let truefalse = 0;
            for(let i = 0; i <= usernames.length && i <+ userpasswords.length; i++){
                if(username.value === usernames[i] && userpassword === userpasswords[i]){
                    truefalse = 1;
                }
            }
            if(truefalse === 1)
                alert("Succes");
            else
                alert("Error");
        }
      </script>
</body>
</html>
