<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Harxz — Official Channel</title>
  <style>
    /* ===== RESET & BASE ===== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Courier New', 'Segoe UI', monospace;
      background: #1a1a1a;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
      overflow-x: hidden;
      image-rendering: pixelated;
    }

    /* ===== BACKGROUND MINECRAFT ===== */
    .bg-minecraft {
      position: fixed;
      inset: 0;
      z-index: 0;
      background: #2d2d2d;
      background-image:
        repeating-linear-gradient(0deg, rgba(60, 60, 60, 0.3) 0px, rgba(60, 60, 60, 0.3) 2px, transparent 2px, transparent 4px),
        repeating-linear-gradient(90deg, rgba(60, 60, 60, 0.3) 0px, rgba(60, 60, 60, 0.3) 2px, transparent 2px, transparent 4px);
    }

    .bg-minecraft .pixel-cloud {
      position: absolute;
      width: 120px;
      height: 40px;
      background: rgba(255, 255, 255, 0.03);
      border-radius: 0;
      animation: cloudMove 60s linear infinite;
      image-rendering: pixelated;
    }
    .bg-minecraft .pixel-cloud:nth-child(1) {
      top: 10%;
      animation-duration: 45s;
      width: 160px;
      height: 30px;
    }
    .bg-minecraft .pixel-cloud:nth-child(2) {
      top: 30%;
      animation-duration: 70s;
      width: 200px;
      height: 35px;
      animation-delay: -15s;
    }
    .bg-minecraft .pixel-cloud:nth-child(3) {
      top: 55%;
      animation-duration: 55s;
      width: 140px;
      height: 25px;
      animation-delay: -30s;
    }
    .bg-minecraft .pixel-cloud:nth-child(4) {
      top: 75%;
      animation-duration: 80s;
      width: 180px;
      height: 30px;
      animation-delay: -45s;
    }

    @keyframes cloudMove {
      0% {
        transform: translateX(-200px) scale(1);
        opacity: 0.3;
      }
      50% {
        opacity: 0.6;
      }
      100% {
        transform: translateX(calc(100vw + 200px)) scale(1.1);
        opacity: 0.3;
      }
    }

    /* ===== CARD ===== */
    .card {
      position: relative;
      z-index: 1;
      max-width: 820px;
      width: 100%;
      background: #c6c6c6;
      padding: 44px 40px 48px;
      border: 4px solid #8b8b8b;
      box-shadow:
        inset 0 0 0 2px #e0e0e0,
        0 8px 0 #5a5a5a,
        0 12px 32px rgba(0, 0, 0, 0.6);
      image-rendering: pixelated;
    }

    /* ===== STATUS BAR ===== */
    .status-bar {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 12px;
      margin-bottom: 18px;
    }

    .pixel-status {
      display: flex;
      align-items: center;
      gap: 14px;
      font-family: 'Courier New', monospace;
      font-size: 20px;
      font-weight: 800;
      color: #1a1a1a;
      background: #a8a8a8;
      padding: 10px 24px 10px 18px;
      border: 3px solid #7a7a7a;
      box-shadow: inset 0 0 0 2px #c0c0c0;
      image-rendering: pixelated;
    }

    .pixel-status .dot {
      width: 18px;
      height: 18px;
      background: #4a9e4a;
      border: 2px solid #2a6a2a;
      box-shadow: 0 0 20px rgba(74, 158, 74, 0.5);
      animation: pixelPulse 1.6s steps(2) infinite;
      image-rendering: pixelated;
    }

    @keyframes pixelPulse {
      0%,
      100% {
        opacity: 0.5;
        transform: scale(0.8);
      }
      50% {
        opacity: 1;
        transform: scale(1.2);
      }
    }

    .pixel-badge {
      font-family: 'Courier New', monospace;
      font-size: 18px;
      font-weight: 800;
      color: #cc3333;
      background: #1a1a1a;
      padding: 8px 22px;
      border: 2px solid #4a4a4a;
      box-shadow: inset 0 0 0 2px #5a5a5a;
      text-transform: uppercase;
      letter-spacing: 1px;
      image-rendering: pixelated;
    }

    /* ===== TITLE ===== */
    .minecraft-title {
      font-family: 'Courier New', monospace;
      font-size: 56px;
      font-weight: 900;
      color: #1a1a1a;
      text-shadow:
        4px 4px 0 #0a0a0a,
        8px 8px 0 #000000,
        0 0 20px rgba(255, 255, 255, 0.05);
      letter-spacing: 4px;
      image-rendering: pixelated;
      text-transform: uppercase;
      margin: 4px 0 10px;
    }

    .minecraft-title span {
      color: #4a9e4a;
      text-shadow:
        4px 4px 0 #1a4a1a,
        8px 8px 0 #0a2a0a;
    }

    /* ===== DESCRIPTION ===== */
    .pixel-desc {
      font-family: 'Courier New', monospace;
      font-size: 22px;
      font-weight: 800;
      color: #1a1a1a;
      line-height: 1.9;
      background: #b8b8b8;
      padding: 20px 28px;
      border: 3px solid #8a8a8a;
      box-shadow: inset 0 0 0 2px #d0d0d0;
      margin: 16px 0 26px;
      image-rendering: pixelated;
    }

    .pixel-desc strong {
      color: #1a4a1a;
      font-weight: 900;
    }

    /* ===== BUTTON PIXEL ===== */
    .btn-pixel {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 18px;
      font-family: 'Courier New', monospace;
      font-weight: 800;
      font-size: 20px;
      color: #1a1a1a;
      background: #c0c0c0;
      border: none;
      padding: 20px 28px;
      border: 4px solid #8a8a8a;
      box-shadow:
        inset 0 0 0 2px #e0e0e0,
        0 6px 0 #5a5a5a,
        0 8px 16px rgba(0, 0, 0, 0.2);
      cursor: pointer;
      transition: all 0.05s steps(2);
      text-decoration: none;
      image-rendering: pixelated;
      transform: translateY(0);
      width: 100%;
      text-align: left;
    }

    .btn-pixel:active {
      transform: translateY(6px);
      box-shadow:
        inset 0 0 0 2px #e0e0e0,
        0 2px 0 #5a5a5a,
        0 4px 8px rgba(0, 0, 0, 0.2);
    }

    .btn-pixel .icon {
      font-size: 32px;
      flex-shrink: 0;
      image-rendering: pixelated;
    }

    .btn-pixel .pixel-label {
      flex: 1;
      font-weight: 800;
      letter-spacing: 0.5px;
      font-size: 20px;
      color: #1a1a1a;
    }

    .btn-pixel .pixel-sub {
      font-size: 16px;
      font-weight: 700;
      color: #2a2a2a;
      display: block;
      margin-top: 4px;
      image-rendering: pixelated;
    }

    /* ===== JOIN BUTTON ===== */
    .btn-join-pixel {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 18px;
      font-family: 'Courier New', monospace;
      font-weight: 800;
      font-size: 24px;
      color: #ffffff;
      background: #4a9e4a;
      border: none;
      padding: 22px 36px;
      border: 4px solid #2a6a2a;
      box-shadow:
        inset 0 0 0 2px #6abe6a,
        0 6px 0 #1a4a1a,
        0 8px 24px rgba(74, 158, 74, 0.3);
      cursor: pointer;
      transition: all 0.05s steps(2);
      text-decoration: none;
      image-rendering: pixelated;
      transform: translateY(0);
      width: 100%;
      margin: 14px 0 22px;
    }

    .btn-join-pixel:active {
      transform: translateY(6px);
      box-shadow:
        inset 0 0 0 2px #6abe6a,
        0 2px 0 #1a4a1a,
        0 4px 12px rgba(74, 158, 74, 0.2);
    }

    .btn-join-pixel .wa-icon {
      display: flex;
      align-items: center;
      gap: 10px;
      background: rgba(255, 255, 255, 0.12);
      padding: 8px 18px 8px 14px;
      border: 2px solid rgba(255, 255, 255, 0.15);
      font-size: 18px;
      font-weight: 700;
    }

    .btn-join-pixel .wa-icon svg {
      width: 26px;
      height: 26px;
      fill: #fff;
    }

    /* ===== ADMIN ===== */
    .admin-label {
      font-family: 'Courier New', monospace;
      font-size: 20px;
      font-weight: 800;
      color: #1a1a1a;
      text-align: center;
      margin: 18px 0 16px;
      letter-spacing: 1px;
    }

    .admin-grid {
      display: flex;
      flex-direction: column;
      gap: 14px;
    }

    .btn-admin-pixel {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 18px;
      font-family: 'Courier New', monospace;
      font-weight: 700;
      font-size: 20px;
      color: #1a1a1a;
      background: #b0b0b0;
      border: none;
      padding: 18px 28px;
      border: 4px solid #7a7a7a;
      box-shadow:
        inset 0 0 0 2px #d0d0d0,
        0 6px 0 #4a4a4a,
        0 8px 16px rgba(0, 0, 0, 0.15);
      cursor: pointer;
      transition: all 0.05s steps(2);
      text-decoration: none;
      image-rendering: pixelated;
      transform: translateY(0);
      width: 100%;
    }

    .btn-admin-pixel:active {
      transform: translateY(6px);
      box-shadow:
        inset 0 0 0 2px #d0d0d0,
        0 2px 0 #4a4a4a,
        0 4px 8px rgba(0, 0, 0, 0.15);
    }

    .btn-admin-pixel .wa-icon {
      display: flex;
      align-items: center;
      gap: 8px;
      background: #25D366;
      padding: 6px 16px 6px 12px;
      border: 2px solid #1a8a4a;
      color: #fff;
      font-weight: 700;
      font-size: 16px;
    }

    .btn-admin-pixel .wa-icon svg {
      width: 24px;
      height: 24px;
      fill: #fff;
    }

    /* ===== GROUP ===== */
    .btn-group {
      display: flex;
      flex-direction: column;
      gap: 16px;
      margin: 20px 0 10px;
    }

    /* ===== FOOTER ===== */
    .footer-pixel {
      margin-top: 30px;
      padding-top: 22px;
      border-top: 4px solid #8a8a8a;
      text-align: center;
      font-family: 'Courier New', monospace;
      font-size: 18px;
      font-weight: 700;
      color: #2a2a2a;
      letter-spacing: 1px;
    }

    .footer-pixel span {
      color: #4a9e4a;
    }

    /* ===== SOUND ===== */
    .pixel-sound {
      display: none;
    }

    /* ===== RESPONSIVE ===== */
    @media (max-width: 700px) {
      .card {
        padding: 28px 20px 32px;
      }
      .minecraft-title {
        font-size: 38px;
        letter-spacing: 2px;
      }
      .pixel-status {
        font-size: 16px;
        padding: 8px 16px 8px 14px;
      }
      .pixel-badge {
        font-size: 14px;
        padding: 6px 16px;
      }
      .pixel-desc {
        font-size: 18px;
        padding: 16px 20px;
      }
      .btn-pixel {
        font-size: 17px;
        padding: 16px 18px;
        gap: 14px;
      }
      .btn-pixel .pixel-label {
        font-size: 17px;
      }
      .btn-pixel .pixel-sub {
        font-size: 14px;
      }
      .btn-pixel .icon {
        font-size: 26px;
      }
      .btn-join-pixel {
        font-size: 20px;
        padding: 18px 24px;
      }
      .btn-join-pixel .wa-icon {
        font-size: 16px;
        padding: 6px 14px 6px 10px;
      }
      .btn-join-pixel .wa-icon svg {
        width: 22px;
        height: 22px;
      }
      .btn-admin-pixel {
        font-size: 17px;
        padding: 16px 20px;
      }
      .btn-admin-pixel .wa-icon {
        font-size: 14px;
        padding: 4px 12px 4px 8px;
      }
      .btn-admin-pixel .wa-icon svg {
        width: 20px;
        height: 20px;
      }
      .admin-label {
        font-size: 17px;
      }
      .footer-pixel {
        font-size: 16px;
      }
    }

    @media (max-width: 480px) {
      .card {
        padding: 18px 14px 22px;
      }
      .minecraft-title {
        font-size: 28px;
        letter-spacing: 1px;
      }
      .pixel-status {
        font-size: 13px;
        padding: 6px 12px 6px 10px;
        gap: 10px;
      }
      .pixel-status .dot {
        width: 14px;
        height: 14px;
      }
      .pixel-badge {
        font-size: 12px;
        padding: 4px 12px;
      }
      .pixel-desc {
        font-size: 15px;
        padding: 14px 16px;
        line-height: 1.7;
      }
      .btn-pixel {
        font-size: 14px;
        padding: 14px 14px;
        gap: 12px;
        flex-wrap: wrap;
      }
      .btn-pixel .pixel-label {
        font-size: 14px;
      }
      .btn-pixel .pixel-sub {
        font-size: 12px;
      }
      .btn-pixel .icon {
        font-size: 20px;
      }
      .btn-join-pixel {
        font-size: 16px;
        padding: 14px 16px;
        gap: 12px;
        flex-wrap: wrap;
      }
      .btn-join-pixel .wa-icon {
        font-size: 13px;
        padding: 4px 10px 4px 8px;
      }
      .btn-join-pixel .wa-icon svg {
        width: 18px;
        height: 18px;
      }
      .btn-admin-pixel {
        font-size: 14px;
        padding: 14px 14px;
        gap: 12px;
        flex-wrap: wrap;
      }
      .btn-admin-pixel .wa-icon {
        font-size: 12px;
        padding: 4px 8px 4px 6px;
      }
      .btn-admin-pixel .wa-icon svg {
        width: 16px;
        height: 16px;
      }
      .admin-label {
        font-size: 14px;
      }
      .footer-pixel {
        font-size: 13px;
        padding-top: 16px;
        margin-top: 22px;
      }
      .btn-group {
        gap: 12px;
      }
      .admin-grid {
        gap: 10px;
      }
    }
  </style>
</head>
<body>

  <!-- ===== BACKGROUND ===== -->
  <div class="bg-minecraft">
    <div class="pixel-cloud"></div>
    <div class="pixel-cloud"></div>
    <div class="pixel-cloud"></div>
    <div class="pixel-cloud"></div>
  </div>

  <!-- ===== AUDIO ===== -->
  <audio id="clickSound" class="pixel-sound">
    <source src="https://www.myinstants.com/media/sounds/minecraft_click.mp3" type="audio/mpeg" />
  </audio>

  <!-- ===== CARD ===== -->
  <div class="card">

    <!-- STATUS -->
    <div class="status-bar">
      <div class="pixel-status">
        <span class="dot"></span>
        <span>Harxz · Online</span>
      </div>
      <div class="pixel-badge">🔴 Channel Aktif</div>
    </div>

    <!-- TITLE -->
    <div class="minecraft-title">
      <span>Harxz</span> Mobi
    </div>

    <!-- DESCRIPTION -->
    <div class="pixel-desc">
      Gabung sekarang Channel <strong>Harxz</strong> agar mendapatkan file/script/apk/rege lainnya, <strong>buruan join!</strong>
    </div>

    <!-- BUTTON GROUP -->
    <div class="btn-group">

      <div class="btn-pixel" id="btn1">
        <span class="icon">📤</span>
        <span class="pixel-label">
          Share-Share 24 Jam
          <span class="pixel-sub">Informasi update terbaru sering bagi² cheat/file/rege/apk mobi dan lainnya</span>
        </span>
      </div>

      <div class="btn-pixel" id="btn2">
        <span class="icon">📁</span>
        <span class="pixel-label">
          File/Apk Mobi VIP
          <span class="pixel-sub">Disini channel sering bagi² Apk Mobi,Set Mobi,file vip hasil buy di seller lain, dikasih free secara percuma cuma</span>
        </span>
      </div>

      <div class="btn-pixel" id="btn3">
        <span class="icon">🎁</span>
        <span class="pixel-label">
          Giveaway
          <span class="pixel-sub">Nanti ada Apk Set Mobi Free Tanpa Buy</span>
        </span>
      </div>

    </div>

    <!-- JOIN CHANNEL -->
    <a href="https://whatsapp.com/channel/0029VbDBZihDeON0zRvgBV3Z" target="_blank" class="btn-join-pixel" id="btnJoin">
      <span class="wa-icon">
        <svg viewBox="0 0 24 24"><path d="M12.032 21.965c-1.821.003-3.6-.48-5.13-1.393l-4.424 1.46 1.478-4.314a9.947 9.947 0 0 1-1.519-5.321c0-5.51 4.482-9.992 9.995-9.992 5.513 0 9.995 4.482 9.995 9.992s-4.482 9.992-9.995 9.992h-.001zm0-18.458a8.464 8.464 0 0 0-8.467 8.467c0 1.761.54 3.48 1.563 4.92l-1.02 2.977 3.113-1.027c1.436.85 3.079 1.299 4.811 1.299 4.669 0 8.467-3.798 8.467-8.467s-3.798-8.467-8.467-8.467z"/><path d="M17.245 13.518c-.308-.154-1.825-.901-2.108-1.004-.283-.103-.489-.154-.695.154s-.797 1.004-.977 1.21c-.18.206-.36.231-.668.077-.308-.154-1.301-.48-2.478-1.529-.916-.816-1.535-1.824-1.715-2.132-.18-.308-.019-.474.135-.627.138-.138.308-.36.462-.539.154-.18.205-.308.308-.514.103-.205.051-.385-.026-.539-.077-.154-.695-1.674-.952-2.292-.251-.602-.506-.502-.695-.512-.18-.01-.386-.01-.593-.01-.206 0-.54.077-.822.385-.283.308-1.08 1.056-1.08 2.574s1.106 2.988 1.26 3.195c.154.206 2.177 3.324 5.273 4.464 3.096 1.14 3.096.76 3.655.712.559-.049 1.804-.737 2.058-1.449.254-.712.254-1.322.18-1.449-.073-.128-.27-.205-.577-.36z"/></svg>
        WA
      </span>
      <span>Join Channel Sekarang →</span>
    </a>

    <!-- ADMIN -->
    <div class="admin-label">KONTAK OFFICIAL ADMIN:</div>
    <div class="admin-grid">
      <a href="https://wa.me/6287752772641" target="_blank" class="btn-admin-pixel" id="admin1">
        <span class="wa-icon">
          <svg viewBox="0 0 24 24"><path d="M12.032 21.965c-1.821.003-3.6-.48-5.13-1.393l-4.424 1.46 1.478-4.314a9.947 9.947 0 0 1-1.519-5.321c0-5.51 4.482-9.992 9.995-9.992 5.513 0 9.995 4.482 9.995 9.992s-4.482 9.992-9.995 9.992h-.001zm0-18.458a8.464 8.464 0 0 0-8.467 8.467c0 1.761.54 3.48 1.563 4.92l-1.02 2.977 3.113-1.027c1.436.85 3.079 1.299 4.811 1.299 4.669 0 8.467-3.798 8.467-8.467s-3.798-8.467-8.467-8.467z"/><path d="M17.245 13.518c-.308-.154-1.825-.901-2.108-1.004-.283-.103-.489-.154-.695.154s-.797 1.004-.977 1.21c-.18.206-.36.231-.668.077-.308-.154-1.301-.48-2.478-1.529-.916-.816-1.535-1.824-1.715-2.132-.18-.308-.019-.474.135-.627.138-.138.308-.36.462-.539.154-.18.205-.308.308-.514.103-.205.051-.385-.026-.539-.077-.154-.695-1.674-.952-2.292-.251-.602-.506-.502-.695-.512-.18-.01-.386-.01-.593-.01-.206 0-.54.077-.822.385-.283.308-1.08 1.056-1.08 2.574s1.106 2.988 1.26 3.195c.154.206 2.177 3.324 5.273 4.464 3.096 1.14 3.096.76 3.655.712.559-.049 1.804-.737 2.058-1.449.254-.712.254-1.322.18-1.449-.073-.128-.27-.205-.577-.36z"/></svg>
          WA
        </span>
        <span>KONTAK 1</span>
      </a>
      <a href="https://wa.me/6281958628819" target="_blank" class="btn-admin-pixel" id="admin2">
        <span class="wa-icon">
          <svg viewBox="0 0 24 24"><path d="M12.032 21.965c-1.821.003-3.6-.48-5.13-1.393l-4.424 1.46 1.478-4.314a9.947 9.947 0 0 1-1.519-5.321c0-5.51 4.482-9.992 9.995-9.992 5.513 0 9.995 4.482 9.995 9.992s-4.482 9.992-9.995 9.992h-.001zm0-18.458a8.464 8.464 0 0 0-8.467 8.467c0 1.761.54 3.48 1.563 4.92l-1.02 2.977 3.113-1.027c1.436.85 3.079 1.299 4.811 1.299 4.669 0 8.467-3.798 8.467-8.467s-3.798-8.467-8.467-8.467z"/><path d="M17.245 13.518c-.308-.154-1.825-.901-2.108-1.004-.283-.103-.489-.154-.695.154s-.797 1.004-.977 1.21c-.18.206-.36.231-.668.077-.308-.154-1.301-.48-2.478-1.529-.916-.816-1.535-1.824-1.715-2.132-.18-.308-.019-.474.135-.627.138-.138.308-.36.462-.539.154-.18.205-.308.308-.514.103-.205.051-.385-.026-.539-.077-.154-.695-1.674-.952-2.292-.251-.602-.506-.502-.695-.512-.18-.01-.386-.01-.593-.01-.206 0-.54.077-.822.385-.283.308-1.08 1.056-1.08 2.574s1.106 2.988 1.26 3.195c.154.206 2.177 3.324 5.273 4.464 3.096 1.14 3.096.76 3.655.712.559-.049 1.804-.737 2.058-1.449.254-.712.254-1.322.18-1.449-.073-.128-.27-.205-.577-.36z"/></svg>
          WA
        </span>
        <span>KONTAK 2</span>
      </a>
    </div>

    <!-- FOOTER -->
    <div class="footer-pixel">
      <span>Harxz</span> Mobi · OFFICIAL
    </div>

  </div>

  <script>
    // ===== MINECRAFT CLICK SOUND =====
    const clickAudio = document.getElementById('clickSound');

    function playClick() {
      clickAudio.currentTime = 0;
      clickAudio.play().catch(() => {});
    }

    document.querySelectorAll('.btn-pixel, .btn-join-pixel, .btn-admin-pixel').forEach(el => {
      el.addEventListener('click', function(e) {
        playClick();
      });
    });

    document.getElementById('btn1').addEventListener('click', function(e) {
      e.preventDefault();
      playClick();
    });
    document.getElementById('btn2').addEventListener('click', function(e) {
      e.preventDefault();
      playClick();
    });
    document.getElementById('btn3').addEventListener('click', function(e) {
      e.preventDefault();
      playClick();
    });
  </script>

</body>
</html>
