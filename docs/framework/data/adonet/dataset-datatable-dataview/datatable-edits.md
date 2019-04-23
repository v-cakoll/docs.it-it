---
title: Modifiche agli oggetti DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 0300ceab16d9a94bd04468f7acd105e69d13e643
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150943"
---
# <a name="datatable-edits"></a>Modifiche agli oggetti DataTable
Quando si apportano modifiche ai valori di colonna in <xref:System.Data.DataRow>, le modifiche vengono inserite direttamente nello stato attuale della riga. Il <xref:System.Data.DataRowState> viene quindi impostato su **Modified**, e le modifiche vengono accettate o rifiutate tramite i <xref:System.Data.DataRow.AcceptChanges%2A> o <xref:System.Data.DataRow.RejectChanges%2A> metodi del **DataRow**. Il **DataRow** inoltre fornisce tre metodi che è possibile usare per sospendere lo stato della riga durante la modifica. Questi metodi sono <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> e <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 Quando si modifica valori di colonna in una **DataRow** direttamente, il **DataRow** gestisce i valori di colonna utilizzando il **corrente**, **predefinito**, e **Originale** le versioni di riga. Oltre a queste versioni di riga, il **BeginEdit**, **EndEdit**, e **CancelEdit** metodi usano una quarta versione: **Proposta**. Per altre informazioni sulle versioni delle righe, vedere [stati e le versioni delle righe](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 Il **proposto** versione di riga disponibile durante un'operazione di modifica iniziata chiamando **BeginEdit** e terminata tramite **EndEdit** o **CancelEdit,**  o chiamando **AcceptChanges** oppure **RejectChanges**.  
  
 Durante l'operazione di modifica, è possibile applicare la logica di convalida a singole colonne valutando i **ProposedValue** nel **ColumnChanged** eventi del **DataTable**. Il **ColumnChanged** evento contiene **DataColumnChangeEventArgs** che mantiene un riferimento per la colonna in fase di modifica e la **ProposedValue**. Una volta terminata la valutazione del valore proposto, è possibile modificarlo o annullare la modifica. Al termine la modifica, la riga viene spostata fuori il **proposto** dello stato.  
  
 È possibile confermare le modifiche chiamando **EndEdit**, oppure è possibile annullarle chiamando **CancelEdit**. Si noti che, sebbene **EndEdit** confermare le modifiche, il **set di dati** non consente l'accettazione di modifiche finché **AcceptChanges** viene chiamato. Si noti inoltre che se si chiama **AcceptChanges** prima del completamento della modifica tramite **EndEdit** oppure **CancelEdit**, la modifica viene terminata e il **proposto** valori di riga vengono accettati sia il **correnti** e **originale** le versioni di riga. Allo stesso modo, la chiamata **RejectChanges** terminare la modifica ed Elimina le **corrente** e **proposto** le versioni di riga. La chiamata **EndEdit** oppure **CancelEdit** dopo la chiamata **AcceptChanges** oppure **RejectChanges** non ha alcun effetto perché la modifica ha già è terminata.  
  
 Nell'esempio seguente viene illustrato come utilizzare **BeginEdit** con **EndEdit** e **CancelEdit**. L'esempio controlla anche il **ProposedValue** nel **ColumnChanged** evento e decide se annullare la modifica.  
  
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
- [Manipolazione di dati in un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [Gestione di eventi DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
