# Olumlama-Sözleri
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Olumlama & Aşk Yazıları</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      background: #ffe6f0;
    }
    #text {
      font-size: 24px;
      font-weight: bold;
      margin: 30px;
      text-align: center;
      padding: 20px;
      border-radius: 10px;
      background-color: white;
      box-shadow: 0 0 15px rgba(0,0,0,0.1);
    }
    button {
      font-size: 18px;
      padding: 10px 20px;
      margin: 10px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    #startBtn { background-color: #ff66a3; color: white; }
    #stopBtn { background-color: #ffb3cc; color: white; }
  </style>
</head>
<body>

  <div id="text">Hazır mısın? 🎀</div>
  <button id="startBtn">Başlat</button>
  <button id="stopBtn">Durdur</button>

  <script>
    const texts = [
      "Seninle her şey mümkün.",
      "Aşk, birlikte büyümektir.",
      "Gözlerinde kayboluyorum.",
      "Kalbin kalbimde atıyor.",
      "Sen gülünce dünya duruyor.",
      "İyi ki varsın, iyi ki benimlesin.",
      "Sevgi, zamanla değil kalple ölçülür.",
      "Sensiz geçen zaman eksik.",
      "Gözlerin, içimdeki güneş.",
      "Sen benim en güzel tesadüfumsun.",
      "İçimi ısıtan tek şey, adın.",
      "Hayat seninle güzel.",
      "Sana her gün yeniden aşık oluyorum.",
      "Birlikte her şey daha anlamlı.",
      "Kalbim seni seçti.",
      "Senin yanında huzur buluyorum.",
      "Seninle her şey daha parlak.",
      "Sonsuzum sensin.",
      "Gülüşün cennetten çalıntı.",
      "Aşkın tanımı sensin.",
      "Kalbim senin ritminde atıyor.",
      "Sen geldin ve her şey tamamlandı.",
      "Rüyalarım bile seni özlüyor.",
      "Sen, günümün en güzel anısısın.",
      "Beraber yaşlanmak istiyorum.",
      "Sevdan içimde bir şiir.",
      "Adını duymak bile yetiyor.",
      "Seninle her an özel.",
      "Birlikte her engel aşılır.",
      "Yıldızlar bile sana özeniyor.",
      "Seni düşündüğümde bile yüzüm gülüyor."
    ];

    let interval;
    let currentIndex = 0;

    function shuffle(array) {
      let newArray = [...array];
      for (let i = newArray.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [newArray[i], newArray[j]] = [newArray[j], newArray[i]];
      }
      return newArray;
    }

    document.getElementById("startBtn").addEventListener("click", () => {
      clearInterval(interval);
      const pool = shuffle(texts); // Yeni karışım
      currentIndex = 0;
      interval = setInterval(() => {
        document.getElementById("text").textContent = pool[currentIndex % pool.length];
        currentIndex++;
      }, 100);
    });

    document.getElementById("stopBtn").addEventListener("click", () => {
      clearInterval(interval);
      // Mevcut ekranda duran yazı kalıyor
    });
  </script>

</body>
</html>
