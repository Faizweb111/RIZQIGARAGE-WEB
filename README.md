<!DOCTYPE html>
<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kedai Alat Ganti Kereta</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: black;
            color: white;
            margin: 0;
            padding: 0;
        }
        .header {
            background-color: red;
            padding: 20px;
            text-align: center;
            font-size: 24px;
            font-weight: bold;
        }
        .container {
            max-width: 900px;
            margin: auto;
            padding: 20px;
        }
        .menu, .search-results {
            display: none;
        }
        .item {
            border: 1px solid red;
            padding: 15px;
            margin: 10px 0;
            background-color: white;
            color: black;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        img {
            width: 150px;
            height: auto;
            border-radius: 8px;
        }
        button {
            background-color: red;
            color: white;
            border: none;
            padding: 10px 20px;
            margin: 10px;
            cursor: pointer;
            font-size: 16px;
            border-radius: 5px;
        }
        button:hover {
            background-color: darkred;
        }
        input {
            padding: 10px;
            width: 100%;
            margin: 10px 0;
            border: 1px solid red;
            border-radius: 5px;
        }
        .footer {
            background-color: red;
            padding: 10px;
            text-align: center;
            position: fixed;
            width: 100%;
            bottom: 0;
        }
    </style>
</head>
<body>
    <div class="header">Rizqi Garage</div>
    <div class="container">
        <button onclick="showHome()">Home</button>
        <button onclick="showMenu()">Menu</button>
        <input type="text" id="search" placeholder="Cari barang..." onkeyup="searchItem()">
        
        <div id="home">
            <p>Hubungi kami di WhatsApp: <a href="https://wa.me/60123456789" style="color: yellow;">+60123456789</a></p>

        </div>
       
        <div id="menu" class="menu">
            <div id="items">
                <div class="item" data-name="Tayar Michelin">
                   <img src="u.jpeg">
                    <p>Rim Kereta King 2.0- <b>RM350/pcs</b></p>
                </div>
                <div class="item" data-name="Bateri Kereta Amaron">
                    <img src="images.jpg">
                    <p>Cooler Kereta Alza- <b>RM80</b></p>
                </div>
                <div class="item" data-name="Lampu LED H4">
                   <img src="images (1).jpg">
                    <p>Stering drift - <b>RM100</b></p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">&copy; 2025 Kedai Alat Ganti Kereta</div>
    <script>
        function showHome() {
            document.getElementById('home').style.display = 'block';
            document.getElementById('menu').style.display = 'none';
        }
        function showMenu() {
            document.getElementById('home').style.display = 'none';
            document.getElementById('menu').style.display = 'block';
        }
        function searchItem() {
            let input = document.getElementById('search').value.toLowerCase();
            let items = document.querySelectorAll('.item');
            items.forEach(item => {
                let name = item.getAttribute('data-name').toLowerCase();
                item.style.display = name.includes(input) ? 'flex' : 'none';
            });
        }
    </script>
</body>
</html>
