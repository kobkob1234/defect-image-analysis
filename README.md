<div dir="rtl">

# ניתוח נתונים וזיהוי חריגות בתמונות רכיבים

פתרון למשימת Junior Data Analyst: היכרות עם הנתונים, הפקת מאפיינים מהתמונות, כלל החלטה לזיהוי תמונות חשודות, בדיקת התוצאות ומסקנות.

## מה יש כאן

| קובץ | תוכן |
|---|---|
| `defect_analysis.ipynb` | המחברת המלאה (חלקים א–ה), כולל הגרפים, מדדי האימות והסיכום. אפשר לקרוא אותה ישירות ב-GitHub, עם כל הפלטים; אם התצוגה ב-GitHub לא נטענת: [צפייה ב-nbviewer](https://nbviewer.org/github/kobkob1234/defect-image-analysis/blob/main/defect_analysis.ipynb). |
| `predictions.csv` | תחזית לכל אחת מ-72 תמונות המבחן: `image_id,predicted_defect,score` |
| `requirements_suggested.txt` | החבילות הנדרשות להרצה |

## התוצאה בקצרה

- **הפתרון:** כלל החלטה שמבוסס על שלוש מדידות של הלוח עצמו: שטח כהה, קו בהיר ושקע בשפה.
- **בקבוצת האימות (42 תמונות):** ‏Precision ‏0.73 (לעומת 33% בבחירה אקראית) ו-Recall ‏0.79.
- **העלייה בהתראות:** נראה שיש לה יותר מסיבה אחת: שינוי בתנאי הצילום באצווה האחרונה, יותר פגמים באצווה C, ותיוגים לא עקביים.

הפירוט המלא בחלק ה של המחברת.

## הרצה מחדש

1. מניחים ליד המחברת את קובצי המשימה: `train.csv`, `test.csv`, `sample_predictions.csv` והתיקייה `images/` (הם לא כלולים כאן).
2. יוצרים סביבת Python 3.12 ומתקינים את החבילות:

</div>

```bash
python3.12 -m venv .venv                 # Windows: py -3.12 -m venv .venv
source .venv/bin/activate                # Windows: .venv\Scripts\activate
pip install -r requirements_suggested.txt ipykernel
```

<div dir="rtl">

3. פותחים את המחברת ב-Jupyter או ב-VS Code, בוחרים את ה-kernel של הסביבה `.venv`, ומריצים Run All. הריצה לוקחת פחות מדקה ויוצרת מחדש את `predictions.csv` ואת התיקייה `results/`.

נבדק עם Python 3.12.10 ועם opencv-python 5.0.0 ו-5.1.0.95; בשתי הגרסאות הריצה מייצרת `predictions.csv` זהה.

</div>
