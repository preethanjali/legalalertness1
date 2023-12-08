<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LEGAL ALERTNESS</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>

    <h1><b><img src="ss.jpg" width="50px">LEGAL ALERTNESS</b></h1>
    
    <header>
        <nav class="navigation">
            <a href="#">Home</a>
            <div class="dropdown">
                <a href="#">Languages</a>
                <div class="dropdown-content">
                    <a href="#">English</a>
                    <a href="#">Tamil</a>
                    <a href="#">Malayalam</a>
                    <a href="#">Telugu</a>
                    <a href="#">Spanish</a>
                    <a href="#">Hindi</a>
                    <a href="#">German</a>
                    <a href="#">Kannada</a>
                    <a href="#">Urdu</a>
                    <a href="#">Marathi</a>
                    <a href="#">Bengali</a>
                    <a href="#">Gujarati</a>
                    <a href="#">Sanskrit</a>
                    <a href="#">Nepali</a>
                    <a href="#">Kashmiri</a>
                    <a href="#">Odia</a>
                    <a href="#">Manipuri</a>
                    <a href="#">Santali</a>
                    <a href="#">Rajasthani</a>
                    <a href="#">French</a>
                </div>
            </div>
            <a href="About.html">About</a>
            <div class="dropdown">
                <a href="#" onclick="toggleContactDropdown()">Contact Us</a>
                <div id="contact-dropdown" class="dropdown-content">
                    <div class="contact-option">
                        <h3>Contact Number</h3>
                        <p>+1 234 567 890</p>
                    </div>
                    <div class="contact-option">
                        <h3>Talk with Our Advisor</h3>
                        <button onclick="openAdvisorChat()">Chat Now</button>
                    </div>
                </div>
            </div>

            <div id="chat-container">
                <div id="chat-messages"></div>
            </div>

            <div class="g-signin2" data-onsuccess="onSignIn" data-clientid="preethanjali2503@gmail.com"></div>

            <a href="#">Help</a>
            <button class="btnSignup-popup">Signup</button>
        </nav>
    </header>

    <div class="wrapper">
        <div class="form-box login">
            <h2>Login</h2>
            <form action="#">
                <div class="input-box">
                    <span class="icon"><ion-icon name="mail"></ion-icon></span>
                    <input type="email" placeholder="eg:legal@gmail.com or 9182...." required>
                    <label>Email or Mob no</label>
                </div>

                <div class="input-box">
                    <span class="icon"><ion-icon name="lock-closed"></ion-icon></span>
                    <input type="password" placeholder="enter any 5 digits" required>
                    <label>Password</label>
                </div>

                <div class="remember-forgot">
                    <label><input type="checkbox"> Remember me</label>
                    <a href="#">Forgot Password?</a>
                </div>
                <button>Login</button>
                <div class="login-register">
                    <p>Don't have an account?<a href="#" class="Register-link">Register</a></p>
                </div>
            </form>
        </div>

        <div class="form-box register">
            <h2>Registration</h2>
            <form action="#" onsubmit="redirectToWelcome(); return false;">
                <div class="input-box">
                    <span class="icon-person"><ion-icon name="person"></ion-icon></span>
                    <input type="text" placeholder="enter your name" required>
                    <label>Username</label>
                </div>

                <div class="input-box">
                    <span class="icon"><ion-icon name="mail"></ion-icon></span>
                    <input type="email" placeholder="eg:legal@gmail.com or 9182...." required>
                    <label>Email or Mob no</label>
                </div>

                <div class="input-box">
                    <span class="icon"><ion-icon name="lock-closed"></ion-icon></span>
                    <input type="password" placeholder="enter any 5 digits" required>
                    <label>Password</label>
                </div>

                <div class="remember-forgot">
                    <label><input type="checkbox"> Agree to the terms & conditions</label>
                    <a href="#">Forgot Password?</a>
                </div>
                <button type="submit">Register</button>
                <div class="login-register">
                    <p>Already have an account?<a href="#" class="login-link">Login</a></p>
                </div>
            </form>
        </div>
    </div>

    <script src="script.js"></script>
    <script type="module" src="https://unpkg.com/ionicons@7.1.0/dist/ionicons/ionicons.esm.js"></script>
    <script nomodule src="https://unpkg.com/ionicons@7.1.0/dist/ionicons/ionicons.js"></script>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
    <!-- Add this script block to your existing HTML file or include it in your script.js file -->
    <script>
        document.addEventListener('DOMContentLoaded', function () {
            const dropdown = document.querySelector('.dropdown');
            const dropdownContent = document.querySelector('.dropdown-content');

            dropdown.addEventListener('click', function () {
                dropdownContent.classList.toggle('show');
            });
        });

        function toggleContactDropdown() {
            var dropdown = document.getElementById("contact-dropdown");
            dropdown.classList.toggle("show");
        }

        function showAdvisorMessage() {
            addMessage("Bot", "Connecting to our advisor. Please wait...");

            setTimeout(function () {
                window.location.href = "chat.html";
            }, 1000); // Adjust the delay as needed
        }

        function openAdvisorChat() {
            showAdvisorMessage();
        }

        function addMessage(sender, message) {
            var chatMessages = document.getElementById('chat-messages');
            var messageDiv = document.createElement('div');
            messageDiv.innerHTML = `<strong>${sender}:</strong> ${message}`;
            chatMessages.appendChild(messageDiv);

            // Scroll to the bottom to show the latest messages
            chatMessages.scrollTop = chatMessages.scrollHeight;
        }
    </script>
    <script src="https://apis.google.com/js/platform.js" async defer></script>
    <script>
        function initGoogleSignIn() {
            gapi.load('auth2', function () {
                gapi.auth2.init({
                    client_id: 'preethanjali2503@gmail.com',
                });
            });
        }

        function onSignIn(googleUser) {
            var profile = googleUser.getBasicProfile();
            console.log('ID: ' + profile.getId()); // Do something with the user's ID
            console.log('Name: ' + profile.getName()); // Do something with the user's name
            console.log('Email: ' + profile.getEmail()); // Do something with the user's email
        }

        document.addEventListener('DOMContentLoaded', initGoogleSignIn);
    </script>
</body>

</html>

<style>
    * { 
    
margin: 0;
padding: 0;
box-sizing: border-box;
font-family: 'poppins', cursive;
}

body {
display: flex;
justify-content: center;
align-items: center;
min-height: 100vh;
background: url('1.jpg') no-repeat;
background-size: cover;
background-position: center;    
}

label {
color: #f2b6b6;
}

h2 {
color: #f2b6b6;
}

span {
color: #f2b6b6;
}

input {
color: #f2b6b6;
font-size: 10em;
}

h1 {
    position: absolute;
    top: 0;
    left: 3%;

}
h1 img {
    width: 50px;
    height: 50px;
    border-radius: 50%; 
    overflow: hidden;
    object-fit: cover;
    margin-top: -5px; 
}


h1 {
    display: flex;
    align-items: center;
}

h1 b {
    margin-left: 4px;
    color: rgb(14, 18, 69);
    font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}






header {
position: absolute;
top: 0;
right: 0;
width: 100;
padding: 20px 100px;
background: #A96F44 #F2ECB6;
display: flex;
justify-content: space-between;
align-items: baseline;
z-index: 99;
}

.g-signin2 {
    margin-top: 20px;
 }
 

.navigation a {
position: relative;
right: 0;
bottom: -6px;
font-size: 1.2em;
color: #f2b6b6; 
text-decoration: dotted;
font-weight: 500;
margin-right: 40px;
transform: scalex(0);
}

.navigation a::after {
content: '';
position: absolute;
right: 0;
bottom: -6px;
width: 100%;
height: 3px;
background: #9c9ca5;
border-radius: 5px;
transform: scaleX(0);
transition: transform .5s;
}

.navigation a:hover::after {
transform-origin: right;
transform: scaleX(1);
}


.dropdown {
    position: relative;
    display: inline-block;
}

.dropdown-content {
    display: none;
    position: absolute;
    background: transparent; 
    min-width: 160px;
    box-shadow: 0px 8px 16px 0px rgba(175, 155, 155, 0.2);
    z-index: 1;
}


.dropdown-content {
    display: none;
}




.dropdown-content a {
    color: #f2b6b6; 
    padding: 9px 9px;
    text-decoration: none;
    font-family: 'cursive';
    transition: all 0.3s ease;  
}

.dropdown-content a:hover {
    background: #f2b6b6;
    width:0%;
    text-decoration: none;
}

.dropdown:hover .dropdown-content {
    display: block;
}

b img {
    background: transparent;
}





.navigation .btnSignup-popup {
position:static;
width: 130px;
height: 50px;
background: transparent;
border: 2px solid #9c9ca5;
outline: none;
border-radius: 6px;
cursor: pointer;
font-size: 1.1em;
color: #f2b6b6;
font-weight: 500;
margin-right: 45px;
transition: 5s;
}

.navigation .btnSignup-popup:hover {
background: #6e1f1f;
color: #843f1e
}

.navigation .btnLogin-popup {
transition: 4s;
overflow:hidden;
}



p {
color: #f2b6b6;
}

.wrapper button {
color: #f2b6b6;
background: transparent;
font-size: 1.3em;
transform: translateY(-25%);
outline: none;
border-radius: 7px;

}


.wrapper {
position: relative;
width: 420px;
height: 470px;
background: transparent;
border: 2px solid rgb(109, 109, 158);
border-radius: 20px;
backdrop-filter: rgb(11, 11, 229);
box-shadow: 0 0 30px #956533;
display: flex;
font-size: 1.1em;
justify-content: center;
align-items: center;
overflow: hidden;
transition: height .5s ease, height .2s ease, border-color: 0.5s ease;
}

.wrapper:hover{
    border-color: #f2b6b6;
    animation: border-glow is infinite alternate;

}

@keyframes wrapper-glow {
    from {
        border-color: #f2b6b6;
        box-shadow: 0 0 20px #9c9ca5;
    }
    to {
        border-color: #f2b6b6;
        box-shadow: 0 0 20px #f2b6b6;
    }
}



.wrapper:hover {
    border-color: #f2b6b6;
    animation: wrapper-glow infinite alternate;
}


.wrapper.active-popup {
    animation: wrapper-glow infinite alternate;
}

.wrapper.active {
    height: 520px;
    animation: wrapper-glow infinite alternate;
}

.wrapper .form-box {
width: 100%;
padding: 50px;
}

.wrapper .form-box.login {
    display: absolute;
    transition: .10s ease;
    transform: translateX(0); 
}

.wrapper.active .form-box.login {
    transition: none;
    transform: translateX(-400px);
}


.wrapper .form-box.register {
    display: absolute;
}

.wrapper .form-box.register {
    position: absolute;
    transition: none;
    transform: translateX(400px);
}

.wrapper.active .form-box.register{
    transition: transform .10% ease;
    transform: translateX(0px); 
}


a {
color: #f2b6b6;
}

label {
color: #f2b6b6;
}

h2 {
color: #f2b6b6;
text-align: center;
font-size: 5em;
}

span {
color: #f2b6b6;
}

input {
color: #f2b6b6;
font-size: 10em;
}



.form-box h2 {
transform: translateY(-0.5%);
align-text: center;
font-size: 2em;
color: #f2b6b6;
position: relative;
}

.input-box {
position: relative;
width: 350px;
height: 40px;
border-bottom: 3px solid #f2b6b6;
margin: 50px 0; 
}

.input-box .icon-person {
position: absolute;
right: 0px;
font-size: 1.2em;
}

.input-box label {
position: absolute;
top: 40%;
left: 5px;
transform: translateY(-130%);
font-size: 6en;
color: #f2b6b6;
font-weight: 700;
pointer-events: none;
transition: all 0.5s ease-in-out;
}

.input-box input:focus~label,
.input-box input:valid~label {
      top: -5px;
}

.input-box input {
width: 100;
height: 100;
background: transparent;
border: none;
outline: none;
font-size: 1em;
color: #f2b6b6;
font-weight: 600;
padding: 0 35px 0 5px;
}

.input-box .icon {
position: absolute;
right: 1px;
font-size: 1.2em;
color: #f2b6b6;
line-height: 57px;
}


.remember-forgot {
    font-size: 1em;
    color: #f2b6b6;
    font-weight: 500;
    margin: -15px 0 15px;
    display: flex;
    justify-content: space-between;
    }
    
    

.remember-forgot label  {
color: #f2b6b6;
font-size: 1em;
font-weight: 600;
}

.remember-forgot label input {
        accent-color: #f2b6b6;
        margin-right: 3px;
}
    
.remember-forgot a{
    color: #f2b6b6;
    text-decoration: none;
}

.remember-forgot a:hover {
    text-decoration: underline;
 }

 .btn {
    width: 100%;
    height: 50px;
    border: #9c9ca5;
    outline: #9c9ca5;
    border-radius: 6px;
    cursor: pointer;
    font-size: 1em;
    color: #f2b6b6;
    font-weight: 500;
    }

button {
    width: 100%;
    height: 50px;
}

.login-register {
transform: translateY(-100%);
font-size: 1em;
color: #f2b6b6;
text-align: center;
font-weight: 500;
margin: 10px 0 8px;
}

.login-register p a {
color: #f2b6b6;
text-decoration: none;
font-weight: 600;
}

.login-register p a:hover {
text-decoration: underline;
}


</style>

<script>
    document.addEventListener('DOMContentLoaded', function () {
    const wrapper = document.querySelector('.wrapper');
    const loginLink = document.querySelector('.login-link');
    const registerLink = document.querySelector('.Register-link');
    
    function showLoginForm() {
        wrapper.classList.remove('active');
    }
    
    function showRegisterForm() {
        wrapper.classList.add('active');
    }

    registerLink.addEventListener('click', showRegisterForm);
    loginLink.addEventListener('click', showLoginForm);
});

document.addEventListener('DOMContentLoaded', function () {
    const dropdown = document.querySelector('.dropdown');
    const dropdownContent = document.querySelector('.dropdown-content');

    dropdown.addEventListener('click', function () {
        dropdownContent.classList.toggle('show');
    });
});



// Add these functions to your existing script.js file

function toggleContactDropdown() {
    var dropdown = document.getElementById("contact-dropdown");
    dropdown.classList.toggle("show");
}




</script>



