---
title: Oggetti DataRow e DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: 8a98dc44eda9ebda09235193c58bd831fc52d04d
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205099"
---
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="6a2ae-102">Oggetti DataRow e DataRowView</span><span class="sxs-lookup"><span data-stu-id="6a2ae-102">DataRows and DataRowViews</span></span>
<span data-ttu-id="6a2ae-103">In un <xref:System.Data.DataView> viene esposto una raccolta enumerabile di oggetti <xref:System.Data.DataRowView>.</span><span class="sxs-lookup"><span data-stu-id="6a2ae-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="6a2ae-104">Gli oggetti **DataRowView** espongono i valori come matrici di oggetti indicizzati in base al nome o al riferimento ordinale della colonna nella tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="6a2ae-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="6a2ae-105">È possibile accedere all' <xref:System.Data.DataRow> oggetto esposto dall'oggetto **DataRowView** utilizzando la <xref:System.Data.DataRowView.Row%2A> proprietà dell'oggetto **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="6a2ae-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="6a2ae-106">Quando si visualizzano i valori utilizzandoun oggetto DataRowView <xref:System.Data.DataView.RowStateFilter%2A> , la proprietà di **DataView** determina quale versione di riga del **DataRow** sottostante è esposta.</span><span class="sxs-lookup"><span data-stu-id="6a2ae-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="6a2ae-107">Per informazioni sull'accesso a versioni di riga diverse utilizzando un **DataRow**, vedere [Stati di riga e versioni di riga](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="6a2ae-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="6a2ae-108">Nell'esempio di codice seguente vengono visualizzati tutti i valori correnti e originali in una tabella.</span><span class="sxs-lookup"><span data-stu-id="6a2ae-108">The following code example displays all the current and original values in a table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6a2ae-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a2ae-109">See also</span></span>

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="6a2ae-110">DataView</span><span class="sxs-lookup"><span data-stu-id="6a2ae-110">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="6a2ae-111">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="6a2ae-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
