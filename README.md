<h2>Facturitas</h2>
<p>The <code>main.py</code> file is the core of the <strong>Facturitas</strong> project. Its main function is to process and structure invoices in PDF format, and subsequently store them in an SQLite database. Below is a description of the workflow of the script:</p>

<ol>
  <li>Imports the necessary modules, including <code>funciones</code>, <code>pandas</code>, and <code>sqlalchemy</code>.</li>
  <li>Creates an empty <code>DataFrame</code> to store data from all invoices.</li>
  <li>Iterates through all folders within the <code>facturas</code> directory and processes each PDF file within those folders.</li>
  <li>For each PDF file:
    <ul>
      <li>Extracts unstructured text using the <code>extraer_texto_pdf</code> function from the <code>funciones</code> module.</li>
      <li>Structures the extracted text using the <code>estructurar_texto</code> function.</li>
      <li>Converts the structured text into a <code>DataFrame</code> with the <code>csv_a_dataframe</code> function.</li>
      <li>Appends the invoice <code>DataFrame</code> to the general <code>DataFrame</code>.</li>
    </ul>
  </li>
  <li>If the invoice currency is "dollars", converts the amount to euros by multiplying by 0.9243.</li>
  <li>Removes non-essential columns from the <code>DataFrame</code>.</li>
  <li>Saves the final <code>DataFrame</code> in an SQLite database called <code>facturas.db</code>.</li>
  <li>Prints confirmation messages indicating that the process has been successfully completed and that the data has been saved in the database.</li>
</ol>

<p>This script automates the processing of invoices, facilitating further analysis with tools like Power BI.</p>
