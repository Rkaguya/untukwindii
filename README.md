<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Permintaan Maaf  💖</title>
  <style>
    body {
      margin: 0;
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(135deg, #ffe6e6, #fff0f5, #fce1f0);
      overflow-x: hidden;
      color: #4a4a4a;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
    }
    h1 {
      color: #e91e63;
      font-size: 2.5em;
      margin-bottom: 0.2em;
    }
    p.subtitle {
      color: #888;
      margin-top: 0;
      margin-bottom: 1.5em;
    }
    .card {
      background: rgba(255,255,255,0.8);
      border-radius: 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.1);
      max-width: 600px;
      padding: 2em;
      position: relative;
      z-index: 2;
      backdrop-filter: blur(10px);
    }
    textarea, input {
      width: 100%;
      border: 2px solid #ffc0cb;
      border-radius: 10px;
      padding: 10px;
      margin-top: 10px;
      font-size: 1em;
      resize: none;
      font-family: 'Poppins', sans-serif;
    }
    button {
      background: #e91e63;
      color: white;
      border: none;
      padding: 10px 18px;
      border-radius: 25px;
      cursor: pointer;
      font-weight: bold;
      transition: all 0.3s ease;
      margin: 5px;
    }
    button:hover {
      background: #ff4081;
      transform: scale(1.05);
    }
    .hearts {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      overflow: hidden;
      z-index: 1;
    }
    .heart {
      position: absolute;
      color: #ff7aa8;
      font-size: 24px;
      animation: fall 6s linear infinite;
      opacity: 0.8;
    }
    @keyframes fall {
      0% { transform: translateY(-10%) rotate(0deg); opacity: 1; }
      100% { transform: translateY(110vh) rotate(720deg); opacity: 0; }
    }
    .message {
      margin-top: 1.5em;
      font-size: 1.1em;
      color: #444;
      white-space: pre-wrap;
      min-height: 100px;
      animation: fadeIn 1s ease-in-out;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
    footer {
      margin-top: 2em;
      font-size: 0.8em;
      color: #999;
    }
  </style>
</head>
<body>

  <div class="hearts"></div>

  <div class="card">
    <h1>💌Surat Permintaan Maaf 💌</h1>
    <p class="subtitle">Untuk seseorang yang sangat berharga Windi Widia Ningsih</p>

    <input type="text" id="name" placeholder="Nama penerima..." value="Windi Widia Ningsih">
    <textarea id="customMsg" rows="5">Teruntuk sayangku Windi maaf yaa sayang kemarin udh ngecewain kamu, sekarang aku sadar kamu sayang aku jadi wajar aja kamu kaya gitu. maaf ya kemarin ninggalin kamu pulang tanpa nganteerin kamu dlu, Maka dari itu aku mau minta maaf dengan sangat tulus lewat website ini maafin aku ya sayang. Yang bertandatangan di bawah ini Rifal Aditia</textarea>

    <div>
      <button id="showMsgBtn">Tampilkan Pesan</button>
      <button id="addHeartBtn">Tambah ❤️</button>
      <button id="resetBtn">Reset Pesan</button>
    </div>

    <div id="typedMessage" class="message"></div>

    <div style="margin-top: 1em;">
      <p style="font-size:0.9em; color:#777;">🎵 Musik Latar:</p>
      <audio controls loop>
        <source src="https://close-teal-27mlsqcjcn.edgeone.app/nadhif-basalamah-bergema-sampai-selamanya-official-lyric-video-128-ytshorts.savetube.me.mp3" type="">
      </audio>
    </div>
  </div>

  <footer> Dibuat dengan cinta — Ubah teks & lagu sesuai hatimu </footer>

  <script>
    // Fungsi mengetik perlahan
    function typeText(element, text, speed = 40) {
      element.textContent = '';
      let i = 0;
      const interval = setInterval(() => {
        element.textContent += text.charAt(i);
        i++;
        if (i > text.length) clearInterval(interval);
      }, speed);
    }

    const showMsgBtn = document.getElementById('showMsgBtn');
    const addHeartBtn = document.getElementById('addHeartBtn');
    const resetBtn = document.getElementById('resetBtn');
    const msgEl = document.getElementById('typedMessage');
    const nameEl = document.getElementById('name');
    const customMsgEl = document.getElementById('customMsg');

    showMsgBtn.addEventListener('click', () => {
      const name = nameEl.value || 'Sayangku';
      const msg = customMsgEl.value;
      const fullMsg = `Dear ${name},\n\n${msg}\n\nAku berharap kamu mau memaafkanku. ATAPU ❤️`;
      typeText(msgEl, fullMsg);
    });

    addHeartBtn.addEventListener('click', () => {
      customMsgEl.value += ' ❤️';
    });

    resetBtn.addEventListener('click', () => {
      nameEl.value = 'Sayangku';
      customMsgEl.value = 'ATAPU ❤️ ';
      msgEl.textContent = '';
    });

    // Animasi hati berjatuhan
    const heartsContainer = document.querySelector('.hearts');
    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
      heart.textContent = '💖';
      heart.style.animationDuration = (4 + Math.random() * 4) + 's';
      heartsContainer.appendChild(heart);
      setTimeout(() => heart.remove(), 8000);
    }
    setInterval(createHeart, 400);
  </script>

</body>
</html>
