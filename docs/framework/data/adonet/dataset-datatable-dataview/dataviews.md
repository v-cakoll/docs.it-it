---
title: DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: aff4d6f648fa091130bfd9951f2a5001947b09a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215911"
---
# <a name="dataviews"></a>DataView
Un oggetto <xref:System.Data.DataView> consente di creare diverse visualizzazioni dei dati archiviati in un oggetto <xref:System.Data.DataTable>. Questa funzionalità è usata spesso nelle applicazioni di associazione dati. Usando un **DataView**, è possibile esporre i dati di una tabella applicando diversi tipi di ordinamento ed è possibile filtrare i dati da riga di stato o sulla base di un'espressione di filtro.  
  
 Oggetto **DataView** offre una visualizzazione dinamica dei dati nell'oggetto sottostante **DataTable**: il contenuto, ordinamento e l'appartenenza riflettono le modifiche appena si verificano. Questo comportamento è diverso dal **selezionare** metodo per il **DataTable**, che restituisce un <xref:System.Data.DataRow> matrice da una tabella basata su un particolare ordine di filtro e/o di ordinamento: questo contenuto riflette le modifiche apportate il sottostanti nella tabella, ma l'appartenenza e l'ordinamento restano statici. Le funzionalità dinamiche del **DataView** lo rendono ideale per applicazioni di data binding.  
  
 Oggetto **DataView** offre una visualizzazione dinamica di un singolo set di dati, molto simile a una vista di database, a cui è possibile applicare l'ordinamento diversi e criteri di filtro. A differenza di una vista di database, tuttavia, un **DataView** non può essere considerato come una tabella e non può fornire una visualizzazione di tabelle unite in join. Inoltre, non è possibile escludere colonne presenti nella tabella di origine, né aggiungere colonne, quali le colonne computazionali, che non sono presenti nella tabella di origine.  
  
 È possibile usare una <xref:System.Data.DataView.DataViewManager%2A> per gestire le impostazioni di visualizzazione per tutte le tabelle in un **set di dati**. Il **DataViewManager** offre un modo pratico per gestire le impostazioni di visualizzazione predefinito per ogni tabella. Quando si associa un controllo a più di una tabella di un **set di dati**, l'associazione a un **DataViewManager** è la scelta ideale.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di un oggetto DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 Viene descritto come creare un **DataView** per una **DataTable**.  
  
 [Ordinamento e applicazione di filtri ai dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 Viene descritto come impostare le proprietà di un **DataView** per restituire subset di righe di dati che soddisfano criteri specifici di filtro o per restituire i dati in un ordine particolare.  
  
 [Oggetti DataRow e DataRowView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 Viene descritto come accedere ai dati esposti dal **DataView**.  
  
 [Ricerca di righe](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 Viene descritto come trovare una determinata riga in una **DataView**.  
  
 [Oggetti ChildView e relazioni](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 Viene descritto come creare visualizzazioni dei dati da una relazione padre-figlio tramite un **DataView**.  
  
 [Modifica di oggetti DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 Viene descritto come modificare i dati sottostanti **DataTable** tramite il **DataView**, inclusa l'abilitazione o disabilitazione degli aggiornamenti.  
  
 [Gestione di eventi DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 Viene descritto come utilizzare il **ListChanged** evento per ricevere una notifica quando il contenuto o l'ordine di un **DataView** è in corso l'aggiornamento.  
  
 [Gestione di oggetti DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 Viene descritto come utilizzare un **DataViewManager** gestire **DataView** le impostazioni per ogni tabella in un **set di dati**.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Applicazioni Web ASP.NET](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))  
 Vengono fornite informazioni generali e procedure passo passo dettagliate per la creazione di applicazioni, Web Form e servizi Web ASP.NET.  
  
 [Applicazioni di Windows](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))  
 Vengono fornite informazioni dettagliate sull'utilizzo di Windows Form e di applicazioni console.  
  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Descrive la **set di dati** oggetto e come è possibile usarlo per gestire i dati dell'applicazione.  
  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Descrive la **DataTable** oggetto e come è possibile usarlo per gestire i dati dell'applicazione da solo o come parte di un **DataSet**.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Vengono descritti l'architettura e i componenti di ADO.NET e come usare ADO.NET per l'accesso alle origini dati esistenti e per la gestione dei dati dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
