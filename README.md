<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Hani AI - الذكاء الاصطناعي الأسطوري</title>
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;800;900&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #00f2fe;
      --secondary: #4facfe;
      --accent: #ff007f;
      --bg: #0b0c10;
      --card-bg: rgba(255, 255, 255, 0.05);
      --text: #ffffff;
      --text-muted: #8e9aaf;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Cairo', sans-serif;
    }

    body {
      background-color: var(--bg);
      color: var(--text);
      overflow-x: hidden;
      line-height: 1.6;
    }

    /* الخلفية والتوهج */
    .glow-bg {
      position: fixed;
      top: -20%;
      left: 50%;
      transform: translateX(-50%);
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, rgba(0, 242, 254, 0.15) 0%, rgba(255, 0, 127, 0.08) 50%, transparent 70%);
      filter: blur(80px);
      z-index: -1;
    }

    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 25px 8%;
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(255, 255, 255, 0.08);
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .logo {
      font-size: 1.8rem;
      font-weight: 900;
      background: linear-gradient(45deg, var(--primary), var(--accent));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      letter-spacing: 1px;
    }

    .nav-btn {
      background: linear-gradient(45deg, var(--secondary), var(--accent));
      border: none;
      padding: 10px 24px;
      border-radius: 30px;
      color: white;
      font-weight: 700;
      cursor: pointer;
      box-shadow: 0 4px 15px rgba(255, 0, 127, 0.3);
      transition: 0.3s;
    }

    .nav-btn:hover {
      transform: scale(1.05);
      box-shadow: 0 6px 20px rgba(0, 242, 254, 0.5);
    }

    /* قسم الهيرو */
    .hero {
      text-align: center;
      padding: 90px 20px 40px;
      max-width: 900px;
      margin: auto;
    }

    .hero .badge {
      display: inline-block;
      padding: 6px 16px;
      background: rgba(0, 242, 254, 0.1);
      border: 1px solid var(--primary);
      border-radius: 50px;
      color: var(--primary);
      font-size: 0.9rem;
      margin-bottom: 20px;
    }

    .hero h1 {
      font-size: 3.5rem;
      font-weight: 900;
      margin-bottom: 20px;
      line-height: 1.2;
    }

    .hero h1 span {
      background: linear-gradient(90deg, #00f2fe, #ff007f);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero p {
      font-size: 1.2rem;
      color: var(--text-muted);
      margin-bottom: 40px;
    }

    /* الشات التجريبي التفاعلي */
    .chat-box {
      background: var(--card-bg);
      border: 1px solid rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(15px);
      border-radius: 20px;
      max-width: 700px;
      margin: 0 auto 60px;
      overflow: hidden;
      box-shadow: 0 20px 40px rgba(0,0,0,0.5);
    }

    .chat-header {
      background: rgba(255, 255, 255, 0.03);
      padding: 15px 20px;
      display: flex;
      align-items: center;
      gap: 10px;
      border-bottom: 1px solid rgba(255, 255, 255, 0.05);
      font-weight: 700;
    }

    .status-dot {
      width: 10px;
      height: 10px;
      background: #00ff66;
      border-radius: 50%;
      box-shadow: 0 0 8px #00ff66;
    }

    .chat-content {
      padding: 20px;
      display: flex;
      flex-direction: column;
      gap: 15px;
      height: 220px;
      overflow-y: auto;
    }

    .msg {
      padding: 12px 18px;
      border-radius: 15px;
      font-size: 0.95rem;
      max-width: 80%;
    }

    .msg.bot {
      background: rgba(0, 242, 254, 0.1);
      border: 1px solid rgba(0, 242, 254, 0.2);
      align-self: flex-start;
    }

    .msg.user {
      background: linear-gradient(45deg, var(--secondary), var(--accent));
      align-self: flex-end;
    }

    .chat-input-bar {
      display: flex;
      padding: 12px;
      background: rgba(0,0,0,0.3);
      border-top: 1px solid rgba(255, 255, 255, 0.05);
      gap: 10px;
    }

    .chat-input-bar input {
      flex: 1;
      background: transparent;
      border: none;
      outline: none;
      color: white;
      font-size: 1rem;
      padding: 0 10px;
    }

    .chat-input-bar button {
      background: var(--primary);
      border: none;
      padding: 10px 22px;
      border-radius: 10px;
      font-weight: bold;
      cursor: pointer;
      transition: 0.2s;
    }

    .chat-input-bar button:hover {
      background: #fff;
    }

    /* بطاقات المميزات */
    .features {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 25px;
      max-width: 1100px;
      margin: 0 auto 100px;
      padding: 0 20px;
    }

    .card {
      background: var(--card-bg);
      border: 1px solid rgba(255, 255, 255, 0.07);
      padding: 30px;
      border-radius: 20px;
      transition: 0.3s;
      text-align: right;
    }

    .card:hover {
      transform: translateY(-8px);
      border-color: var(--primary);
      box-shadow: 0 10px 30px rgba(0, 242, 254, 0.15);
    }

    .card-icon {
      font-size: 2.5rem;
      margin-bottom: 15px;
    }

    .card h3 {
      font-size: 1.3rem;
      margin-bottom: 10px;
      color: #fff;
    }

    .card p {
      color: var(--text-muted);
      font-size: 0.95rem;
    }

    footer {
      text-align: center;
      padding: 30px;
      border-top: 1px solid rgba(255, 255, 255, 0.05);
      color: var(--text-muted);
    }
  </style>
</head>
<body>

  <div class="glow-bg"></div>

  <header>
    <div class="logo">⚡ Hani AI</div>
    <button class="nav-btn" onclick="focusChat()">جربني الآن</button>
  </header>

  <main>
    <section class="hero">
      <span class="badge">🔥 أقوى وأذكى نموذج ذكاء اصطناعي</span>
      <h1>تخطى كل الحدود مع قوة <br><span>Hani AI الأسطوري</span></h1>
      <p>توليد صور 4K، برمجة أكواد خارقة، وحلول فورية لكل أفكارك في ثوانٍ معدودة.</p>
    </section>

    <!-- شات تفاعلي لتجربة الموقع -->
    <section class="chat-box">
      <div class="chat-header">
        <div class="status-dot"></div>
        <span>محادثة حية مع Hani AI</span>
      </div>
      <div class="chat-content" id="chatContent">
        <div class="msg bot">مرحباً بك يا أسطورة! أنا Hani AI، اكتب لي أي شيء وأنا أنفذه لك فوراً! ⚡</div>
      </div>
      <div class="chat-input-bar">
        <input type="text" id="userInput" placeholder="اكتب سؤالك أو فكرتك هنا..." onkeypress="handleKey(event)">
        <button onclick="sendMsg()">إرسال</button>
      </div>
    </section>

    <!-- بطاقات المميزات -->
    <section class="features">
      <div class="card">
        <div class="card-icon">🎨</div>
        <h3>توليد صور وإبداع</h3>
        <p>تخيل أي مشهد وسأقوم بصياغة أفضل برومبتات واقعية وسينمائية لإنتاج صور خرافية.</p>
      </div>

      <div class="card">
        <div class="card-icon">💻</div>
        <h3>برمجة وتطوير فوري</h3>
        <p>كتابة مواقع وتطبيقات وحل أصعب الأخطاء البرمجية بكل اللغات بسرعة البرق.</p>
      </div>

      <div class="card">
        <div class="card-icon">⚡</div>
        <h3>سرعة فائقة وذكاء غير محدود</h3>
        <p>إجابات دقيقة، كتابة مقالات، تلخيص، وتفكير استراتيجي يفهم احتياجاتك بذكاء خارق.</p>
      </div>
    </section>
  </main>

  <footer>
    <p>تم التصميم والتطوير بواسطة <strong>Hani AI</strong> © 2026. جميع الحقوق محفوظة للأسطورة.</p>
  </footer>

  <script>
    const chatContent = document.getElementById('chatContent');
    const userInput = document.getElementById('userInput');

    function focusChat() {
      userInput.focus();
    }

    function handleKey(e) {
      if (e.key === 'Enter') sendMsg();
    }

    function sendMsg() {
      const text = userInput.value.trim();
      if (!text) return;

      // إضافة رسالة المستخدم
      appendMsg(text, 'user');
      userInput.value = '';

      // رد Hani AI التلقائي
      setTimeout(() => {
        const replies = [
          `طلبك الأسطوري "${text}" قيد التنفيذ بأقصى سرعة! ⚡`,
          `يا ساتر على الفكرة الخرافية! تم تحليل "${text}" وجاهز أساعدك! 🚀`,
          `Hani AI يحييك! بخصوص "${text}"، تقدر تعتبر المهمة تمت بنجاح وبأعلى جودة! 🔥`
        ];
        const randomReply = replies[Math.floor(Math.random() * replies.length)];
        appendMsg(randomReply, 'bot');
      }, 500);
    }

    function appendMsg(text, sender) {
      const msgDiv = document.createElement('div');
      msgDiv.className = `msg ${sender}`;
      msgDiv.innerText = text;
      chatContent.appendChild(msgDiv);
      chatContent.scrollTop = chatContent.scrollHeight;
    }
  </script>

</body>
</html>