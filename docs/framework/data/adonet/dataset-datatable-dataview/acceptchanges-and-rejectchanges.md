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
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="9ef5e-102">AcceptChanges e RejectChanges</span><span class="sxs-lookup"><span data-stu-id="9ef5e-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="9ef5e-103">Dopo la verifica dell'accuratezza delle modifiche apportate ai <xref:System.Data.DataTable>dati in un oggetto, è possibile accettare <xref:System.Data.DataRow.AcceptChanges%2A> le modifiche utilizzando <xref:System.Data.DataRow>il metodo dell' <xref:System.Data.DataSet>oggetto, <xref:System.Data.DataTable>o, che imposta i valori di **riga correnti come** I valori originali e impostano la proprietà **RowState** su **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="9ef5e-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="9ef5e-104">L'accettazione o il rifiuto delle modifiche Cancella tutte le informazioni **RowError** e imposta la proprietà **HasErrors** su **false**.</span><span class="sxs-lookup"><span data-stu-id="9ef5e-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="9ef5e-105">È inoltre possibile che l'accettazione o il rifiuto delle modifiche influisca sui dati di aggiornamento nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9ef5e-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="9ef5e-106">Per ulteriori informazioni, vedere [aggiornamento di origini dati con DataAdapter](../updating-data-sources-with-dataadapters.md).</span><span class="sxs-lookup"><span data-stu-id="9ef5e-106">For more information, see [Updating Data Sources with DataAdapters](../updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="9ef5e-107">Se nella **DataTable**sono presenti vincoli di chiave esterna, le modifiche accettate o rifiutate mediante **AcceptChanges** e **RejectChanges** vengono propagate alle righe figlio del **DataRow** in base **al ForeignKeyConstraint. AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="9ef5e-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="9ef5e-108">Per altre informazioni, vedere [vincoli DataTable](datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="9ef5e-108">For more information, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="9ef5e-109">L'esempio seguente controlla se sono presenti righe con errori, risolve errori laddove è possibile e rifiuta le righe contenenti errori non risolvibili.</span><span class="sxs-lookup"><span data-stu-id="9ef5e-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="9ef5e-110">Si noti che, per gli errori risolti, il valore di **RowError** viene reimpostato su una stringa vuota, causando l'impostazione della proprietà **HasErrors** su **false**.</span><span class="sxs-lookup"><span data-stu-id="9ef5e-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="9ef5e-111">Quando tutte le righe con errori sono state risolte o rifiutate, **AcceptChanges** viene chiamato per accettare tutte le modifiche per l'intero **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="9ef5e-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9ef5e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ef5e-112">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="9ef5e-113">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="9ef5e-113">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="9ef5e-114">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9ef5e-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
