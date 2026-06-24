<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Madagascar Centella - Travel Kit</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Cairo:wght=400;600;700;900&display=swap');
  :root {
    --pink-dark:#c0566e; --pink-light:#fce8ef; --pink:#e8a0b0;
    --brown-dark:#7a5530; --brown-light:#f5ede0; --brown:#b8864e;
    --text:#2a1a0e; --muted:#7a6655;
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  body{font-family:'Cairo',sans-serif;background:#faf8f6;color:var(--text);overflow-x:hidden;}

  .hero{background:linear-gradient(135deg,#fce8ef 0%,#f5ede0 100%);text-align:center;padding:48px 20px 36px;border-bottom:1px solid #e8d5c0;}
  .hero .brand{font-size:12px;letter-spacing:4px;text-transform:uppercase;color:var(--muted);margin-bottom:8px;}
  .hero h1{font-size:clamp(24px,6vw,42px);font-weight:900;line-height:1.2;margin-bottom:10px;}
  .hero p{font-size:15px;color:var(--muted);max-width:460px;margin:0 auto;}

  .products-section{padding:36px 16px;max-width:700px;margin:0 auto;text-align:center;}
  .products-section h2{font-size:19px;color:var(--muted);font-weight:600;margin-bottom:20px;}
  .products-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;}
  .product-card{border-radius:20px;padding:24px 16px 20px;cursor:pointer;transition:transform 0.2s,box-shadow 0.2s;border:2.5px solid transparent;}
  .product-card:hover{transform:translateY(-4px);box-shadow:0 12px 32px rgba(0,0,0,0.12);}
  .product-card.pink-card{background:linear-gradient(160deg,#fce8ef,#f7d0dc);border-color:var(--pink);}
  .product-card.brown-card{background:linear-gradient(160deg,#f5ede0,#ead5b8);border-color:var(--brown);}
  .product-card.pink-card.active{box-shadow:0 0 0 3px var(--pink-dark),0 12px 32px rgba(192,86,110,0.2);}
  .product-card.brown-card.active{box-shadow:0 0 0 3px var(--brown-dark),0 12px 32px rgba(122,85,48,0.2);}
  .card-badge{display:inline-block;font-size:10px;font-weight:700;letter-spacing:2px;padding:3px 10px;border-radius:20px;margin-bottom:10px;}
  .pink-card .card-badge{background:var(--pink-dark);color:white;}
  .brown-card .card-badge{background:var(--brown-dark);color:white;}
  .card-name{font-size:17px;font-weight:900;margin-bottom:5px;}
  .pink-card .card-name{color:var(--pink-dark);}
  .brown-card .card-name{color:var(--brown-dark);}
  .card-sub{font-size:12px;color:var(--muted);margin-bottom:14px;}
  .card-price{font-size:26px;font-weight:900;}
  .pink-card .card-price{color:var(--pink-dark);}
  .brown-card .card-price{color:var(--brown-dark);}
  .card-price span{font-size:13px;font-weight:600;}
  .card-cta{display:block;margin-top:14px;padding:9px;border-radius:12px;font-family:'Cairo',sans-serif;font-size:13px;font-weight:700;cursor:pointer;border:none;}
  .pink-card .card-cta{background:var(--pink-dark);color:white;}
  .brown-card .card-cta{background:var(--brown-dark);color:white;}

  .detail-section{display:none;max-width:680px;margin:0 auto;padding:0 16px 36px;animation:fadeSlide 0.4s ease;}
  .detail-section.visible{display:block;}
  @keyframes fadeSlide{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}
  .detail-card{border-radius:22px;padding:24px 20px;margin-bottom:20px;}
  .detail-card.pink-bg{background:linear-gradient(135deg,#fce8ef,#f7d0dc);border:2px solid var(--pink);}
  .detail-card.brown-bg{background:linear-gradient(135deg,#f5ede0,#ead5b8);border:2px solid var(--brown);}
  .product-img{width:100%;max-width:360px;display:block;margin:0 auto 18px;border-radius:18px;box-shadow:0 10px 30px rgba(0,0,0,0.15);}
  .detail-card h3{font-size:21px;font-weight:900;text-align:center;margin-bottom:6px;}
  .pink-bg h3{color:var(--pink-dark);}
  .brown-bg h3{color:var(--brown-dark);}
  .skin-type{text-align:center;font-size:13px;color:var(--muted);margin-bottom:14px;font-weight:600;}
  .benefits{display:flex;flex-direction:column;gap:7px;margin-bottom:18px;}
  .benefit-item{display:flex;align-items:center;gap:9px;background:rgba(255,255,255,0.65);border-radius:11px;padding:9px 13px;font-size:13px;font-weight:600;}
  .benefit-icon{font-size:18px;}
  .buy-btn{display:block;width:100%;padding:15px;border-radius:15px;font-family:'Cairo',sans-serif;font-size:17px;font-weight:900;cursor:pointer;border:none;transition:transform 0.15s,box-shadow 0.15s;}
  .buy-btn:hover{transform:scale(1.02);box-shadow:0 8px 24px rgba(0,0,0,0.18);}
  .buy-btn.pink{background:linear-gradient(135deg,var(--pink-dark),#a04060);color:white;}
  .buy-btn.brown{background:linear-gradient(135deg,var(--brown-dark),#5a3520);color:white;}

  .order-section{display:none;max-width:580px;margin:0 auto;padding:0 16px 60px;animation:fadeSlide 0.4s ease;}
  .order-section.visible{display:block;}
  .order-card{border-radius:22px;background:white;padding:26px 22px;box-shadow:0 4px 24px rgba(0,0,0,0.08);}
  .order-card h3{font-size:19px;font-weight:900;margin-bottom:18px;text-align:center;}
  .order-card.pink-border{border-top:5px solid var(--pink-dark);}
  .order-card.brown-border{border-top:5px solid var(--brown-dark);}
  .form-group{margin-bottom:14px;}
  .form-group label{display:block;font-size:12px;font-weight:700;color:var(--muted);margin-bottom:5px;}
  .form-group input,.form-group select{width:100%;padding:11px 14px;border-radius:11px;border:1.5px solid #e0d5c8;font-family:'Cairo',sans-serif;font-size:14px;color:var(--text);background:#faf8f6;outline:none;transition:border-color 0.2s;direction:rtl;appearance:none;}
  .form-group input:focus,.form-group select:focus{border-color:var(--pink-dark);background:white;}
  .bf input:focus,.bf select:focus{border-color:var(--brown-dark)!important;}

  .delivery-options{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:14px;}
  .delivery-option{border:2px solid #e0d5c8;border-radius:13px;padding:13px 10px;text-align:center;cursor:pointer;transition:all 0.2s;background:#faf8f6;}
  .delivery-option.sel-pink{border-color:var(--pink-dark);background:var(--pink-light);}
  .delivery-option.sel-brown{border-color:var(--brown-dark);background:var(--brown-light);}
  .delivery-option .dicon{font-size:22px;margin-bottom:3px;}
  .delivery-option .dlabel{font-size:12px;font-weight:700;}
  .delivery-option .dprice{font-size:14px;font-weight:900;margin-top:3px;}
  .pp{color:var(--pink-dark);} .bp{color:var(--brown-dark);}

  .summary-box{border-radius:14px;padding:18px;margin:18px 0;}
  .pink-s{background:var(--pink-light);border:2px solid var(--pink);}
  .brown-s{background:var(--brown-light);border:2px solid var(--brown);}
  .summary-row{display:flex;justify-content:space-between;font-size:14px;padding:5px 0;border-bottom:1px solid rgba(0,0,0,0.07);}
  .summary-row:last-of-type{border-bottom:none;}
  .slabel{color:var(--muted);font-weight:600;}
  .sval{font-weight:700;}
  .total-row{margin-top:10px;padding-top:10px;font-size:19px;font-weight:900;display:flex;justify-content:space-between;border-top:2px solid;}
  .pt{color:var(--pink-dark);border-color:var(--pink-dark);}
  .bt{color:var(--brown-dark);border-color:var(--brown-dark);}

  .confirm-btn{display:block;width:100%;padding:16px;border-radius:14px;font-family:'Cairo',sans-serif;font-size:18px;font-weight:900;cursor:pointer;border:none;transition:transform 0.15s,box-shadow 0.15s;margin-top:6px;}
  .confirm-btn:hover:not(:disabled){transform:scale(1.02);box-shadow:0 8px 24px rgba(0,0,0,0.2);}
  .confirm-btn.pink{background:linear-gradient(135deg,var(--pink-dark),#a04060);color:white;}
  .confirm-btn.brown{background:linear-gradient(135deg,var(--brown-dark),#5a3520);color:white;}
  .confirm-btn:disabled{opacity:0.45;cursor:not-allowed;}
  .success-inner{text-align:center;padding:30px 16px;}
  .success-inner .si{font-size:52px;margin-bottom:10px;}
  .success-inner h3{font-size:22px;font-weight:900;margin-bottom:6px;}
  .success-inner p{color:var(--muted);font-size:14px;}
  @media(max-width:420px){.products-grid{grid-template-columns:1fr;}}
</style>
</head>
<body>

<div class="hero">
  <p class="brand">Madagascar Centella · SKIN1004</p>
  <h1>بشرة صافية تبدأ من هنا</h1>
  <p>كيت سفر متكامل بقوة سنتيلا المدغشقر — اختر ما يناسب بشرتك</p>
</div>

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

<div class="detail-section" id="detail-pink">
  <div class="detail-card pink-bg">
    <img class="product-img" src="pink-kit.png" alt="سنتيلا الوردي">
    <h3>🌸 سنتيلا الوردي — Travel Kit</h3>
    <div class="skin-type">✦ مثالي للبشرة الحساسة، المختلطة، والمعرضة لحب الشباب ✦</div>
    <div class="benefits">
      <div class="benefit-item"><span class="benefit-icon">🧴</span> 4 منتجات: فوم تنظيف + تونر + أمبولة + جل كريم</div>
      <div class="benefit-item"><span class="benefit-icon">✈️</span> حجم سفر مثالي — مسموح في حقيبة الكابين</div>
      <div class="benefit-item"><span class="benefit-icon">💊</span> يقلل الاحمرار والتهيج ويرطب بعمق</div>
      <div class="benefit-item"><span class="benefit-icon">⭐</span> روتين عناية كامل في خطوة واحدة</div>
    </div>
    <button class="buy-btn pink" onclick="scrollToOrder('pink')">اشتري الآن — 4500 دج 🛒</button>
  </div>
</div>

<div class="detail-section" id="detail-brown">
  <div class="detail-card brown-bg">
    <img class="product-img" src="brown-kit.png" alt="سنتيلا البني">
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

<div class="order-section" id="order-section">
  <div class="order-card" id="order-card">
    <h3 id="order-title">🛒 أكمل طلبك</h3>
    <div class="form-group"><label>الاسم</label><input type="text" id="fname" placeholder="الاسم الأول"></div>
    <div class="form-group"><label>اللقب</label><input type="text" id="lname" placeholder="اللقب"></div>
    <div class="form-group"><label>رقم الهاتف</label><input type="tel" id="phone" placeholder="0xxxxxxxx"></div>
    <div class="form-group"><label>الولاية</label><select id="wilaya" onchange="updateDelivery()"><option value="">— اختر الولاية —</option></select></div>
    <label style="display:block;font-size:12px;font-weight:700;color:var(--muted);margin-bottom:7px;">نوع التوصيل</label>
    <div class="delivery-options">
      <div class="delivery-option" id="opt-home" onclick="selectDelivery('home')">
        <div class="dicon">🏠</div><div class="dlabel">توصيل للمنزل</div><div class="dprice" id="price-home">—</div>
      </div>
      <div class="delivery-option" id="opt-office" onclick="selectDelivery('office')">
        <div class="dicon">🏢</div><div class="dlabel">توصيل للمكتب</div><div class="dprice" id="price-office">—</div>
      </div>
    </div>
    <div class="form-group"><label>الدائرة / البلدية</label><input type="text" id="commune" placeholder="اسم الدائرة"></div>
    <div class="form-group"><label>العنوان <span style="color:#bbb;font-weight:400;">(اختياري)</span></label><input type="text" id="address" placeholder="العنوان التفصيلي"></div>
    <div class="summary-box" id="summary-box">
      <div class="summary-row"><span class="slabel">المنتج</span><span class="sval" id="sum-product">—</span></div>
      <div class="summary-row"><span class="slabel">سعر المنتج</span><span class="sval" id="sum-price">—</span></div>
      <div class="summary-row"><span class="slabel">سعر التوصيل</span><span class="sval" id="sum-delivery">—</span></div>
      <div class="total-row" id="sum-total-row"><span>المجموع الكلي</span><span id="sum-total">—</span></div>
    </div>
    <button class="confirm-btn" id="confirm-btn" onclick="submitOrder()" disabled>تأكيد الطلب</button>
  </div>
</div>

<script>
const DELIVERY = {
  "أدرار":[1600,1120],"الشلف":[800,520],"الأغواط":[950,670],"أم البواقي":[700,520],
  "باتنة":[500,370],"بجاية":[750,520],"بسكرة":[800,570],"بشار":[1100,720],
  "البليدة":[750,520],"البويرة":[750,520],"تمنراست":[1600,1120],"تبسة":[800,520],
  "تلمسان":[950,620],"تيارت":[800,520],"تيزي وزو":[800,520],"الجزائر":[600,520],
  "الجلفة":[950,670],"جيجل":[800,520],"سطيف":[750,520],"سعيدة":[800,570],
  "سكيكدة":[750,520],"سيدي بلعباس":[800,520],"عنابة":[750,520],"قالمة":[750,520],
  "قسنطينة":[750,520],"المدية":[800,520],"مستغانم":[800,520],"المسيلة":[800,570],
  "معسكر":[800,520],"ورقلة":[950,670],"وهران":[800,520],"البيض":[1100,670],
  "إليزي":[0,0],"برج بوعريريج":[750,520],"بومرداس":[750,520],"الطارف":[750,520],
  "تندوف":[0,0],"تيسمسيلت":[800,520],"الوادي":[950,670],"خنشلة":[600,520],
  "سوق أهراس":[700,520],"تيبازة":[800,520],"ميلة":[700,520],"عين الدفلى":[800,520],
  "النعامة":[1100,670],"عين تموشنت":[800,520],"غرداية":[950,670],"غليزان":[800,520],
  "تيميمون":[1400,970],"برج باجي مختار":[0,0],"أولاد جلال":[950,670],
  "بني عباس":[1000,970],"عين صالح":[1600,0],"عين قزام":[1600,0],
  "تقرت":[950,670],"جانت":[0,0],"المغير":[950,0],"المنيعة":[1000,0]
};
const PRICES={pink:4500,brown:4000};
let cur=null,dv=null;
const sel=document.getElementById('wilaya');
Object.keys(DELIVERY).forEach(w=>{const o=document.createElement('option');o.value=w;o.textContent=w;sel.appendChild(o);});

function selectProduct(t){
  cur=t;dv=null;
  document.querySelectorAll('.product-card').forEach(c=>c.classList.remove('active'));
  document.getElementById('card-'+t).classList.add('active');
  ['pink','brown'].forEach(x=>document.getElementById('detail-'+x).classList.remove('visible'));
  document.getElementById('order-section').classList.remove('visible');
  const el=document.getElementById('detail-'+t);
  el.classList.add('visible');
  setTimeout(()=>el.scrollIntoView({behavior:'smooth',block:'start'}),100);
}

function scrollToOrder(t){
  cur=t;
  const oc=document.getElementById('order-card'),cb=document.getElementById('confirm-btn'),sb=document.getElementById('summary-box');
  oc.className='order-card '+(t==='pink'?'pink-border':'brown-border');
  document.getElementById('order-title').textContent=t==='pink'?'🌸 أكملي طلب سنتيلا الوردي':'🤎 أكمل طلب سنتيلا البني';
  cb.className='confirm-btn '+t;
  sb.className='summary-box '+(t==='pink'?'pink-s':'brown-s');
  document.getElementById('sum-total-row').className='total-row '+(t==='pink'?'pt':'bt');
  const pc=t==='pink'?'pp':'bp';
  document.getElementById('price-home').className='dprice '+pc;
  document.getElementById('price-office').className='dprice '+pc;
  document.querySelectorAll('.form-group').forEach(g=>t==='brown'?g.classList.add('bf'):g.classList.remove('bf'));
  dv=null;
  ['home','office'].forEach(x=>document.getElementById('opt-'+x).className='delivery-option');
  document.getElementById('price-home').textContent='—';
  document.getElementById('price-office').textContent='—';
  document.getElementById('sum-product').textContent=t==='pink'?'سنتيلا الوردي':'سنتيلا البني';
  document.getElementById('sum-price').textContent=PRICES[t]+' دج';
  document.getElementById('sum-delivery').textContent='—';
  document.getElementById('sum-total').textContent='—';
  cb.disabled=true;
  document.getElementById('order-section').classList.add('visible');
  setTimeout(()=>document.getElementById('order-section').scrollIntoView({behavior:'smooth',block:'start'}),100);
}

function updateDelivery(){
  const w=document.getElementById('wilaya').value;
  if(!w||!DELIVERY[w])return;
  const[h,o]=DELIVERY[w];
  document.getElementById('price-home').textContent=h>0?h+' دج':'غير متاح';
  document.getElementById('price-office').textContent=o>0?o+' دج':'غير متاح';
  if(dv==='home'&&h===0){dv=null;document.getElementById('opt-home').className='delivery-option';}
  if(dv==='office'&&o===0){dv=null;document.getElementById('opt-office').className='delivery-option';}
  updateTotal();
}

function selectDelivery(t){
  const w=document.getElementById('wilaya').value;
  if(!w||!DELIVERY[w])return;
  const[h,o]=DELIVERY[w];
  if(t==='home'&&h===0)return;
  if(t==='office'&&o===0)return;
  dv=t;
  ['home','office'].forEach(x=>document.getElementById('opt-'+x).className='delivery-option');
  document.getElementById('opt-'+t).classList.add('sel-'+cur);
  updateTotal();
}

function updateTotal(){
  const w=document.getElementById('wilaya').value;
  if(!w||!dv||!cur){document.getElementById('sum-delivery').textContent='—';document.getElementById('sum-total').textContent='—';document.getElementById('confirm-btn').disabled=true;return;}
  const[h,o]=DELIVERY[w],dc=dv==='home'?h:o,pp=PRICES[cur];
  document.getElementById('sum-delivery').textContent=dc+' دج';
  document.getElementById('sum-total').textContent=(pp+dc)+' دج';
  document.getElementById('confirm-btn').disabled=false;
}

async function submitOrder(){
  const fname=document.getElementById('fname').value.trim(),lname=document.getElementById('lname').value.trim(),
    phone=document.getElementById('phone').value.trim(),wilaya=document.getElementById('wilaya').value,
    commune=document.getElementById('commune').value.trim(),address=document.getElementById('address').value.trim();
  if(!fname||!lname||!phone||!wilaya||!dv||!commune){alert('يرجى تعبئة جميع الحقول المطلوبة');return;}
  const btn=document.getElementById('confirm-btn');
  btn.disabled=true;btn.textContent='⏳ جارٍ الإرسال...';
  const[h,o]=DELIVERY[wilaya],dc=dv==='home'?h:o,pp=PRICES[cur];

  // إنشاء iframe مخفي لتجاوز CORS
  const iframe=document.createElement('iframe');
  iframe.style.display='none';
  iframe.name='hf';
  document.body.appendChild(iframe);

  // إنشاء form وإرساله عبر iframe للرابط الخاص بك
  const form=document.createElement('form');
  form.method='POST';
  form.action='https://script.google.com/macros/s/AKfycbzEGKEfvIUyIQVnWcIP5KqzmuQIUgygVX_BcX8-hv8fkzmxwSGvEbvyZFxhEcAL63AW6A/exec';
  form.target='hf';
  form.style.display='none';

  const fields={
    'الاسم':fname,'اللقب':lname,'الهاتف':phone,'الولاية':wilaya,'الدائرة':commune,
    'العنوان':address||'غير محدد',
    'المنتج':cur==='pink'?'سنتيلا الوردي (4500 دج)':'سنتيلا البني (4000 دج)',
    'نوع_التوصيل':dv==='home'?'منزل':'مكتب',
    'سعر_التوصيل':dc+' دج',
    'المجموع_الكلي':(pp+dc)+' دج',
    'التاريخ':new Date().toLocaleString('ar-DZ')
  };

  for(const[k,v] of Object.entries(fields)){
    const inp=document.createElement('input');
    inp.type='hidden'; inp.name=k; inp.value=v;
    form.appendChild(inp);
  }

  document.body.appendChild(form);
  form.submit();

  setTimeout(()=>{
    document.getElementById('order-card').innerHTML=`<div class="success-inner"><div class="si">✅</div><h3>تم استلام طلبك!</h3><p>سيتصل بك فريقنا قريباً على الرقم <strong>${phone}</strong></p><br><p style="color:var(--muted);font-size:13px;">المجموع: <strong>${pp+dc} دج</strong></p></div>`;
    try{form.remove();iframe.remove();}catch(e){}
  },2500);
}
</script>
</body>
</html>
