# موقع GTA MODDER DZ — نسخة GitHub فقط (بدون Firebase)

كل شيء على GitHub: الموقع، المودات، الصور، والتعليقات.

## محتوى المجلد
| الملف | الوظيفة |
|---|---|
| `index.html` | الموقع كاملاً + لوحة التحكم |
| `data.json` | المودات والأخبار والفيديوهات (لوحة التحكم تعدّله تلقائياً) |
| `config.js` | إعدادات التعليقات (Giscus) |
| `logo.jpg` | شعار القناة |

الصور التي ترفعها من لوحة التحكم تُحفظ تلقائياً في مجلد `images/` داخل الـ repository.

---

## الجزء 1: نشر الموقع على GitHub Pages

1. أنشئ حساباً على https://github.com إن لم يكن لديك.
2. اضغط **+ ← New repository**، سمّه `gtamodderdz`، اختر **Public**، ثم **Create repository**.
3. اضغط **uploading an existing file**، واسحب الملفات الأربعة: `index.html` و`data.json` و`config.js` و`logo.jpg`، ثم **Commit changes**.
4. ادخل **Settings ← Pages**، وفي **Source** اختر **Deploy from a branch**، الفرع `main` والمجلد `/ (root)` ← **Save**.
5. بعد دقيقة أو دقيقتين يصبح موقعك متاحاً على:
   `https://اسم-حسابك.github.io/gtamodderdz/`

---

## الجزء 2: لوحة التحكم (أنت فقط)

### إنشاء مفتاح الدخول (مرة واحدة)
1. في GitHub: صورتك أعلى اليمين ← **Settings ← Developer settings ← Personal access tokens ← Fine-grained tokens ← Generate new token**.
2. **Token name:** `gtamodderdz-admin` — **Expiration:** اختر مدة (مثلاً سنة).
3. **Repository access:** اختر **Only select repositories** ← `gtamodderdz`.
4. **Permissions ← Repository permissions ← Contents:** اختر **Read and write**.
5. اضغط **Generate token** وانسخ المفتاح (يبدأ بـ `github_pat_`). احفظه في مكان آمن — لن يظهر مرة أخرى.

### الدخول
- افتح: `https://اسم-حسابك.github.io/gtamodderdz/#admin`
- اسم الحساب والـ repository يُملآن تلقائياً، الصق المفتاح، ثم **دخول**.
- يبقى المتصفح متذكراً لك، وسيظهر زر **لوحة التحكم** في القائمة. للخروج: زر "تسجيل الخروج" في أعلى اللوحة.

### من لوحة التحكم تستطيع:
- رفع مود (صور + اسم + قسم + صانع + حجم + إصدار + وصف + رابط تحميل)، تعديله أو حذفه.
- نشر الأخبار وإضافة الفيديوهات (مع صورة مصغّرة اختيارية).
- كل تغيير يظهر للزوار بعد **دقيقة أو دقيقتين** (وقت تحديث GitHub Pages).

### لماذا لا يستطيع أحد غيرك النشر؟
- GitHub لا يسمح لأي شخص بتعديل ملفات الـ repository إلا صاحبه.
- صفحة `#admin` بدون مفتاحك لا تفعل شيئاً — حتى لو نسخ أحدهم الكود.
- **لا تشارك المفتاح أبداً**، ولا تُدخله على جهاز عام. إن تسرّب: احذفه من GitHub وأنشئ واحداً جديداً.

---

## الجزء 3: التعليقات والتفاعلات (Giscus)

1. في الـ repository: **Settings ← General ← Features** وفعّل **Discussions** ✅.
2. ثبّت تطبيق Giscus: https://github.com/apps/giscus ← **Install** ← اختر `gtamodderdz` فقط.
3. (اختياري لكن أفضل) في تبويب **Discussions** أنشئ تصنيفاً جديداً باسم `Comments` من نوع **Announcement** (حتى لا ينشئ أحد نقاشات عشوائية).
4. افتح https://giscus.app/ar واكتب في خانة المستودع: `اسم-حسابك/gtamodderdz`، واختر التصنيف `Comments`.
5. انزل لقسم **تمكين giscus** ستجد كوداً فيه `data-repo-id="..."` و `data-category-id="..."`.
6. افتح `config.js` في GitHub (أيقونة القلم ✏️) وضع القيم:
   ```js
   repo: "اسم-حسابك/gtamodderdz",
   repoId: "R_xxxxxxxx",
   category: "Comments",
   categoryId: "DIC_xxxxxxxx"
   ```
   ثم **Commit changes**.

بعدها ستظهر تحت كل مود: تفاعلات (❤️ 👍 🚀 …) وصندوق تعليقات. الزائر يحتاج حساب GitHub مجاني للتفاعل.
لحذف تعليق مزعج: افتح تبويب **Discussions** في الـ repository واحذفه من هناك.

---

## ملاحظات
- **ملفات المودات:** ارفعها على MediaFire / Google Drive / Mega وضع الرابط في "رابط التحميل".
- **حجم الـ repository:** GitHub ينصح بأقل من 1GB — الصور تُضغط تلقائياً (≈200–400KB للصورة)، فهذا يكفي لآلاف الصور.
- **لا تفتح `index.html` بالنقر المزدوج من جهازك** — جرّب دائماً على رابط GitHub Pages.
- **دومين خاص (اختياري):** **Settings ← Pages ← Custom domain** (مثل `gtamodderdz.com`).
