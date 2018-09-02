---
title: Eliminazione di DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: e7e687dfa6af47161be9d26054eb58f319a5099d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425596"
---
# <a name="datarow-deletion"></a>Eliminazione di DataRow
Sono disponibili due metodi è possibile usare per eliminare un <xref:System.Data.DataRow> dell'oggetto da un <xref:System.Data.DataTable> oggetto: il **rimuovere** metodo del <xref:System.Data.DataRowCollection> oggetto e il <xref:System.Data.DataRow.Delete%2A> metodo del **DataRow**oggetto. Mentre il <xref:System.Data.DataRowCollection.Remove%2A> eliminazioni metodo una **DataRow** dal **DataRowCollection**, il <xref:System.Data.DataRow.Delete%2A> metodo contrassegna solo la riga per l'eliminazione. La rimozione effettiva si verifica quando l'applicazione chiama il **AcceptChanges** (metodo). L'utilizzo di <xref:System.Data.DataRow.Delete%2A> consente di verificare a livello di programmazione le righe contrassegnate per l'eliminazione prima che vengano eliminate effettivamente. Quando una riga è contrassegnata per l'eliminazione, la relativa proprietà <xref:System.Data.DataRow.RowState%2A> è impostata su <xref:System.Data.DataRow.Delete%2A>.  
  
 <xref:System.Data.DataRow.Delete%2A> e <xref:System.Data.DataRowCollection.Remove%2A> non devono essere chiamato in un ciclo foreach durante l'iterazione tramite un oggetto <xref:System.Data.DataRowCollection>. <xref:System.Data.DataRow.Delete%2A> e <xref:System.Data.DataRowCollection.Remove%2A> non modificano lo stato della raccolta.  
  
 Quando si usa una <xref:System.Data.DataSet> o **DataTable** in combinazione con un **DataAdapter** e un'origine dati relazionale, usare il **eliminare** metodo il  **DataRow** per rimuovere la riga. Il **eliminare** metodo contrassegna la riga come **Deleted** nel **set di dati** oppure **DataTable** ma non lo rimuove. Invece, quando la **DataAdapter** rileva una riga contrassegnata come **Deleted**, esegue relativo **DeleteCommand** metodo per eliminare la riga nell'origine dati. La riga può quindi essere rimosso definitivamente usando il **AcceptChanges** (metodo). Se si usa **rimuovere** per eliminare la riga, la riga viene rimossa completamente dalla tabella, ma la **DataAdapter** non eliminerà la riga nell'origine dati.  
  
 Il **rimuovere** metodo per il **DataRowCollection** accetta una **DataRow** come argomento e lo rimuove dalla raccolta, come illustrato nell'esempio seguente.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 Al contrario, l'esempio seguente viene illustrato come chiamare il **eliminare** metodo su un **DataRow** modificare relativo **RowState** a **Deleted** .  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Se una riga è contrassegnata per l'eliminazione e si chiama il **AcceptChanges** metodo per il **DataTable** dell'oggetto, la riga viene rimossa dal **DataTable**. Al contrario, se si chiama **RejectChanges**, il **RowState** Ripristina la riga si trovava prima di essere contrassegnato come **Deleted**.  
  
> [!NOTE]
>  Se il **RowState** di un **DataRow** viene **Added**, vale a dire è stato aggiunto solo alla tabella e viene quindi contrassegnato come **Deleted**, è rimosso dalla tabella.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [Manipolazione di dati in un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
