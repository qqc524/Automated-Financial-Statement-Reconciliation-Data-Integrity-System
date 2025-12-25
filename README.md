<h1>Financial Statement Reconciliation & Data Integrity System</h1>

<p>The system is designed to support <strong>financial controls, data integrity, and auditability</strong>, simulating workflows in Finance and Accounting where incoming third-party statements must be reconciled against internally derived calculations.</p>

<h2>Background</h2>
<p>Weekly financial statements are received as PDF files from external partners. These documents:</p>
<ul>
    <li>Are unstructured and inconsistent</li>
    <li>May change line items week-to-week</li>
    <li>Require manual reconciliation</li>
    <li>Introduce risk of human error and missed discrepancies</li>
</ul>
<p>An automated pipeline extracts transaction-level details and summary totals from PDF statements, transforms them into normalized datasets, and reconciles calculated results against official statement totals.</p>

<h2>System Features</h2>

<h3>1. Data Ingestion</h3>
<ul>
    <li>Automatically processes weekly PDF statements dropped into a folder</li>
    <li>Detects and converts misnamed PDFs</li>
    <li>Tracks processed files to support <strong>incremental weekly updates</strong></li>
</ul>

<h3>2. Transaction-Level Extraction (Long Format)</h3>
<ul>
    <li>Extracts detailed line items:
        <ul>
            <li>Gross Sales (with unit counts)</li>
            <li>Net Sales</li>
            <li>Insurance</li>
            <li>Credits</li>
            <li>All deductions (dynamic, statement-dependent)</li>
        </ul>
    </li>
    <li>Stores data in a normalized, audit-friendly structure</li>
</ul>

<h3>3. Calculated Financial Summary</h3>
<ul>
    <li>Aggregates transactions to calculate:
        <ul>
            <li>Net Sales</li>
            <li>Total Expenses</li>
            <li>Net Profit</li>
        </ul>
    </li>
    <li>Uses internal logic rather than trusting statement totals blindly</li>
</ul>

<h3>4. Statement Summary Capture</h3>
<ul>
    <li>Extracts official statement totals:
        <ul>
            <li>Gross Sales</li>
            <li>Net Sales</li>
            <li>Credits</li>
            <li>Deductions</li>
            <li>Net Payment Total</li>
        </ul>
    </li>
</ul>

<h3>5. Automated Reconciliation</h3>
<ul>
    <li>Merges calculated results with statement-reported totals</li>
    <li>Flags discrepancies via:
        <ul>
            <li>Net Profit Difference</li>
        </ul>
    </li>
    <li>Enables fast identification of mismatches or data issues</li>
</ul>

<h3>6. Reporting Output</h3>
<ul>
    <li>Exports a single Excel file with:
        <ul>
            <li><strong>Transaction Details</strong> (long-format, audit-ready)</li>
            <li><strong>Summary Comparison</strong> (calculated vs statement values)</li>
        </ul>
    </li>
</ul>

<h2 class="tech">Technologies used:</h2>
<ul>
    <li>Python</li>
    <li>PDF parsing (pdfplumber)</li>
    <li>Regular expressions</li>
    <li>pandas</l
