# PCOS

מדריך אינטראקטיבי על תסמונת השחלות הפוליציסטיות (PCOS) — נעם בר-אל עזריאל, דיאטנית קלינית.

**GitHub:** https://github.com/noambarel2907-png/PCOS
**אתר חי:** https://pcos.noambarel.co.il (Cloudflare Pages — פרוס אוטומטית מ-main)

---

## מבנה הפרויקט

```
index.html                      ← הכלי כולו (דף פתיח + מדריך), HTML+CSS+JS בקובץ אחד
noam-logo-cover.png             ← "noam big logo" — משמש גם בדף הפתיח וגם בקרדיט בתחתית המדריך
og-image.png                    ← תמונת שיתוף לוואטסאפ/פייסבוק (זהה לכל שאר הפרויקטים, מקור: noam-barel-logo/5-social-share/og-default.png)
manifest.json                   ← PWA manifest — קובע את השם "PCOS" כשמוסיפים למסך הבית
favicon.ico / favicon-16x16.png / favicon-32x32.png / apple-touch-icon.png / android-chrome-192x192.png / android-chrome-512x512.png
                                 ← זהים לחלוטין לקבצי האייקון של clinic-skills (Skills List) — הועתקו משם בכוונה לשמירה על אחידות
logo.png                        ← לוגו ישן (עלה, רקע שקוף) — לא בשימוש יותר בדף, נשאר בריפו להיסטוריה בלבד
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

- `og:title` / `twitter:title`: "המדריך האינטרקטיבי ל-PCOS"
- `og:description` / `twitter:description`: "כל מה שאת צריכה לדעת על תסמונת השחלות הפוליציסטיות"
- `og:image` / `twitter:image`: `og-image.png` (חייב להישאר קובץ אמיתי בשורש הריפו — WhatsApp/Facebook לא טוענים base64/data URIs)

אם משתנה הכותרת/התיאור של המדריך — לעדכן גם את `<title>` בראש הקובץ וגם את תגיות ה-OG, לשמור עליהם מסונכרנים.

## הוספה למסך הבית (PWA)

- `manifest.json` (`short_name: "PCOS"`) + `apple-mobile-web-app-title` + `application-name` — קובעים שהשם שמוצע כברירת מחדל כשמוסיפים את הדף למסך הבית (iOS/Android) הוא "PCOS", גם אם כותרת הטאב בדפדפן ארוכה יותר.
- האייקון שמוצג הוא `apple-touch-icon.png`/`android-chrome-*.png` — אותם קבצים בדיוק כמו ב-clinic-skills (Skills List) ו-NB Clinic App.

---

## זרימת עבודה

```bash
# עריכה → commit → push → Cloudflare מפרס אוטומטית
git add <file>
git commit -m "תיאור קצר"
git push
```
