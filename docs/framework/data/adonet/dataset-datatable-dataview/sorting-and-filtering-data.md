---
title: Ordinamento e applicazione di filtri ai dati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 09cee2f2b2c3288c835912c9f311bf2511c7b0d0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785920"
---
# <a name="sorting-and-filtering-data"></a>Ordinamento e applicazione di filtri ai dati
In <xref:System.Data.DataView> sono disponibili diversi metodi di ordinamento e applicazione di filtri ai dati in una <xref:System.Data.DataTable>:  
  
- La proprietà <xref:System.Data.DataView.Sort%2A> viene usata per specificare criteri di ordinamento basati su una o più colonne e includere i parametri ASC (ascendente) e DESC (discendente).  
  
- La proprietà <xref:System.Data.DataView.ApplyDefaultSort%2A> consente di creare automaticamente un criterio di ordinamento ascendente, basato sulla colonna o sulle colonne di chiave primaria della tabella. <xref:System.Data.DataView.ApplyDefaultSort%2A>si applica solo quando la proprietà **Sort** è un riferimento null o una stringa vuota e quando la tabella contiene una chiave primaria definita.  
  
- La proprietà <xref:System.Data.DataView.RowFilter%2A> consente di specificare subset di righe sulla base dei relativi valori di colonna. Per informazioni dettagliate sulle espressioni valide per la proprietà **RowFilter** , vedere le informazioni di riferimento <xref:System.Data.DataColumn.Expression%2A> per la proprietà <xref:System.Data.DataColumn> della classe.  
  
     Se si desidera restituire i risultati di una particolare query sui dati, anziché fornire una visualizzazione dinamica di un subset di dati, utilizzare i <xref:System.Data.DataView.Find%2A> metodi o <xref:System.Data.DataView.FindRows%2A> del **DataView** per ottenere prestazioni ottimali anziché impostare  **Proprietà RowFilter** . Impostando la proprietà **RowFilter** , viene ricompilato l'indice per i dati, aggiungendo un sovraccarico all'applicazione e diminuendo le prestazioni. È consigliabile usare la proprietà **RowFilter** in un'applicazione con associazione a dati in cui un controllo associato Visualizza i risultati filtrati. I metodi **Find** e **FindRows** sfruttano l'indice corrente senza richiedere la ricompilazione dell'indice. Per ulteriori informazioni sui metodi **Find** e **FindRows** , vedere [ricerca di righe](finding-rows.md).  
  
- La proprietà <xref:System.Data.DataView.RowStateFilter%2A> consente di specificare le versioni di riga da visualizzare. Il **DataView** gestisce in modo implicito la versione di riga da esporre a seconda del tipo di **RowState** della riga sottostante. Se, ad esempio, **RowStateFilter** è impostato su **DataViewRowState. Deleted**, il **DataView** espone la versione di riga **originale** di tutte le righe **eliminate** perché non è disponibile una versione di riga **corrente** . È possibile determinare la versione di riga di una riga esposta tramite la proprietà **rowversion** dell'oggetto **DataRowView**.  
  
     Nella tabella seguente vengono illustrate le opzioni per **DataViewRowState**.  
  
    |Opzioni di DataViewRowState|Descrizione|  
    |------------------------------|-----------------|  
    |**CurrentRows**|La versione di riga **corrente** di tutte le righe non **modificate**, **aggiunte**e **modificate** . Questa è l'impostazione predefinita.|  
    |**Aggiunto**|Versione di riga **corrente** di tutte le righe **aggiunte** .|  
    |**Eliminato**|Versione di riga **originale** di tutte le righe **eliminate** .|  
    |**ModifiedCurrent**|Versione di riga **corrente** di tutte le righe **modificate** .|  
    |**ModifiedOriginal**|Versione di riga **originale** di tutte le righe **modificate** .|  
    |**None**|Nessuna riga.|  
    |**OriginalRows**|Versione di riga **originale** di tutte le righe non **modificate**, **modificate**ed **eliminate** .|  
    |**Invariato**|Versione di riga **corrente** di tutte le righe non **modificate** .|  
  
 Per altre informazioni sugli Stati delle righe e sulle versioni delle righe, vedere Stati di riga [e versioni](row-states-and-row-versions.md)di riga.  
  
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

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [DataView](dataviews.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
