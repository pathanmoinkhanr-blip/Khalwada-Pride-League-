# Khalwada-Pride-League-
KPL players registration 
<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Khalwada Pride League - Cricket Tournament</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Rajdhani:wght@400;500;600;700&family=Noto+Sans+Devanagari:wght@400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --green: #00c853;
    --dark-green: #007b38;
    --gold: #ffd700;
    --orange: #ff6d00;
    --dark: #0a0f0a;
    --darker: #060a06;
    --card: #111811;
    --card2: #162016;
    --border: #1e3a1e;
    --text: #e8f5e9;
    --muted: #7a9e7a;
    --red: #ff3d3d;
    --white: #ffffff;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Rajdhani', 'Noto Sans Devanagari', sans-serif;
    background: var(--darker);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ========== BACKGROUND ========== */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background:
      radial-gradient(ellipse at 20% 20%, rgba(0,200,83,0.06) 0%, transparent 60%),
      radial-gradient(ellipse at 80% 80%, rgba(255,109,0,0.05) 0%, transparent 60%),
      repeating-linear-gradient(0deg, transparent, transparent 40px, rgba(0,200,83,0.015) 40px, rgba(0,200,83,0.015) 41px),
      repeating-linear-gradient(90deg, transparent, transparent 40px, rgba(0,200,83,0.015) 40px, rgba(0,200,83,0.015) 41px);
    pointer-events: none; z-index: 0;
  }

  /* ========== HEADER ========== */
  .header {
    background: linear-gradient(135deg, #0a1a0a 0%, #0f2a0f 50%, #0a1a0a 100%);
    border-bottom: 3px solid var(--green);
    padding: 16px 20px;
    text-align: center;
    position: relative; z-index: 10;
    box-shadow: 0 4px 30px rgba(0,200,83,0.2);
  }

  .header-badge {
    display: inline-block;
    background: var(--orange);
    color: white;
    font-size: 11px; font-weight: 700;
    padding: 3px 12px; border-radius: 20px;
    letter-spacing: 1px; margin-bottom: 8px;
    text-transform: uppercase;
  }

  .header h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(28px, 7vw, 52px);
    letter-spacing: 3px;
    color: var(--white);
    text-shadow: 0 0 30px rgba(0,200,83,0.5), 0 2px 4px rgba(0,0,0,0.8);
    line-height: 1;
  }

  .header h1 span { color: var(--green); }

  .header-sub {
    font-size: 13px; color: var(--gold);
    font-weight: 600; letter-spacing: 2px;
    text-transform: uppercase; margin-top: 4px;
  }

  .header-nav {
    display: flex; justify-content: center; gap: 8px;
    margin-top: 14px; flex-wrap: wrap;
  }

  .nav-btn {
    background: transparent;
    border: 1.5px solid var(--border);
    color: var(--muted);
    padding: 7px 18px; border-radius: 6px;
    font-family: 'Rajdhani', sans-serif;
    font-size: 13px; font-weight: 600;
    cursor: pointer; transition: all 0.2s;
    letter-spacing: 0.5px;
  }

  .nav-btn:hover, .nav-btn.active {
    border-color: var(--green);
    color: var(--green);
    background: rgba(0,200,83,0.08);
    box-shadow: 0 0 12px rgba(0,200,83,0.15);
  }

  /* ========== PAGES ========== */
  .page { display: none; padding: 20px 16px; max-width: 640px; margin: 0 auto; position: relative; z-index: 1; }
  .page.active { display: block; animation: fadeIn 0.3s ease; }
  @keyframes fadeIn { from { opacity:0; transform: translateY(8px); } to { opacity:1; transform: translateY(0); } }

  /* ========== CARDS ========== */
  .card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    margin-bottom: 16px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.4);
  }

  .card-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 20px; letter-spacing: 2px;
    color: var(--green); margin-bottom: 16px;
    display: flex; align-items: center; gap: 8px;
    border-bottom: 1px solid var(--border);
    padding-bottom: 10px;
  }

  /* ========== FORM ========== */
  .form-group { margin-bottom: 14px; }

  label {
    display: block;
    font-size: 12px; font-weight: 700;
    color: var(--muted); text-transform: uppercase;
    letter-spacing: 1px; margin-bottom: 6px;
  }

  input, select, textarea {
    width: 100%;
    background: var(--card2);
    border: 1.5px solid var(--border);
    color: var(--text);
    padding: 11px 14px;
    border-radius: 8px;
    font-family: 'Rajdhani', 'Noto Sans Devanagari', sans-serif;
    font-size: 15px;
    transition: border-color 0.2s, box-shadow 0.2s;
    outline: none;
  }

  input:focus, select:focus, textarea:focus {
    border-color: var(--green);
    box-shadow: 0 0 0 3px rgba(0,200,83,0.1);
  }

  input::placeholder, textarea::placeholder { color: #3a5a3a; }

  select option { background: #111; }

  textarea { resize: vertical; min-height: 80px; }

  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }

  /* ========== BUTTONS ========== */
  .btn {
    width: 100%; padding: 14px;
    border: none; border-radius: 10px;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 18px; letter-spacing: 2px;
    cursor: pointer; transition: all 0.2s;
    margin-top: 8px;
  }

  .btn-primary {
    background: linear-gradient(135deg, var(--dark-green), var(--green));
    color: white;
    box-shadow: 0 4px 20px rgba(0,200,83,0.3);
  }

  .btn-primary:hover {
    transform: translateY(-1px);
    box-shadow: 0 6px 25px rgba(0,200,83,0.4);
  }

  .btn-primary:active { transform: translateY(0); }

  .btn-orange {
    background: linear-gradient(135deg, #e65100, var(--orange));
    color: white;
    box-shadow: 0 4px 20px rgba(255,109,0,0.3);
  }

  .btn-danger {
    background: linear-gradient(135deg, #b71c1c, var(--red));
    color: white;
    box-shadow: 0 4px 15px rgba(255,61,61,0.2);
    font-size: 14px; padding: 10px;
    width: auto; display: inline-block;
  }

  .btn-small {
    font-family: 'Rajdhani', sans-serif;
    font-size: 12px; padding: 6px 14px;
    width: auto; margin: 0;
    border-radius: 6px; font-weight: 700;
    letter-spacing: 0.5px;
  }

  /* ========== HOME PAGE ========== */
  .hero {
    text-align: center; padding: 30px 0 20px;
  }

  .cricket-icon {
    font-size: 64px; margin-bottom: 16px;
    display: block;
    filter: drop-shadow(0 0 20px rgba(0,200,83,0.4));
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.05); }
  }

  .hero h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 30px; letter-spacing: 3px;
    color: var(--white); margin-bottom: 6px;
  }

  .hero p { color: var(--muted); font-size: 14px; line-height: 1.5; }

  .info-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin: 20px 0; }

  .info-box {
    background: var(--card2);
    border: 1px solid var(--border);
    border-radius: 10px; padding: 14px;
    text-align: center;
  }

  .info-box .val {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 22px; color: var(--gold);
    display: block;
  }

  .info-box .lbl { font-size: 11px; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; }

  /* ========== PAYMENT SECTION ========== */
  .payment-box {
    background: linear-gradient(135deg, #0f2a0f, #1a3a1a);
    border: 2px solid var(--green);
    border-radius: 12px; padding: 20px;
    text-align: center; margin: 16px 0;
  }

  .payment-box h3 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 20px; letter-spacing: 2px;
    color: var(--gold); margin-bottom: 4px;
  }

  .upi-id {
    background: var(--card);
    border: 1px dashed var(--green);
    border-radius: 8px; padding: 12px;
    font-size: 18px; font-weight: 700;
    color: var(--green); margin: 12px 0;
    word-break: break-all; letter-spacing: 1px;
  }

  .qr-placeholder {
    width: 160px; height: 160px;
    margin: 12px auto;
    background: white;
    border-radius: 8px;
    display: flex; align-items: center;
    justify-content: center;
    overflow: hidden; position: relative;
  }

  .qr-placeholder img {
    width: 100%; height: 100%;
    object-fit: contain;
  }

  .qr-grid {
    display: grid; grid-template-columns: repeat(10,1fr); gap: 2px;
    padding: 8px;
  }

  .qr-cell {
    aspect-ratio: 1;
    background: black;
    border-radius: 1px;
  }

  .fee-amount {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 36px; color: var(--orange);
    display: block; margin: 6px 0;
  }

  .fee-note { font-size: 12px; color: var(--muted); }

  /* ========== UPLOAD ========== */
  .upload-area {
    border: 2px dashed var(--border);
    border-radius: 10px; padding: 24px;
    text-align: center; cursor: pointer;
    transition: all 0.2s; position: relative;
    background: var(--card2);
  }

  .upload-area:hover {
    border-color: var(--green);
    background: rgba(0,200,83,0.04);
  }

  .upload-area input[type="file"] {
    position: absolute; inset: 0;
    opacity: 0; cursor: pointer;
    border: none; padding: 0;
  }

  .upload-icon { font-size: 32px; margin-bottom: 8px; }

  .upload-text { color: var(--muted); font-size: 13px; }

  .upload-preview {
    margin-top: 12px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px; padding: 10px;
    display: flex; align-items: center; gap: 10px;
    font-size: 13px; color: var(--green);
  }

  /* ========== SUCCESS ========== */
  .success-msg {
    background: linear-gradient(135deg, #0a2a15, #0f3a1a);
    border: 2px solid var(--green);
    border-radius: 12px; padding: 24px;
    text-align: center; margin: 20px 0;
    animation: fadeIn 0.4s ease;
  }

  .success-msg .check { font-size: 48px; margin-bottom: 8px; }

  .success-msg h3 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 24px; color: var(--green);
    letter-spacing: 2px; margin-bottom: 4px;
  }

  .success-msg p { color: var(--muted); font-size: 13px; }

  .reg-id {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 20px; color: var(--gold);
    background: var(--card2);
    border: 1px solid var(--border);
    border-radius: 6px; padding: 8px 16px;
    margin: 10px 0; display: inline-block;
    letter-spacing: 3px;
  }

  /* ========== ADMIN ========== */
  .admin-login {
    max-width: 360px; margin: 40px auto 0;
  }

  .admin-header-box {
    text-align: center; margin-bottom: 20px;
  }

  .admin-header-box .icon { font-size: 48px; }

  .admin-header-box h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 28px; letter-spacing: 3px;
    color: var(--gold); margin-top: 8px;
  }

  /* ========== PLAYERS TABLE ========== */
  .players-list { overflow-x: auto; }

  .players-table {
    width: 100%; border-collapse: collapse;
    font-size: 13px;
  }

  .players-table th {
    background: rgba(0,200,83,0.1);
    color: var(--green);
    padding: 10px 12px;
    text-align: left;
    font-size: 11px; text-transform: uppercase;
    letter-spacing: 1px;
    border-bottom: 1px solid var(--border);
    white-space: nowrap;
  }

  .players-table td {
    padding: 10px 12px;
    border-bottom: 1px solid rgba(30,58,30,0.5);
    vertical-align: middle;
    color: var(--text);
  }

  .players-table tr:hover td { background: rgba(0,200,83,0.03); }

  .status-badge {
    padding: 3px 10px; border-radius: 20px;
    font-size: 11px; font-weight: 700;
    text-transform: uppercase; letter-spacing: 0.5px;
  }

  .status-pending { background: rgba(255,215,0,0.15); color: var(--gold); border: 1px solid rgba(255,215,0,0.3); }
  .status-approved { background: rgba(0,200,83,0.15); color: var(--green); border: 1px solid rgba(0,200,83,0.3); }
  .status-rejected { background: rgba(255,61,61,0.15); color: var(--red); border: 1px solid rgba(255,61,61,0.3); }

  /* ========== STATS ========== */
  .stats-row { display: grid; grid-template-columns: repeat(3,1fr); gap: 10px; margin-bottom: 16px; }

  .stat-box {
    background: var(--card2);
    border: 1px solid var(--border);
    border-radius: 10px; padding: 14px;
    text-align: center;
  }

  .stat-box .num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 28px; display: block;
  }

  .stat-box .lbl { font-size: 11px; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; }

  .num-green { color: var(--green); }
  .num-gold { color: var(--gold); }
  .num-orange { color: var(--orange); }

  /* ========== SETTINGS ========== */
  .settings-section { margin-bottom: 20px; }

  .settings-section h3 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 16px; letter-spacing: 2px;
    color: var(--muted); text-transform: uppercase;
    margin-bottom: 12px;
    display: flex; align-items: center; gap: 6px;
  }

  /* ========== ALERT ========== */
  .alert {
    padding: 12px 16px; border-radius: 8px;
    font-size: 13px; margin-bottom: 12px;
    font-weight: 600;
  }

  .alert-error { background: rgba(255,61,61,0.1); border: 1px solid rgba(255,61,61,0.3); color: var(--red); }
  .alert-success { background: rgba(0,200,83,0.1); border: 1px solid rgba(0,200,83,0.3); color: var(--green); }
  .alert-info { background: rgba(255,215,0,0.08); border: 1px solid rgba(255,215,0,0.2); color: var(--gold); }

  /* ========== SEARCH ========== */
  .search-bar {
    display: flex; gap: 8px; margin-bottom: 14px;
  }

  .search-bar input { flex: 1; }

  /* ========== MODAL ========== */
  .modal-overlay {
    display: none; position: fixed; inset: 0;
    background: rgba(0,0,0,0.85);
    z-index: 1000; align-items: center;
    justify-content: center; padding: 16px;
  }

  .modal-overlay.open { display: flex; }

  .modal {
    background: var(--card);
    border: 1px solid var(--green);
    border-radius: 14px; padding: 24px;
    max-width: 500px; width: 100%;
    max-height: 90vh; overflow-y: auto;
    animation: fadeIn 0.2s ease;
  }

  .modal-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 22px; letter-spacing: 2px;
    color: var(--green); margin-bottom: 16px;
  }

  .modal-close {
    float: right; background: none; border: none;
    color: var(--muted); font-size: 20px;
    cursor: pointer; line-height: 1;
  }

  .detail-row { display: flex; justify-content: space-between;
    padding: 8px 0; border-bottom: 1px solid var(--border);
    font-size: 14px; gap: 12px;
  }

  .detail-row:last-child { border-bottom: none; }
  .detail-label { color: var(--muted); font-size: 12px; min-width: 120px; }
  .detail-value { color: var(--text); font-weight: 600; text-align: right; }

  .proof-img {
    width: 100%; border-radius: 8px;
    border: 1px solid var(--border);
    max-height: 200px; object-fit: contain;
    background: var(--card2); margin-top: 8px;
  }

  .action-btns { display: flex; gap: 8px; margin-top: 12px; }

  .btn-approve {
    background: linear-gradient(135deg, var(--dark-green), var(--green));
    color: white; border: none;
    padding: 10px 20px; border-radius: 8px;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 15px; letter-spacing: 1px;
    cursor: pointer; transition: all 0.2s; flex: 1;
  }

  .btn-reject {
    background: linear-gradient(135deg, #b71c1c, var(--red));
    color: white; border: none;
    padding: 10px 20px; border-radius: 8px;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 15px; letter-spacing: 1px;
    cursor: pointer; transition: all 0.2s; flex: 1;
  }

  .step-indicator {
    display: flex; gap: 0; margin-bottom: 20px;
  }

  .step {
    flex: 1; text-align: center; padding: 10px 4px;
    border-bottom: 3px solid var(--border);
    font-size: 11px; color: var(--muted);
    text-transform: uppercase; letter-spacing: 0.5px;
    transition: all 0.2s;
  }

  .step.active { border-color: var(--green); color: var(--green); font-weight: 700; }
  .step.done { border-color: var(--dark-green); color: var(--dark-green); }

  .reg-form-step { display: none; }
  .reg-form-step.active { display: block; animation: fadeIn 0.3s ease; }

  .copy-btn {
    background: var(--card2); border: 1px solid var(--border);
    color: var(--green); padding: 6px 14px;
    border-radius: 6px; font-size: 12px;
    cursor: pointer; font-weight: 700;
    transition: all 0.2s;
  }

  .copy-btn:hover { border-color: var(--green); background: rgba(0,200,83,0.1); }

  .no-data {
    text-align: center; padding: 40px 20px;
    color: var(--muted); font-size: 14px;
  }

  .no-data .icon { font-size: 40px; margin-bottom: 8px; }

  @media (max-width: 480px) {
    .form-row { grid-template-columns: 1fr; }
    .info-grid { grid-template-columns: 1fr 1fr; }
    .stats-row { grid-template-columns: repeat(3,1fr); }
  }

  .floating-cricket {
    position: fixed; bottom: 20px; right: 20px;
    width: 50px; height: 50px;
    background: linear-gradient(135deg, var(--dark-green), var(--green));
    border-radius: 50%; display: flex; align-items: center;
    justify-content: center; font-size: 24px;
    box-shadow: 0 4px 20px rgba(0,200,83,0.4);
    cursor: pointer; z-index: 100;
    transition: transform 0.2s;
  }

  .floating-cricket:hover { transform: scale(1.1) rotate(10deg); }

  .divider { height: 1px; background: var(--border); margin: 16px 0; }

  .tag {
    display: inline-block;
    background: rgba(0,200,83,0.1);
    border: 1px solid rgba(0,200,83,0.2);
    color: var(--green); font-size: 11px;
    padding: 2px 8px; border-radius: 4px;
    margin: 2px; font-weight: 700;
    text-transform: uppercase;
  }
</style>
</head>
<body>

<!-- HEADER -->
<div class="header">
  <div class="header-badge">🏆 Official Registration Portal</div>
  <h1>KHALWADA <span>PRIDE</span> LEAGUE</h1>
  <div class="header-sub">🏏 Cricket Tournament 2025</div>
  <div class="header-nav">
    <button class="nav-btn active" onclick="showPage('home')">🏠 Home</button>
    <button class="nav-btn" onclick="showPage('register')">📝 Register</button>
    <button class="nav-btn" onclick="showPage('admin')">🔐 Admin</button>
  </div>
</div>

<!-- ==================== HOME PAGE ==================== -->
<div id="page-home" class="page active">
  <div class="hero">
    <span class="cricket-icon">🏏</span>
    <h2>Welcome to KPL 2025</h2>
    <p>Khalwada ki sabse badi cricket league mein participate karo!<br>Registration karo, payment karo, aur apna safar shuru karo.</p>
  </div>

  <div id="home-info-grid" class="info-grid">
    <div class="info-box">
      <span class="val" id="home-fee">₹200</span>
      <span class="lbl">Entry Fee</span>
    </div>
    <div class="info-box">
      <span class="val" id="home-deadline">30 Jun</span>
      <span class="lbl">Last Date</span>
    </div>
    <div class="info-box">
      <span class="val" id="home-slots">50</span>
      <span class="lbl">Max Players</span>
    </div>
    <div class="info-box">
      <span class="val" id="home-registered">0</span>
      <span class="lbl">Registered</span>
    </div>
  </div>

  <div class="card" id="home-details-card">
    <div class="card-title">📋 Tournament Details</div>
    <div id="home-tournament-info">
      <div class="detail-row">
        <span class="detail-label">📍 Venue</span>
        <span class="detail-value" id="home-venue">Khalwada Ground</span>
      </div>
      <div class="detail-row">
        <span class="detail-label">📅 Start Date</span>
        <span class="detail-value" id="home-start">01 July 2025</span>
      </div>
      <div class="detail-row">
        <span class="detail-label">📞 Contact</span>
        <span class="detail-value" id="home-contact">—</span>
      </div>
      <div class="detail-row">
        <span class="detail-label">💰 Prize Pool</span>
        <span class="detail-value" id="home-prize">TBD</span>
      </div>
    </div>
    <div id="home-extra-info" style="margin-top:12px; color: var(--muted); font-size: 13px; line-height: 1.6;"></div>
  </div>

  <button class="btn btn-primary" onclick="showPage('register')">
    📝 ABHI REGISTER KARO
  </button>
</div>

<!-- ==================== REGISTER PAGE ==================== -->
<div id="page-register" class="page">

  <div id="reg-success" style="display:none;">
    <div class="success-msg">
      <div class="check">✅</div>
      <h3>Registration Successful!</h3>
      <p>Aapki registration submit ho gayi hai.</p>
      <div class="reg-id" id="reg-id-display">KPL-0000</div>
      <p style="color: var(--muted); font-size: 12px; margin-top: 8px;">Yeh ID save kar lo. Admin verify karne ke baad aapko confirm kiya jayega.</p>
    </div>
    <button class="btn btn-primary" onclick="resetRegistration()">🔄 Naya Registration</button>
  </div>

  <div id="reg-form-container">
    <div class="card" style="margin-bottom:12px; padding:14px;">
      <div class="step-indicator">
        <div class="step active" id="step-1">1. Info</div>
        <div class="step" id="step-2">2. Cricket</div>
        <div class="step" id="step-3">3. Payment</div>
      </div>

      <!-- STEP 1: BASIC INFO -->
      <div class="reg-form-step active" id="form-step-1">
        <div class="card-title">👤 Personal Information</div>

        <div class="form-group">
          <label>पूरा नाम / Full Name *</label>
          <input type="text" id="r-name" placeholder="Aapka poora naam">
        </div>

        <div class="form-row">
          <div class="form-group">
            <label>उम्र / Age *</label>
            <input type="number" id="r-age" placeholder="Age" min="10" max="60">
          </div>
          <div class="form-group">
            <label>मोबाइल / Mobile *</label>
            <input type="tel" id="r-mobile" placeholder="10 digit number">
          </div>
        </div>

        <div class="form-group">
          <label>पता / Address</label>
          <input type="text" id="r-address" placeholder="Ghar ka address">
        </div>

        <div class="form-group">
          <label>Email (Optional)</label>
          <input type="email" id="r-email" placeholder="email@example.com">
        </div>

        <button class="btn btn-primary" onclick="nextStep(1)">AAGE BADHO →</button>
      </div>

      <!-- STEP 2: CRICKET DETAILS -->
      <div class="reg-form-step" id="form-step-2">
        <div class="card-title">🏏 Cricket Details</div>

        <div class="form-row">
          <div class="form-group">
            <label>Batting Style</label>
            <select id="r-batting">
              <option value="">Select</option>
              <option>Right Hand</option>
              <option>Left Hand</option>
            </select>
          </div>
          <div class="form-group">
            <label>Bowling Style</label>
            <select id="r-bowling">
              <option value="">Select</option>
              <option>Fast</option>
              <option>Medium Fast</option>
              <option>Spin (Off)</option>
              <option>Spin (Leg)</option>
              <option>Don't Bowl</option>
            </select>
          </div>
        </div>

        <div class="form-group">
          <label>Playing Role *</label>
          <select id="r-role">
            <option value="">Select Role</option>
            <option>Batsman</option>
            <option>Bowler</option>
            <option>All Rounder</option>
            <option>Wicket Keeper</option>
            <option>Wicket Keeper Batsman</option>
          </select>
        </div>

        <div class="form-group">
          <label>Jersey Number (Preferred)</label>
          <input type="number" id="r-jersey" placeholder="e.g. 7, 18, 45" min="1" max="99">
        </div>

        <div class="form-group">
          <label>Experience Level</label>
          <select id="r-experience">
            <option value="">Select</option>
            <option>Beginner (Naaya)</option>
            <option>Intermediate</option>
            <option>Experienced</option>
            <option>Professional</option>
          </select>
        </div>

        <div style="display:flex; gap:8px; margin-top:8px;">
          <button class="btn btn-primary" onclick="prevStep(2)" style="background: var(--card2); border: 1px solid var(--border); color: var(--muted); box-shadow: none;">← WAPAS</button>
          <button class="btn btn-primary" onclick="nextStep(2)" style="flex:2;">PAYMENT KARO →</button>
        </div>
      </div>

      <!-- STEP 3: PAYMENT -->
      <div class="reg-form-step" id="form-step-3">
        <div class="card-title">💳 Payment & Proof</div>

        <div class="payment-box">
          <h3>💰 Registration Fee</h3>
          <span class="fee-amount" id="pay-fee-display">₹200</span>
          <div class="fee-note">Yeh fee non-refundable hai</div>

          <div style="margin-top: 16px;">
            <div style="font-size: 12px; color: var(--muted); margin-bottom: 6px; text-transform: uppercase; letter-spacing: 1px;">UPI ID pe Payment Karo:</div>
            <div class="upi-id" id="pay-upi-display">9876543210@paytm</div>
            <button class="copy-btn" onclick="copyUPI()">📋 Copy UPI ID</button>
          </div>

          <div style="margin-top: 16px;">
            <div style="font-size: 12px; color: var(--muted); margin-bottom: 8px; text-transform: uppercase; letter-spacing: 1px;">Ya QR Code Scan Karo:</div>
            <div class="qr-placeholder">
              <img id="qr-img-display" src="" alt="QR Code" style="display:none;">
              <div id="qr-default-text" style="color: #555; font-size: 11px; text-align:center; padding: 20px; font-family: 'Rajdhani', sans-serif;">
                📱<br>QR Code<br>Admin Panel se<br>Upload karein
              </div>
            </div>
          </div>
        </div>

        <div class="form-group">
          <label>UPI Transaction ID / Reference Number *</label>
          <input type="text" id="r-txn" placeholder="e.g. T2025012345678">
        </div>

        <div class="form-group">
          <label>Payment Screenshot / Proof *</label>
          <div class="upload-area" onclick="document.getElementById('r-proof').click()">
            <input type="file" id="r-proof" accept="image/*" onchange="handleProofUpload(this)">
            <div class="upload-icon">📸</div>
            <div class="upload-text">Payment screenshot yahan upload karo<br><small>PNG, JPG, JPEG (Max 5MB)</small></div>
          </div>
          <div id="proof-preview" style="display:none;" class="upload-preview">
            <span>✅</span>
            <span id="proof-filename"></span>
          </div>
        </div>

        <div style="display:flex; gap:8px; margin-top:8px;">
          <button class="btn btn-primary" onclick="prevStep(3)" style="background: var(--card2); border: 1px solid var(--border); color: var(--muted); box-shadow: none;">← WAPAS</button>
          <button class="btn btn-orange" onclick="submitRegistration()" style="flex:2;">🎉 SUBMIT REGISTRATION</button>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ==================== ADMIN PAGE ==================== -->
<div id="page-admin" class="page">

  <!-- LOGIN FORM -->
  <div id="admin-login" class="admin-login">
    <div class="admin-header-box">
      <div class="icon">🔐</div>
      <h2>Admin Login</h2>
      <p style="color: var(--muted); font-size: 13px; margin-top: 4px;">Admin Panel Access</p>
    </div>
    <div class="card">
      <div id="login-error" class="alert alert-error" style="display:none;"></div>
      <div class="form-group">
        <label>Admin ID / Username</label>
        <input type="text" id="admin-user" placeholder="Username">
      </div>
      <div class="form-group">
        <label>Password</label>
        <input type="password" id="admin-pass" placeholder="Password" onkeypress="if(event.key==='Enter') adminLogin()">
      </div>
      <button class="btn btn-primary" onclick="adminLogin()">🔓 LOGIN</button>
    </div>
  </div>

  <!-- ADMIN DASHBOARD -->
  <div id="admin-dashboard" style="display:none;">
    <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:16px;">
      <div>
        <div style="font-family: 'Bebas Neue', sans-serif; font-size: 22px; letter-spacing: 2px; color: var(--green);">ADMIN PANEL</div>
        <div style="font-size: 12px; color: var(--muted);">KPL 2025 Management</div>
      </div>
      <button onclick="adminLogout()" style="background: rgba(255,61,61,0.1); border: 1px solid rgba(255,61,61,0.3); color: var(--red); padding: 8px 14px; border-radius: 8px; cursor: pointer; font-size: 13px; font-weight: 700;">Logout</button>
    </div>

    <!-- TAB NAV -->
    <div style="display:flex; gap:0; margin-bottom:16px; border-radius:8px; overflow:hidden; border: 1px solid var(--border);">
      <button class="admin-tab active" onclick="showAdminTab('players')" id="atab-players">👥 Players</button>
      <button class="admin-tab" onclick="showAdminTab('settings')" id="atab-settings">⚙️ Settings</button>
    </div>

    <!-- PLAYERS TAB -->
    <div id="atab-content-players">
      <div class="stats-row">
        <div class="stat-box">
          <span class="num num-gold" id="stat-total">0</span>
          <span class="lbl">Total</span>
        </div>
        <div class="stat-box">
          <span class="num num-green" id="stat-approved">0</span>
          <span class="lbl">Approved</span>
        </div>
        <div class="stat-box">
          <span class="num num-orange" id="stat-pending">0</span>
          <span class="lbl">Pending</span>
        </div>
      </div>

      <div class="card">
        <div class="search-bar">
          <input type="text" id="search-input" placeholder="🔍 Player search karo..." oninput="renderPlayersTable()">
        </div>

        <div class="players-list">
          <table class="players-table">
            <thead>
              <tr>
                <th>#</th>
                <th>Name</th>
                <th>Mobile</th>
                <th>Role</th>
                <th>Status</th>
                <th>Action</th>
              </tr>
            </thead>
            <tbody id="players-tbody"></tbody>
          </table>
          <div id="no-players" class="no-data" style="display:none;">
            <div class="icon">🏏</div>
            <div>Koi registered player nahi hai abhi.</div>
          </div>
        </div>
      </div>

      <button class="btn btn-primary" onclick="exportCSV()" style="background: linear-gradient(135deg, #1a3a5c, #1565c0);">
        📥 CSV Export Karo
      </button>
    </div>

    <!-- SETTINGS TAB -->
    <div id="atab-content-settings" style="display:none;">

      <div class="card">
        <div class="card-title">🏆 Tournament Settings</div>

        <div class="settings-section">
          <div class="form-group">
            <label>Tournament Name</label>
            <input type="text" id="s-name" placeholder="Tournament ka naam">
          </div>
          <div class="form-row">
            <div class="form-group">
              <label>Entry Fee (₹)</label>
              <input type="number" id="s-fee" placeholder="200" min="0">
            </div>
            <div class="form-group">
              <label>Max Players</label>
              <input type="number" id="s-slots" placeholder="50" min="1">
            </div>
          </div>
          <div class="form-row">
            <div class="form-group">
              <label>Start Date</label>
              <input type="date" id="s-start">
            </div>
            <div class="form-group">
              <label>Registration Deadline</label>
              <input type="date" id="s-deadline">
            </div>
          </div>
          <div class="form-group">
            <label>Venue / Maidan</label>
            <input type="text" id="s-venue" placeholder="Tournament ka maidan">
          </div>
          <div class="form-row">
            <div class="form-group">
              <label>Contact Number</label>
              <input type="tel" id="s-contact" placeholder="Contact">
            </div>
            <div class="form-group">
              <label>Prize Pool</label>
              <input type="text" id="s-prize" placeholder="e.g. ₹10,000">
            </div>
          </div>
          <div class="form-group">
            <label>Additional Info</label>
            <textarea id="s-info" placeholder="Koi bhi zaruri information..."></textarea>
          </div>
        </div>

        <div class="divider"></div>

        <div class="settings-section">
          <h3>💳 Payment Settings</h3>
          <div class="form-group">
            <label>UPI ID</label>
            <input type="text" id="s-upi" placeholder="yourname@upi">
          </div>
          <div class="form-group">
            <label>QR Code Image (Upload)</label>
            <div class="upload-area" onclick="document.getElementById('qr-upload').click()">
              <input type="file" id="qr-upload" accept="image/*" onchange="handleQRUpload(this)">
              <div class="upload-icon">📱</div>
              <div class="upload-text">QR Code image upload karo</div>
            </div>
            <div id="qr-preview" style="display:none; margin-top:10px;">
              <img id="qr-preview-img" style="width:120px; height:120px; border-radius:8px; border:1px solid var(--green); object-fit:contain; background:white;">
            </div>
          </div>
        </div>

        <div class="divider"></div>

        <div class="settings-section">
          <h3>🔐 Admin Credentials Update</h3>
          <div class="form-group">
            <label>New Username</label>
            <input type="text" id="s-new-user" placeholder="New username">
          </div>
          <div class="form-group">
            <label>Current Password *</label>
            <input type="password" id="s-curr-pass" placeholder="Current password">
          </div>
          <div class="form-group">
            <label>New Password</label>
            <input type="password" id="s-new-pass" placeholder="New password">
          </div>
          <div class="form-group">
            <label>Confirm New Password</label>
            <input type="password" id="s-conf-pass" placeholder="Confirm password">
          </div>
        </div>

        <div id="settings-alert" style="display:none;" class="alert"></div>
        <button class="btn btn-primary" onclick="saveSettings()">💾 SETTINGS SAVE KARO</button>
      </div>
    </div>
  </div>
</div>

<!-- ==================== PLAYER DETAIL MODAL ==================== -->
<div class="modal-overlay" id="player-modal">
  <div class="modal">
    <div style="display:flex; justify-content:space-between; align-items:flex-start; margin-bottom:12px;">
      <div class="modal-title" id="modal-player-name">Player Details</div>
      <button class="modal-close" onclick="closeModal()">✕</button>
    </div>
    <div id="modal-body"></div>
  </div>
</div>

<style>
  .admin-tab {
    flex: 1; padding: 11px 8px;
    background: var(--card2); border: none;
    color: var(--muted); cursor: pointer;
    font-family: 'Rajdhani', sans-serif;
    font-size: 13px; font-weight: 700;
    transition: all 0.2s; letter-spacing: 0.5px;
    border-right: 1px solid var(--border);
  }
  .admin-tab:last-child { border-right: none; }
  .admin-tab.active { background: rgba(0,200,83,0.1); color: var(--green); }
</style>

<script>
// ============================================================
//  STATE & STORAGE
// ============================================================
const STORAGE_KEY = 'kpl_data';

function loadData() {
  try {
    const raw = localStorage.getItem(STORAGE_KEY);
    return raw ? JSON.parse(raw) : getDefaultData();
  } catch(e) { return getDefaultData(); }
}

function saveData(data) {
  try { localStorage.setItem(STORAGE_KEY, JSON.stringify(data)); } catch(e) {}
}

function getDefaultData() {
  return {
    admin: { username: 'admin', password: 'kpl2025' },
    settings: {
      tournamentName: 'Khalwada Pride League 2025',
      fee: 200,
      slots: 50,
      startDate: '',
      deadline: '',
      venue: 'Khalwada Ground',
      contact: '',
      prize: '',
      info: '',
      upiId: '9876543210@paytm',
      qrCode: ''
    },
    players: []
  };
}

let state = loadData();
let proofFileData = null;
let regStep = 1;

// ============================================================
//  NAVIGATION
// ============================================================
function showPage(page) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
  document.getElementById('page-' + page).classList.add('active');
  const btns = document.querySelectorAll('.nav-btn');
  const map = { home: 0, register: 1, admin: 2 };
  btns[map[page]].classList.add('active');

  if (page === 'home') updateHome();
  if (page === 'admin') updatePaymentInfo();
}

// ============================================================
//  HOME
// ============================================================
function updateHome() {
  const s = state.settings;
  const reg = state.players.length;

  document.getElementById('home-fee').textContent = '₹' + s.fee;
  document.getElementById('home-slots').textContent = s.slots;
  document.getElementById('home-registered').textContent = reg;

  if (s.deadline) {
    const d = new Date(s.deadline);
    document.getElementById('home-deadline').textContent =
      d.getDate() + ' ' + d.toLocaleString('en', {month:'short'});
  }

  document.getElementById('home-venue').textContent = s.venue || '—';
  document.getElementById('home-contact').textContent = s.contact || '—';
  document.getElementById('home-prize').textContent = s.prize || 'TBD';

  if (s.startDate) {
    const d = new Date(s.startDate);
    document.getElementById('home-start').textContent =
      d.getDate() + ' ' + d.toLocaleString('en', {month:'long'}) + ' ' + d.getFullYear();
  }

  if (s.info) {
    document.getElementById('home-extra-info').textContent = s.info;
  }
}

// ============================================================
//  PAYMENT INFO UPDATE
// ============================================================
function updatePaymentInfo() {
  const s = state.settings;
  const upiEl = document.getElementById('pay-upi-display');
  const feeEl = document.getElementById('pay-fee-display');
  const qrImg = document.getElementById('qr-img-display');
  const qrDef = document.getElementById('qr-default-text');

  if (upiEl) upiEl.textContent = s.upiId || '9876543210@paytm';
  if (feeEl) feeEl.textContent = '₹' + (s.fee || 200);

  if (s.qrCode && qrImg) {
    qrImg.src = s.qrCode;
    qrImg.style.display = 'block';
    if (qrDef) qrDef.style.display = 'none';
  }
}

// ============================================================
//  REGISTRATION STEPS
// ============================================================
function nextStep(current) {
  if (current === 1) {
    const name = document.getElementById('r-name').value.trim();
    const age = document.getElementById('r-age').value;
    const mob = document.getElementById('r-mobile').value.trim();

    if (!name) return alert('Naam bharo!');
    if (!age || age < 10 || age > 60) return alert('Sahi age bharo (10-60)!');
    if (!mob || mob.length < 10) return alert('10 digit mobile number bharo!');
  }

  if (current === 2) {
    const role = document.getElementById('r-role').value;
    if (!role) return alert('Playing role select karo!');
  }

  updatePaymentInfo();

  document.getElementById('form-step-' + current).classList.remove('active');
  document.getElementById('form-step-' + (current + 1)).classList.add('active');
  document.getElementById('step-' + current).classList.remove('active');
  document.getElementById('step-' + current).classList.add('done');
  document.getElementById('step-' + (current + 1)).classList.add('active');
  regStep = current + 1;
}

function prevStep(current) {
  document.getElementById('form-step-' + current).classList.remove('active');
  document.getElementById('form-step-' + (current - 1)).classList.add('active');
  document.getElementById('step-' + current).classList.remove('active');
  document.getElementById('step-' + (current - 1)).classList.remove('done');
  document.getElementById('step-' + (current - 1)).classList.add('active');
  regStep = current - 1;
}

// ============================================================
//  PROOF UPLOAD
// ============================================================
function handleProofUpload(input) {
  const file = input.files[0];
  if (!file) return;
  if (file.size > 5 * 1024 * 1024) return alert('File 5MB se badi hai!');

  const reader = new FileReader();
  reader.onload = function(e) {
    proofFileData = e.target.result;
    document.getElementById('proof-preview').style.display = 'flex';
    document.getElementById('proof-filename').textContent = file.name;
  };
  reader.readAsDataURL(file);
}

function handleQRUpload(input) {
  const file = input.files[0];
  if (!file) return;
  const reader = new FileReader();
  reader.onload = function(e) {
    state.settings.qrCode = e.target.result;
    saveData(state);
    const prev = document.getElementById('qr-preview');
    const img = document.getElementById('qr-preview-img');
    prev.style.display = 'block';
    img.src = e.target.result;
  };
  reader.readAsDataURL(file);
}

// ============================================================
//  SUBMIT REGISTRATION
// ============================================================
function submitRegistration() {
  const txn = document.getElementById('r-txn').value.trim();
  if (!txn) return alert('Transaction ID bharo!');
  if (!proofFileData) return alert('Payment proof upload karo!');

  const id = 'KPL-' + String(state.players.length + 1).padStart(4, '0');

  const player = {
    id,
    name: document.getElementById('r-name').value.trim(),
    age: document.getElementById('r-age').value,
    mobile: document.getElementById('r-mobile').value.trim(),
    address: document.getElementById('r-address').value.trim(),
    email: document.getElementById('r-email').value.trim(),
    batting: document.getElementById('r-batting').value,
    bowling: document.getElementById('r-bowling').value,
    role: document.getElementById('r-role').value,
    jersey: document.getElementById('r-jersey').value,
    experience: document.getElementById('r-experience').value,
    txnId: txn,
    proof: proofFileData,
    status: 'pending',
    timestamp: new Date().toLocaleString('en-IN'),
    fee: state.settings.fee
  };

  state.players.push(player);
  saveData(state);

  document.getElementById('reg-id-display').textContent = id;
  document.getElementById('reg-form-container').style.display = 'none';
  document.getElementById('reg-success').style.display = 'block';
}

function resetRegistration() {
  proofFileData = null;
  document.getElementById('reg-form-container').style.display = 'block';
  document.getElementById('reg-success').style.display = 'none';

  ['r-name','r-age','r-mobile','r-address','r-email','r-batting','r-bowling','r-role','r-jersey','r-experience','r-txn'].forEach(id => {
    const el = document.getElementById(id);
    if (el) el.value = '';
  });

  document.getElementById('proof-preview').style.display = 'none';

  for (let i = 1; i <= 3; i++) {
    document.getElementById('form-step-' + i).classList.remove('active');
    document.getElementById('step-' + i).classList.remove('active', 'done');
  }
  document.getElementById('form-step-1').classList.add('active');
  document.getElementById('step-1').classList.add('active');
  regStep = 1;
}

// ============================================================
//  COPY UPI
// ============================================================
function copyUPI() {
  const upi = document.getElementById('pay-upi-display').textContent;
  navigator.clipboard.writeText(upi).then(() => {
    alert('UPI ID copy ho gaya: ' + upi);
  }).catch(() => {
    prompt('Copy karo:', upi);
  });
}

// ============================================================
//  ADMIN LOGIN
// ============================================================
function adminLogin() {
  const user = document.getElementById('admin-user').value.trim();
  const pass = document.getElementById('admin-pass').value;
  const errEl = document.getElementById('login-error');

  if (user === state.admin.username && pass === state.admin.password) {
    document.getElementById('admin-login').style.display = 'none';
    document.getElementById('admin-dashboard').style.display = 'block';
    loadAdminSettings();
    renderPlayersTable();
    updateStats();
  } else {
    errEl.style.display = 'block';
    errEl.textContent = '❌ Wrong username ya password!';
    document.getElementById('admin-pass').value = '';
  }
}

function adminLogout() {
  document.getElementById('admin-dashboard').style.display = 'none';
  document.getElementById('admin-login').style.display = 'block';
  document.getElementById('admin-user').value = '';
  document.getElementById('admin-pass').value = '';
  document.getElementById('login-error').style.display = 'none';
}

// ============================================================
//  ADMIN TABS
// ============================================================
function showAdminTab(tab) {
  ['players', 'settings'].forEach(t => {
    document.getElementById('atab-content-' + t).style.display = 'none';
    document.getElementById('atab-' + t).classList.remove('active');
  });
  document.getElementById('atab-content-' + tab).style.display = 'block';
  document.getElementById('atab-' + tab).classList.add('active');

  if (tab === 'players') { renderPlayersTable(); updateStats(); }
}

// ============================================================
//  STATS
// ============================================================
function updateStats() {
  const players = state.players;
  document.getElementById('stat-total').textContent = players.length;
  document.getElementById('stat-approved').textContent = players.filter(p => p.status === 'approved').length;
  document.getElementById('stat-pending').textContent = players.filter(p => p.status === 'pending').length;
}

// ============================================================
//  PLAYERS TABLE
// ============================================================
function renderPlayersTable() {
  const query = (document.getElementById('search-input')?.value || '').toLowerCase();
  const players = state.players.filter(p =>
    p.name.toLowerCase().includes(query) ||
    p.mobile.includes(query) ||
    p.id.toLowerCase().includes(query)
  );

  const tbody = document.getElementById('players-tbody');
  const noData = document.getElementById('no-players');

  if (players.length === 0) {
    tbody.innerHTML = '';
    noData.style.display = 'block';
  } else {
    noData.style.display = 'none';
    tbody.innerHTML = players.map((p, i) => `
      <tr>
        <td style="color:var(--muted); font-size:12px;">${p.id}</td>
        <td><strong>${p.name}</strong></td>
        <td style="color:var(--muted);">${p.mobile}</td>
        <td><span class="tag">${p.role || '—'}</span></td>
        <td><span class="status-badge status-${p.status}">${p.status.toUpperCase()}</span></td>
        <td><button class="btn btn-small btn-primary" onclick="openPlayerModal('${p.id}')">👁 View</button></td>
      </tr>
    `).join('');
  }

  updateStats();
}

// ============================================================
//  PLAYER MODAL
// ============================================================
function openPlayerModal(playerId) {
  const p = state.players.find(x => x.id === playerId);
  if (!p) return;

  document.getElementById('modal-player-name').textContent = '🏏 ' + p.name;

  const statusColor = p.status === 'approved' ? 'num-green' : p.status === 'rejected' ? '' : 'num-gold';

  document.getElementById('modal-body').innerHTML = `
    <div class="detail-row"><span class="detail-label">Registration ID</span><span class="detail-value" style="color:var(--gold);">${p.id}</span></div>
    <div class="detail-row"><span class="detail-label">Name</span><span class="detail-value">${p.name}</span></div>
    <div class="detail-row"><span class="detail-label">Age</span><span class="detail-value">${p.age}</span></div>
    <div class="detail-row"><span class="detail-label">Mobile</span><span class="detail-value">${p.mobile}</span></div>
    <div class="detail-row"><span class="detail-label">Address</span><span class="detail-value">${p.address || '—'}</span></div>
    <div class="detail-row"><span class="detail-label">Email</span><span class="detail-value">${p.email || '—'}</span></div>
    <div class="detail-row"><span class="detail-label">Role</span><span class="detail-value">${p.role}</span></div>
    <div class="detail-row"><span class="detail-label">Batting</span><span class="detail-value">${p.batting || '—'}</span></div>
    <div class="detail-row"><span class="detail-label">Bowling</span><span class="detail-value">${p.bowling || '—'}</span></div>
    <div class="detail-row"><span class="detail-label">Experience</span><span class="detail-value">${p.experience || '—'}</span></div>
    <div class="detail-row"><span class="detail-label">Jersey #</span><span class="detail-value">${p.jersey || '—'}</span></div>
    <div class="detail-row"><span class="detail-label">Fee Paid</span><span class="detail-value" style="color:var(--green);">₹${p.fee}</span></div>
    <div class="detail-row"><span class="detail-label">Txn ID</span><span class="detail-value" style="color:var(--gold);">${p.txnId}</span></div>
    <div class="detail-row"><span class="detail-label">Registered</span><span class="detail-value">${p.timestamp}</span></div>
    <div class="detail-row"><span class="detail-label">Status</span><span class="detail-value"><span class="status-badge status-${p.status}">${p.status.toUpperCase()}</span></span></div>

    <div style="margin-top:14px;">
      <div style="font-size:12px; color:var(--muted); text-transform:uppercase; letter-spacing:1px; margin-bottom:6px;">💳 Payment Proof</div>
      ${p.proof ? `<img src="${p.proof}" class="proof-img" alt="Payment Proof">` : '<div style="color:var(--muted); font-size:13px;">Proof nahi mila</div>'}
    </div>

    <div class="action-btns" style="margin-top:16px;">
      <button class="btn-approve" onclick="updateStatus('${p.id}', 'approved')">✅ Approve</button>
      <button class="btn-reject" onclick="updateStatus('${p.id}', 'rejected')">❌ Reject</button>
    </div>
  `;

  document.getElementById('player-modal').classList.add('open');
}

function closeModal() {
  document.getElementById('player-modal').classList.remove('open');
}

function updateStatus(playerId, status) {
  const idx = state.players.findIndex(p => p.id === playerId);
  if (idx !== -1) {
    state.players[idx].status = status;
    saveData(state);
    closeModal();
    renderPlayersTable();
    updateStats();
    alert(`Player ${status === 'approved' ? 'Approve' : 'Reject'} ho gaya! ✅`);
  }
}

// ============================================================
//  SETTINGS
// ============================================================
function loadAdminSettings() {
  const s = state.settings;
  document.getElementById('s-name').value = s.tournamentName || '';
  document.getElementById('s-fee').value = s.fee || 200;
  document.getElementById('s-slots').value = s.slots || 50;
  document.getElementById('s-start').value = s.startDate || '';
  document.getElementById('s-deadline').value = s.deadline || '';
  document.getElementById('s-venue').value = s.venue || '';
  document.getElementById('s-contact').value = s.contact || '';
  document.getElementById('s-prize').value = s.prize || '';
  document.getElementById('s-info').value = s.info || '';
  document.getElementById('s-upi').value = s.upiId || '';

  if (s.qrCode) {
    document.getElementById('qr-preview').style.display = 'block';
    document.getElementById('qr-preview-img').src = s.qrCode;
  }
}

function saveSettings() {
  const alertEl = document.getElementById('settings-alert');

  // Password change logic
  const currPass = document.getElementById('s-curr-pass').value;
  const newPass = document.getElementById('s-new-pass').value;
  const confPass = document.getElementById('s-conf-pass').value;
  const newUser = document.getElementById('s-new-user').value.trim();

  if (currPass || newPass || confPass || newUser) {
    if (!currPass) {
      alertEl.className = 'alert alert-error';
      alertEl.style.display = 'block';
      alertEl.textContent = '❌ Current password bharo!';
      return;
    }
    if (currPass !== state.admin.password) {
      alertEl.className = 'alert alert-error';
      alertEl.style.display = 'block';
      alertEl.textContent = '❌ Current password galat hai!';
      return;
    }
    if (newPass && newPass !== confPass) {
      alertEl.className = 'alert alert-error';
      alertEl.style.display = 'block';
      alertEl.textContent = '❌ New passwords match nahi kar rahe!';
      return;
    }
    if (newUser) state.admin.username = newUser;
    if (newPass) state.admin.password = newPass;
  }

  // Save settings
  state.settings = {
    ...state.settings,
    tournamentName: document.getElementById('s-name').value.trim(),
    fee: parseInt(document.getElementById('s-fee').value) || 200,
    slots: parseInt(document.getElementById('s-slots').value) || 50,
    startDate: document.getElementById('s-start').value,
    deadline: document.getElementById('s-deadline').value,
    venue: document.getElementById('s-venue').value.trim(),
    contact: document.getElementById('s-contact').value.trim(),
    prize: document.getElementById('s-prize').value.trim(),
    info: document.getElementById('s-info').value.trim(),
    upiId: document.getElementById('s-upi').value.trim(),
  };

  saveData(state);

  // Clear password fields
  ['s-curr-pass', 's-new-pass', 's-conf-pass', 's-new-user'].forEach(id => {
    document.getElementById(id).value = '';
  });

  alertEl.className = 'alert alert-success';
  alertEl.style.display = 'block';
  alertEl.textContent = '✅ Settings save ho gayi! Changes apply ho gaye.';

  setTimeout(() => { alertEl.style.display = 'none'; }, 3000);
}

// ============================================================
//  CSV EXPORT
// ============================================================
function exportCSV() {
  if (state.players.length === 0) return alert('Koi player nahi hai export karne ke liye!');

  const headers = ['ID', 'Name', 'Age', 'Mobile', 'Address', 'Email', 'Role', 'Batting', 'Bowling', 'Experience', 'Jersey', 'Fee', 'Txn ID', 'Status', 'Date'];
  const rows = state.players.map(p => [
    p.id, p.name, p.age, p.mobile, p.address || '', p.email || '',
    p.role, p.batting || '', p.bowling || '', p.experience || '',
    p.jersey || '', p.fee, p.txnId, p.status, p.timestamp
  ].map(v => `"${String(v).replace(/"/g, '""')}"`).join(','));

  const csv = [headers.join(','), ...rows].join('\n');
  const blob = new Blob([csv], { type: 'text/csv;charset=utf-8;' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url; a.download = 'KPL_Players_' + new Date().toISOString().slice(0,10) + '.csv';
  a.click();
  URL.revokeObjectURL(url);
}

// ============================================================
//  MODAL CLOSE ON OVERLAY CLICK
// ============================================================
document.getElementById('player-modal').addEventListener('click', function(e) {
  if (e.target === this) closeModal();
});

// ============================================================
//  INIT
// ============================================================
updateHome();
</script>

</body>
</html>
