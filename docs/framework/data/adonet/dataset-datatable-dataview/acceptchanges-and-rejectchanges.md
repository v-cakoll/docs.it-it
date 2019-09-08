---
title: AcceptChanges e RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: c537fa808fc6ba4c740e71bfd70fe9cd1f3bd31a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785568"
---
# <a name="acceptchanges-and-rejectchanges"></a>AcceptChanges e RejectChanges
Dopo la verifica dell'accuratezza delle modifiche apportate ai <xref:System.Data.DataTable>dati in un oggetto, è possibile accettare <xref:System.Data.DataRow.AcceptChanges%2A> le modifiche utilizzando <xref:System.Data.DataRow>il metodo dell' <xref:System.Data.DataSet>oggetto, <xref:System.Data.DataTable>o, che imposta i valori di **riga correnti come** I valori originali e impostano la proprietà **RowState** su **Unchanged**. L'accettazione o il rifiuto delle modifiche Cancella tutte le informazioni **RowError** e imposta la proprietà **HasErrors** su **false**. È inoltre possibile che l'accettazione o il rifiuto delle modifiche influisca sui dati di aggiornamento nell'origine dati. Per ulteriori informazioni, vedere [aggiornamento di origini dati con DataAdapter](../updating-data-sources-with-dataadapters.md).  
  
 Se nella **DataTable**sono presenti vincoli di chiave esterna, le modifiche accettate o rifiutate mediante **AcceptChanges** e **RejectChanges** vengono propagate alle righe figlio del **DataRow** in base **al ForeignKeyConstraint. AcceptRejectRule**. Per altre informazioni, vedere [vincoli DataTable](datatable-constraints.md).  
  
 L'esempio seguente controlla se sono presenti righe con errori, risolve errori laddove è possibile e rifiuta le righe contenenti errori non risolvibili. Si noti che, per gli errori risolti, il valore di **RowError** viene reimpostato su una stringa vuota, causando l'impostazione della proprietà **HasErrors** su **false**. Quando tutte le righe con errori sono state risolte o rifiutate, **AcceptChanges** viene chiamato per accettare tutte le modifiche per l'intero **DataTable**.  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Manipolazione di dati in un oggetto DataTable](manipulating-data-in-a-datatable.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
