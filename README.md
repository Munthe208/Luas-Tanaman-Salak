<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Data Produksi Salak</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
        }
        table, th, td {
            border: 1px solid black;
        }
        th, td {
            padding: 10px;
            text-align: center;
        }
    </style>
</head>
<body>
    <h1>Tabel Pengisian Data Produksi Salak</h1>

    <table>
        <thead>
            <tr>
                <th>No</th>
                <th>Kecamatan</th>
                <th>Luas Lahan (Ha)</th>
                <th>Jumlah Batang (Otomatis)</th>
                <th>Produksi (Ton) (Otomatis)</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>Kec. Psp. Batunadua</td>
                <td><input type="number" id="luas_batunadua" name="luas_batunadua" step="0.01" oninput="hitungProduksi('batunadua')"></td>
                <td><span id="batang_batunadua">0</span></td>
                <td><span id="produksi_batunadua">0</span></td>
            </tr>
            <tr>
                <td>2</td>
                <td>Kec. Psp. Angkola Julu</td>
                <td><input type="number" id="luas_angkola" name="luas_angkola" step="0.01" oninput="hitungProduksi('angkola')"></td>
                <td><span id="batang_angkola">0</span></td>
                <td><span id="produksi_angkola">0</span></td>
            </tr>
            <tr>
                <td>3</td>
                <td>Kec. Psp. Hutaimbaru</td>
                <td><input type="number" id="luas_hutaimbaru" name="luas_hutaimbaru" step="0.01" oninput="hitungProduksi('hutaimbaru')"></td>
                <td><span id="batang_hutaimbaru">0</span></td>
                <td><span id="produksi_hutaimbaru">0</span></td>
            </tr>
            <tr>
                <td>4</td>
                <td>Kec. Psp. Utara</td>
                <td><input type="number" id="luas_utara" name="luas_utara" step="0.01" oninput="hitungProduksi('utara')"></td>
                <td><span id="batang_utara">0</span></td>
                <td><span id="produksi_utara">0</span></td>
            </tr>
            <tr>
                <td>5</td>
                <td>Kec. Psp. Selatan</td>
                <td><input type="number" id="luas_selatan" name="luas_selatan" step="0.01" oninput="hitungProduksi('selatan')"></td>
                <td><span id="batang_selatan">0</span></td>
                <td><span id="produksi_selatan">0</span></td>
            </tr>
            <tr>
                <td>6</td>
                <td>Kec. Psp. Tenggara</td>
                <td><input type="number" id="luas_tenggara" name="luas_tenggara" step="0.01" oninput="hitungProduksi('tenggara')"></td>
                <td><span id="batang_tenggara">0</span></td>
                <td><span id="produksi_tenggara">0</span></td>
            </tr>
        </tbody>
    </table>

    <script>
        // Fungsi untuk menghitung jumlah batang dan produksi berdasarkan luas lahan
        function hitungProduksi(kecamatan) {
            const luasLahan = parseFloat(document.getElementById('luas_' + kecamatan).value) || 0;

            // Setiap 1 hektar ada 800 batang
            const jumlahBatang = luasLahan * 800;

            // Setiap batang menghasilkan 40 kg, jadi produksi total dalam ton adalah:
            const produksi = (jumlahBatang * 40) / 1000; // dikonversi ke ton

            // Update tampilan hasil di tabel
            document.getElementById('batang_' + kecamatan).textContent = jumlahBatang.toFixed(0); // Jumlah batang
            document.getElementById('produksi_' + kecamatan).textContent = produksi.toFixed(2); // Produksi dalam ton
        }
    </script>
</body>
</html>
