---
title: Informazioni sugli errori di riga
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b1f9070-d032-48c7-b030-bd8fbb2ca59a
ms.openlocfilehash: cf798ac88ba83e890086cec7424c8c363980718f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530545"
---
# <a name="row-error-information"></a><span data-ttu-id="2074c-102">Informazioni sugli errori di riga</span><span class="sxs-lookup"><span data-stu-id="2074c-102">Row Error Information</span></span>
<span data-ttu-id="2074c-103">Per evitare di dover rispondere agli errori delle righe mentre si modificano i valori di una <xref:System.Data.DataTable>, è possibile aggiungere alla riga le informazioni sugli errori per un uso successivo.</span><span class="sxs-lookup"><span data-stu-id="2074c-103">To avoid having to respond to row errors while editing values in a <xref:System.Data.DataTable>, you can add the error information to the row for later use.</span></span> <span data-ttu-id="2074c-104">A questo scopo, l'oggetto <xref:System.Data.DataRow> fornisce una proprietà <xref:System.Data.DataRow.RowError%2A> su ciascuna riga.</span><span class="sxs-lookup"><span data-stu-id="2074c-104">The <xref:System.Data.DataRow> object provides a <xref:System.Data.DataRow.RowError%2A> property on each row for this purpose.</span></span> <span data-ttu-id="2074c-105">Aggiunta di dati per il **RowError** proprietà di un **DataRow** imposta la <xref:System.Data.DataRow.HasErrors%2A> proprietà del **DataRow** a **true**.</span><span class="sxs-lookup"><span data-stu-id="2074c-105">Adding data to the **RowError** property of a **DataRow** sets the <xref:System.Data.DataRow.HasErrors%2A> property of the **DataRow** to **true**.</span></span> <span data-ttu-id="2074c-106">Se il **DataRow** fa parte di un **DataTable**, e **DataRow. HasErrors** è **true**, il **DataTable. HasErrors** risulta anche la proprietà **true**.</span><span class="sxs-lookup"><span data-stu-id="2074c-106">If the **DataRow** is part of a **DataTable**, and **DataRow.HasErrors** is **true**, the **DataTable.HasErrors** property is also **true**.</span></span> <span data-ttu-id="2074c-107">Si applica anche al **set di dati** a cui il **DataTable** appartiene.</span><span class="sxs-lookup"><span data-stu-id="2074c-107">This applies as well to the **DataSet** to which the **DataTable** belongs.</span></span> <span data-ttu-id="2074c-108">Durante il test per gli errori, è possibile controllare la **HasErrors** proprietà per determinare se le informazioni sull'errore è stato aggiunto a tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="2074c-108">When testing for errors, you can check the **HasErrors** property to determine if error information has been added to any rows.</span></span> <span data-ttu-id="2074c-109">Se **HasErrors** viene **true**, è possibile usare il <xref:System.Data.DataTable.GetErrors%2A> metodo del **DataTable** per restituire ed esaminare solo le righe con errori, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2074c-109">If **HasErrors** is **true**, you can use the <xref:System.Data.DataTable.GetErrors%2A> method of the **DataTable** to return and examine only the rows with errors, as shown in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2074c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2074c-110">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="2074c-111">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="2074c-111">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="2074c-112">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="2074c-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
