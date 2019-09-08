---
title: Modifiche agli oggetti DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 689a297eb5368d35c2e7dd034426edbe665e7ed2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785381"
---
# <a name="datatable-edits"></a>Modifiche agli oggetti DataTable
Quando si apportano modifiche ai valori di colonna in <xref:System.Data.DataRow>, le modifiche vengono inserite direttamente nello stato attuale della riga. <xref:System.Data.DataRow.AcceptChanges%2A> <xref:System.Data.DataRow.RejectChanges%2A>Viene quindi impostato su Modified e le modifiche vengono accettate o rifiutate utilizzando i metodi o del DataRow. <xref:System.Data.DataRowState> Il **DataRow** fornisce anche tre metodi che è possibile usare per sospendere lo stato della riga durante la modifica. Questi metodi sono <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> e <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 Quando si modificano i valori di colonna direttamente in un **DataRow** , **DataRow** gestisce i valori delle colonne utilizzando le versioni di riga **corrente**, **predefinita**e **originale** . Oltre a queste versioni di riga, i metodi **BeginEdit**, **EndEdit**e **CancelEdit** utilizzano una quarta versione di riga: **Proposto**. Per ulteriori informazioni sulle versioni di riga, vedere [Stati di riga e versioni di riga](row-states-and-row-versions.md).  
  
 La versione di riga **proposta** esiste durante un'operazione di modifica che inizia chiamando **BeginEdit** e termina usando **EndEdit** o **CancelEdit** o chiamando **AcceptChanges** o **RejectChanges**.  
  
 Durante l'operazione di modifica, è possibile applicare la logica di convalida a singole colonne valutando **ProposedValue** nell'evento **ColumnChanged** di **DataTable**. L'evento **ColumnChanged** include **DataColumnChangeEventArgs** che mantengono un riferimento alla colonna che sta cambiando e a **ProposedValue**. Una volta terminata la valutazione del valore proposto, è possibile modificarlo o annullare la modifica. Al termine della modifica, la riga viene spostata all'esterno dello stato **proposto** .  
  
 È possibile confermare le modifiche chiamando **EndEdit**oppure è possibile annullarle chiamando **CancelEdit**. Si noti che mentre **EndEdit** conferma le modifiche, il **set di dati** non accetta effettivamente le modifiche fino a quando non viene chiamato il metodo **AcceptChanges** . Si noti inoltre che se si chiama **AcceptChanges** prima di aver terminato la modifica con **EndEdit** o **CancelEdit**, la modifica viene terminata e i valori delle righe **proposte** vengono accettati sia per le versioni di riga **correnti** che **originali** . Allo stesso modo, la chiamata a **RejectChanges** termina la modifica e rimuove le versioni di riga **corrente** e **proposta** . La chiamata di **EndEdit** o **CancelEdit** dopo la chiamata di **AcceptChanges** o **RejectChanges** non ha effetto perché la modifica è già terminata.  
  
 Nell'esempio seguente viene illustrato come utilizzare **BeginEdit** con **EndEdit** e **CancelEdit**. Nell'esempio viene inoltre controllato **ProposedValue** nell'evento **ColumnChanged** e viene deciso se annullare la modifica.  
  
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
