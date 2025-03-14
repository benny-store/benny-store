<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Connexion</title>
    <script src="https://www.gstatic.com/firebasejs/9.6.1/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.6.1/firebase-auth.js"></script>
</head>
<body>
    <h2>Connexion et Inscription</h2>
    <input type="email" id="email" placeholder="Email">
    <input type="password" id="password" placeholder="Mot de passe">
    <button onclick="register()">S'inscrire</button>
    <button onclick="login()">Se connecter</button>
    <button onclick="logout()">Se déconnecter</button>

    <script>
        // Configuration Firebase (remplace avec ton propre config Firebase)
        const firebaseConfig = {
            apiKey: "AIzaSyDh8W9EZbcySMEaDvzfMzBbrzjJ-vyCp0U ",
            authDomain: "auth--software-store.firebaseapp.com",
        };
        firebase.initializeApp(firebaseConfig);

        function register() {
            let email = document.getElementById("email").value;
            let password = document.getElementById("password").value;
            firebase.auth().createUserWithEmailAndPassword(email, password)
                .then((userCredential) => alert("Compte créé avec succès !"))
                .catch((error) => alert(error.message));
        }

        function login() {
            let email = document.getElementById("email").value;
            let password = document.getElementById("password").value;
            firebase.auth().signInWithEmailAndPassword(email, password)
                .then((userCredential) => alert("Connexion réussie !"))
                .catch((error) => alert(error.message));
        }

        function logout() {
            firebase.auth().signOut().then(() => alert("Déconnecté !"));
        }
    </script>
</body>
</html>