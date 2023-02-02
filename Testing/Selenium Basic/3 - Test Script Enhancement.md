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


```java
public class Demo14 {

	@Test
	public void test() throws Exception {

		// Path from where the excel file has to be read
		// ? String filePath = System.getProperty("user.dir") + "\\Cred.xlsx";

		FileInputStream fis = new FileInputStream("C:\\Users\\karan.rawat01\\Documents\\Java\\Liquid\\dat1.xlsx");

		// Workbook reference of the excel file
		XSSFWorkbook workbook = new XSSFWorkbook(fis);

		// Sheet which needs to be accessed from within the workbook
		// ?XSSFSheet sheet = workbook.getSheetAt(0);
		XSSFSheet sheet = workbook.getSheet("Rock");

		// Count the number of rows
		int noOfRows = sheet.getLastRowNum() - sheet.getFirstRowNum();

		// int cellsCount = sheet.getRow(1).getLastCellNum();
		// System.out.println(cellsCount);

		System.out.println(noOfRows);
		System.out.println(sheet.getRow(1).getCell(0).getNumericCellValue());
		System.out.println(sheet.getRow(1).getCell(1).getStringCellValue());
		System.out.println(sheet.getRow(1).getCell(2).getRawValue());
		System.out.println(sheet.getRow(1).getCell(3).getStringCellValue());
		System.out.println(sheet.getRow(1).getCell(4).getDateCellValue());

		// iterating through whole Table
		for (int i = 0; i < noOfRows; i++) {
			int cellsCount = sheet.getRow(i).getLastCellNum();
			System.out.println("Row " + i + " data is : ");
			for (int j = 0; j < cellsCount; j++) {
				System.out.print(sheet.getRow(i).getCell(j) + " ");
			}
			System.out.println();
		}

		sheet.getRow(1).createCell(5).setCellValue("Pune");// updating cell value
		sheet.createRow(2).createCell(5).setCellValue("Banglore");// create new cell value
		System.out.println(sheet.getRow(1).getCell(5).getStringCellValue());

		XSSFRow row2=sheet.createRow(4);
        
        //create a cell object to enter value in it using cell Index
        row2.createCell(0).setCellValue("mary");
        row2.createCell(1).setCellValue("Jane");
        row2.createCell(2).setCellValue("janes@gmail.com");
        row2.createCell(3).setCellValue("male");
        row2.createCell(4).setCellValue("8786823923432");
        row2.createCell(5).setCellValue("Park9 Lane, Flat C2 , New Jersey");

	//Create an output stream with the location where the file has to be created
		FileOutputStream fos = new FileOutputStream("C:\\Users\\karan.rawat01\\Documents\\Java\\Liquid\\dat1.xlsx");
		workbook.write(fos);
		workbook.close();
		fos.close();

	}
}

```
## Taking Screenshot

```java
        //Typecast the driver reference variable with TakesScreenshot for access the methods from TakesScreenshot interface
          //getScreenshotAs method will take arguement for the output type of the file
          File scrFile = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);

        //Using the FileUtils class copy the generated screenshot file to any location
          FileUtils.copyFile(scrFile, new File("C:\\Users\\some_user\\Desktop\\Image.png"));
```

## Exception Handling

During script execution, your test methods (a block of statements within the @test annotation) may encounter unexpected Java exceptions like

-   ArrayOutOfBoundsException
    
-   NullPointerException
    
-   ArithmeticException
    
-   NoSuchElementException