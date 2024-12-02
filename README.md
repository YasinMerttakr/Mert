<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stok Takip Uygulaması</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }
        .container {
            width: 80%;
            margin: 20px auto;
            padding: 20px;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            text-align: center;
            color: #333;
        }
        input, button {
            padding: 10px;
            margin: 10px;
            width: 100%;
            box-sizing: border-box;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        table, th, td {
            border: 1px solid #ddd;
        }
        th, td {
            padding: 12px;
            text-align: left;
        }
        th {
            background-color: #f4f4f4;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Stok Takip Uygulaması</h1>
    <a href="#" id="openApp" style="color: blue; text-decoration: underline; display: block; text-align: center; margin-bottom: 20px;">Uygulamayı Açmak İçin Tıklayın</a>

    <div id="app" style="display: none;">
        <h2>Stok Girişi</h2>
        <input type="text" id="productName" placeholder="Ürün Adı">
        <input type="number" id="productQuantity" placeholder="Ürün Miktarı" min="1">
        <button onclick="addProduct()">Ürün Ekle</button>

        <h2>Stok Listesi</h2>
        <table id="productTable">
            <thead>
                <tr>
                    <th>Ürün Adı</th>
                    <th>Ürün Miktarı</th>
                </tr>
            </thead>
            <tbody></tbody>
        </table>
    </div>
</div>

<script>
    // Sayfa yüklendiğinde uygulamayı açan fonksiyon
    document.getElementById("openApp").addEventListener("click", function() {
        document.getElementById("app").style.display = "block";
        document.getElementById("openApp").style.display = "none";
    });

    // Ürün ekleme fonksiyonu
    function addProduct() {
        var productName = document.getElementById("productName").value;
        var productQuantity = document.getElementById("productQuantity").value;

        if (productName === "" || productQuantity === "") {
            alert("Lütfen ürün adı ve miktarını girin.");
            return;
        }

        // Yeni satır ekle
        var table = document.getElementById("productTable").getElementsByTagName('tbody')[0];
        var newRow = table.insertRow();

        var cell1 = newRow.insertCell(0);
        var cell2 = newRow.insertCell(1);

        cell1.textContent = productName;
        cell2.textContent = productQuantity;

        // Formu temizle
        document.getElementById("productName").value = "";
        document.getElementById("productQuantity").value = "";
    }
</script>

</body>
</html>
