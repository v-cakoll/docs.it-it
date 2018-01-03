---
title: Ordinamento e applicazione di filtri ai dati
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
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f514095e551967928d610451cfcaa9a829c0989f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="sorting-and-filtering-data"></a>Ordinamento e applicazione di filtri ai dati
In <xref:System.Data.DataView> sono disponibili diversi metodi di ordinamento e applicazione di filtri ai dati in una <xref:System.Data.DataTable>:  
  
-   La proprietà <xref:System.Data.DataView.Sort%2A> viene usata per specificare criteri di ordinamento basati su una o più colonne e includere i parametri ASC (ascendente) e DESC (discendente).  
  
-   La proprietà <xref:System.Data.DataView.ApplyDefaultSort%2A> consente di creare automaticamente un criterio di ordinamento ascendente, basato sulla colonna o sulle colonne di chiave primaria della tabella. <xref:System.Data.DataView.ApplyDefaultSort%2A>si applica solo quando il **ordinamento** proprietà è un riferimento null o una stringa vuota, e quando la tabella contiene una chiave primaria definita.  
  
-   La proprietà <xref:System.Data.DataView.RowFilter%2A> consente di specificare subset di righe sulla base dei relativi valori di colonna. Per informazioni dettagliate sulle espressioni valide per il **RowFilter** proprietà, vedere le informazioni di riferimento per il <xref:System.Data.DataColumn.Expression%2A> proprietà del <xref:System.Data.DataColumn> classe.  
  
     Se si desidera restituire i risultati di una particolare query sui dati anziché fornire una visualizzazione dinamica di un subset dei dati, utilizzare il <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> metodi il **DataView** per ottenere prestazioni ottimali anziché l'impostazione di **RowFilter** proprietà. L'impostazione di **RowFilter** proprietà ricompilato l'indice per i dati, aggiungendo un sovraccarico all'applicazione e riducendo le prestazioni. Il **RowFilter** proprietà è più adatta in un'applicazione con associazione a dati in cui i risultati filtrati vengono visualizzati da un controllo associato. Il **trovare** e **FindRows** metodi si avvalgono dell'indice corrente senza richiedere l'indice da ricompilare. Per ulteriori informazioni sul **trovare** e **FindRows** metodi, vedere [ricerca righe](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).  
  
-   La proprietà <xref:System.Data.DataView.RowStateFilter%2A> consente di specificare le versioni di riga da visualizzare. Il **DataView** gestisce in modo implicito la versione di riga per esporre varia a seconda di **RowState** della riga sottostante. Ad esempio, se il **RowStateFilter** è impostata su **DataViewRowState. Deleted**, **DataView** espone il **originale** versione di riga tutti **Deleted** righe in quanto non esiste alcun **corrente** versione di riga. È possibile determinare la versione di riga di una riga è esposto tramite la **RowVersion** proprietà del **DataRowView**.  
  
     Nella tabella seguente illustra le opzioni per **DataViewRowState**.  
  
    |Opzioni di DataViewRowState|Descrizione|  
    |------------------------------|-----------------|  
    |**CurrentRows**|Il **corrente** versione della riga di tutti i **Unchanged**, **Added**, e **Modified** righe. Questa è l'impostazione predefinita.|  
    |**Aggiunta**|Il **corrente** versione di riga all **Added** righe.|  
    |**Eliminato**|Il **originale** versione di riga all **Deleted** righe.|  
    |**ModifiedCurrent**|Il **corrente** versione di riga all **Modified** righe.|  
    |**ModifiedOriginal**|Il **originale** versione di riga all **Modified** righe.|  
    |**None**|Nessuna riga.|  
    |**OriginalRows**|Il **originale** versione della riga di tutti i **Unchanged**, **Modified**, e **Deleted** righe.|  
    |**Non modificato**|Il **corrente** versione di riga all **Unchanged** righe.|  
  
 Per ulteriori informazioni sulla riga stati e le versioni di riga, vedere [stati delle righe e le versioni di riga](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 Nell'esempio di codice seguente viene creata una visualizzazione in cui vengono mostrati tutti i prodotti il cui numero di unità disponibili in magazzino è inferiore o uguale al livello di riordinamento. I prodotti vengono ordinati prima in base all'identificatore del fornitore, quindi in base al nome del prodotto.  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
