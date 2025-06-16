<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tıklama Oyunu</title>
  <style>
    body { background: #f7f7f7; font-family: Arial, sans-serif; text-align: center; padding: 20px; }
    #oyun { background: #fff; padding: 20px; border-radius: 10px; box-shadow: 0 0 10px rgba(0,0,0,0.1); max-width: 400px; margin:auto; }
    #tikla { font-size: 2rem; padding: 15px 30px; margin:10px; }
    #dukkan { font-size: 1rem; padding:8px 16px; margin:10px; }
    .info { font-size:1.2rem; margin:10px; }
  </style>
</head>
<body>
  <div id="oyun">
    <h1>Tıklama Oyunu</h1>
    <div class="info" id="puan">Puan: 0</div>
    <div class="info" id="gold">Gold: 0</div>
    <div class="info" id="guc">Güç: 1</div>
    <button id="tikla">TIKLA!</button><br>
    <button id="dukkan">Dükkan (10 Gold)</button>
  </div>

  <script>
    let puan = 0, gold = 0, guc = 1;
    const puanEl = document.getElementById('puan');
    const goldEl = document.getElementById('gold');
    const gucEl = document.getElementById('guc');
    document.getElementById('tikla').onclick = () => {
      puan += guc;
      if (puan % 10 === 0) gold++;
      puanEl.textContent = 'Puan: ' + puan;
      goldEl.textContent = 'Gold: ' + gold;
    };
    document.getElementById('dukkan').onclick = () => {
      if (gold >= 10) {
        gold -= 10;
        guc++;
        goldEl.textContent = 'Gold: ' + gold;
        gucEl.textContent = 'Güç: ' + guc;
      } else {
        alert('Dükkan açmak için en az 10 Gold gerekiyor!');
      }
    };
  </script>
</body>
</html>
