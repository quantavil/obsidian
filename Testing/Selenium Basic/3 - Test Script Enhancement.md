![[Pasted image 20230201102716.png]]

_**Apache POI**_ uses certain terms to work with _Microsoft Excel._
- **Workbook**:	A workbook represents a Microsoft Excel file. It can be used for creating and maintaining the spreadsheet. A workbook may contain many sheets.
- **Sheet**:	A sheet refers to a page in a Microsoft Excel file that contains the number of rows and columns.
- **Row**:	A row represents a collection of cells, which is used to represent a row in the spreadsheet.
- **Cell**:	A cell is indicated by a row and column combination. Data entered by a user is stored in a cell. Data can be of the type such as string, numeric value, or formula.



## Managing Excel

![[Pasted image 20230201152351.png]]
_Apache POI_ provides various interfaces and classes that help us to work with _Excel._ It provides a _**"Workbook "**_ interface to maintain Excel Workbooks.

-   **Workbook**: XSSFWorkbook and HSSFWorkbook classes implement this interface.
-   **XSSFWorkbook**: Is a class representation of XLSX file.
-   **HSSFWorkbook**: Is a class representation of XLS file.
-   **Sheet**: XSSFSheet and HSSFSheet classes implement this interface.
-   **XSSFSheet**: Is a class representing a sheet in an XLSX file.
-   **HSSFSheet**: Is a class representing a sheet in an XLS file.
-   **Row**: XSSFRow and HSSFRow classes implement this interface.
-   **XSSFRow**: Is a class representing a row in the sheet of XLSX file.
-   **HSSFRow**: Is a class representing a row in the sheet of XLS file.
-   **Cell**: XSSFCell and HSSFCell classes implement this interface.
-   **XSSFCell**: Is a class representing a cell in a row of XLSX file.
-   **HSSFCell:** Is a class representing a cell in a row of XLS file.