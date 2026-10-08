# HIGH LIFE — تجربة براند فاخرة (ديمو كونسبت) / Premium Brand Experience (Concept Demo)

موقع تفاعلي يوضّح كيف يتحول موقع المشروع من *معلومات تعريفية* إلى
*تجربة براند رقمية* — عربي RTL أولاً، مع تبديل كامل عربي/إنجليزي ووضعي دارك/لايت.

> **هذا ديمو كونسبت — ليس الموقع النهائي.**
> كل المنتجات والأسعار والشهادات والصور Placeholder — بلا أي ادّعاءات.
>
> **This is a concept demo — not the final production website.**
> All products, prices, testimonials and visuals are placeholders — no claims.

---

## المحتويات / What's inside

| الملف / File | الغرض / Purpose |
|---|---|
| `index.html` | التجربة كاملة — HTML + CSS + JS في ملف واحد، بدون build |
| `README.md` | هذا الملف — التشغيل والنشر |
| `DEMO_PRESENTATION.md` | WHY / WHAT / HOW / BUSINESS VALUE / PRODUCTION VERSION |

> `archive/` (نسخة v1 القديمة) و `preview/` (لقطات شاشة) ملفات محلية فقط — غير منشورة على GitHub.

**مسار التجربة / Experience flow:**

```
وصول → اكتشاف → إحساس → فهم → ثقة → استكشاف → تحويل
ARRIVE → DISCOVER → FEEL → UNDERSTAND → TRUST → EXPLORE → CONVERT
```

**الأقسام / Sections:** مقدمة سينمائية → هيرو متحرك مع السكرول →
01 بيان البراند → 02 عالم البراند (4 فصول مثبتة) → 03 القطع المميزة →
04 قصة المنتج (مدفوعة بالسكرول) → 05 المجموعة (فلاتر + بحث) → 06 هندسة الثقة →
07 لماذا هذا التصميم (تفاعلي) → 08 قبل/بعد → 09 من الهوية إلى الموقع →
10 نسختك → خاتمة CTA.

**أدوات التجربة (أعلى الشاشة):**
- **عربي / EN** — تبديل لغة كامل مع قلب الاتجاه RTL ⇄ LTR وحفظ في `localStorage`.
- **☀ / ☾** — تبديل دارك/لايت بتلاوّن سلس (Dark: أسود/فحمي/عاجي/شمبانيا — Light: عاجي دافئ/كريمي/فحمي).
- **اشرح لي التجربة** — وضع الشرح: كل قسم يعرض بطاقة «ليه؟ وإزاي؟» (10 بطاقات)، محفوظ في `localStorage`.
- **واتساب عائم** — `wa.me/201000000000` (رقم تجريبي واضح — غيّره لرقم حقيقي عند الاستخدام).

---

## التشغيل محليًا / Run locally

لا تحتاج أي أدوات بناء:

```powershell
# الخيار A — افتح الملف مباشرة
start .\index.html

# الخيار B — سيرفر ساكن
npx serve .
python -m http.server 8080
```

يحتاج إنترنت لخطوط Google ومكتبات CDN (GSAP, ScrollTrigger, Lenis).
بدون اتصال الموقع يظل يعمل بالكامل (كشف المحتوى + بلا أخطاء) — يفقد فقط سلاسة الحركة.

---

## النشر / Deploy

**Live:** https://nexora-01-eg.github.io/high-life-demo/

### GitHub Pages
```powershell
git add index.html README.md DEMO_PRESENTATION.md
git commit -m "HIGH LIFE — concept demo"
git branch -M main
git remote add origin https://github.com/nexora-01-eg/high-life-demo.git
git push -u origin main
```
ثم: **Settings → Pages → Deploy from a branch → `main` / root → Save**.

### Vercel
```powershell
npm i -g vercel
vercel        # بدون أي إعدادات
vercel --prod
```

### Netlify
- **سحب وإفلات:** [app.netlify.com/drop](https://app.netlify.com/drop)
- **CLI:** `netlify deploy --dir . --prod`

### أي استضافة أخرى
ارفع `index.html` إلى جذر الموقع — لا يوجد ما يُترجم.

---

## التقنية / Tech

- **HTML / CSS / JavaScript** — ملف واحد، بدون إطار عمل أو build
- **GSAP 3.12 + ScrollTrigger** (اختياري) — تثبيت الهيرو والفصول، parallax، أرقام الأقسام
- **Lenis 1.1** (اختياري) — سكرول سلس (يُلغي تلقائيًا مع `prefers-reduced-motion`)
- **خطوط Google:** `Vazirmatn` (فارسي — نصوص وواجهة عربية) + `Amiri` (عناوين عاطفية فاخرة) + `Inter` (إنجليزي/أرقام)
- **i18n:** كل نص بخاصيتي `data-ar` / `data-en` — تبديل فوري مع قلب `dir` على `<html>`
- كشف المحتوى = `IntersectionObserver` + سحب-فحص عند السكرول → لا يعلق عنصر أبدًا
- نقاط التوقف: **1100 / 900 / 640 px**
- يحترم `prefers-reduced-motion` (بلا مقدمة، كل المحتوى ظاهر فورًا)

---

## التخصيص / Customizing for a real brand

كل شيء في `index.html`:

1. **الألوان** — كتلتا `:root` (دارك) و `html[data-theme="light"]` أعلى `<style>`:
   `--bg / --text / --champ / --card` … الخ.
2. **الخطوط** — رابط Google Fonts + متغيرات `--f-brand / --f-body / --f-display`.
3. **المحتوى** — نص عربي في `data-ar` ونظيره في `data-en` على نفس العنصر (ارضِ الاثنين).
4. **واتساب / هاتف** — ابحث عن `wa.me/201000000000` (زر عائم + أزرار الخاتمة + الفوتر).
5. **الصور** — الكتل البصرية `.vis` (تدرّجات CSS + ضوء + حبيبات). استبدلها بـ `<img>`/`<video>`
   عند توفر التصوير الحقيقي.
6. **وضع الشرح** — البطاقات `<aside class="why">` داخل كل قسم — عدّلها أو احذفها بحرية.

---

*Concept demo built as a portfolio sample by **nexora-01-eg**. Not a live store.*
