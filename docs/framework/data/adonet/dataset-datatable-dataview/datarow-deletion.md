---
title: Eliminazione di DataRow
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
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5102e1e2d95bd6adc29d5f2a2317bc15f8386cdc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="datarow-deletion"></a>Eliminazione di DataRow
Sono disponibili due metodi è possibile utilizzare per eliminare un <xref:System.Data.DataRow> dell'oggetto da un <xref:System.Data.DataTable> oggetto: il **rimuovere** metodo il <xref:System.Data.DataRowCollection> oggetto e il <xref:System.Data.DataRow.Delete%2A> metodo il **DataRow**oggetto. Mentre il <xref:System.Data.DataRowCollection.Remove%2A> metodo elimina un **DataRow** dal **DataRowCollection**, <xref:System.Data.DataRow.Delete%2A> metodo contrassegna solo la riga per l'eliminazione. La rimozione effettiva si verifica quando l'applicazione chiama il **AcceptChanges** metodo. L'utilizzo di <xref:System.Data.DataRow.Delete%2A> consente di verificare a livello di programmazione le righe contrassegnate per l'eliminazione prima che vengano eliminate effettivamente. Quando una riga è contrassegnata per l'eliminazione, la relativa proprietà <xref:System.Data.DataRow.RowState%2A> è impostata su <xref:System.Data.DataRow.Delete%2A>.  
  
 <xref:System.Data.DataRow.Delete%2A> e <xref:System.Data.DataRowCollection.Remove%2A> non devono essere chiamato in un ciclo foreach durante l'iterazione tramite un oggetto <xref:System.Data.DataRowCollection>. <xref:System.Data.DataRow.Delete%2A> e <xref:System.Data.DataRowCollection.Remove%2A> non modificano lo stato della raccolta.  
  
 Quando si utilizza un <xref:System.Data.DataSet> o **DataTable** in combinazione con un **DataAdapter** e un'origine dati relazionale, utilizzare il **eliminare** metodo il  **DataRow** per rimuovere la riga. Il **eliminare** metodo contrassegna la riga come **Deleted** nel **DataSet** o **DataTable** , ma non rimuoverla. Invece, quando il **DataAdapter** rileva una riga contrassegnata come **Deleted**, viene eseguito il relativo **DeleteCommand** metodo per eliminare la riga nell'origine dati. La riga può quindi essere rimossi in modo permanente utilizzando il **AcceptChanges** metodo. Se si utilizza **rimuovere** per eliminare la riga, la riga viene rimossa completamente dalla tabella, ma la **DataAdapter** non eliminerà la riga nell'origine dati.  
  
 Il **rimuovere** metodo il **DataRowCollection** accetta un **DataRow** come argomento e la rimuove dalla raccolta, come illustrato nell'esempio seguente.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 Al contrario, nell'esempio seguente viene illustrato come chiamare il **eliminare** metodo su un **DataRow** per modificare il relativo **RowState** per **Deleted** .  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Se una riga è contrassegnata per l'eliminazione e si chiama il **AcceptChanges** metodo il **DataTable** dell'oggetto, la riga viene rimossa dal **DataTable**. Al contrario, se si chiama **RejectChanges**, **RowState** della riga viene ripristinato in vigore prima di essere contrassegnato come **Deleted**.  
  
> [!NOTE]
>  Se il **RowState** di un **DataRow** è **Added**, ovvero è stata appena aggiunta alla tabella e quindi viene contrassegnato come **Deleted**, è rimosso dalla tabella.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [Manipolazione di dati in un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
