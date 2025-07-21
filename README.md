# gaucher_dusun_formu.html
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Gaucher Düşün! Klinik Değerlendirme</title>
  <style>
    body { font-family: Arial; margin: 20px; background-color: #f9f9f9; }
    h2 { color: #2c3e50; }
    table { border-collapse: collapse; width: 100%; margin-bottom: 20px; }
    th, td { border: 1px solid #ccc; padding: 10px; }
    th { background-color: #e8e8e8; }
    .risk-high { color: red; font-weight: bold; }
    .risk-low { color: green; font-weight: bold; }
    button { padding: 10px 20px; background-color: #3498db; color: white; border: none; cursor: pointer; }
  </style>
</head>
<body>

  <h2>🧬 Gaucher Düşün! Klinik Değerlendirme Formu</h2>
  <form id="gaucherForm">
    <table>
      <tr><th>Kategori</th><th>Bulgu</th><th>Seç</th></tr>
      <tr><td>Hematolojik</td><td>Trombositopeni</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>Hematolojik</td><td>Anemi</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>Hematolojik</td><td>Splenomegali</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>İskelet</td><td>Kemik ağrısı</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>İskelet</td><td>Kemik krizi / AVN</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>İskelet</td><td>Erlenmeyer flask deformitesi</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>Gastrointestinal</td><td>Hepatomegali</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>Gastrointestinal</td><td>Büyüme geriliği</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>Gastrointestinal</td><td>Transaminaz yüksekliği</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>Nörolojik</td><td>Gelişimsel gerilik</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>Nörolojik</td><td>Epileptik nöbet</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>Nörolojik</td><td>Okülomotor disfonksiyon</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>Genetik</td><td>Ailede Gaucher öyküsü</td><td><input type="checkbox" name="bulgu"></td></tr>
      <tr><td>Genetik</td><td>Ashkenazi kökeni</td><td><input type="checkbox" name="bulgu"></td></tr>
    </table>
    <button type="button" onclick="hesapla()">Değerlendir</button>
  </form>

  <div id="sonuc" style="margin-top: 20px;"></div>

  <script>
    function hesapla() {
      let secilenler = document.querySelectorAll('input[name="bulgu"]:checked').length;
      let sonuc = document.getElementById("sonuc");
      let mesaj = "";

      if (secilenler >= 3) {
        mesaj = `<p>✅ <strong>${secilenler} bulgu</strong> seçildi. <span class="risk-high">Gaucher Düşün!</span><br>
        ➤ Lyso-Gb1 testi<br>➤ GBA enzim aktivitesi<br>➤ GBA genetik analizi önerilir.</p>`;
      } else {
        mesaj = `<p>🔍 <strong>${secilenler} bulgu</strong> seçildi. <span class="risk-low">Takip önerilir.</span></p>`;
      }

      sonuc.innerHTML = mesaj;
    }
  </script>

</body>
</html>
