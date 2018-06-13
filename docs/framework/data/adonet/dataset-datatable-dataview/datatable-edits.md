---
title: Modifiche agli oggetti DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: b806e642a5cce6a55ff0dcecc9b018f3ee78bad8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758620"
---
# <a name="datatable-edits"></a><span data-ttu-id="cc624-102">Modifiche agli oggetti DataTable</span><span class="sxs-lookup"><span data-stu-id="cc624-102">DataTable Edits</span></span>
<span data-ttu-id="cc624-103">Quando si apportano modifiche ai valori di colonna in <xref:System.Data.DataRow>, le modifiche vengono inserite direttamente nello stato attuale della riga.</span><span class="sxs-lookup"><span data-stu-id="cc624-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="cc624-104">Il <xref:System.Data.DataRowState> viene quindi impostato su **Modified**, e le modifiche vengono accettate o rifiutate tramite il <xref:System.Data.DataRow.AcceptChanges%2A> o <xref:System.Data.DataRow.RejectChanges%2A> metodi del **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="cc624-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="cc624-105">Il **DataRow** inoltre fornisce tre metodi che è possibile utilizzare per sospendere lo stato della riga durante la modifica.</span><span class="sxs-lookup"><span data-stu-id="cc624-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="cc624-106">Questi metodi sono <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> e <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc624-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="cc624-107">Quando si modificano i valori di colonna in un **DataRow** direttamente, il **DataRow** gestisce i valori di colonna utilizzando il **corrente**, **predefinito**, e **Originale** versioni di riga.</span><span class="sxs-lookup"><span data-stu-id="cc624-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="cc624-108">Oltre a queste versioni di riga, il **BeginEdit**, **EndEdit**, e **CancelEdit** metodi utilizzano una quarta versione: **proposto**.</span><span class="sxs-lookup"><span data-stu-id="cc624-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="cc624-109">Per ulteriori informazioni sulle versioni delle righe, vedere [stati delle righe e le versioni di riga](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="cc624-109">For more information about row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="cc624-110">Il **proposto** presente versione di riga durante un'operazione di modifica iniziata chiamando **BeginEdit** e che termina con **EndEdit** o **CancelEdit,**  o chiamando **AcceptChanges** o **RejectChanges**.</span><span class="sxs-lookup"><span data-stu-id="cc624-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="cc624-111">Durante l'operazione di modifica, è possibile applicare la logica di convalida a singole colonne valutando il **ProposedValue** nel **ColumnChanged** evento del **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="cc624-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="cc624-112">Il **ColumnChanged** evento contiene **DataColumnChangeEventArgs** che mantenere un riferimento per la colonna in fase di modifica e la **ProposedValue**.</span><span class="sxs-lookup"><span data-stu-id="cc624-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="cc624-113">Una volta terminata la valutazione del valore proposto, è possibile modificarlo o annullare la modifica.</span><span class="sxs-lookup"><span data-stu-id="cc624-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="cc624-114">Al termine della modifica, la riga perde il **proposto** stato.</span><span class="sxs-lookup"><span data-stu-id="cc624-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="cc624-115">È possibile confermare le modifiche chiamando **EndEdit**, o annullarle chiamando **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="cc624-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="cc624-116">Si noti che, sebbene **EndEdit** confermare le modifiche, il **set di dati** effettivamente non accettare le modifiche fino a **AcceptChanges** viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="cc624-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="cc624-117">Si noti inoltre che se si chiama **AcceptChanges** prima del completamento della modifica tramite **EndEdit** o **CancelEdit**, la modifica viene terminata e il **proposto** vengono accettati i valori di riga per entrambi i **corrente** e **originale** versioni di riga.</span><span class="sxs-lookup"><span data-stu-id="cc624-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="cc624-118">Allo stesso modo, la chiamata **RejectChanges** termina la modifica ed elimina il **corrente** e **proposto** versioni di riga.</span><span class="sxs-lookup"><span data-stu-id="cc624-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="cc624-119">La chiamata **EndEdit** o **CancelEdit** dopo la chiamata **AcceptChanges** o **RejectChanges** non ha alcun effetto perché la modifica ha già è terminata.</span><span class="sxs-lookup"><span data-stu-id="cc624-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="cc624-120">Nell'esempio seguente viene illustrato come utilizzare **BeginEdit** con **EndEdit** e **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="cc624-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="cc624-121">Nell'esempio viene inoltre verificato di **ProposedValue** nel **ColumnChanged** evento e decide di annullare la modifica.</span><span class="sxs-lookup"><span data-stu-id="cc624-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable  
workTable.Columns.Add("LastName", Type.GetType("System.String"))  
  
AddHandler workTable.ColumnChanged, _  
  New DataColumnChangeEventHandler(AddressOf OnColumnChanged)  
  
Dim workRow As DataRow = workTable.NewRow()  
workRow(0) = "Smith"  
workTable.Rows.Add(workRow)  
  
workRow.BeginEdit()  
' Causes the ColumnChanged event to write a message and cancel the edit.  
workRow(0) = ""       
workRow.EndEdit()  
  
' Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow(0), workRow.RowState)  
  
Private Shared Sub OnColumnChanged( _  
  sender As Object, args As DataColumnChangeEventArgs)  
  If args.Column.ColumnName = "LastName" Then  
    If args.ProposedValue.ToString() = "" Then  
      Console.WriteLine("Last Name cannot be blank.  Edit canceled.")  
      args.Row.CancelEdit()  
    End If  
  End If  
End Sub  
```  
  
```csharp  
DataTable workTable  = new DataTable();  
workTable.Columns.Add("LastName", typeof(String));  
  
workTable.ColumnChanged +=   
  new DataColumnChangeEventHandler(OnColumnChanged);  
  
DataRow workRow = workTable.NewRow();  
workRow[0] = "Smith";  
workTable.Rows.Add(workRow);  
  
workRow.BeginEdit();  
// Causes the ColumnChanged event to write a message and cancel the edit.  
workRow[0] = "";       
workRow.EndEdit();  
  
// Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow[0], workRow.RowState);    
  
protected static void OnColumnChanged(  
  Object sender, DataColumnChangeEventArgs args)  
{  
  if (args.Column.ColumnName == "LastName")  
    if (args.ProposedValue.ToString() == "")  
    {  
      Console.WriteLine("Last Name cannot be blank. Edit canceled.");  
      args.Row.CancelEdit();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc624-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc624-122">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataRowVersion>  
 [<span data-ttu-id="cc624-123">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="cc624-123">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="cc624-124">Gestione di eventi DataTable</span><span class="sxs-lookup"><span data-stu-id="cc624-124">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [<span data-ttu-id="cc624-125">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="cc624-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
