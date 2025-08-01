# Luckylocoz2
Coinlluckylocoz
<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>تعدين العملات الرقمية</title>
  <style>
    body { font-family: Tahoma, Arial; background: #222; color: #fff; text-align: center; padding: 40px;}
    .container { background: #333; border-radius: 12px; display: inline-block; padding: 30px 50px; }
    h1 { color: #f9d923; }
    .status { margin: 20px 0; font-size: 1.2em;}
    .hashrate { font-size: 2em; color: #14ffec;}
    button { padding: 12px 28px; border: none; border-radius: 6px; background: #f9d923; color: #222; font-size: 1em; cursor: pointer;}
    button:active { background: #f1c40f;}
  </style>
</head>
<body>
  <div class="container">
    <h1>منصة تعدين العملات الرقمية</h1>
    <div class="status" id="status">الحالة: متوقف</div>
    <div>سرعة الهاش الحالية:</div>
    <div class="hashrate" id="hashrate">0 H/s</div>
    <button id="toggleBtn">ابدأ التعدين</button>
  </div>
  <script>
    let mining = false;
    let interval;
    document.getElementById('toggleBtn').onclick = function() {
      mining = !mining;
      document.getElementById('status').textContent = 'الحالة: ' + (mining ? 'يعمل' : 'متوقف');
      this.textContent = mining ? 'أوقف التعدين' : 'ابدأ التعدين';
      if (mining) {
        interval = setInterval(() => {
          // محاكاة سرعة الهاش فقط
          let fakeHashrate = Math.floor(Math.random() * 1000) + 100;
          document.getElementById('hashrate').textContent = fakeHashrate + ' H/s';
        }, 1000);
      } else {
        clearInterval(interval);
        document.getElementById('hashrate').textContent = '0 H/s';
      }
    }
  </script>
</body>
</html>
