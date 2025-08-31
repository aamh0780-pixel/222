<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>سيت جدورة الماني درجة اولى</title>
  <style>
    body {
      font-family: Tahoma, sans-serif;
      background: #fff;
      margin: 0;
      padding: 0;
      direction: rtl;
    }
    .container {
      max-width: 500px;
      margin: auto;
      padding: 20px;
    }
    .product-img {
      width: 100%;
      border-radius: 12px;
      margin-bottom: 15px;
    }
    h1 {
      font-size: 22px;
      margin-bottom: 10px;
    }
    .price {
      font-size: 18px;
      margin: 10px 0;
    }
    .old-price {
      text-decoration: line-through;
      color: #999;
    }
    .new-price {
      font-weight: bold;
      color: #d32f2f;
    }
    .description {
      background: #f9f9f9;
      padding: 12px;
      border-radius: 10px;
      margin: 15px 0;
      font-size: 14px;
      line-height: 1.6;
    }
    .form-group {
      margin-bottom: 15px;
    }
    input, select, textarea {
      width: 100%;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 14px;
    }
    .quantity {
      display: flex;
      align-items: center;
      margin: 15px 0;
    }
    .quantity button {
      width: 35px;
      height: 35px;
      font-size: 18px;
      border: none;
      background: #ddd;
      cursor: pointer;
      border-radius: 5px;
    }
    .quantity input {
      width: 50px;
      text-align: center;
      border: none;
      font-size: 16px;
    }
    .whatsapp-btn {
      display: block;
      width: 100%;
      background: #25D366;
      color: white;
      text-align: center;
      padding: 15px;
      border-radius: 8px;
      font-size: 18px;
      text-decoration: none;
      transition: background 0.3s;
    }
    .whatsapp-btn:hover {
      background: #20b954;
    }
  </style>
  <script>
    function changeQty(val){
      let qty = document.getElementById("qty");
      let current = parseInt(qty.value);
      if(val === 'plus'){ qty.value = current + 1; }
      else if(val === 'minus' && current > 1){ qty.value = current - 1; }
    }

    function sendToWhatsApp(){
      let name = document.getElementById("name").value.trim();
      let phone = document.getElementById("phone").value.trim();
      let qty = document.getElementById("qty").value;
      let address = document.getElementById("address").value.trim();

      if(name === "" || phone === "" || address === ""){
        alert("يرجى ملء جميع الحقول قبل إتمام الطلب ✅");
        return;
      }

      let message = `طلب جديد:%0Aالاسم: ${name}%0Aالهاتف: ${phone}%0Aالكمية: ${qty}%0Aالعنوان: ${address}`;
      window.open(`https://wa.me/9647738238588?text=${message}`,"_blank");
    }
  </script>
</head>
<body>
  <div class="container">
    <!-- صورة المنتج -->
<img src="4.jpg" alt="سيت جدورة الماني" class="product-img">

    <!-- اسم المنتج والسعر -->
    <h1>سيت جدورة الماني درجة اولى</h1>
    <div class="price">
      <span class="old-price">IQD 65,000</span><br>
      <span class="new-price">IQD 55,000</span>
    </div>

    <!-- وصف / مميزات -->
    <div class="description">
      ✅ تصميم ألماني أنيق ستانلس ستيل عالي الجودة <br>
      ✅ قواعد متعددة الطبقات لتوزيع الحرارة بشكل متساو وسريع <br>
      ✅ مثالي لتحضير الأرز، الحساء، الصلصات، المقليات، والطهي بالبخار <br>
      ✅ سهل التنظيف ويمكن غسله في غسالة الصحون. <br>
    </div>

    <!-- الكمية -->
    <label>عدد القطع:</label>
    <div class="quantity">
      <button onclick="changeQty('minus')">-</button>
      <input type="text" id="qty" value="1" readonly>
      <button onclick="changeQty('plus')">+</button>
    </div>

    <!-- بيانات العميل -->
    <div class="form-group">
      <input type="text" id="name" placeholder="اسمك بالكامل">
    </div>
    <div class="form-group">
      <input type="tel" id="phone" placeholder="رقم الهاتف">
    </div>
    <div class="form-group">
      <textarea id="address" placeholder="العنوان بالتفصيل"></textarea>
    </div>

    <!-- زر واتساب -->
    <a href="javascript:void(0)" onclick="sendToWhatsApp()" class="whatsapp-btn">إتمام الطلب عبر واتساب</a>
  </div>
</body>
</html>
