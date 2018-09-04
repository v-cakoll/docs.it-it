---
title: Ordinamento e applicazione di filtri ai dati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: ade08deca909b32090b7d2d7cf8c6ba9ce9e7679
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43538683"
---
# <a name="sorting-and-filtering-data"></a>Ordinamento e applicazione di filtri ai dati
In <xref:System.Data.DataView> sono disponibili diversi metodi di ordinamento e applicazione di filtri ai dati in una <xref:System.Data.DataTable>:  
  
-   La proprietà <xref:System.Data.DataView.Sort%2A> viene usata per specificare criteri di ordinamento basati su una o più colonne e includere i parametri ASC (ascendente) e DESC (discendente).  
  
-   La proprietà <xref:System.Data.DataView.ApplyDefaultSort%2A> consente di creare automaticamente un criterio di ordinamento ascendente, basato sulla colonna o sulle colonne di chiave primaria della tabella. <xref:System.Data.DataView.ApplyDefaultSort%2A> si applica solo quando la **ordinamento** proprietà è un riferimento null o stringhe vuote, e quando la tabella è definita una chiave primaria.  
  
-   La proprietà <xref:System.Data.DataView.RowFilter%2A> consente di specificare subset di righe sulla base dei relativi valori di colonna. Per informazioni dettagliate sulle espressioni valide per i **RowFilter** proprietà, vedere le informazioni di riferimento per il <xref:System.Data.DataColumn.Expression%2A> proprietà del <xref:System.Data.DataColumn> classe.  
  
     Se si desidera restituire i risultati di una particolare query sui dati anziché fornire una visualizzazione dinamica di un subset dei dati, usano il <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> metodi delle **DataView** per ottenere prestazioni ottimali anziché impostando il **RowFilter** proprietà. Impostando il **RowFilter** proprietà ricompila l'indice per i dati, aggiungendo un sovraccarico all'applicazione e riducendo le prestazioni. Il **RowFilter** proprietà è particolarmente utile in un'applicazione con associazione a dati in cui un controllo associato vengono visualizzati i risultati filtrati. Il **trovare** e **FindRows** metodi si avvalgono dell'indice corrente senza richiedere l'indice da ricompilare. Per altre informazioni sul **trovare** e **FindRows** metodi, vedere [ricerca righe](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).  
  
-   La proprietà <xref:System.Data.DataView.RowStateFilter%2A> consente di specificare le versioni di riga da visualizzare. Il **DataView** gestisce in modo implicito la versione di riga per l'esposizione a seconda di **RowState** della riga sottostante. Ad esempio, se il **RowStateFilter** è impostata su **DataViewRowState. Deleted**, il **DataView** espone il **originale** versione della riga di tutti i **Deleted** righe in quanto non esiste alcun **corrente** versione di riga. È possibile determinare quale versione di riga di una riga è esposto tramite il **RowVersion** proprietà delle **DataRowView**.  
  
     La tabella seguente illustra le opzioni per la **DataViewRowState**.  
  
    |Opzioni di DataViewRowState|Descrizione|  
    |------------------------------|-----------------|  
    |**CurrentRows**|Il **correnti** versione di riga di tutte le **Unchanged**, **Added**, e **Modified** righe. Questa è l'impostazione predefinita.|  
    |**Aggiunto**|Il **correnti** versione di riga di tutte le **Added** righe.|  
    |**Eliminato**|Il **originale** versione di riga del tutto **Deleted** righe.|  
    |**ModifiedCurrent**|Il **corrente** versione di riga del tutto **Modified** righe.|  
    |**ModifiedOriginal**|Il **originale** versione di riga del tutto **Modified** righe.|  
    |**None**|Nessuna riga.|  
    |**OriginalRows**|Il **originali** versione di riga di tutte le **Unchanged**, **Modified**, e **Deleted** righe.|  
    |**non modificato**|Il **correnti** versione di riga del tutto **Unchanged** righe.|  
  
 Per altre informazioni sulla riga stati e le versioni di riga, vedere [stati e le versioni delle righe](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
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
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
