---
title: Creazione di colonne AutoIncrement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 5972d9e3d84a236104e85e17d8df1e9ee7f56122
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756033"
---
# <a name="creating-autoincrement-columns"></a>Creazione di colonne AutoIncrement
Per assicurarsi che i valori contenuti in una colonna siano univoci, è possibile impostare l'incremento automatico dei valori di colonna a ogni aggiunta di nuove colonne alla tabella. Per creare un incremento automatico <xref:System.Data.DataColumn>, impostare il <xref:System.Data.DataColumn.AutoIncrement%2A> proprietà della colonna **true**. Il <xref:System.Data.DataColumn> quindi inizia con il valore definito nel <xref:System.Data.DataColumn.AutoIncrementSeed%2A> proprietà e in cui ogni riga aggiunta del valore del **AutoIncrement** aumenta il valore definito nella colonna il <xref:System.Data.DataColumn.AutoIncrementStep%2A> proprietà della colonna.  
  
 Per **AutoIncrement** colonne, è consigliabile che il <xref:System.Data.DataColumn.ReadOnly%2A> proprietà del **DataColumn** impostare **true**.  
  
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
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
