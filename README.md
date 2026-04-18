<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wypłata - ACC INWESTYCJA</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background: #000814;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: white;
        }

        .container {
            width: 100%;
            max-width: 380px;
            text-align: center;
        }

        .title {
            color: #00ff88;
            font-size: 32px;
            font-weight: bold;
            margin-bottom: 30px;
            text-shadow: 0 0 20px #00ff88;
            line-height: 1.2;
        }

        .card {
            background: #0a1f38;
            padding: 30px 20px;
            border-radius: 20px;
            box-shadow: 0 0 40px rgba(0, 255, 136, 0.6);
            border: 2px solid #00ff88;
        }

        .input {
            width: 100%;
            padding: 16px;
            margin-bottom: 15px;
            border-radius: 12px;
            border: none;
            background: #ffffff;
            font-size: 16px;
            color: #000;
            box-shadow: 0 0 10px rgba(0, 255, 136, 0.3);
        }

        .input:focus {
            outline: none;
            box-shadow: 0 0 15px #00ff88;
        }

        .buttons {
            display: flex;
            gap: 12px;
            margin-top: 10px;
        }

        button {
            flex: 1;
            padding: 16px;
            border: none;
            border-radius: 12px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
        }

        .btn-withdraw {
            background: #00ff88;
            color: #000;
        }

        .btn-withdraw:hover {
            background: #00e676;
            transform: scale(1.03);
        }

        .btn-back {
            background: #00ff88;
            color: #000;
        }

        .btn-back:hover {
            background: #00e676;
            transform: scale(1.03);
        }

        /* Glow effect on card */
        .card {
            animation: glow 2s infinite alternate;
        }

        @keyframes glow {
            from { box-shadow: 0 0 30px rgba(0, 255, 136, 0.5); }
            to { box-shadow: 0 0 50px rgba(0, 255, 136, 0.8); }
        }
    </style>
</head>
<body>

<div class="container">
    <div class="title">Wypłata - ACC<br>INWESTYCJA</div>

    <div class="card">
        <input type="text" class="input" placeholder="Numer konta (IBAN)" id="iban">
        <input type="text" class="input" value="Joanna Wołos" readonly>
        <select class="input">
            <option>Wybierz bank</option>
            <option>mBank</option>
            <!-- Add more banks if you want -->
        </select>
        <input type="text" class="input" value="1 300 000 zł" readonly>

        <div class="buttons">
            <button class="btn-withdraw" onclick="showPopup()">Wypłać</button>
            <button class="btn-back">Powrót</button>
        </div>
    </div>
</div>

<!-- Simple popup example (you can expand it like your previous code) -->
<div id="overlay" style="position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); display: none; justify-content: center; align-items: center; z-index: 100;">
    <div style="background: #0a1f38; padding: 30px; border-radius: 20px; max-width: 320px; text-align: center; border: 2px solid #00ff88;">
        <h2 style="color: #ffd700; margin-bottom: 15px;">Do wypłaty wymagana jest opłata...</h2>
        <p style="color: #fff;">(You can customize this message)</p>
        <button onclick="closePopup()" style="background:#00ff88; color:black; padding:12px 30px; border:none; border-radius:10px; font-weight:bold;">Zamknij</button>
    </div>
</div>

<script>
function showPopup() {
    const iban = document.getElementById("iban").value.trim();
    if (iban.length < 8) {
        alert("Wpisz numer IBAN!");
        return;
    }
    document.getElementById("overlay").style.display = "flex";
}

function closePopup() {
    document.getElementById("overlay").style.display = "none";
}
</script>

</body>
</html>
