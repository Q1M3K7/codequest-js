# codequest-js
 “JavaScript öğrenme oyunu”
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>CodeQuest: JS Macerası</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="menu">
    <h1>🎮 CodeQuest</h1>
    <p>JavaScript Adası'na hoş geldin! Bölümlerden birini seç:</p>
    <ul>
      <li><a href="level1_variables.html">1. Ormanın Kalbi (Değişkenler)</a></li>
      <li><a href="level2_conditions.html">2. Kristal Nehir (Koşullar)</a></li>
      <li><a href="level3_loops.html">3. Sonsuz Mağara (Döngüler)</a></li>
    </ul>
  </div>
</body>
</html>
body {
  background: #20232a;
  color: #ddd;
  font-family: 'Segoe UI', sans-serif;
  margin: 0;
  padding: 0;
}
.menu {
  padding: 40px;
  text-align: center;
}
.menu a {
  color: #61dafb;
  text-decoration: none;
  font-size: 1.2em;
}
.menu ul {
  list-style: none;
  padding: 0;
}
.menu li {
  margin: 15px 0;
}
textarea {
  width: 100%;
  height: 120px;
  background: #000;
  color: #0f0;
  padding: 10px;
  font-family: monospace;
}
button {
  padding: 10px 18px;
  background: #61dafb;
  border: none;
  cursor: pointer;
  font-size: 1em;
}
#output {
  margin-top: 10px;
  padding: 10px;
  background: #111;
  white-space: pre-wrap;
}
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>Ormanın Kalbi</title>
<link rel="stylesheet" href="style.css">
</head>
<body>
  <h2>🌲 Ormanın Kalbi</h2>
  <p><strong>Echo:</strong> “let ve const ile su ve ateşi tanımlamalısın.”</p>
  <textarea id="code">// Kodunu buraya yaz
let su = "temiz";
const ates = "yakildi";
document.getElementById("output").textContent = "Kamp hazır!";</textarea>
  <button onclick="calistir()">▶️ Çalıştır</button>
  <div id="output"></div>

  <script>
    function calistir(){
      const code = document.getElementById("code").value;
      const out = document.getElementById("output");
      try {
        new Function(code)();
        if(code.includes("let") && code.includes("const")){
          out.textContent = "✅ Kamp hazır!";
        } else {
          out.textContent = "⚠️ let ve const kullanmalısın.";
        }
      } catch(e){
        out.textContent = "❌ HATA: " + e.message;
      }
    }
  </script>
</body>
</html>
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>Kristal Nehir</title>
<link rel="stylesheet" href="style.css">
</head>
<body>
  <h2>🌊 Kristal Nehir</h2>
  <p><strong>Echo:</strong> “renk değişkenini kontrol et. Eğer 'yeşil' ise geçiş izni ver.”</p>
  <textarea id="code">// Kodunu buraya yaz
let renk = "kırmızı";
if (renk === "yeşil") {
  console.log("Geçiş izni verildi");
} else {
  console.log("Tehlikeli geçit");
}</textarea>
  <button onclick="calistir()">▶️ Çalıştır</button>
  <div id="output"></div>

  <script>
    function calistir(){
      const code = document.getElementById("code").value;
      const out = document.getElementById("output");
      try {
        const log = [];
        const console={log:(m)=>log.push(m)};
        new Function("console", code)(console);
        if(log.includes("Geçiş izni verildi")||log.includes("Tehlikeli geçit")){
          out.textContent = "✅ " + log.join("\\n");
        } else {
          out.textContent = "⚠️ `if/else` kontrolü eksik.";
        }
      } catch(e){
        out.textContent = "❌ HATA: "+e.message;
      }
    }
  </script>
</body>
</html>
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>Sonsuz Mağara</title>
<link rel="stylesheet" href="style.css">
</head>
<body>
  <h2>⛏️ Sonsuz Mağara</h2>
  <p><strong>Echo:</strong> “for veya while ile 5 kayayı kır ve 'Kaya kırıldı!' yazdır.”</p>
  <textarea id="code">// Kodunu buraya yaz
for (let i = 0; i < 5; i++) {
  console.log("Kaya kırıldı!");
}</textarea>
  <button onclick="calistir()">▶️ Çalıştır</button>
  <div id="output"></div>

  <script>
    function calistir(){
      const code = document.getElementById("code").value;
      const out = document.getElementById("output");
      try {
        const log = [];
        const console={log:(m)=>log.push(m)};
        new Function("console", code)(console);
        const count = log.filter(m=>"Kaya kırıldı!").length;
        if(count===5){
          out.textContent = "✅ Tüm kayalar kırıldı!";
        } else {
          out.textContent = "⚠️ 5 defa 'Kaya kırıldı!' yazmalısın.";
        }
      } catch(e){
        out.textContent = "❌ HATA: "+e.message;
      }
    }
  </script>
</body>
</html>
# CodeQuest - JavaScript Adasında Hayatta Kal

## Kurulum
1. Bu klasörü bilgisayarına indir.
2. Tüm dosyalar aynı klasörde olsun.
3. `index.html` dosyasına çift tıkla, tarayıcıda aç.

## Oynama
- Menüden istediğin bölümü seç.
- Karşına çıkan kod kutusuna JavaScript kodunu yaz.
- "Çalıştır" butonuna bas ve sonucu anında gör.

## Bölümler
1. Ormanın Kalbi: Değişkenler (`let`, `const`)
2. Kristal Nehir: Koşullu İfadeler (`if / else`)
3. Sonsuz Mağara: Döngüler (`for`, `while`)

## İlerleyen aşamalarda yeni bölümler eklenecektir.
