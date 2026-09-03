# رفع الموقع على Render (مجاني)

هذا المجلد يحتوي على كل ما تحتاجه لرفع موقعك على Render باستخدام أقل فئة (Free) — وهي فئة كافية تمامًا لموقع تعريفي ثابت مثل هذا، ولا تتطلب أي بطاقة دفع.

## الملفات
- `index.html` — الموقع كاملاً (صفحة واحدة، لا يحتاج بناء/Build).
- `render.yaml` — ملف إعداد جاهز (Blueprint) يخبر Render أن هذا موقع ثابت (Static Site) على الخطة المجانية.

## الخطوات

### 1) ارفع الملفات إلى GitHub
1. أنشئ مستودع (repository) جديد على حسابك في GitHub — مثلاً باسم `yahya-majrashi-portfolio` (أو استخدم مستودعك الحالي `My-profile-web`).
2. ارفع إليه ملفي `index.html` و `render.yaml` الموجودين في هذا المجلد (بالسحب والإفلات عبر واجهة GitHub، أو عبر git):
   ```bash
   git init
   git add index.html render.yaml
   git commit -m "Add portfolio site"
   git branch -M main
   git remote add origin https://github.com/<username>/<repo-name>.git
   git push -u origin main
   ```

### 2) اربط المستودع بـ Render
1. سجّل الدخول إلى [dashboard.render.com](https://dashboard.render.com).
2. اضغط **New +** ثم اختر **Blueprint**.
3. اختر حساب GitHub الخاص بك، ثم اختر المستودع الذي رفعت إليه الملفات.
4. سيكتشف Render ملف `render.yaml` تلقائيًا ويعرض عليك خدمة باسم `yahya-majrashi-portfolio` على الخطة **Free** — اضغط **Apply** للمتابعة.
5. انتظر دقيقة أو أقل حتى ينتهي النشر (Deploy)، وستحصل على رابط مباشر بصيغة:
   `https://yahya-majrashi-portfolio.onrender.com`

### طريقة بديلة (بدون render.yaml)
إذا فضّلت عدم استخدام ملف Blueprint:
1. من لوحة Render اضغط **New +** ثم **Static Site**.
2. اربط نفس المستودع.
3. اترك **Build Command** فارغًا، وضع **Publish Directory** = `.` (نقطة واحدة فقط).
4. اختر الخطة **Free** واضغط **Create Static Site**.

## بعد النشر
- أي تعديل تدفعه (push) إلى فرع `main` سيُنشر تلقائيًا خلال ثوانٍ (Auto-Deploy مفعّل افتراضيًا).
- يمكنك لاحقًا ربط دومين خاص بك من إعدادات الخدمة في Render (Settings → Custom Domains) إن رغبت.
