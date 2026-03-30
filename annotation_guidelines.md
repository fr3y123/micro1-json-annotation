# Document Annotation & Validation Guidelines

## Objective
Ensure AI-extracted JSON data matches the source document exactly in value, structure, and meaning.

---

## 1. Validation Process

1. Compare each JSON field with the source PDF
2. Verify:
   - Text accuracy (no spelling or truncation errors)
   - Numerical correctness
   - Proper field placement in JSON
3. Correct any discrepancies

---

## 2. Numerical Validation

- Recalculate:
  - Line item totals (quantity × unit price)
  - Subtotals
  - VAT / tax
  - Final totals

- Ensure:
  - No rounding errors
  - Values match document exactly

---

## 3. Table Validation

- Ensure all rows are extracted
- Verify:
  - No missing items
  - Correct alignment of columns
  - Accurate totals per row

---

## 4. JSON Structure Validation

- Confirm correct nesting
- Ensure fields are in proper locations
- Validate required fields exist

---

## 5. Language Accuracy (Bilingual)

- Ensure extracted text matches original language
- Do not translate unless required
- Preserve names, numbers, and formatting exactly

---

## 6. Common Errors to Catch

- Incorrect totals
- Missing rows
- Misplaced fields
- OCR misreads (e.g., 0 vs O)
- Language misinterpretation

---

## 7. Notes

- Add validation notes when corrections are made
- Maintain consistency across documents
