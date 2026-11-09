# One-Page Resume Builder 一頁履歷產生器

**Fill in a form → live A4 preview that is guaranteed to fit exactly one page → print to PDF. Free, no login, no server, your data never leaves your device.**

**填表即見 A4 預覽,保證啱啱好一頁,列印就係 PDF。免費、免登入、無伺服器,資料唔會離開你部機。**

## Try it

Open `index.html` in any browser (double-click works, no server needed).
It loads with a filled Chinese sample so you can see the result at once —
press **English sample** to switch to the English version, or **清除全部
Clear** and type your own.

## Use it in 2 minutes

1. Fill in your name, target role, contact, summary, education (up to 3),
   experience (up to 3) and skills. Experience bullets: one achievement per
   line — write the result plus a number if you have one
   (e.g. “followers grew from 800 to 2,400”).
2. Watch the preview update live. The meter under the layout controls tells
   you how much of the page you have used.
3. If it goes over one page, press **一鍵縮到一頁 Auto-fit to one page** —
   it steps the font size, line spacing and margins down until it fits.
   If it still does not fit at the smallest settings, shorten the content:
   cut a bullet or a line from the summary.
4. Press **列印 / 存成 PDF Print to PDF** and choose “Save as PDF” in the
   print dialog. That is the file you send to employers.

## 兩分鐘用法

1. 填姓名、目標職位、聯絡、簡介、學歷 (最多 3 個)、經驗 (最多 3 個)、技能。
   經驗要點每行一點,寫成果加數字 (例如「追蹤人數由 800 升到 2,400」)。
2. 預覽即時更新,版面控制下面有用量錶,話你知用咗幾多版。
3. 超出一頁就撳 **一鍵縮到一頁**,佢會逐級縮細字體、行距、邊距直到啱啱好。
   縮到最細都仲超,就要刪內容:減一個要點或者簡介寫短啲。
4. 撳 **列印 / 存成 PDF**,喺列印對話框揀「另存為 PDF」,就係交畀僱主嘅檔案。

## What it does

- Chinese + English sample resumes, one-click switch; two templates
  (Classic / Modern).
- Live A4 preview with a real page-fit meter (measured from the rendered
  page, not guessed) and an auto-fit button.
- Font size (9.5–12 pt), line spacing (1.15 / 1.3 / 1.45) and margin
  (10 / 15 / 20 mm) controls.
- Auto-save to this browser's localStorage — reopen the page and your
  draft is back. Nothing is uploaded anywhere.
- Print stylesheet: only the resume prints, exactly one A4 page
  (`@page { size: A4; margin: 0 }`).

## Honest limits — what it does NOT do

- **No AI writing.** It does not write your bullets for you and does not
  improve your wording. What you type is what prints.
- **No online submission.** It does not send your resume to employers,
  job boards or anyone else. You print the PDF and send it yourself.
- **No template store.** Two templates only (Classic / Modern). No photo,
  no icons, no fancy graphics — a plain text resume that prints cleanly.
- **No server storage.** Your draft lives only in this browser's
  localStorage. Clearing browser data erases it; switching browsers or
  devices starts from empty. Print your PDF before you clear anything.
- **One page, hard limit.** At most 3 education and 3 experience entries.
  If your history genuinely needs two pages, this tool is the wrong one.

## Tech

Pure HTML/CSS/ES5 in a single `index.html`, white background, iOS 16
Safari safe, zero external resources, works offline. Tests in `tests/`:

```
node tests/test_resume.js
python3 -c "import html.parser; html.parser.HTMLParser().feed(open('index.html').read())"
```

Tests check: HTML parses, JS is ES5-only (no arrow functions / const /
let / fetch / optional chaining / template literals), print CSS is A4
one-page, localStorage save/load round-trips (including corrupt and denied
storage), both samples fit one page at default settings, and a bloated
resume is correctly flagged as over one page.

## Licence

MIT.
