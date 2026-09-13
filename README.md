# الكبير أوي — حزمة جاهزة للربط والنشر

هذه النسخة جهزت لك:
- تصميم متجر أسود/ذهبي متجاوب.
- بحث وأقسام ومنتجات وسلة.
- Checkout والدفع عند الاستلام.
- تقييد المحافظة على المنيا.
- حساب عميل حقيقي عبر Supabase Auth (بريد + كلمة مرور + هاتف).
- صفحة "طلباتي".
- لوحة تاجر: عرض الطلبات وتغيير الحالة وإضافة المنتجات.
- قاعدة بيانات مع RLS وTrigger لإنشاء ملف العميل تلقائياً.
- شعار المحل داخل assets/logo.png.

## تشغيل المتجر الحقيقي
1. أنشئ مشروع Supabase.
2. افتح SQL Editor ونفّذ schema.sql بالكامل.
3. من Project Settings > API خذ Project URL و **Publishable key** (يبدأ عادةً بـ sb_publishable_).
4. افتح index.html وضع القيم مكان:
   YOUR_SUPABASE_URL
   YOUR_SUPABASE_PUBLISHABLE_KEY
5. أنشئ حساب التاجر من Authentication > Users.
6. خذ UUID لحساب التاجر ثم نفّذ في SQL Editor:
   update public.profiles set role='admin' where id='UUID-HERE';
7. ارفع الملفات إلى Vercel أو Netlify أو أي استضافة Static.

## مهم
لا تضع Secret/Service Role Key داخل index.html أو المتصفح.
هذه الحزمة لا تتضمن بوابة دفع إلكتروني؛ الدفع الحالي عند الاستلام.
