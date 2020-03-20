---
title: Oggetti DataRow e DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: 14e7e1ccb051410c351e49afee9f2d6809264833
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151299"
---
# <a name="datarows-and-datarowviews"></a>Oggetti DataRow e DataRowView
In un <xref:System.Data.DataView> viene esposto una raccolta enumerabile di oggetti <xref:System.Data.DataRowView>. Gli oggetti **DataRowView** espongono i valori come matrici di oggetti indicizzati in base al nome o al riferimento ordinale della colonna nella tabella sottostante. È possibile <xref:System.Data.DataRow> accedere all'oggetto esposto da <xref:System.Data.DataRowView.Row%2A> **DataRowView** utilizzando la proprietà di **DataRowView**.  
  
 Quando si visualizzano i valori utilizzando <xref:System.Data.DataView.RowStateFilter%2A> un **DataRowView**, la proprietà del **DataView** determina quale versione di riga del **DataRow** sottostante viene esposta. Per informazioni sull'accesso a versioni di riga diverse mediante **DataRow**, vedere [Stati riga e Versioni riga](row-states-and-row-versions.md).  
  
 Nell'esempio di codice seguente vengono visualizzati tutti i valori correnti e originali in una tabella.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [DataView](dataviews.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
