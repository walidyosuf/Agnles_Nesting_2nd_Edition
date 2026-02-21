Angle Section Cutting Optimizer (L-Sections)
A web-based tool for optimizing the cutting of equal angle steel sections (L-sections) to minimize waste and maximize material utilization. Supports two optimization modes: automatic variable-length selection and fully customizable stock lengths with quantities per section.

Features
Upload Requirements: Upload an Excel file containing required pieces (section, reference, length, quantity, steel grade).

Two Optimization Modes:

Variable Lengths (Optimized): Automatically selects the best stock length from 6m to 13m in 10cm increments using a best‑fit decreasing algorithm.

Custom Stock Lengths per Section: Define your own available stock lengths and quantities for each section. You can add multiple entries per section, each with a specific quantity (or unlimited). The optimizer will respect these inventory limits.

Integrated Weight Database: Built‑in weight per meter for hundreds of equal angle profiles (based on standard tables). If a section is not found, a warning is shown and weight is set to zero.

Detailed Reports:

Overall summary (net weight, raw material weight, efficiency).

Cutting plan by material group, including which stock lengths were used.

Valuable scrap report (lengths ≥ 1.5 m) aggregated by length.

Detailed cutting plan with patterns aggregated for clarity.

Export Options: Export results to Excel (multiple sheets) or PDF, or simply print the plan.

How to Use
Open the tool – just load the HTML file in any modern browser (no server required).

Choose a mode:

Variable Lengths – let the tool decide the best lengths.

Custom Stock Lengths per Section – you will define your own inventory.

Upload your requirements file (Excel .xlsx format).
The file must contain these columns (in this order):

Column A: Section (must start with "L", e.g., L50X50X5)

Column B: Item / Reference (any text)

Column C: Length (mm) – required length of each piece

Column D: Quantity (number of pieces of that length)

Column E: Steel Grade (e.g., S235JR)

If you chose Custom mode:

After uploading, a dropdown will appear listing all unique section+steel combinations from your file.

For each section you want to define stock, select it from the dropdown, enter a length (mm) and an optional quantity (leave empty for unlimited), then click Add. Repeat to add multiple lengths for the same section.

A preview table shows all your custom stock items. You can remove any item by clicking "Remove".

Sections you do not add any stock for will automatically use a default length of 12 m with unlimited quantity.

Click Generate Cutting Plan.

View the results in the three report sections: overall summary, cutting plan details, and valuable scrap.

Use the Export Options to download the plan as Excel or PDF.

Input File Format
The Excel file must have the following columns (header row optional, data starts from row 1):

Section	Item/Ref	Length (mm)	Qty	Steel Grade
L50X50X5	Beam 1	2000	4	S235JR
L60X60X6	Column 2	3500	2	S275JR
Section names can be in formats like L50X50X5, L50*50*5, L50x50x5. The tool normalizes them.

Length must be in millimeters.

Qty is the number of identical pieces required.

Custom Stock Lengths with Quantities
When using the Custom mode, you can define exactly what stock you have in your warehouse. For each section+steel combination, you may add one or more entries:

Length (mm) – must be between 6000 and 13000.

Quantity – the number of bars of that length you have available. If left empty, it is considered unlimited.

The optimizer will try to use these lengths while respecting the available quantities. It will choose the most efficient length in each iteration (highest utilization) and consume stock accordingly. If you have multiple lengths for the same section, the tool will pick the best one dynamically.

Output Reports
Overall Optimization Summary
Net Weight (required pieces) in tonnes

Raw Material Weight (including scrap) in tonnes

Material Utilization Efficiency (%)

Cutting Plan Details by Material Group
A table showing per section+steel group:

Weight per meter

Which raw lengths were used and how many times

Total bars used

Net weight, raw material weight, efficiency

Valuable Scrap Report (≥ 1.5 m)
Aggregated by identical scrap length, showing quantity for each.

Detailed Cutting Plan (Aggregated)
For each material group, the plan is shown as patterns (same raw length and same cut combination). Each pattern shows:

Number of bars with that pattern

Raw material length

List of cuts (with item and length)

Scrap per bar

Efficiency of the pattern

Export Formats
Excel: Three sheets – Summary, Scrap Report, Detailed Plan (aggregated).

PDF: A formatted document with the same information, suitable for printing or sharing.

Technologies Used
HTML5 / CSS3 (Tailwind CSS for styling)

JavaScript (ES6)

SheetJS (xlsx) for Excel import/export

jsPDF + jspdf-autotable for PDF generation

Built‑in weight database (over 200 angle profiles)

License
This project is open source and available under the MIT License.

Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

Note: This tool runs entirely in your browser – no data is sent to any server. Your material lists remain private.
