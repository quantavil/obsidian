![[Pasted image 20230201102716.png]]

_**Apache POI**_ uses certain terms to work with _Microsoft Excel._
- **Workbook**:	A workbook represents a Microsoft Excel file. It can be used for creating and maintaining the spreadsheet. A workbook may contain many sheets.
- **Sheet**:	A sheet refers to a page in a Microsoft Excel file that contains the number of rows and columns.
- **Row**:	A row represents a collection of cells, which is used to represent a row in the spreadsheet.
- **Cell**:	A cell is indicated by a row and column combination. Data entered by a user is stored in a cell. Data can be of the type such as string, numeric value, or formula.

![[Pasted image 20230201152351.png]]

## Managing Excel

_Apache POI_ provides various interfaces and classes that help us to work with _Excel._ It provides a _**"Workbook "**_ interface to maintain Excel Workbooks.

-   **HSSFWorkbook-** These class methods are used to read/write data to Microsoft Excel file in **.xls** format. It is compatible with MS-Office versions 97–2003.
-   **XSSFWorkbook-** These class methods are used to read-write data to Microsoft Excel in **.xls** or **.xlsx** format. It is compatible with MS-Office versions 2007 or late
- -   **HSSFSheet -** This class is used to create a new sheet in the HSSFWorkbook, ie, the older format of Excel.
-   **XSSFSheet -** This class is used to create a new sheet in the XSSFWorkbook., ie, the new format of Excel
- -   **HSSFRow** - This represents a row in the HSSFSheet.
-   **XSSFRow** - This represents a row in the XSSFSheet.
- **HSSFCell** - We use it to work with cells of HSSFRow.
-   **XSSFCell** - We use it to work with cells of XSSFRow.