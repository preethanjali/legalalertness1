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
