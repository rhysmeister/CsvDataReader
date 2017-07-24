CsvDataReader
=============

A simple C# IDataReader implementation to read CSV files.  This was built to improve CSV performance in PowerShell.  The goal is to enable code like the following.

__If you download the DLL, you need to Unblock it before you can use it.  That's done in the File Properties dialog box.__


	[System.Reflection.Assembly]::LoadFrom("CsvDataReader.dll")
  $separator=[char]9; # Pipe character 
  #$separator=";"
  #$separator=$null; # defaults to comma (,) in this case
	$reader = New-Object SqlUtilities.CsvDataReader("SimpleCsv.txt", $separator);
		
	$bulkCopy = new-object ("Data.SqlClient.SqlBulkCopy") $ConnectionString
	$bulkCopy.DestinationTableName = "CsvDataReader"
		
	$bulkCopy.WriteToServer($reader);




