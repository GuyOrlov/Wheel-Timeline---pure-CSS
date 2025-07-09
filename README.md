# 📊 Power BI DAX Wheel Timeline

A dynamic, interactive **wheel timeline** built using **pure DAX and HTML** — designed for **Power BI**.

---

## 🌀 What it is

This visual lets you:
- Display a **circular timeline** with years **2000–2025**.
- Highlight a selected year using a **slicer button** in Power BI.
- Use no JavaScript — it’s entirely built with **DAX**, CSS custom properties, and an HTML Viewer or HTML Content custom visual.

---

## ✨ Inspired by

Originally inspired by [cbolson’s CodePen wheel timeline](https://codepen.io/cbolson/pen/vEBWwxL) — an elegant pure CSS demo.

I adapted the concept for Power BI to:
- Work inside a DAX measure.
- Respond dynamically to a slicer selection.
- Keep the wheel spinning effect fully inside the Power BI ecosystem.

---

## 🚀 How it works

1. **DAX Year Table**  
   Creates years from 2000 to 2025 with an index for each year.

2. **Slicer**  
   Lets you pick a year to highlight on the wheel.

3. **DAX HTML Measure**  
   Dynamically generates the HTML for the entire wheel timeline.  
   Uses `GENERATESERIES` and `CONCATENATEX` to build each `<li>` with the correct `checked` attribute.

4. **HTML Viewer**  
   Renders the final wheel timeline right in your report.

---

## 🎥 Demo Video

Watch how the wheel spins and the content updates dynamically — [link to your demo video here].

---

## 📂 How to use

1. Copy the **DAX Year Table**:
   ```DAX
   YearTable =
   ADDCOLUMNS(
     GENERATESERIES(2000, 2025, 1),
     "Index", [Value] - 2000
   )
