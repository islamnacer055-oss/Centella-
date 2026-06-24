# Centella-
Centella
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Madagascar Centella - Travel Kit</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;900&display=swap');

  :root {
    --pink: #e8a0b0;
    --pink-dark: #c0566e;
    --pink-light: #fce8ef;
    --brown: #b8864e;
    --brown-dark: #7a5530;
    --brown-light: #f5ede0;
    --white: #ffffff;
    --text: #2a1a0e;
    --muted: #7a6655;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Cairo', sans-serif;
    background: #faf8f6;
    color: var(--text);
    overflow-x: hidden;
  }

  /* HERO */
  .hero {
    background: linear-gradient(135deg, #fce8ef 0%, #f5ede0 100%);
    text-align: center;
    padding: 48px 20px 36px;
    border-bottom: 1px solid #e8d5c0;
  }
  .hero .brand {
    font-size: 13px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 8px;
  }
  .hero h1 {
    font-size: clamp(26px, 6vw, 44px);
    font-weight: 900;
    line-height: 1.2;
    color: var(--text);
    margin-bottom: 12px;
  }
  .hero p {
    font-size: 16px;
    color: var(--muted);
    max-width: 480px;
    margin: 0 auto 32px;
  }

  /* PRODUCT CARDS */
  .products-section {
    padding: 40px 16px;
    max-width: 700px;
    margin: 0 auto;
    text-align: center;
  }
  .products-section h2 {
    font-size: 20px;
    color: var(--muted);
    font-weight: 600;
    margin-bottom: 24px;
  }
  .products-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }
  .product-card {
    border-radius: 20px;
    padding: 28px 20px 24px;
    cursor: pointer;
    transition: transform 0.2s, box-shadow 0.2s;
    border: 2.5px solid transparent;
    position: relative;
    overflow: hidden;
  }
  .product-card:hover { transform: translateY(-4px); box-shadow: 0 12px 32px rgba(0,0,0,0.12); }
  .product-card.pink-card {
    background: linear-gradient(160deg, #fce8ef 0%, #f7d0dc 100%);
    border-color: var(--pink);
  }
  .product-card.brown-card {
    background: linear-gradient(160deg, #f5ede0 0%, #ead5b8 100%);
    border-color: var(--brown);
  }
  .product-card.active {
    box-shadow: 0 0 0 3px currentColor, 0 12px 32px rgba(0,0,0,0.15);
  }
  .product-card.pink-card.active { box-shadow: 0 0 0 3px var(--pink-dark), 0 12px 32px rgba(192,86,110,0.2); }
  .product-card.brown-card.active { box-shadow: 0 0 0 3px var(--brown-dark), 0 12px 32px rgba(122,85,48,0.2); }
  .card-badge {
    display: inline-block;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 2px;
    padding: 4px 12px;
    border-radius: 20px;
    margin-bottom: 12px;
  }
  .pink-card .card-badge { background: var(--pink-dark); color: white; }
  .brown-card .card-badge { background: var(--brown-dark); color: white; }
  .card-name {
    font-size: 18px;
    font-weight: 900;
    margin-bottom: 6px;
  }
  .pink-card .card-name { color: var(--pink-dark); }
  .brown-card .card-name { color: var(--brown-dark); }
  .card-sub {
    font-size: 13px;
    color: var(--muted);
    margin-bottom: 16px;
  }
  .card-price {
    font-size: 28px;
    font-weight: 900;
  }
  .pink-card .card-price { color: var(--pink-dark); }
  .brown-card .card-price { color: var(--brown-dark); }
  .card-price span { font-size: 14px; font-weight: 600; }
  .card-cta {
    display: block;
    margin-top: 16px;
    padding: 10px;
    border-radius: 12px;
    font-family: 'Cairo', sans-serif;
    font-size: 14px;
    font-weight: 700;
    cursor: pointer;
    border: none;
    transition: opacity 0.2s;
  }
  .card-cta:hover { opacity: 0.85; }
  .pink-card .card-cta { background: var(--pink-dark); color: white; }
  .brown-card .card-cta { background: var(--brown-dark); color: white; }

  /* PRODUCT DETAIL SECTION */
  .detail-section {
    display: none;
    max-width: 680px;
    margin: 0 auto;
    padding: 0 16px 40px;
    animation: fadeSlide 0.4s ease;
  }
  .detail-section.visible { display: block; }
  @keyframes fadeSlide {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .detail-card {
    border-radius: 24px;
    padding: 28px 24px;
    margin-bottom: 24px;
  }
  .detail-card.pink-bg { background: linear-gradient(135deg, #fce8ef, #f7d0dc); border: 2px solid var(--pink); }
  .detail-card.brown-bg { background: linear-gradient(135deg, #f5ede0, #ead5b8); border: 2px solid var(--brown); }
  .detail-card img {
    width: 100%;
    max-width: 340px;
    display: block;
    margin: 0 auto 20px;
    border-radius: 16px;
    box-shadow: 0 8px 24px rgba(0,0,0,0.12);
  }
  .detail-card h3 {
    font-size: 22px;
    font-weight: 900;
    text-align: center;
    margin-bottom: 8px;
  }
  .pink-bg h3 { color: var(--pink-dark); }
  .brown-bg h3 { color: var(--brown-dark); }
  .skin-type {
    text-align: center;
    font-size: 14px;
    color: var(--muted);
    margin-bottom: 16px;
    font-weight: 600;
  }
  .benefits {
    display: flex;
    flex-direction: column;
    gap: 8px;
    margin-bottom: 20px;
  }
  .benefit-item {
    display: flex;
    align-items: center;
    gap: 10px;
    background: rgba(255,255,255,0.6);
    border-radius: 12px;
    padding: 10px 14px;
    font-size: 14px;
    font-weight: 600;
  }
  .benefit-icon { font-size: 20px; }
  .buy-btn {
    display: block;
    width: 100%;
    padding: 16px;
    border-radius: 16px;
    font-family: 'Cairo', sans-serif;
    font-size: 18px;
    font-weight: 900;
    cursor: pointer;
    border: none;
    transition: transform 0.15s, box-shadow 0.15s;
    letter-spacing: 1px;
  }
  .buy-btn:hover { transform: scale(1.02); box-shadow: 0 8px 24px rgba(0,0,0,0.18); }
  .buy-btn.pink { background: linear-gradient(135deg, var(--pink-dark), #a04060); color: white; }
  .buy-btn.brown { background: linear-gradient(135deg, var(--brown-dark), #5a3520); color: white; }

  /* ORDER FORM */
  .order-section {
    display: none;
    max-width: 600px;
    margin: 0 auto;
    padding: 0 16px 60px;
    animation: fadeSlide 0.4s ease;
  }
  .order-section.visible { display: block; }
  .order-card {
    border-radius: 24px;
    background: white;
    padding: 28px 24px;
    box-shadow: 0 4px 24px rgba(0,0,0,0.08);
  }
  .order-card h3 {
    font-size: 20px;
    font-weight: 900;
    margin-bottom: 20px;
    text-align: center;
  }
  .order-card.pink-border { border-top: 5px solid var(--pink-dark); }
  .order-card.brown-border { border-top: 5px solid var(--brown-dark); }
  .form-group { margin-bottom: 16px; }
  .form-group label {
    display: block;
    font-size: 13px;
    font-weight: 700;
    color: var(--muted);
    margin-bottom: 6px;
    letter-spacing: 0.5px;
  }
  .form-group input, .form-group select, .form-group textarea {
    width: 100%;
    padding: 12px 16px;
    border-radius: 12px;
    border: 1.5px solid #e0d5c8;
    font-family: 'Cairo', sans-serif;
    font-size: 15px;
    color: var(--text);
    background: #faf8f6;
    outline: none;
    transition: border-color 0.2s;
    direction: rtl;
  }
  .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
    border-color: var(--pink-dark);
    background: white;
  }
  .form-group.brown-focus input:focus, .form-group.brown-focus select:focus {
    border-color: var(--brown-dark);
  }
  .delivery-options {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    margin-bottom: 16px;
  }
  .delivery-option {
    border: 2px solid #e0d5c8;
    border-radius: 14px;
    padding: 14px 12px;
    text-align: center;
    cursor: pointer;
    transition: all 0.2s;
    background: #faf8f6;
  }
  .delivery-option.selected-pink { border-color: var(--pink-dark); background: var(--pink-light); }
  .delivery-option.selected-brown { border-color: var(--brown-dark); background: var(--brown-light); }
  .delivery-option .icon { font-size: 24px; margin-bottom: 4px; }
  .delivery-option .label { font-size: 13px; font-weight: 700; color: var(--text); }
  .delivery-option .price { font-size: 15px; font-weight: 900; margin-top: 4px; }
  .delivery-option .price.pink-price { color: var(--pink-dark); }
  .delivery-option .price.brown-price { color: var(--brown-dark); }

  .summary-box {
    border-radius: 16px;
    padding: 20px;
    margin: 20px 0;
    text-align: center;
  }
  .summary-box.pink-summary { background: var(--pink-light); border: 2px solid var(--pink); }
  .summary-box.brown-summary { background: var(--brown-light); border: 2px solid var(--brown); }
  .summary-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 15px;
    padding: 6px 0;
    border-bottom: 1px solid rgba(0,0,0,0.07);
  }
  .summary-row:last-of-type { border-bottom: none; }
  .summary-label { color: var(--muted); font-weight: 600; }
  .summary-value { font-weight: 700; }
  .total-row {
    margin-top: 12px;
    padding-top: 12px;
    border-top: 2px solid currentColor;
    font-size: 20px;
    font-weight: 900;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .total-row.pink-total { color: var(--pink-dark); border-color: var(--pink-dark); }
  .total-row.brown-total { color: var(--brown-dark); border-color: var(--brown-dark); }

  .confirm-btn {
    display: block;
    width: 100%;
    padding: 18px;
    border-radius: 16px;
    font-family: 'Cairo', sans-serif;
    font-size: 19px;
    font-weight: 900;
    cursor: pointer;
    border: none;
    transition: transform 0.15s, box-shadow 0.15s;
    margin-top: 8px;
  }
  .confirm-btn:hover { transform: scale(1.02); box-shadow: 0 8px 24px rgba(0,0,0,0.2); }
  .confirm-btn.pink { background: linear-gradient(135deg, var(--pink-dark), #a04060); color: white; }
  .confirm-btn.brown { background: linear-gradient(135deg, var(--brown-dark), #5a3520); color: white; }
  .confirm-btn:disabled { opacity: 0.5; cursor: not-allowed; transform: none; }

  .success-msg {
    display: none;
    text-align: center;
    padding: 32px 20px;
    animation: fadeSlide 0.5s ease;
  }
  .success-msg .icon { font-size: 56px; margin-bottom: 12px; }
  .success-msg h3 { font-size: 24px; font-weight: 900; margin-bottom: 8px; }
  .success-msg p { color: var(--muted); font-size: 15px; }

  /* DIVIDER */
  .section-divider {
    width: 60px;
    height: 3px;
    border-radius: 2px;
    margin: 0 auto 24px;
  }
  .pink-divider { background: var(--pink-dark); }
  .brown-divider { background: var(--brown-dark); }

  @media (max-width: 420px) {
    .products-grid { grid-template-columns: 1fr; }
    .delivery-options { grid-template-columns: 1fr 1fr; }
  }
</style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <p class="brand">Madagascar Centella · SKIN1004</p>
  <h1>بشرة صافية تبدأ من هنا</h1>
  <p>كيت سفر متكامل بقوة سنتيلا المدغشقر — اختر ما يناسب بشرتك</p>
</div>

<!-- PRODUCT SELECTION -->
<div class="products-section">
  <h2>اختر منتجك</h2>
  <div class="products-grid">
    <div class="product-card pink-card" id="card-pink" onclick="selectProduct('pink')">
      <div class="card-badge">TRAVEL KIT</div>
      <div class="card-name">سنتيلا الوردي</div>
      <div class="card-sub">للبشرة الحساسة والمختلطة</div>
      <div class="card-price">4500 <span>دج</span></div>
      <button class="card-cta">اختيار ←</button>
    </div>
    <div class="product-card brown-card" id="card-brown" onclick="selectProduct('brown')">
      <div class="card-badge">TRAVEL KIT</div>
      <div class="card-name">سنتيلا البني</div>
      <div class="card-sub">للبشرة الدهنية والمسامية</div>
      <div class="card-price">4000 <span>دج</span></div>
      <button class="card-cta">اختيار ←</button>
    </div>
  </div>
</div>

<!-- PINK PRODUCT DETAIL -->
<div class="detail-section" id="detail-pink">
  <div class="detail-card pink-bg">
    <img src="/mnt/user-data/uploads/11199.png" alt="سنتيلا الوردي" onerror="this.style.display='none'">
    <h3>🌸 سنتيلا الوردي — Travel Kit</h3>
    <div class="skin-type">✦ مثالي للبشرة الحساسة، المختلطة، والمعرضة لحب الشباب ✦</div>
    <div class="benefits">
      <div class="benefit-item"><span class="benefit-icon">🧴</span> 4 منتجات في بوكس واحد: فوم + تونر + أمبولة + جل كريم</div>
      <div class="benefit-item"><span class="benefit-icon">✈️</span> حجم سفر مثالي — مسموح في حقيبة الكابين</div>
      <div class="benefit-item"><span class="benefit-icon">💊</span> يقلل الاحمرار والتهيج ويرطب بعمق</div>
      <div class="benefit-item"><span class="benefit-icon">⭐</span> روتين عناية كامل في خطوة واحدة</div>
    </div>
    <button class="buy-btn pink" onclick="scrollToOrder('pink')">اشتري الآن — 4500 دج 🛒</button>
  </div>
</div>

<!-- BROWN PRODUCT DETAIL -->
<div class="detail-section" id="detail-brown">
  <div class="detail-card brown-bg">
    <img src="/mnt/user-data/uploads/11197.png" alt="سنتيلا البني" onerror="this.style.display='none'">
    <h3>🤎 سنتيلا البني — Travel Kit</h3>
    <div class="skin-type">✦ مثالي للبشرة الدهنية، المسامية، والمعرضة للرؤوس السوداء ✦</div>
    <div class="benefits">
      <div class="benefit-item"><span class="benefit-icon">🧴</span> 4 منتجات: فوم + تونر + أمبولة + زيت تنظيف + جل كريم</div>
      <div class="benefit-item"><span class="benefit-icon">🔬</span> يضيّق المسام ويعالج الرؤوس السوداء</div>
      <div class="benefit-item"><span class="benefit-icon">💧</span> يوازن الدهون دون تجفيف البشرة</div>
      <div class="benefit-item"><span class="benefit-icon">⭐</span> روتين علاجي متكامل خلال السفر</div>
    </div>
    <button class="buy-btn brown" onclick="scrollToOrder('brown')">اشتري الآن — 4000 دج 🛒</button>
  </div>
</div>

<!-- ORDER FORM -->
<div class="order-section" id="order-section">
  <div class="order-card" id="order-card">
    <h3 id="order-title">🛒 أكمل طلبك</h3>

    <div class="form-group">
      <label>الاسم</label>
      <input type="text" id="fname" placeholder="الاسم الأول">
    </div>
    <div class="form-group">
      <label>اللقب</label>
      <input type="text" id="lname" placeholder="اللقب">
    </div>
    <div class="form-group">
      <label>رقم الهاتف</label>
      <input type="tel" id="phone" placeholder="0xxxxxxxx">
    </div>
    <div class="form-group">
      <label>الولاية</label>
      <select id="wilaya" onchange="updateDelivery()">
        <option value="">— اختر الولاية —</option>
      </select>
    </div>

    <label style="display:block;font-size:13px;font-weight:700;color:var(--muted);margin-bottom:8px;">نوع التوصيل</label>
    <div class="delivery-options">
      <div class="delivery-option" id="opt-home" onclick="selectDelivery('home')">
        <div class="icon">🏠</div>
        <div class="label">توصيل للمنزل</div>
        <div class="price" id="price-home">—</div>
      </div>
      <div class="delivery-option" id="opt-office" onclick="selectDelivery('office')">
        <div class="icon">🏢</div>
        <div class="label">توصيل للمكتب</div>
        <div class="price" id="price-office">—</div>
      </div>
    </div>

    <div class="form-group">
      <label>الدائرة</label>
      <input type="text" id="commune" placeholder="اسم الدائرة أو البلدية">
    </div>
    <div class="form-group">
      <label>العنوان <span style="color:#aaa;font-weight:400;">(اختياري)</span></label>
      <input type="text" id="address" placeholder="العنوان التفصيلي">
    </div>

    <!-- SUMMARY -->
    <div class="summary-box" id="summary-box">
      <div class="summary-row">
        <span class="summary-label">المنتج</span>
        <span class="summary-value" id="sum-product">—</span>
      </div>
      <div class="summary-row">
        <span class="summary-label">سعر المنتج</span>
        <span class="summary-value" id="sum-price">—</span>
      </div>
      <div class="summary-row">
        <span class="summary-label">سعر التوصيل</span>
        <span class="summary-value" id="sum-delivery">—</span>
      </div>
      <div class="total-row" id="sum-total-row">
        <span>المجموع الكلي</span>
        <span id="sum-total">—</span>
      </div>
    </div>

    <button class="confirm-btn" id="confirm-btn" onclick="submitOrder()" disabled>تأكيد الطلب</button>

    <div class="success-msg" id="success-msg">
      <div class="icon">✅</div>
      <h3>تم استلام طلبك!</h3>
      <p>سيتصل بك فريقنا قريباً لتأكيد الطلب والتوصيل</p>
    </div>
  </div>
</div>

<script>
// Wilaya delivery prices: [home, office]
const DELIVERY = {
  "Chlef": [800, 520],
  "Laghouat": [950, 670],
  "Oum El Bouaghi": [700, 520],
  "Batna": [500, 370],
  "Bejaia": [750, 520],
  "Biskra": [800, 570],
  "Bechar": [1100, 720],
  "Blida": [750, 520],
  "Bouira": [750, 520],
  "Tamanrasset": [1600, 1120],
  "Tebessa": [800, 520],
  "Tlemcen": [950, 620],
  "Tiaret": [800, 520],
  "Tizi Ouzou": [800, 520],
  "Alger": [600, 520],
  "Djelfa": [950, 670],
  "Jijel": [800, 520],
  "Sétif": [750, 520],
  "Saida": [800, 570],
  "Skikda": [750, 520],
  "Sidi Bel Abbès": [800, 520],
  "Annaba": [750, 520],
  "Guelma": [750, 520],
  "Constantine": [750, 520],
  "Medea": [800, 520],
  "Mostaganem": [800, 520],
  "M'Sila": [800, 570],
  "Mascara": [800, 520],
  "Ouargla": [950, 670],
  "Oran": [800, 520],
  "El Bayadh": [1100, 670],
  "Illizi": [0, 0],
  "Bordj Bou Arreridj": [750, 520],
  "Boumerdes": [750, 520],
  "El Tarf": [750, 520],
  "Tindouf": [0, 0],
  "Tissemsilt": [800, 520],
  "El Oued": [950, 670],
  "Khenchela": [600, 520],
  "Souk Ahras": [700, 520],
  "Tipaza": [800, 520],
  "Mila": [700, 520],
  "Ain Defla": [800, 520],
  "Naama": [1100, 670],
  "Ain Temouchent": [800, 520],
  "Ghardaia": [950, 670],
  "Relizane": [800, 520],
  "Timimoun": [1400, 970],
  "Bordj Badji Mokhtar": [0, 0],
  "Ouled Djellal": [950, 670],
  "Bêni Abbès": [1000, 970],
  "In Salah": [1600, 0],
  "In Guezzam": [1600, 0],
  "Touggourt": [950, 670],
  "Djanet": [0, 0],
  "M'Ghair": [950, 0],
  "Meniaa": [1000, 0]
};

const PRICES = { pink: 4500, brown: 4000 };
let currentProduct = null;
let selectedDelivery = null;

// Populate wilaya dropdown
const sel = document.getElementById('wilaya');
Object.keys(DELIVERY).forEach(w => {
  const opt = document.createElement('option');
  opt.value = w;
  opt.textContent = w;
  sel.appendChild(opt);
});

function selectProduct(type) {
  currentProduct = type;
  selectedDelivery = null;

  document.querySelectorAll('.product-card').forEach(c => c.classList.remove('active'));
  document.getElementById('card-' + type).classList.add('active');

  // hide both details
  document.getElementById('detail-pink').classList.remove('visible');
  document.getElementById('detail-brown').classList.remove('visible');
  document.getElementById('order-section').classList.remove('visible');

  // show selected
  const detailEl = document.getElementById('detail-' + type);
  detailEl.classList.add('visible');

  setTimeout(() => {
    detailEl.scrollIntoView({ behavior: 'smooth', block: 'start' });
  }, 100);
}

function scrollToOrder(type) {
  currentProduct = type;
  const orderSection = document.getElementById('order-section');
  const orderCard = document.getElementById('order-card');
  const confirmBtn = document.getElementById('confirm-btn');
  const summaryBox = document.getElementById('summary-box');

  // Style based on product
  orderCard.className = 'order-card ' + (type === 'pink' ? 'pink-border' : 'brown-border');
  document.getElementById('order-title').textContent = type === 'pink' ? '🌸 أكملي طلب سنتيلا الوردي' : '🤎 أكمل طلب سنتيلا البني';
  confirmBtn.className = 'confirm-btn ' + type;
  summaryBox.className = 'summary-box ' + (type === 'pink' ? 'pink-summary' : 'brown-summary');
  const totalRow = document.getElementById('sum-total-row');
  totalRow.className = 'total-row ' + (type === 'pink' ? 'pink-total' : 'brown-total');

  // Style delivery prices
  document.querySelectorAll('.delivery-option .price').forEach(p => {
    p.className = 'price ' + (type === 'pink' ? 'pink-price' : 'brown-price');
  });

  // Style form focus
  document.querySelectorAll('.form-group').forEach(g => {
    if (type === 'brown') g.classList.add('brown-focus');
    else g.classList.remove('brown-focus');
  });

  // Reset delivery
  selectedDelivery = null;
  document.querySelectorAll('.delivery-option').forEach(o => o.classList.remove('selected-pink', 'selected-brown'));
  document.getElementById('price-home').textContent = '—';
  document.getElementById('price-office').textContent = '—';

  // Update summary
  document.getElementById('sum-product').textContent = type === 'pink' ? 'سنتيلا الوردي' : 'سنتيلا البني';
  document.getElementById('sum-price').textContent = PRICES[type] + ' دج';
  document.getElementById('sum-delivery').textContent = '—';
  document.getElementById('sum-total').textContent = '—';
  confirmBtn.disabled = true;

  orderSection.classList.add('visible');
  setTimeout(() => orderSection.scrollIntoView({ behavior: 'smooth', block: 'start' }), 100);
}

function updateDelivery() {
  const wilaya = document.getElementById('wilaya').value;
  if (!wilaya || !DELIVERY[wilaya]) return;
  const [home, office] = DELIVERY[wilaya];
  const type = currentProduct;

  document.getElementById('price-home').textContent = home > 0 ? home + ' دج' : 'غير متاح';
  document.getElementById('price-office').textContent = office > 0 ? office + ' دج' : 'غير متاح';

  // Reset delivery if selected was not available
  if (selectedDelivery === 'home' && home === 0) selectDelivery(null);
  if (selectedDelivery === 'office' && office === 0) selectDelivery(null);

  updateTotal();
}

function selectDelivery(type) {
  const wilaya = document.getElementById('wilaya').value;
  if (!wilaya || !DELIVERY[wilaya]) return;
  const [home, office] = DELIVERY[wilaya];
  if (type === 'home' && home === 0) return;
  if (type === 'office' && office === 0) return;

  selectedDelivery = type;
  const t = currentProduct;

  document.getElementById('opt-home').classList.remove('selected-pink', 'selected-brown');
  document.getElementById('opt-office').classList.remove('selected-pink', 'selected-brown');

  if (type) {
    document.getElementById('opt-' + type).classList.add('selected-' + t);
  }
  updateTotal();
}

function updateTotal() {
  const wilaya = document.getElementById('wilaya').value;
  if (!wilaya || !selectedDelivery || !currentProduct) {
    document.getElementById('sum-delivery').textContent = '—';
    document.getElementById('sum-total').textContent = '—';
    document.getElementById('confirm-btn').disabled = true;
    return;
  }
  const [home, office] = DELIVERY[wilaya];
  const deliveryCost = selectedDelivery === 'home' ? home : office;
  const productPrice = PRICES[currentProduct];
  const total = productPrice + deliveryCost;

  document.getElementById('sum-delivery').textContent = deliveryCost + ' دج';
  document.getElementById('sum-total').textContent = total + ' دج';
  document.getElementById('confirm-btn').disabled = false;
}

async function submitOrder() {
  const fname = document.getElementById('fname').value.trim();
  const lname = document.getElementById('lname').value.trim();
  const phone = document.getElementById('phone').value.trim();
  const wilaya = document.getElementById('wilaya').value;
  const commune = document.getElementById('commune').value.trim();
  const address = document.getElementById('address').value.trim();

  if (!fname || !lname || !phone || !wilaya || !selectedDelivery || !commune) {
    alert('يرجى تعبئة جميع الحقول المطلوبة');
    return;
  }

  const btn = document.getElementById('confirm-btn');
  btn.disabled = true;
  btn.textContent = '⏳ جارٍ الإرسال...';

  const [home, office] = DELIVERY[wilaya];
  const deliveryCost = selectedDelivery === 'home' ? home : office;
  const productPrice = PRICES[currentProduct];
  const total = productPrice + deliveryCost;

  const payload = {
    الاسم: fname,
    اللقب: lname,
    الهاتف: phone,
    الولاية: wilaya,
    الدائرة: commune,
    العنوان: address || 'غير محدد',
    المنتج: currentProduct === 'pink' ? 'سنتيلا الوردي (4500 دج)' : 'سنتيلا البني (4000 دج)',
    'نوع التوصيل': selectedDelivery === 'home' ? 'منزل' : 'مكتب',
    'سعر التوصيل': deliveryCost + ' دج',
    'المجموع الكلي': total + ' دج',
    التاريخ: new Date().toLocaleString('ar-DZ')
  };

  try {
    await fetch('https://script.google.com/macros/s/AKfycbzEGKEfvIUyIQVnWcIP5KqzmuQIUgygVX_BcX8-hv8fkzmxwSGvEbvyZFxhEcAL63AW6A/exec', {
      method: 'POST',
      mode: 'no-cors',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(payload)
    });
  } catch (e) {
    console.error('Send error:', e);
  }

  // Show success
  document.getElementById('order-card').innerHTML = `
    <div class="success-msg" style="display:block">
      <div class="icon">✅</div>
      <h3>تم استلام طلبك!</h3>
      <p>سيتصل بك فريقنا قريباً على الرقم <strong>${phone}</strong> لتأكيد الطلب والتوصيل</p>
      <br>
      <p style="color:var(--muted);font-size:13px;">المجموع: <strong>${total} دج</strong></p>
    </div>
  `;
}
</script>
</body>
</html>
