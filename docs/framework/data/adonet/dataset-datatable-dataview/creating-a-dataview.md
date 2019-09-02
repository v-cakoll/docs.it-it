---
title: Creazione di un oggetto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 391c071f19149e9690c9121b1094aef5bfa605cd
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203827"
---
# <a name="creating-a-dataview"></a>Creazione di un oggetto DataView
Per creare un <xref:System.Data.DataView>, sono disponibili due modalità. È possibile usare il costruttore **DataView** oppure è possibile creare un riferimento alla <xref:System.Data.DataTable.DefaultView%2A> proprietà di. <xref:System.Data.DataTable> Il costruttore **DataView** può essere vuoto oppure può assumere un **oggetto DataTable** come singolo argomento oppure un **DataTable** insieme a criteri di filtro, criteri di ordinamento e un filtro di stato della riga. Per ulteriori informazioni sugli argomenti aggiuntivi disponibili per l'utilizzo con **DataView**, vedere [ordinamento e filtro dei dati](sorting-and-filtering-data.md).  
  
 Poiché l'indice di un oggetto **DataView** viene compilato sia quando viene creato il **DataView** , sia quando viene modificata una delle proprietà **Sort**, **RowFilter**o **RowStateFilter** , si ottengono le migliori prestazioni fornendo eventuali iniziali ordinare o filtrare i criteri come argomenti del costruttore quando si crea il **DataView**. La creazione di un oggetto **DataView** senza specificare criteri di ordinamento o di filtro e l'impostazione delle proprietà **Sort**, **RowFilter**o **RowStateFilter** in un secondo momento comporta la compilazione dell'indice almeno due volte: una volta quando il **DataView** è creato e di nuovo quando una delle proprietà di ordinamento o filtro viene modificata.  
  
 Si noti che se si crea un **DataView** usando il costruttore che non accetta argomenti, non sarà possibile usare il **DataView** fino a quando non viene impostata la proprietà **Table** .  
  
 Nell'esempio di codice seguente viene illustrato come creare un **DataView** utilizzando il costruttore **DataView** . Insieme alla **DataTable**vengono forniti un **RowFilter**, una colonna di **ordinamento** e **DataViewRowState** .  
  
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
  
 Nell'esempio di codice riportato di seguito viene illustrato come ottenere un riferimento al **DataView** predefinito di una **DataTable** utilizzando la proprietà **DefaultView** della tabella.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [DataView](dataviews.md)
- [Ordinamento e applicazione di filtri ai dati](sorting-and-filtering-data.md)
- [DataTable](datatables.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
