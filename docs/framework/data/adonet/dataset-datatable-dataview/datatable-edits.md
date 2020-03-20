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
# <a name="datatable-edits"></a>Modifiche agli oggetti DataTable
Quando si apportano modifiche ai valori di colonna in <xref:System.Data.DataRow>, le modifiche vengono inserite direttamente nello stato attuale della riga. Viene <xref:System.Data.DataRowState> quindi impostata su **Modificato**e le modifiche <xref:System.Data.DataRow.AcceptChanges%2A> vengono <xref:System.Data.DataRow.RejectChanges%2A> accettate o rifiutate utilizzando i metodi o di **DataRow**. Il **DataRow** fornisce inoltre tre metodi che è possibile utilizzare per sospendere lo stato della riga durante la modifica. Questi metodi sono <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> e <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 Quando si modificano direttamente i valori delle colonne in un **DataRow,** il **DataRow** gestisce i valori di colonna utilizzando le versioni di riga **Current**, **Default**e **Original** . Oltre a queste versioni di riga, i metodi **BeginEdit**, **EndEdit**e **CancelEdit** utilizzano una versione della quarta riga: **Proposed**. Per ulteriori informazioni sulle versioni delle righe, vedere [Stati riga e Versioni riga](row-states-and-row-versions.md).  
  
 La versione **della** riga Proposta esiste durante un'operazione di modifica che inizia chiamando **BeginEdit** e che termina utilizzando **EndEdit** o **CancelEdit** oppure chiamando **AcceptChanges** o **RejectChanges**.  
  
 Durante l'operazione di modifica, è possibile applicare la logica di convalida a singole colonne valutando **ProposedValue** nell'evento **ColumnChanged** dell'oggetto **DataTable**. **L'evento ColumnChanged** contiene **DataColumnChangeEventArgs** che mantengono un riferimento alla colonna che viene modificata e al **ProposedValue**. Una volta terminata la valutazione del valore proposto, è possibile modificarlo o annullare la modifica. Al termine della modifica, la riga esce dallo stato **Proposto.**  
  
 È possibile confermare le modifiche chiamando **EndEdit**oppure annullarle chiamando **CancelEdit**. Si noti che mentre **EndEdit** conferma le modifiche, il **DataSet** non accetta effettivamente le modifiche fino a quando **AcceptChanges** viene chiamato. Si noti inoltre che se si chiama **AcceptChanges** prima di aver terminato la modifica con **EndEdit** o **CancelEdit**, la modifica viene terminata e i valori di riga **Proposed** vengono accettati per entrambe le versioni di riga **Current** e **Original** . Allo stesso modo, la chiamata **RejectChanges** termina la modifica ed elimina le versioni di riga **Corrente** e **Proposta.** La chiamata a **EndEdit** o **CancelEdit** dopo aver chiamato **AcceptChanges** o **RejectChanges** non ha alcun effetto perché la modifica è già terminata.  
  
 Nell'esempio riportato di seguito viene illustrato come utilizzare **BeginEdit** con **EndEdit** e **CancelEdit**. Nell'esempio viene inoltre controllato il **ProposedValue** nel **ColumnChanged** evento e decide se annullare la modifica.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [Manipolazione di dati in un oggetto DataTable](manipulating-data-in-a-datatable.md)
- [Gestione di eventi DataTable](handling-datatable-events.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
