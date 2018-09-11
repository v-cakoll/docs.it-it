---
title: AcceptChanges e RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: 30b2c303b1823430c480f0706500f8f7e7053c4c
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44272969"
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="7768a-102">AcceptChanges e RejectChanges</span><span class="sxs-lookup"><span data-stu-id="7768a-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="7768a-103">Dopo aver verificato la correttezza delle modifiche apportate ai dati in un <xref:System.Data.DataTable>, è possibile accettare le modifiche utilizzando il <xref:System.Data.DataRow.AcceptChanges%2A> metodo per il <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, o <xref:System.Data.DataSet>, che imposterà il **corrente** riga per i valori di **originale** i valori e imposterà il **RowState** proprietà **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="7768a-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="7768a-104">Accettare o rifiutare le modifiche apportate a qualsiasi Azzera **RowError** informazioni e imposta il **HasErrors** proprietà **false**.</span><span class="sxs-lookup"><span data-stu-id="7768a-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="7768a-105">È inoltre possibile che l'accettazione o il rifiuto delle modifiche influisca sui dati di aggiornamento nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="7768a-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="7768a-106">Per altre informazioni, vedere [l'aggiornamento di origini dati con DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span><span class="sxs-lookup"><span data-stu-id="7768a-106">For more information, see [Updating Data Sources with DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="7768a-107">Se i vincoli di chiave esterni esistono nel **DataTable**, le modifiche accettate o rifiutate tramite **AcceptChanges** e **RejectChanges** vengono propagati alle righe figlio del  **DataRow** in base al **AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="7768a-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="7768a-108">Per altre informazioni, vedere [vincoli DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="7768a-108">For more information, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="7768a-109">L'esempio seguente controlla se sono presenti righe con errori, risolve errori laddove è possibile e rifiuta le righe contenenti errori non risolvibili.</span><span class="sxs-lookup"><span data-stu-id="7768a-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="7768a-110">Si noti che, per risolvere gli errori, il **RowError** valore viene reimpostato su una stringa vuota, provocando la **HasErrors** proprietà da impostare **false**.</span><span class="sxs-lookup"><span data-stu-id="7768a-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="7768a-111">Quando sono state risolte o rifiutate, tutte le righe con errori **AcceptChanges** viene chiamato per accettare tutte le modifiche per l'intera **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="7768a-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7768a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7768a-112">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="7768a-113">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="7768a-113">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="7768a-114">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="7768a-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
