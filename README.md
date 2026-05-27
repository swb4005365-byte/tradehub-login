# TradeHub Pro — منصة التجارة الإلكترونية العالمية

> **الإصدار**: 11.0.0 | **الحالة**: مكتمل | **آخر تحديث**: R11 — Dual-Channel OTP (Email + WhatsApp)

---

## 🌐 روابط المنصة

| الصفحة | الرابط | الوصف |
|--------|--------|-------|
| الرئيسية | `/index.html` | الصفحة الرئيسية والسلايدر |
| المنتجات | `/products.html` | تصفح وبحث المنتجات |
| تفاصيل المنتج | `/product.html?id={id}` | صفحة المنتج الواحد |
| سلة التسوق | `/cart.html` | إدارة السلة |
| إتمام الطلب | `/checkout.html` | Checkout متعدد الخطوات |
| طلباتي | `/my-orders.html` | تتبع الطلبات |
| المصادقة | `/auth.html` | دخول + تسجيل + Google OAuth |
| البائع | `/seller.html` | لوحة تحكم البائع |
| المدير | `/admin-login.html` → `/admin.html` | لوحة المدير العام (17 قسم) |
| Offline | `/offline.html` | صفحة عدم الاتصال |

---

## ✅ الميزات المكتملة (R1–R11)

### 📡 إرسال OTP بقناتين مزدوجتين — Email + WhatsApp (R11)
- [x] **`sendPhoneOTP()`** في `js/auth.js` تبحث عن بريد المستخدم المسجّل في `registered_users` عبر رقم هاتفه
- [x] **قناة البريد الإلكتروني**: تُظهر البريد المُموَّه (u***@domain.com) + شارة "✓ أُرسل" في واجهة الخطوة 2
- [x] **قناة واتساب**: رابط `wa.me/{phone}?text=رمز+التحقق` يُفتح تلقائياً بعد 1.5 ثانية من إرسال OTP
- [x] **زر "افتح واتساب"** تفاعلي يتحول لـ "✓ فُتح" بعد النقر
- [x] **معالجة المستخدم غير المسجّل**: واتساب فقط (بدون بريد في قاعدة البيانات)
- [x] **`_maskEmail()`** تموّه البريد بأمان للعرض
- [x] **`_buildWaOtpLink()`** مستقلة تعمل حتى بدون `whatsapp.js`
- [x] **Demo badge محسَّن**: يعرض الرمز بخط 28px + توضيح القنوات
- [x] إضافة `countries.js` + `whatsapp.js` لجميع الصفحات: `seller.html`, `checkout.html`, `my-orders.html`, `admin.html`

---

## ✅ الميزات المكتملة (R1–R9)

### 🛒 التجارة الإلكترونية (R1)
- [x] الصفحة الرئيسية مع سلايدر وفئات وعروض
- [x] صفحة المنتجات مع فلاتر وبحث
- [x] صفحة تفاصيل المنتج مع المواصفات
- [x] سلة التسوق مع حساب تلقائي
- [x] Checkout بـ 3 خطوات (عنوان → دفع → تأكيد)
- [x] صفحة طلباتي مع تتبع الحالة

### 🔐 نظام المصادقة (R4 + R8)
- [x] تسجيل حساب جديد (مشتري / بائع)
- [x] تسجيل الدخول بالبريد وكلمة المرور
- [x] **Google OAuth** عبر GIS SDK (بدون Firebase)
- [x] استعادة كلمة المرور بـ OTP
- [x] SHA-256 لتشفير كلمات المرور
- [x] JWT محلي بـ HMAC-SHA256
- [x] موافقة المدير على الحسابات الجديدة
- [x] Auth Guards لحماية الصفحات

### 🛡️ لوحة المدير العام (R2 + R3)
- [x] لوحة رئيسية مع إحصائيات
- [x] إدارة المنتجات والفئات
- [x] إدارة المستخدمين والبائعين
- [x] إدارة الطلبات
- [x] نظام التذاكر والدعم
- [x] إدارة التقييمات
- [x] تقارير ومخططات
- [x] تصدير CSV
- [x] إعدادات المنصة (الشعار، الألوان)

### 🤖 وكيل الذكاء الاصطناعي (R9+R10 — DeepSeek Agent v3.0)
- [x] **DeepSeek API** محرك أساسي (OpenAI-compatible format)
- [x] **Streaming Responses** — عرض الرد كلمة بكلمة (SSE)
- [x] **AIAgent class** — منطق وكيل متعدد الخطوات
- [x] **Tool Simulation** — بحث منتجات، فحص طلبات، حسابات، تحويل عملات
- [x] **قاعدة معرفة موسّعة** 35+ موضوع: علوم، تقنية، برمجة، تاريخ، جغرافيا، رياضيات، اقتصاد، صحة، طبخ، فضاء، رياضة، سفر، لغات، فلسفة، بيئة
- [x] **لوحة إعدادات** DeepSeek مدمجة — إضافة API Key مباشرةً من الواجهة
- [x] **Floating Widget** قابل للسحب في جميع الصفحات
- [x] **اقتراحات سريعة** موسّعة (8 أزرار شاملة)
- [x] **حفظ سجل المحادثة** في localStorage
- [x] **Rule-based Fallback** — يعمل بدون API Key
- [x] **إشعار API Notice** للمستخدمين غير المُعدَّلين
- [x] مؤشر كتابة متحرك
- [x] شارة الرسائل غير المقروءة
- [x] فقاعة ترحيب تلقائية

### 📱 PWA — Progressive Web App (R9 — جديد)
- [x] **manifest.json** كامل مع shortcuts وscreenshots
- [x] **Service Worker** (sw.js) بـ 3 استراتيجيات تخزين
- [x] **Cache-First** للأصول الثابتة والصور
- [x] **Network-First** للـ API والصفحات
- [x] **Offline Fallback** → offline.html
- [x] **beforeinstallprompt** handler متقدم
- [x] **بانر تثبيت ذكي** مع خيارات (تثبيت / لاحقاً / لا شكراً)
- [x] **تذكير بالتثبيت** بعد 3 أيام
- [x] **إشعار اكتمال التثبيت**
- [x] **بانر تحديث SW** عند توفر إصدار جديد
- [x] **Push Notifications** جاهزة للتفعيل
- [x] **Background Sync** جاهز للتفعيل
- [x] **PWA Meta Tags** في جميع الصفحات (10 صفحات)

---

## ⚠️ الإجراء الإلزامي — Google OAuth

> **المشكلة:** `[GSI_LOGGER]: The given origin is not allowed for the given client ID.`

### الخطوات المطلوبة (يدوي من المستخدم):

```
1. افتح: https://console.cloud.google.com/apis/credentials

2. ابحث عن:
   Client ID: 726460253312-36qi0iv0a42ulb84r0b7m59or7utcfsd.apps.googleusercontent.com

3. انقر "Edit" → قسم "Authorized JavaScript Origins"

4. أضف الروابط التالية:
   ✅ https://YOUR-SITE.staticapp.io   ← رابط موقعك المنشور
   ✅ http://localhost:3000            ← للتطوير المحلي
   ✅ http://localhost                 ← للتطوير المحلي

5. انقر "Save"

6. انتظر 5-10 دقائق حتى يتفعل التغيير
```

### الحالة الحالية:
- ✅ الكود جاهز بالكامل في `auth.html`
- ✅ `GOOGLE_CLIENT_ID = '726460253312-...'` مُعيَّن
- ✅ `initGoogleSignIn()` يعمل مع retry loop
- ✅ `handleGoogleCredential()` يدعم Login + Auto-Register
- ⚠️ **يحتاج إضافة Authorized Origins في Google Cloud Console**

---

## 🤖 تفعيل Gemini AI (اختياري)

لتفعيل المساعد الذكي بـ Gemini API (مجاناً):

```javascript
// في js/chatbot.js — السطر ~26:
GEMINI_API_KEY: '', // ضع مفتاحك هنا

// للحصول على مفتاح مجاني:
// https://aistudio.google.com/app/apikey
```

**بدون Gemini API** → يعمل المساعد بقاعدة معرفة عربية محلية كاملة (18+ موضوع)

---

## 📁 هيكل الملفات

```
tradehub-pro/
├── 📄 index.html          → الرئيسية (PWA ✅ + Chatbot ✅)
├── 📄 products.html       → المنتجات (PWA ✅ + Chatbot ✅)
├── 📄 product.html        → تفاصيل المنتج (PWA ✅ + Chatbot ✅)
├── 📄 cart.html           → السلة (PWA ✅ + Chatbot ✅)
├── 📄 auth.html           → المصادقة + Google OAuth (PWA ✅ + Chatbot ✅)
├── 📄 checkout.html       → إتمام الطلب (PWA ✅ + Chatbot ✅)
├── 📄 my-orders.html      → طلباتي (PWA ✅ + Chatbot ✅)
├── 📄 seller.html         → لوحة البائع (PWA ✅ + Chatbot ✅)
├── 📄 admin-login.html    → بوابة المدير (PWA ✅)
├── 📄 admin.html          → لوحة المدير (PWA ✅ + Chatbot ✅)
├── 📄 offline.html        → صفحة عدم الاتصال ← جديدة
├── 📄 manifest.json       → PWA Manifest ← جديد
├── 📄 sw.js               → Service Worker ← جديد
├── icons/
│   ├── icon.svg           → أيقونة SVG قابلة للتطوير
│   └── generate-icons.html → مولّد الأيقونات
├── js/
│   ├── auth.js            → JWT + SHA256 + OTP
│   ├── main.js            → Logo + Header
│   ├── home.js            → Slider + Products
│   ├── chatbot.js         → AI Widget + PWA Manager ← جديد
│   └── pwa-icons.js       → مولّد أيقونات Canvas ← جديد
└── css/
    └── style.css          → التصميم الرئيسي
```

---

## 🗄️ نموذج البيانات (RESTful Table API)

| الجدول | الغرض | الحقول الرئيسية |
|--------|--------|----------------|
| `pending_users` | طلبات تسجيل معلقة | name, email, password_hash, role |
| `registered_users` | المستخدمون المعتمدون | name, email, password_hash, role, google_id |
| `password_reset` | رموز OTP | email, code, expires_at |
| `products` | المنتجات | name, price, category, supplier_id |
| `orders` | الطلبات | user_id, items, total, status |
| `cart` | سلة التسوق | user_id, product_id, quantity |
| `categories` | فئات المنتجات | name, icon, description |
| `tickets` | تذاكر الدعم | user_id, subject, message, status |
| `reviews` | التقييمات | product_id, user_id, rating, comment |
| `platform_settings` | إعدادات المنصة | logo_type, logo_text, colors |

---

## 🔧 المهام المعلقة (R7)

- [ ] `admin.html`: تحديث `loadOrders()` → `tables/orders` (بدلاً من `tables/admin_orders`)
- [ ] `seller.html`: جلب طلبات البائع من `tables/orders` مع فلتر `supplier_id`

---

## 🚀 الخطوات التالية الموصى بها (R10)

1. **نشر الموقع** → الحصول على الرابط الحقيقي
2. **إضافة Authorized Origins** في Google Cloud Console
3. **اختبار Google OAuth** بعد إضافة الرابط
4. **تفعيل Gemini API** (اختياري — مجاني)
5. **تثبيت التطبيق كـ PWA** واختبار الإشعارات
6. **إنشاء أيقونات PNG حقيقية** بدلاً من SVG (لـ iOS)
7. **تفعيل Push Notifications** في sw.js
8. **إضافة نظام تقييمات** للمنتجات

---

## 👤 بيانات الدخول التجريبية

| الدور | البريد | كلمة المرور |
|-------|--------|-------------|
| **المدير** | — | يُدخَل في `admin-login.html` |
| **بائع** | أي بريد مسجَّل | كلمة مروره |
| **مشتري** | أي بريد مسجَّل | كلمة مروره |

> ⚠️ الحسابات الجديدة تحتاج موافقة المدير (إلا حسابات Google)

---

*تم إنشاء هذا المشروع بـ HTML5 + CSS3 + Vanilla JS بدون أي framework خلفي*
