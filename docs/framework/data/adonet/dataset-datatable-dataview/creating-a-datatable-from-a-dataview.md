---
title: Creazione di un oggetto DataTable da un oggetto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d45cf41-d8ae-4409-af3e-a96a7e476d85
ms.openlocfilehash: 6e066bcbe02fa9cf498e11af431b9f6dcd4432ab
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785518"
---
# <a name="creating-a-datatable-from-a-dataview"></a><span data-ttu-id="d8e59-102">Creazione di un oggetto DataTable da un oggetto DataView</span><span class="sxs-lookup"><span data-stu-id="d8e59-102">Creating a DataTable from a DataView</span></span>
<span data-ttu-id="d8e59-103">Una volta recuperati i dati da un'origine dati e compilato un tipo <xref:System.Data.DataTable>, è possibile ordinare, filtrare o limitare i dati restituiti senza doverli recuperare nuovamente.</span><span class="sxs-lookup"><span data-stu-id="d8e59-103">Once you have retrieved data from a data source, and have filled a <xref:System.Data.DataTable> with the data, you may want to sort, filter, or otherwise limit the returned data without retrieving it again.</span></span> <span data-ttu-id="d8e59-104">Questo è reso possibile dalla classe <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="d8e59-104">The <xref:System.Data.DataView> class makes this possible.</span></span> <span data-ttu-id="d8e59-105">Inoltre, se è <xref:System.Data.DataTable> necessario creare un nuovo <xref:System.Data.DataView>da, è possibile utilizzare il <xref:System.Data.DataView.ToTable%2A> metodo per copiare tutte le righe e le colonne oppure un subset dei dati in un nuovo <xref:System.Data.DataTable>oggetto.</span><span class="sxs-lookup"><span data-stu-id="d8e59-105">In addition, if you need to create a new <xref:System.Data.DataTable> from the <xref:System.Data.DataView>, you can use the <xref:System.Data.DataView.ToTable%2A> method to copy all the rows and columns, or a subset of the data into a new <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="d8e59-106">Il metodo <xref:System.Data.DataView.ToTable%2A> fornisce gli overload per:</span><span class="sxs-lookup"><span data-stu-id="d8e59-106">The <xref:System.Data.DataView.ToTable%2A> method provides overloads to:</span></span>  
  
- <span data-ttu-id="d8e59-107">Creare un tipo <xref:System.Data.DataTable> contenente colonne che rappresentano un subset delle colonne del tipo <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="d8e59-107">Create a <xref:System.Data.DataTable> containing columns that are a subset of the columns in the <xref:System.Data.DataView>.</span></span>  
  
- <span data-ttu-id="d8e59-108">Creare un <xref:System.Data.DataTable> oggetto che include solo righe distinte <xref:System.Data.DataView>dall'oggetto, in modo analogo alla parola chiave DISTINCT in Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="d8e59-108">Create a <xref:System.Data.DataTable> that includes only distinct rows from the <xref:System.Data.DataView>, analogously to the DISTINCT keyword in Transact-SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8e59-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8e59-109">Example</span></span>  
 <span data-ttu-id="d8e59-110">Nell'esempio di applicazione console seguente viene <xref:System.Data.DataTable> creato un oggetto contenente i dati della tabella **Person. Contact** del database di esempio **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="d8e59-110">The following console application example creates a <xref:System.Data.DataTable> that contains data from the **Person.Contact** table in the **AdventureWorks** sample database.</span></span> <span data-ttu-id="d8e59-111">Successivamente, nell'esempio viene creato un oggetto ordinato <xref:System.Data.DataView> e filtrato <xref:System.Data.DataTable>in base a.</span><span class="sxs-lookup"><span data-stu-id="d8e59-111">Next, the example creates a sorted and filtered <xref:System.Data.DataView> based on the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="d8e59-112">Dopo aver visualizzato il contenuto di <xref:System.Data.DataTable> <xref:System.Data.DataView>e, nell'esempio viene creato un nuovo <xref:System.Data.DataTable> oggetto dall' <xref:System.Data.DataView> oggetto chiamando il <xref:System.Data.DataView.ToTable%2A> metodo, selezionando solo un subset delle colonne disponibili.</span><span class="sxs-lookup"><span data-stu-id="d8e59-112">After displaying the contents of the <xref:System.Data.DataTable> and the <xref:System.Data.DataView>, the example creates a new <xref:System.Data.DataTable> from the <xref:System.Data.DataView> by calling the <xref:System.Data.DataView.ToTable%2A> method, selecting only a subset of the available columns.</span></span> <span data-ttu-id="d8e59-113">Infine, viene visualizzato il contenuto del nuovo tipo <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="d8e59-113">Finally, the example displays the contents of the new <xref:System.Data.DataTable>.</span></span>  
  
```vb  
Private Sub DemonstrateDataView()  
    ' Retrieve a DataTable from the AdventureWorks sample database.  
    ' connectionString is assumed to be a valid connection string.  
    Dim adapter As New SqlDataAdapter( _  
       "SELECT FirstName, LastName, EmailAddress FROM Person.Contact WHERE FirstName LIKE 'Mich%'", connectionString)  
    Dim table As New DataTable  
  
    adapter.Fill(table)  
    Console.WriteLine("Original table name: " & table.TableName)  
    ' Print current table values.  
    PrintTableOrView(table, "Current Values in Table")  
  
    ' Now create a DataView based on the DataTable.  
    ' Sort and filter the data.  
    Dim view As DataView = table.DefaultView  
    view.Sort = "LastName, FirstName"  
    view.RowFilter = "LastName > 'M'"  
    PrintTableOrView(view, "Current Values in View")  
  
    ' Create a new DataTable based on the DataView,  
    ' requesting only two columns with distinct values  
    ' in the columns.  
    Dim newTable As DataTable = view.ToTable("UniqueLastNames", True, "FirstName", "LastName")  
    PrintTableOrView(newTable, "Table created from DataView")  
    Console.WriteLine("New table name: " & newTable.TableName)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
    End Sub  
  
Private Sub PrintTableOrView(ByVal dv As DataView, ByVal label As String)  
    Dim sw As System.IO.StringWriter  
    Dim output As String  
    Dim table As DataTable = dv.Table  
  
    Console.WriteLine(label)  
  
    ' Loop through each row in the view.  
    For Each rowView As DataRowView In dv  
        sw = New System.IO.StringWriter  
  
        ' Loop through each column.  
        For Each col As DataColumn In table.Columns  
            ' Output the value of each column's data.  
            sw.Write(rowView(col.ColumnName).ToString() & ", ")  
        Next  
        output = sw.ToString  
        ' Trim off the trailing ", ", so the output looks correct.  
        If output.Length > 2 Then  
            output = output.Substring(0, output.Length - 2)  
        End If  
        ' Display the row in the console window.  
        Console.WriteLine(output)  
    Next  
    Console.WriteLine()  
End Sub  
  
Private Sub PrintTableOrView(ByVal table As DataTable, ByVal label As String)  
    Dim sw As System.IO.StringWriter  
    Dim output As String  
  
    Console.WriteLine(label)  
  
    ' Loop through each row in the table.  
    For Each row As DataRow In table.Rows  
        sw = New System.IO.StringWriter  
        ' Loop through each column.  
        For Each col As DataColumn In table.Columns  
            ' Output the value of each column's data.  
            sw.Write(row(col).ToString() & ", ")  
        Next  
        output = sw.ToString  
        ' Trim off the trailing ", ", so the output looks correct.  
        If output.Length > 2 Then  
            output = output.Substring(0, output.Length - 2)  
        End If  
        ' Display the row in the console window.  
        Console.WriteLine(output)  
    Next  
    Console.WriteLine()  
    End Sub  
End Module  
```  
  
```csharp  
private static void DemonstrateDataView()  
{  
// Retrieve a DataTable from the AdventureWorks sample database.  
// connectionString is assumed to be a valid connection string.  
SqlDataAdapter adapter = new SqlDataAdapter(  
    "SELECT FirstName, LastName, EmailAddress " +  
    "FROM Person.Contact WHERE FirstName LIKE 'Mich%'",   
       GetConnectionString());  
DataTable table = new DataTable();  
  
adapter.Fill(table);  
Console.WriteLine("Original table name: " + table.TableName);  
// Print current table values.  
PrintTableOrView(table, "Current Values in Table");  
  
// Now create a DataView based on the DataTable.  
// Sort and filter the data.  
DataView view = table.DefaultView;  
view.Sort = "LastName, FirstName";  
view.RowFilter = "LastName > 'M'";  
PrintTableOrView(view, "Current Values in View");  
  
// Create a new DataTable based on the DataView,  
// requesting only two columns with distinct values  
// in the columns.  
DataTable newTable = view.ToTable("UniqueLastNames",  
     true, "FirstName", "LastName");  
PrintTableOrView(newTable, "Table created from DataView");  
Console.WriteLine("New table name: " + newTable.TableName);  
  
Console.WriteLine("Press any key to continue.");  
Console.ReadKey();  
}  
  
private static void PrintTableOrView(DataView dv, string label)  
{  
System.IO.StringWriter sw;  
string output;  
DataTable table = dv.Table;  
  
Console.WriteLine(label);  
  
// Loop through each row in the view.  
foreach (DataRowView rowView in dv)  
{  
    sw = new System.IO.StringWriter();  
  
    // Loop through each column.  
    foreach (DataColumn col in table.Columns)  
    {  
        // Output the value of each column's data.  
        sw.Write(rowView[col.ColumnName].ToString() + ", ");  
    }  
    output = sw.ToString();  
    // Trim off the trailing ", ", so the output looks correct.  
    if (output.Length > 2)  
    {  
        output = output.Substring(0, output.Length - 2);  
    }  
    // Display the row in the console window.  
    Console.WriteLine(output);  
}  
Console.WriteLine();  
}  
  
private static void PrintTableOrView(DataTable table, string label)  
{  
System.IO.StringWriter sw;  
string output;  
  
Console.WriteLine(label);  
  
// Loop through each row in the table.  
foreach (DataRow row in table.Rows)  
{  
    sw = new System.IO.StringWriter();  
    // Loop through each column.  
    foreach (DataColumn col in table.Columns)  
    {  
        // Output the value of each column's data.  
        sw.Write(row[col].ToString() + ", ");  
    }  
    output = sw.ToString();  
    // Trim off the trailing ", ", so the output looks correct.  
    if (output.Length > 2)  
    {  
        output = output.Substring(0, output.Length - 2);  
    }  
    // Display the row in the console window.  
    Console.WriteLine(output);  
} //  
Console.WriteLine();  
}  
```  
  
 <span data-ttu-id="d8e59-114">}</span><span class="sxs-lookup"><span data-stu-id="d8e59-114">}</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e59-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8e59-115">See also</span></span>

- <xref:System.Data.DataView.ToTable%2A>
- [<span data-ttu-id="d8e59-116">DataView</span><span class="sxs-lookup"><span data-stu-id="d8e59-116">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="d8e59-117">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d8e59-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
