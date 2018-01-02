---
title: Oggetti DataRow e DataRowView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ac8209432cd975539983226cfba51f229d696bd4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="9fac7-102">Oggetti DataRow e DataRowView</span><span class="sxs-lookup"><span data-stu-id="9fac7-102">DataRows and DataRowViews</span></span>
<span data-ttu-id="9fac7-103">In un <xref:System.Data.DataView> viene esposto una raccolta enumerabile di oggetti <xref:System.Data.DataRowView>.</span><span class="sxs-lookup"><span data-stu-id="9fac7-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="9fac7-104">Il **DataRowView** gli oggetti espongano valori come matrici di oggetti indicizzati in base al nome o il riferimento ordinale della colonna nella tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="9fac7-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="9fac7-105">È possibile accedere il <xref:System.Data.DataRow> esposto dal **DataRowView** utilizzando il <xref:System.Data.DataRowView.Row%2A> proprietà del **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="9fac7-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="9fac7-106">Quando si visualizzano i valori utilizzando un **DataRowView**, <xref:System.Data.DataView.RowStateFilter%2A> proprietà del **DataView** determina quale versione di riga dell'oggetto sottostante **DataRow** viene esposta.</span><span class="sxs-lookup"><span data-stu-id="9fac7-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="9fac7-107">Per informazioni sull'accesso a diverse versioni di riga utilizzando un **DataRow**, vedere [stati delle righe e le versioni di riga](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="9fac7-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="9fac7-108">Nell'esempio di codice seguente vengono visualizzati tutti i valori correnti e originali in una tabella.</span><span class="sxs-lookup"><span data-stu-id="9fac7-108">The following code example displays all the current and original values in a table.</span></span>  
  
```vb  
Dim catView As DataView = New DataView(catDS.Tables("Categories"))  
Console.WriteLine("Current Values:")  
WriteView(catView)  
Console.WriteLine("Original Values:")  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal  
WriteView(catView)      
  
Public Shared Sub WriteView(thisDataView As DataView)  
  Dim rowView As DataRowView  
  Dim i As Integer  
  
  For Each rowView In thisDataView  
    For i = 0 To thisDataView.Table.Columns.Count - 1  
      Console.Write(rowView(i) & vbTab)  
    Next  
    Console.WriteLine()  
  Next  
End Sub  
```  
  
```csharp  
DataView catView = new DataView(catDS.Tables["Categories"]);  
Console.WriteLine("Current Values:");  
WriteView(catView);  
Console.WriteLine("Original Values:");  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal;  
WriteView(catView);  
  
public static void WriteView(DataView thisDataView)  
{  
  foreach (DataRowView rowView in thisDataView)  
  {  
    for (int i = 0; i < thisDataView.Table.Columns.Count; i++)  
      Console.Write(rowView[i] + "\t");  
    Console.WriteLine();  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fac7-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fac7-109">See Also</span></span>  
 <xref:System.Data.DataRowVersion>  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [<span data-ttu-id="9fac7-110">DataView</span><span class="sxs-lookup"><span data-stu-id="9fac7-110">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="9fac7-111">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="9fac7-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
