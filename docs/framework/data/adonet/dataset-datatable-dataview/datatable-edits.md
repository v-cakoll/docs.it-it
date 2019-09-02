---
title: Modifiche agli oggetti DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: a970ebda76f5bb6bdea704dabef2ee305436c613
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205009"
---
# <a name="datatable-edits"></a><span data-ttu-id="70d60-102">Modifiche agli oggetti DataTable</span><span class="sxs-lookup"><span data-stu-id="70d60-102">DataTable Edits</span></span>
<span data-ttu-id="70d60-103">Quando si apportano modifiche ai valori di colonna in <xref:System.Data.DataRow>, le modifiche vengono inserite direttamente nello stato attuale della riga.</span><span class="sxs-lookup"><span data-stu-id="70d60-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="70d60-104"><xref:System.Data.DataRow.AcceptChanges%2A> <xref:System.Data.DataRow.RejectChanges%2A>Viene quindi impostato su Modified e le modifiche vengono accettate o rifiutate utilizzando i metodi o del DataRow. <xref:System.Data.DataRowState></span><span class="sxs-lookup"><span data-stu-id="70d60-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="70d60-105">Il **DataRow** fornisce anche tre metodi che è possibile usare per sospendere lo stato della riga durante la modifica.</span><span class="sxs-lookup"><span data-stu-id="70d60-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="70d60-106">Questi metodi sono <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> e <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="70d60-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="70d60-107">Quando si modificano i valori di colonna direttamente in un **DataRow** , **DataRow** gestisce i valori delle colonne utilizzando le versioni di riga **corrente**, **predefinita**e **originale** .</span><span class="sxs-lookup"><span data-stu-id="70d60-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="70d60-108">Oltre a queste versioni di riga, i metodi **BeginEdit**, **EndEdit**e **CancelEdit** utilizzano una quarta versione di riga: **Proposto**.</span><span class="sxs-lookup"><span data-stu-id="70d60-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="70d60-109">Per ulteriori informazioni sulle versioni di riga, vedere [Stati di riga e versioni di riga](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="70d60-109">For more information about row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="70d60-110">La versione di riga **proposta** esiste durante un'operazione di modifica che inizia chiamando **BeginEdit** e termina usando **EndEdit** o **CancelEdit** o chiamando **AcceptChanges** o **RejectChanges**.</span><span class="sxs-lookup"><span data-stu-id="70d60-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="70d60-111">Durante l'operazione di modifica, è possibile applicare la logica di convalida a singole colonne valutando **ProposedValue** nell'evento **ColumnChanged** di **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="70d60-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="70d60-112">L'evento **ColumnChanged** include **DataColumnChangeEventArgs** che mantengono un riferimento alla colonna che sta cambiando e a **ProposedValue**.</span><span class="sxs-lookup"><span data-stu-id="70d60-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="70d60-113">Una volta terminata la valutazione del valore proposto, è possibile modificarlo o annullare la modifica.</span><span class="sxs-lookup"><span data-stu-id="70d60-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="70d60-114">Al termine della modifica, la riga viene spostata all'esterno dello stato **proposto** .</span><span class="sxs-lookup"><span data-stu-id="70d60-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="70d60-115">È possibile confermare le modifiche chiamando **EndEdit**oppure è possibile annullarle chiamando **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="70d60-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="70d60-116">Si noti che mentre **EndEdit** conferma le modifiche, il **set di dati** non accetta effettivamente le modifiche fino a quando non viene chiamato il metodo **AcceptChanges** .</span><span class="sxs-lookup"><span data-stu-id="70d60-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="70d60-117">Si noti inoltre che se si chiama **AcceptChanges** prima di aver terminato la modifica con **EndEdit** o **CancelEdit**, la modifica viene terminata e i valori delle righe **proposte** vengono accettati sia per le versioni di riga **correnti** che **originali** .</span><span class="sxs-lookup"><span data-stu-id="70d60-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="70d60-118">Allo stesso modo, la chiamata a **RejectChanges** termina la modifica e rimuove le versioni di riga **corrente** e **proposta** .</span><span class="sxs-lookup"><span data-stu-id="70d60-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="70d60-119">La chiamata di **EndEdit** o **CancelEdit** dopo la chiamata di **AcceptChanges** o **RejectChanges** non ha effetto perché la modifica è già terminata.</span><span class="sxs-lookup"><span data-stu-id="70d60-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="70d60-120">Nell'esempio seguente viene illustrato come utilizzare **BeginEdit** con **EndEdit** e **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="70d60-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="70d60-121">Nell'esempio viene inoltre controllato **ProposedValue** nell'evento **ColumnChanged** e viene deciso se annullare la modifica.</span><span class="sxs-lookup"><span data-stu-id="70d60-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="70d60-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70d60-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="70d60-123">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="70d60-123">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="70d60-124">Gestione di eventi DataTable</span><span class="sxs-lookup"><span data-stu-id="70d60-124">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="70d60-125">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="70d60-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
