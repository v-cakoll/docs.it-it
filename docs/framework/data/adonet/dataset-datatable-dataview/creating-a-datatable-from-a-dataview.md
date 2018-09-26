---
title: Creazione di un oggetto DataTable da un oggetto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d45cf41-d8ae-4409-af3e-a96a7e476d85
ms.openlocfilehash: ccf95ff250cc7c23b1ff981087de0f1310472880
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170496"
---
# <a name="creating-a-datatable-from-a-dataview"></a><span data-ttu-id="a342e-102">Creazione di un oggetto DataTable da un oggetto DataView</span><span class="sxs-lookup"><span data-stu-id="a342e-102">Creating a DataTable from a DataView</span></span>
<span data-ttu-id="a342e-103">Una volta recuperati i dati da un'origine dati e compilato un tipo <xref:System.Data.DataTable>, è possibile ordinare, filtrare o limitare i dati restituiti senza doverli recuperare nuovamente.</span><span class="sxs-lookup"><span data-stu-id="a342e-103">Once you have retrieved data from a data source, and have filled a <xref:System.Data.DataTable> with the data, you may want to sort, filter, or otherwise limit the returned data without retrieving it again.</span></span> <span data-ttu-id="a342e-104">Questo è reso possibile dalla classe <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="a342e-104">The <xref:System.Data.DataView> class makes this possible.</span></span> <span data-ttu-id="a342e-105">Inoltre, se è necessario creare un nuovo <xref:System.Data.DataTable> dal <xref:System.Data.DataView>, è possibile utilizzare il <xref:System.Data.DataView.ToTable%2A> per copiare tutte le righe e colonne o un subset dei dati in un nuovo metodo <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="a342e-105">In addition, if you need to create a new <xref:System.Data.DataTable> from the <xref:System.Data.DataView>, you can use the <xref:System.Data.DataView.ToTable%2A> method to copy all the rows and columns, or a subset of the data into a new <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="a342e-106">Il metodo <xref:System.Data.DataView.ToTable%2A> fornisce gli overload per:</span><span class="sxs-lookup"><span data-stu-id="a342e-106">The <xref:System.Data.DataView.ToTable%2A> method provides overloads to:</span></span>  
  
-   <span data-ttu-id="a342e-107">Creare un tipo <xref:System.Data.DataTable> contenente colonne che rappresentano un subset delle colonne del tipo <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="a342e-107">Create a <xref:System.Data.DataTable> containing columns that are a subset of the columns in the <xref:System.Data.DataView>.</span></span>  
  
-   <span data-ttu-id="a342e-108">Creare un <xref:System.Data.DataTable> che include solo righe distinte provenienti dalla <xref:System.Data.DataView>, in modo analogo alla parola chiave DISTINCT in Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a342e-108">Create a <xref:System.Data.DataTable> that includes only distinct rows from the <xref:System.Data.DataView>, analogously to the DISTINCT keyword in Transact-SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a342e-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a342e-109">Example</span></span>  
 <span data-ttu-id="a342e-110">L'esempio di applicazione console seguente crea una <xref:System.Data.DataTable> che contiene i dati dal **Person. Contact** nella tabella di **AdventureWorks** database di esempio.</span><span class="sxs-lookup"><span data-stu-id="a342e-110">The following console application example creates a <xref:System.Data.DataTable> that contains data from the **Person.Contact** table in the **AdventureWorks** sample database.</span></span> <span data-ttu-id="a342e-111">Successivamente, nell'esempio viene creato un controllo ordinato e filtrato <xref:System.Data.DataView> base il <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="a342e-111">Next, the example creates a sorted and filtered <xref:System.Data.DataView> based on the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="a342e-112">Dopo aver visualizzato il contenuto del <xref:System.Data.DataTable> e il <xref:System.Data.DataView>, nell'esempio viene creato un nuovo <xref:System.Data.DataTable> dal <xref:System.Data.DataView> chiamando il <xref:System.Data.DataView.ToTable%2A> metodo, selezionando solo un subset delle colonne disponibili.</span><span class="sxs-lookup"><span data-stu-id="a342e-112">After displaying the contents of the <xref:System.Data.DataTable> and the <xref:System.Data.DataView>, the example creates a new <xref:System.Data.DataTable> from the <xref:System.Data.DataView> by calling the <xref:System.Data.DataView.ToTable%2A> method, selecting only a subset of the available columns.</span></span> <span data-ttu-id="a342e-113">Infine, viene visualizzato il contenuto del nuovo tipo <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="a342e-113">Finally, the example displays the contents of the new <xref:System.Data.DataTable>.</span></span>  
  
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
  
 <span data-ttu-id="a342e-114">}</span><span class="sxs-lookup"><span data-stu-id="a342e-114">}</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a342e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a342e-115">See Also</span></span>  
 <xref:System.Data.DataView.ToTable%2A>  
 [<span data-ttu-id="a342e-116">DataView</span><span class="sxs-lookup"><span data-stu-id="a342e-116">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="a342e-117">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="a342e-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
