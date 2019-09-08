---
title: Creazione di colonne espressioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 1c4e0b368a8eb154207382ae70b9767f5a5fe64d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785444"
---
# <a name="creating-expression-columns"></a>Creazione di colonne espressioni
È possibile definire un'espressione per una colonna per consentire che questa contenga un valore calcolato sulla base di altri valori di colonna nella stessa riga o sulla base di valori di colonna di più righe della tabella. Per definire l'espressione da valutare, usare la proprietà <xref:System.Data.DataColumn.Expression%2A> della colonna di destinazione e la proprietà <xref:System.Data.DataColumn.ColumnName%2A> per fare riferimento ad altre colonne nell'espressione. La proprietà <xref:System.Data.DataColumn.DataType%2A> specificata per la colonna di espressioni deve essere adeguata per il valore restituito dall'espressione.  
  
 La tabella seguente indica diversi usi possibili delle colonne di espressioni in una tabella.  
  
|Tipo di espressione|Esempio|  
|---------------------|-------------|  
|Confronto|"Total > = 500"|  
|Calcolo|"UnitPrice * Quantity"|  
|Aggregazione|Sum(Price)|  
  
 È possibile impostare la proprietà **Expression** per un oggetto **DataColumn** esistente oppure è possibile includere la proprietà come terzo argomento <xref:System.Data.DataColumn> passato al costruttore, come illustrato nell'esempio seguente.  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 Le espressioni possono fare riferimento ad altre colonne di espressioni. Viene tuttavia generata un'eccezione se è presente un riferimento circolare, ovvero quando due espressioni fanno riferimento l'una all'altra. Per le regole sulla scrittura di espressioni, <xref:System.Data.DataColumn.Expression%2A> vedere la proprietà della classe **DataColumn** .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Definizione dello schema DataTable](datatable-schema-definition.md)
- [DataTable](datatables.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
