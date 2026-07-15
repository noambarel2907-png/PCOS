# PCOS

מדריך אינטראקטיבי על תסמונת השחלות הפוליציסטיות (PCOS) — נעם בר-אל עזריאל, דיאטנית קלינית.

**GitHub:** https://github.com/noambarel2907-png/PCOS
**אתר חי:** https://pcos.noambarel.co.il (Cloudflare Pages — פרוס אוטומטית מ-main)

---

## מבנה הפרויקט

```
index.html            ← הכלי כולו (דף פתיח + מדריך), HTML+CSS+JS בקובץ אחד
logo.png              ← לוגו קטן (עלה, רקע שקוף) — קרדיט בתחתית המדריך
noam-logo-cover.png   ← "noam big logo" — הלוגו הגדול בדף הפתיח
og-image.png          ← תמונת שיתוף לוואטסאפ/פייסבוק (זהה לכל שאר הפרויקטים, מקור: noam-barel-logo/5-social-share/og-default.png)
```

קובץ HTML סטטי יחיד — ללא build step, ללא תלויות חיצוניות. הגופנים (Fredoka One, Assistant) מוטמעים כ-base64 בתוך `<style>`.

---

## מבנה הדף

1. **דף פתיח (`#coverPage`)** — לוגו, כותרת "PCOS – מדריך אינטראקטיבי", תקציר על מה שבמדריך, דיסקליימר, וכפתור "כניסה למדריך" (`enterGuide()`).
2. **המדריך עצמו (`#guideContent`)** — מוסתר (`display:none`) עד לחיצה על הכפתור. שישה טאבים: מנגנון / התערבות / תזונה / פוריות / תוספים / סיכום.
3. **כפתור שיחת היכרות** (`.cta-block`, לפני ה-footer) — מקשר ל-`https://noambarel.co.il/paths/rise`.

---

## טכנולוגיה

- HTML + CSS + JS בלבד, ללא frameworks
- פונטים: `Fredoka One` (כותרות), `Assistant` (טקסט גוף)
- כיוון: RTL עברית
- רקע: `#F5F0E8` (קרם), צבע ראשי: `#5C3010` (חום כהה), ירוק הדגשה: `#4A7C3F`

---

## תגיות שיתוף (OG/WhatsApp)

- `og:title` / `twitter:title`: "PCOS - מדריך אינטראקטיבי"
- `og:description` / `twitter:description`: "כל מה שאת צריכה לדעת ב-10 דקות"
- `og:image` / `twitter:image`: `og-image.png` (חייב להישאר קובץ אמיתי בשורש הריפו — WhatsApp/Facebook לא טוענים base64/data URIs)

אם משתנה הכותרת/התיאור של המדריך — לעדכן גם את `<title>` בראש הקובץ וגם את תגיות ה-OG, לשמור עליהם מסונכרנים.

---

## זרימת עבודה

```bash
# עריכה → commit → push → Cloudflare מפרס אוטומטית
git add <file>
git commit -m "תיאור קצר"
git push
```
