# Forma Studio — كود جاهز للنشر على Vercel

بورتفوليو بالعربية، بنفس الهوية الداكنة والأزرق، مع الأعمال الأربعة الأصلية والخدمات وعرض الشعارات بحجم أكبر. الخطوط والصور مرفقة محليًا.

## النشر عبر GitHub وVercel

1. فك ضغط الحزمة.
2. أنشئ مستودعًا على GitHub وارفع **محتويات المجلد** إليه، بحيث يكون `vercel.json` في جذر المستودع، وبجواره مجلد `public`.
3. في Vercel، اختر Add New ثم Project واستورد المستودع.
4. إعدادات المشروع:
   - Framework Preset: **Other**.
   - Root Directory: جذر المستودع الذي يحتوي على `vercel.json`.
   - Output Directory: **public**.
   - Build Command: فارغ.
   - Install Command: فارغ.
5. اضغط Deploy. إعدادات النشر مرفقة في `vercel.json`.

الموقع HTML وCSS وJavaScript ثابت، ولا يحتاج إلى خطوة بناء أو تثبيت حزم.

## تعديل المحتوى

- `public/index.html`: النصوص، الخدمات وعناوين الأعمال.
- `public/style.css`: الألوان والخطوط وترتيب الأقسام.
- `public/app.js`: تكبير المشاريع وتجهيز رسالة الطلب ونسخها.
- `public/assets/`: الشعارات والخطوط المحلية وترخيصها.

عند تغيير صورة عمل، استبدل الملف المقابل داخل `public/assets`، ثم عدّل العنوان والتصنيف في HTML وفي قائمة `projects` داخل `app.js` إذا تغيّر اسم المشروع.

## التواصل

النموذج الحالي يجهّز رسالة طلب قابلة للنسخ. لإضافة تواصل مباشر، ضع رابط حسابك في القسم الذي يحمل `id="contact"` باستخدام رابط مثل:

```html
<a class="button" href="رابط-حسابك-الكامل" target="_blank" rel="noopener noreferrer">تواصل معي</a>
```

استبدل قيمة `href` برابطك الحقيقي قبل إضافة الرابط إلى الصفحة.

## معاينة محلية اختيارية

يمكن فتح `public/index.html` في المتصفح لمعاينة التصميم. أو تشغيل خادم محلي من داخل مجلد المشروع:

```bash
python3 -m http.server 8000 --directory public
```

ثم افتح `http://localhost:8000`. نسخ الرسالة إلى الحافظة يعمل على HTTPS أو localhost، مع إمكانية تحديد النص يدويًا عند عدم توفر الحافظة.

## المرجع

- [إعداد مشروع Vercel](https://vercel.com/docs/project-configuration/vercel-json)
- [إعدادات البناء](https://vercel.com/docs/builds/configure-a-build)
