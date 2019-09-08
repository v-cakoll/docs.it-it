---
title: Informazioni sugli errori di riga
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b1f9070-d032-48c7-b030-bd8fbb2ca59a
ms.openlocfilehash: 5ede6e2cd52ad55f8c35a42d137044dd1ceea400
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785962"
---
# <a name="row-error-information"></a>Informazioni sugli errori di riga
Per evitare di dover rispondere agli errori delle righe mentre si modificano i valori di una <xref:System.Data.DataTable>, è possibile aggiungere alla riga le informazioni sugli errori per un uso successivo. A questo scopo, l'oggetto <xref:System.Data.DataRow> fornisce una proprietà <xref:System.Data.DataRow.RowError%2A> su ciascuna riga. L'aggiunta di dati alla proprietà **RowError** di un **DataRow** imposta <xref:System.Data.DataRow.HasErrors%2A> la proprietà di **DataRow** su **true**. Se **DataRow** fa parte di una **DataTable**e **DataRow. HasErrors** è **true**, anche la proprietà **DataTable. HasErrors** è **true**. Questo vale anche per il **set di dati** a cui appartiene la **DataTable** . Quando si verificano errori, è possibile controllare la proprietà **HasErrors** per determinare se le informazioni sull'errore sono state aggiunte a qualsiasi riga. Se **HasErrors** è **true**, è possibile usare il <xref:System.Data.DataTable.GetErrors%2A> metodo dell' **oggetto DataTable** per restituire ed esaminare solo le righe con errori, come illustrato nell'esempio seguente.  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
workTable.Columns.Add("CustID", Type.GetType("System.Int32"))  
workTable.Columns.Add("Total", Type.GetType("System.Double"))  
  
AddHandler workTable.RowChanged, New DataRowChangeEventHandler(AddressOf OnRowChanged)  
  
Dim i  As Int32  
  
For i  = 0 To 10  
  workTable.Rows.Add(New Object() {i , i *100})  
Next  
  
If workTable.HasErrors Then  
  Console.WriteLine("Errors in Table " & workTable.TableName)  
  
  Dim myRow As DataRow  
  
  For Each myRow In workTable.GetErrors()  
    Console.WriteLine("CustID = " & myRow("CustID").ToString())  
    Console.WriteLine(" Error = " & myRow.RowError & vbCrLf)  
  Next  
End If  
  
Private Shared Sub OnRowChanged( _  
    sender As Object, args As DataRowChangeEventArgs)  
  ' Check for zero values.  
  If CDbl(args.Row("Total")) = 0 Then args.Row.RowError = _  
      "Total cannot be 0."  
End Sub  
```  
  
```csharp  
DataTable  workTable = new DataTable("Customers");  
workTable.Columns.Add("CustID", typeof(Int32));  
workTable.Columns.Add("Total", typeof(Double));  
  
workTable.RowChanged += new DataRowChangeEventHandler(OnRowChanged);  
  
for (int i = 0; i < 10; i++)  
  workTable.Rows.Add(new Object[] {i, i*100});  
  
if (workTable.HasErrors)  
{  
  Console.WriteLine("Errors in Table " + workTable.TableName);  
  
  foreach (DataRow myRow in workTable.GetErrors())  
  {  
    Console.WriteLine("CustID = " + myRow["CustID"]);  
    Console.WriteLine(" Error = " + myRow.RowError + "\n");  
  }  
}  
  
protected static void OnRowChanged(  
    Object sender, DataRowChangeEventArgs args)  
{  
  // Check for zero values.  
  if (args.Row["Total"].Equals(0D))  
    args.Row.RowError = "Total cannot be 0.";  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- [Manipolazione di dati in un oggetto DataTable](manipulating-data-in-a-datatable.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
