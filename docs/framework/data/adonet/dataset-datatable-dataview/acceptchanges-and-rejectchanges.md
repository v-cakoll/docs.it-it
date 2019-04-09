---
title: AcceptChanges e RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: bbcc666b99c2bade479e5ee51750b043c820845d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172900"
---
# <a name="acceptchanges-and-rejectchanges"></a>AcceptChanges e RejectChanges
Dopo aver verificato la correttezza delle modifiche apportate ai dati in un <xref:System.Data.DataTable>, è possibile accettare le modifiche utilizzando il <xref:System.Data.DataRow.AcceptChanges%2A> metodo per il <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, o <xref:System.Data.DataSet>, che imposterà il **corrente** riga per i valori di **originale** i valori e imposterà il **RowState** proprietà **Unchanged**. Accettare o rifiutare le modifiche apportate a qualsiasi Azzera **RowError** informazioni e imposta il **HasErrors** proprietà **false**. È inoltre possibile che l'accettazione o il rifiuto delle modifiche influisca sui dati di aggiornamento nell'origine dati. Per altre informazioni, vedere [l'aggiornamento di origini dati con DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).  
  
 Se i vincoli di chiave esterni esistono nel **DataTable**, le modifiche accettate o rifiutate tramite **AcceptChanges** e **RejectChanges** vengono propagati alle righe figlio del  **DataRow** in base al **AcceptRejectRule**. Per altre informazioni, vedere [vincoli DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 L'esempio seguente controlla se sono presenti righe con errori, risolve errori laddove è possibile e rifiuta le righe contenenti errori non risolvibili. Si noti che, per risolvere gli errori, il **RowError** valore viene reimpostato su una stringa vuota, provocando la **HasErrors** proprietà da impostare **false**. Quando sono state risolte o rifiutate, tutte le righe con errori **AcceptChanges** viene chiamato per accettare tutte le modifiche per l'intera **DataTable**.  
  
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
- [Manipolazione di dati in un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
