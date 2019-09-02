---
title: Creazione di colonne espressioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 8ae8c8e020a3d8ada5bdcd5037187e6f3abd33a4
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203846"
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
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
