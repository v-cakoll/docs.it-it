---
title: Creazione di un oggetto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: d118f97e425782dbdf89c7e5d1eccd4d371b419c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759114"
---
# <a name="creating-a-dataview"></a>Creazione di un oggetto DataView
Per creare un <xref:System.Data.DataView>, sono disponibili due modalità. È possibile utilizzare il **DataView** costruttore, oppure è possibile creare un riferimento al <xref:System.Data.DataTable.DefaultView%2A> proprietà del <xref:System.Data.DataTable>. Il **DataView** costruttore può essere vuoto oppure può accettare un **DataTable** come argomento singolo, o un **DataTable** insieme ai criteri di filtro, criteri di ordinamento e una riga filtro di stato. Per ulteriori informazioni sugli argomenti aggiuntivi per l'utilizzo con il **DataView**, vedere [ordinamento e filtraggio dei dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Poiché l'indice per un **DataView** viene compilato sia quando la **DataView** viene creato e quando un il **ordinamento**, **RowFilter**, o  **RowStateFilter** si modificano le proprietà, per ottenere prestazioni ottimali di fornire qualsiasi tipo di ordinamento iniziale o criteri di filtro come argomenti del costruttore quando si crea il **DataView**. Creazione di un **DataView** senza specificare i criteri di ordinamento o filtro e quindi impostando la **ordinamento**, **RowFilter**, o **RowStateFilter** le proprietà in un secondo momento fa sì che l'indice verrà compilato almeno due volte: una volta quando il **DataView** viene creato e nuovamente quando le proprietà di ordinamento o filtro vengono modificate.  
  
 Si noti che se si crea un **DataView** utilizzando il costruttore che non accetta alcun argomento, non sarà in grado di utilizzare il **DataView** fino a quando non è stato impostato il **tabella** proprietà .  
  
 Esempio di codice riportato di seguito viene illustrato come creare un **DataView** utilizzando il **DataView** costruttore. Oggetto **RowFilter**, **ordinamento** colonna, e **DataViewRowState** vengono forniti con il **DataTable**.  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 Esempio di codice riportato di seguito viene illustrato come ottenere un riferimento all'impostazione predefinita **DataView** di un **DataTable** utilizzando il **DefaultView** proprietà della tabella.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Ordinamento e applicazione di filtri ai dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
