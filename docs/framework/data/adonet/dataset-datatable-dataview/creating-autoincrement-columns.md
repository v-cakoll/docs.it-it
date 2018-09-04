---
title: Creazione di colonne AutoIncrement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 9c6b5393e1928828bca001ba1d2336f09e64c22c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43536615"
---
# <a name="creating-autoincrement-columns"></a>Creazione di colonne AutoIncrement
Per assicurarsi che i valori contenuti in una colonna siano univoci, è possibile impostare l'incremento automatico dei valori di colonna a ogni aggiunta di nuove colonne alla tabella. Per creare un incremento automatico <xref:System.Data.DataColumn>, impostare il <xref:System.Data.DataColumn.AutoIncrement%2A> proprietà della colonna **true**. Il <xref:System.Data.DataColumn> quindi inizia con il valore definito nel <xref:System.Data.DataColumn.AutoIncrementSeed%2A> proprietà e con ogni riga aggiunta del valore del **AutoIncrement** aumenta il valore definito nella colonna di <xref:System.Data.DataColumn.AutoIncrementStep%2A> proprietà della colonna.  
  
 Per **AutoIncrement** colonne, è consigliabile che le <xref:System.Data.DataColumn.ReadOnly%2A> proprietà del **DataColumn** essere impostato su **true**.  
  
 Nell'esempio seguente viene illustrato come creare una colonna con valore iniziale pari a 200 e con incrementi in 3 passaggi.  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.DataColumn>  
 [Definizione dello schema DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
