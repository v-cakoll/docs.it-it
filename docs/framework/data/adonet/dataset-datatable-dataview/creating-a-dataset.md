---
title: Creazione di un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: d496167b7bce31491402414c43ae0bcdee423b89
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786498"
---
# <a name="creating-a-dataset"></a>Creazione di un dataset
È possibile creare un'istanza di un tipo<xref:System.Data.DataSet> chiamando il costruttore <xref:System.Data.DataSet>. Facoltativamente, specificare un nome di argomento. Se non si specifica alcun nome per il tipo <xref:System.Data.DataSet>, verrà usato il nome "NewDataSet".  
  
 È inoltre possibile creare un nuovo tipo <xref:System.Data.DataSet> basato su un tipo <xref:System.Data.DataSet> esistente. Il nuovo tipo <xref:System.Data.DataSet> può essere una copia esatta del <xref:System.Data.DataSet> esistente; un duplicato del tipo <xref:System.Data.DataSet> in cui viene copiata la struttura relazionale o lo schema ma in cui non è presente alcun dato proveniente dal <xref:System.Data.DataSet> esistente; oppure un subset del tipo <xref:System.Data.DataSet>, contenente solo le righe modificate del <xref:System.Data.DataSet> esistente usando il metodo <xref:System.Data.DataSet.GetChanges%2A>. Per ulteriori informazioni, vedere [copia del contenuto del set di dati](copying-dataset-contents.md).  
  
 Nell'esempio di codice seguente viene illustrata la creazione di un'istanza di un tipo <xref:System.Data.DataSet>.  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a>Vedere anche

- [Popolamento di un set di dati da un oggetto DataAdapter](../populating-a-dataset-from-a-dataadapter.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
