---
title: Creazione di un oggetto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 9d21b17068ff3ce5b0bd3990144383d7f9ded2f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151338"
---
# <a name="creating-a-dataview"></a>Creazione di un oggetto DataView
Per creare un <xref:System.Data.DataView>, sono disponibili due modalità. È possibile utilizzare il costruttore **DataView** oppure <xref:System.Data.DataTable.DefaultView%2A> creare <xref:System.Data.DataTable>un riferimento alla proprietà dell'oggetto . Il **DataView** costruttore può essere vuoto o può accettare un **DataTable** come un singolo argomento o un **DataTable** con criteri di filtro, criteri di ordinamento e un filtro di stato di riga. Per ulteriori informazioni sugli argomenti aggiuntivi disponibili per l'utilizzo con **DataView**, vedere [Ordinamento e filtro dei dati](sorting-and-filtering-data.md).  
  
 Poiché l'indice per un **DataView** viene compilato sia quando viene creato il **DataView** e quando una delle proprietà **Sort**, **RowFilter**o **RowStateFilter** viene modificata, è possibile ottenere prestazioni ottimali fornendo qualsiasi criterio di ordinamento iniziale o di filtro come argomenti del costruttore quando si crea il **DataView**. La creazione di un **DataView** senza specificare i criteri di ordinamento o filtro e quindi impostando le proprietà **Sort**, **RowFilter**o **RowStateFilter** in un secondo momento determina la compilazione dell'indice almeno due volte: una volta quando viene creato il **DataView** e di nuovo quando una delle proprietà di ordinamento o filtro viene modificata.  
  
 Si noti che se si crea un **DataView** utilizzando il costruttore che non accetta argomenti, non sarà possibile utilizzare il **DataView** fino a quando non è stata impostata la **Table** proprietà.  
  
 Esempio di codice seguente viene illustrato come creare un **DataView** utilizzando il **DataView** costruttore. Vengono forniti una colonna **RowFilter**, **Sort** e **DataViewRowState** insieme a **DataTable**.  
  
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
  
 Esempio di codice seguente viene illustrato come ottenere un riferimento al **DataView** predefinito di un **DataTable** utilizzando il **DefaultView** proprietà della tabella.  
  
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
- [Panoramica di ADO.NET](../ado-net-overview.md)
