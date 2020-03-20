---
title: Modifiche agli oggetti DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 9e8c4204b51121b147fc7614066d9b849a687574
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151260"
---
# <a name="datatable-edits"></a><span data-ttu-id="b382b-102">Modifiche agli oggetti DataTable</span><span class="sxs-lookup"><span data-stu-id="b382b-102">DataTable Edits</span></span>
<span data-ttu-id="b382b-103">Quando si apportano modifiche ai valori di colonna in <xref:System.Data.DataRow>, le modifiche vengono inserite direttamente nello stato attuale della riga.</span><span class="sxs-lookup"><span data-stu-id="b382b-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="b382b-104">Viene <xref:System.Data.DataRowState> quindi impostata su **Modificato**e le modifiche <xref:System.Data.DataRow.AcceptChanges%2A> vengono <xref:System.Data.DataRow.RejectChanges%2A> accettate o rifiutate utilizzando i metodi o di **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="b382b-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="b382b-105">Il **DataRow** fornisce inoltre tre metodi che è possibile utilizzare per sospendere lo stato della riga durante la modifica.</span><span class="sxs-lookup"><span data-stu-id="b382b-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="b382b-106">Questi metodi sono <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> e <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="b382b-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="b382b-107">Quando si modificano direttamente i valori delle colonne in un **DataRow,** il **DataRow** gestisce i valori di colonna utilizzando le versioni di riga **Current**, **Default**e **Original** .</span><span class="sxs-lookup"><span data-stu-id="b382b-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="b382b-108">Oltre a queste versioni di riga, i metodi **BeginEdit**, **EndEdit**e **CancelEdit** utilizzano una versione della quarta riga: **Proposed**.</span><span class="sxs-lookup"><span data-stu-id="b382b-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="b382b-109">Per ulteriori informazioni sulle versioni delle righe, vedere [Stati riga e Versioni riga](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="b382b-109">For more information about row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="b382b-110">La versione **della** riga Proposta esiste durante un'operazione di modifica che inizia chiamando **BeginEdit** e che termina utilizzando **EndEdit** o **CancelEdit** oppure chiamando **AcceptChanges** o **RejectChanges**.</span><span class="sxs-lookup"><span data-stu-id="b382b-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="b382b-111">Durante l'operazione di modifica, è possibile applicare la logica di convalida a singole colonne valutando **ProposedValue** nell'evento **ColumnChanged** dell'oggetto **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="b382b-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="b382b-112">**L'evento ColumnChanged** contiene **DataColumnChangeEventArgs** che mantengono un riferimento alla colonna che viene modificata e al **ProposedValue**.</span><span class="sxs-lookup"><span data-stu-id="b382b-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="b382b-113">Una volta terminata la valutazione del valore proposto, è possibile modificarlo o annullare la modifica.</span><span class="sxs-lookup"><span data-stu-id="b382b-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="b382b-114">Al termine della modifica, la riga esce dallo stato **Proposto.**</span><span class="sxs-lookup"><span data-stu-id="b382b-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="b382b-115">È possibile confermare le modifiche chiamando **EndEdit**oppure annullarle chiamando **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="b382b-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="b382b-116">Si noti che mentre **EndEdit** conferma le modifiche, il **DataSet** non accetta effettivamente le modifiche fino a quando **AcceptChanges** viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="b382b-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="b382b-117">Si noti inoltre che se si chiama **AcceptChanges** prima di aver terminato la modifica con **EndEdit** o **CancelEdit**, la modifica viene terminata e i valori di riga **Proposed** vengono accettati per entrambe le versioni di riga **Current** e **Original** .</span><span class="sxs-lookup"><span data-stu-id="b382b-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="b382b-118">Allo stesso modo, la chiamata **RejectChanges** termina la modifica ed elimina le versioni di riga **Corrente** e **Proposta.**</span><span class="sxs-lookup"><span data-stu-id="b382b-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="b382b-119">La chiamata a **EndEdit** o **CancelEdit** dopo aver chiamato **AcceptChanges** o **RejectChanges** non ha alcun effetto perché la modifica è già terminata.</span><span class="sxs-lookup"><span data-stu-id="b382b-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="b382b-120">Nell'esempio riportato di seguito viene illustrato come utilizzare **BeginEdit** con **EndEdit** e **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="b382b-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="b382b-121">Nell'esempio viene inoltre controllato il **ProposedValue** nel **ColumnChanged** evento e decide se annullare la modifica.</span><span class="sxs-lookup"><span data-stu-id="b382b-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b382b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b382b-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="b382b-123">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="b382b-123">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="b382b-124">Gestione di eventi DataTable</span><span class="sxs-lookup"><span data-stu-id="b382b-124">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="b382b-125">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b382b-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
