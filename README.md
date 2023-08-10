<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hil Fr. Ling</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #dad9d9;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            margin: 0;
        }
        #berandaLink {
            text-decoration: none;
            color: #3498db;
            cursor: pointer;
        }
        #response {
            margin-top: 20px;
            background-color: #ca5656;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
            display: none;
            text-align: center;
        }
        #response p {
            margin-bottom: 10px;
        }
        #yesButton, #noButton {
            background-color: #3498db;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 4px;
            cursor: pointer;
            margin: 5px;
            opacity: 0; /* Mengatur opasitas awal menjadi 0 */
        }
        #result {
            display: none;
            font-weight: bold;
            margin-top: 10px;
            opacity: 0; /* Mengatur opasitas awal menjadi 0 */
            transition: opacity 1s ease-in-out; /* Animasi perubahan opasitas selama 1 detik */
        }
        #footer {
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 12px;
            color: #777;
        }
    </style>
</head>
<body>
    <header>
        <h1>Halo Lica, sibuk?<a href="#" id="berandaLink">kalo engga coba tekan</a></h1>
    </header>
    
    <div id="response">
        <p>u love me?</p>
        <button id="yesButton">Yes daddy</button>
        <button id="noButton">G</button>
        <p id="result"></p>
    </div>
    
    <div id="footer">
        <p>from Hilkya Fr. Linggar</p>
    </div>
    
    <script>
        var berandaLink = document.getElementById("berandaLink");
        var responseDiv = document.getElementById("response");
        var yesButton = document.getElementById("yesButton");
        var noButton = document.getElementById("noButton");
        var result = document.getElementById("result");
        
        function getRandomInsult() {
            var insults = ["HUH?", "ANJ?", "oh", "mana boleh kek gt", "hm", "wkwkwkwk okey"];
            return insults[Math.floor(Math.random() * insults.length)];
        }
        
        berandaLink.addEventListener("click", function() {
            berandaLink.style.display = "none";
            responseDiv.style.display = "block";
            fadeIn(yesButton); // Memulai animasi fadeIn pada tombol Ya
            fadeIn(noButton); // Memulai animasi fadeIn pada tombol Tidak
        });
        
        yesButton.addEventListener("click", function() {
            result.textContent = "hehehehe, i knew it. i love u too ling. I LOVE U MOST";
            result.style.display = "block";
            fadeIn(result); // Memulai animasi fadeIn pada hasil jawaban
        });
        
        noButton.addEventListener("click", function() {
            result.textContent = getRandomInsult();
            result.style.display = "block";
            noButton.style.animation = "shake 1s"; // Menambahkan animasi getar pada tombol Tidak
            setTimeout(function() {
                noButton.style.animation = "";
            }, 500); // Menghapus animasi getar setelah 0.5 detik
            fadeIn(result); // Memulai animasi fadeIn pada hasil jawaban
        });
        
        function fadeIn(element) {
            var op = 0.1;  // Opasitas awal
            element.style.display = "block"; // Menampilkan elemen sebelum animasi dimulai
            var timer = setInterval(function () {
                if (op >= 1){
                    clearInterval(timer); // Menghentikan interval animasi ketika opasitas mencapai 1
                }
                element.style.opacity = op;
                op += 0.1;  // Menambah opasitas sedikit demi sedikit
            }, 100); // Interval animasi 100ms (0.1 detik)
        }
    </script>
</body>
</html>
