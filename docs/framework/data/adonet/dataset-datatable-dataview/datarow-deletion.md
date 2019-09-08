---
title: Eliminazione di DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 3f48339539f08bbc1c2c15035741375bd9ade553
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784718"
---
# <a name="datarow-deletion"></a>Eliminazione di DataRow
Esistono due metodi che è possibile utilizzare per eliminare un <xref:System.Data.DataRow> oggetto da un <xref:System.Data.DataTable> oggetto: <xref:System.Data.DataRowCollection> il metodo **Remove** dell'oggetto e il <xref:System.Data.DataRow.Delete%2A> metodo dell'oggetto **DataRow** . Mentre il <xref:System.Data.DataRowCollection.Remove%2A> metodo elimina un **DataRow** da **DataRowCollection**, il <xref:System.Data.DataRow.Delete%2A> metodo contrassegna solo la riga per l'eliminazione. La rimozione effettiva si verifica quando l'applicazione chiama il metodo **AcceptChanges** . L'utilizzo di <xref:System.Data.DataRow.Delete%2A> consente di verificare a livello di programmazione le righe contrassegnate per l'eliminazione prima che vengano eliminate effettivamente. Quando una riga è contrassegnata per l'eliminazione, la relativa proprietà <xref:System.Data.DataRow.RowState%2A> è impostata su <xref:System.Data.DataRow.Delete%2A>.  
  
 <xref:System.Data.DataRow.Delete%2A> e <xref:System.Data.DataRowCollection.Remove%2A> non devono essere chiamato in un ciclo foreach durante l'iterazione tramite un oggetto <xref:System.Data.DataRowCollection>. <xref:System.Data.DataRow.Delete%2A> e <xref:System.Data.DataRowCollection.Remove%2A> non modificano lo stato della raccolta.  
  
 Quando si usa <xref:System.Data.DataSet> un **oggetto o DataTable** insieme a **un DataAdapter** e a un'origine dati relazionale, usare il metodo **Delete** del **DataRow** per rimuovere la riga. Il metodo **Delete** contrassegna la riga come **eliminata** nel **DataSet** o **DataTable** , ma non la rimuove. Al contrario, quando **DataAdapter** rileva una riga contrassegnata come **eliminata**, viene eseguito il metodo **DeleteCommand** per eliminare la riga nell'origine dati. La riga può quindi essere rimossa definitivamente usando il metodo **AcceptChanges** . Se si utilizza **Rimuovi** per eliminare la riga, la riga viene rimossa interamente dalla tabella, ma l'oggetto **DataAdapter** non eliminerà la riga nell'origine dati.  
  
 Il metodo **Remove** di **DataRowCollection** accetta un **DataRow** come argomento e lo rimuove dalla raccolta, come illustrato nell'esempio seguente.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 Al contrario, nell'esempio seguente viene illustrato come chiamare il metodo **Delete** su un **DataRow** per modificare il valore di **RowState** in **Deleted**.  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Se una riga è contrassegnata per l'eliminazione e si chiama il metodo **AcceptChanges** dell'oggetto **DataTable** , la riga viene rimossa dalla **DataTable**. Al contrario, se si chiama **RejectChanges**, il **RowState** della riga ritorna a quello che era prima che venisse contrassegnato come **eliminato**.  
  
> [!NOTE]
> Se viene **aggiunto il valore** **RowState** di un **DataRow** , ovvero è stato appena aggiunto alla tabella e viene quindi contrassegnato come **eliminato**, viene rimosso dalla tabella.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Manipolazione di dati in un oggetto DataTable](manipulating-data-in-a-datatable.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
