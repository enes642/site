<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aron Roleplay</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: url('https://i.postimg.cc/k5RnC80F/resim-2025-01-12-145158422.png') no-repeat center center fixed;
            background-size: 56%;
            background-position: center center;
            margin: 0;
            padding: 0;
        }

        header {
            background-color: rgba(0, 0, 0, 0.6);
            color: white;
            padding: 10px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        header h1 {
            margin: 0;
        }

        nav a {
            color: white;
            text-decoration: none;
            margin-left: 20px;
            font-size: 18px;
        }

        nav a:hover {
            color: #4CAF50;
        }

        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
        }

        .form-container {
            background-color: rgba(0, 0, 0, 0.7);
            padding: 30px;
            border-radius: 8px;
            width: 350px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
        }

        h2 {
            text-align: center;
            color: white;
            font-size: 24px;
        }

        label {
            font-weight: bold;
            display: block;
            margin-top: 10px;
            color: #fff;
        }

        input[type="text"], input[type="email"], input[type="number"] {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border: none;
            border-radius: 4px;
            margin-bottom: 20px;
        }

        input[type="submit"] {
            width: 100%;
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 18px;
        }

        input[type="submit"]:hover {
            background-color: #45a049;
        }

        .total-amount {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
            text-align: center;
            color: #fff;
        }

        .ticket-message {
            margin-top: 20px;
            font-size: 16px;
            color: #ffcc00;
            text-align: center;
            font-weight: bold;
            display: none;
        }

        .discord-link {
            text-align: center;
            margin-top: 20px;
            width: 100%;
        }

        .discord-link a {
            color: #7289DA;
            font-size: 56px;
            text-decoration: none;
            display: inline-block;
            text-align: center;
        }

        .discord-link a:hover {
            text-decoration: underline;
        }

        .discord-header {
            font-size: 30px;
            color: #fff;
            text-align: center;
            margin: 20px 0;
        }

        .discord-logo {
            display: inline-block;
            width: 30px;
            height: 30px;
            background-image: url('https://upload.wikimedia.org/wikipedia/commons/7/7c/Discord_logo.svg');
            background-size: cover;
            margin-right: 10px;
        }

        .server-info {
            background-color: rgba(0, 0, 0, 0.7);
            padding: 20px;
            margin-top: 20px;
            width: 80%;
            color: white;
            text-align: center;
            border-radius: 8px;
        }

        .server-info p {
            font-size: 20px;
            margin: 0;
        }

    </style>
</head>
<body>

    <header>
        <h1>Aron Roleplay</h1>
        <nav>
            <a href="#" id="home">Anasayfa</a>
            <a href="#" id="balance2">Bakiye Yükleme</a>
            <a href="#" id="discord-link">
                <span class="discord-logo"></span>Discordumuz
            </a>
            <a href="#" id="about">Hakkımızda</a>
        </nav>
    </header>

    <div class="container">
        <div id="home-content">
            <h2>Hoşgeldiniz! Aron Roleplay'e hoşgeldiniz. Aşağıdaki menüden seçim yapabilirsiniz.</h2>
        </div>

        <!-- Bakiye Yükleme Formu -->
        <div id="form-container" class="form-container">
            <h2>Bakiye Yüklemek İçin Aşağıdakileri Düzgünce Giriniz</h2>
            <form id="payment-form">
                <label for="username">Kullanıcı Adı:</label>
                <input type="text" id="username" name="username" required>

                <label for="balance">Yüklenecek Bakiye:</label>
                <input type="number" id="balance" name="balance" required>

                <label for="email">Email Adresi:</label>
                <input type="email" id="email" name="email" required>

                <input type="submit" value="Gönder">
            </form>

            <div id="total-amount" class="total-amount"></div>
            <div id="ticket-message" class="ticket-message">
                Lütfen Discord adresimizden ticket açınız, destek ekibimiz sizinle ilgilenecektir.
            </div>
        </div>

        <!-- Discord ve Hakkımızda -->
        <div id="discord-container" class="discord-link" style="display: none;">
            <div class="discord-header">Discord Sunucumuza Katılmak İçin Tıklayın:</div>
            <a href="https://discord.gg/AronMta" target="_blank">discord.gg/AronMta</a>
        </div>

        <div id="about-section" class="server-info" style="display: none;">
            <p>Aron Roleplay MTA platformunda hizmet veren bir sunucudur. Sunucumuzda Sesli/Text Roller dönmektedir, ve oyuncularımızın kaliteli rol yapmasını sağlamaktayız.</p>
            <p>Sunucumuz Sesli/Text Hard Türkiye İstanbul'da ve Global konsepti ile aktif.</p>
        </div>
    </div>

    <script>
        const balanceLink = document.getElementById('balance2');
        const homeContent = document.getElementById('home-content');
        const formContainer = document.getElementById('form-container');
        const discordLink = document.getElementById('discord-container');
        const aboutSection = document.getElementById('about-section');

        balanceLink.addEventListener('click', function() {
            homeContent.style.display = 'none';
            discordLink.style.display = 'none';
            aboutSection.style.display = 'none';
            formContainer.style.display = 'block';
        });

        document.getElementById('about').addEventListener('click', function() {
            homeContent.style.display = 'none';
            formContainer.style.display = 'none';
            discordLink.style.display = 'none';
            aboutSection.style.display = 'block';
        });

        document.getElementById('discord-link').addEventListener('click', function() {
            homeContent.style.display = 'none';
            formContainer.style.display = 'none';
            discordLink.style.display = 'block';
            aboutSection.style.display = 'none';
        });

        const paymentForm = document.getElementById('payment-form');
        const totalAmountDiv = document.getElementById('total-amount');
        const ticketMessage = document.getElementById('ticket-message');

        paymentForm.addEventListener('submit', function(event) {
            event.preventDefault();

            const balance = document.getElementById('balance').value;

            if (balance) {
                totalAmountDiv.textContent = 'Ödenecek Toplam Tutar: ' + balance + ' TL';
                ticketMessage.style.display = 'block'; // Ticket mesajını göster
            } else {
                totalAmountDiv.textContent = 'Bakiye girmediniz!';
                ticketMessage.style.display = 'none'; // Mesajı gizle
            }
        });

        window.onload = function() {
            homeContent.style.display = 'block';
            formContainer.style.display = 'none';
            discordLink.style.display = 'none';
            aboutSection.style.display = 'none';
        };
    </script>

</body>
</html>
