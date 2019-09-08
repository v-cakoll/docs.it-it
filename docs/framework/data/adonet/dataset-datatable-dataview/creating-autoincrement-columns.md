---
title: Creazione di colonne AutoIncrement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 5e4a36829107480a44980c7210b39c21231c67f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786450"
---
# <a name="creating-autoincrement-columns"></a>Creazione di colonne AutoIncrement
Per assicurarsi che i valori contenuti in una colonna siano univoci, è possibile impostare l'incremento automatico dei valori di colonna a ogni aggiunta di nuove colonne alla tabella. Per creare un incremento <xref:System.Data.DataColumn>automatico, impostare la <xref:System.Data.DataColumn.AutoIncrement%2A> proprietà della colonna su **true**. Inizia quindi con il valore definito <xref:System.Data.DataColumn.AutoIncrementSeed%2A> nella proprietà e, a ogni riga aggiunta, il valore della colonna **AutoIncrement** <xref:System.Data.DataColumn.AutoIncrementStep%2A> aumenta in base al valore definito nella proprietà della colonna. <xref:System.Data.DataColumn>  
  
 Per le colonne di **incremento automatico** è consigliabile impostare <xref:System.Data.DataColumn.ReadOnly%2A> la proprietà dell'oggetto **DataColumn** su **true**.  
  
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

- <xref:System.Data.DataColumn>
- [Definizione dello schema DataTable](datatable-schema-definition.md)
- [DataTable](datatables.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
