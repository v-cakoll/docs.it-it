---
title: Modifiche agli oggetti DataTable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d33bd8900c48222142a46ed2c5bd64412d2eaab5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="datatable-edits"></a>Modifiche agli oggetti DataTable
Quando si apportano modifiche ai valori di colonna in <xref:System.Data.DataRow>, le modifiche vengono inserite direttamente nello stato attuale della riga. Il <xref:System.Data.DataRowState> viene quindi impostato su **Modified**, e le modifiche vengono accettate o rifiutate tramite il <xref:System.Data.DataRow.AcceptChanges%2A> o <xref:System.Data.DataRow.RejectChanges%2A> metodi del **DataRow**. Il **DataRow** inoltre fornisce tre metodi che è possibile utilizzare per sospendere lo stato della riga durante la modifica. Questi metodi sono <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> e <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 Quando si modificano i valori di colonna in un **DataRow** direttamente, il **DataRow** gestisce i valori di colonna utilizzando il **corrente**, **predefinito**, e **Originale** versioni di riga. Oltre a queste versioni di riga, il **BeginEdit**, **EndEdit**, e **CancelEdit** metodi utilizzano una quarta versione: **proposto**. Per ulteriori informazioni sulle versioni delle righe, vedere [stati delle righe e le versioni di riga](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 Il **proposto** presente versione di riga durante un'operazione di modifica iniziata chiamando **BeginEdit** e che termina con **EndEdit** o **CancelEdit,**  o chiamando **AcceptChanges** o **RejectChanges**.  
  
 Durante l'operazione di modifica, è possibile applicare la logica di convalida a singole colonne valutando il **ProposedValue** nel **ColumnChanged** evento del **DataTable**. Il **ColumnChanged** evento contiene **DataColumnChangeEventArgs** che mantenere un riferimento per la colonna in fase di modifica e la **ProposedValue**. Una volta terminata la valutazione del valore proposto, è possibile modificarlo o annullare la modifica. Al termine della modifica, la riga perde il **proposto** stato.  
  
 È possibile confermare le modifiche chiamando **EndEdit**, o annullarle chiamando **CancelEdit**. Si noti che, sebbene **EndEdit** confermare le modifiche, il **set di dati** effettivamente non accettare le modifiche fino a **AcceptChanges** viene chiamato. Si noti inoltre che se si chiama **AcceptChanges** prima del completamento della modifica tramite **EndEdit** o **CancelEdit**, la modifica viene terminata e il **proposto** vengono accettati i valori di riga per entrambi i **corrente** e **originale** versioni di riga. Allo stesso modo, la chiamata **RejectChanges** termina la modifica ed elimina il **corrente** e **proposto** versioni di riga. La chiamata **EndEdit** o **CancelEdit** dopo la chiamata **AcceptChanges** o **RejectChanges** non ha alcun effetto perché la modifica ha già è terminata.  
  
 Nell'esempio seguente viene illustrato come utilizzare **BeginEdit** con **EndEdit** e **CancelEdit**. Nell'esempio viene inoltre verificato di **ProposedValue** nel **ColumnChanged** evento e decide di annullare la modifica.  
  
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
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataRowVersion>  
 [La modifica dei dati in un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Gestione degli eventi di DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
