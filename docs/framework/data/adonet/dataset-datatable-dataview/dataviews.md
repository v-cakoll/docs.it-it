---
title: DataView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5b79461a6fc3314ca4178e0f9b1cff1c468cc3e6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="dataviews"></a>DataView
Un oggetto <xref:System.Data.DataView> consente di creare diverse visualizzazioni dei dati archiviati in un oggetto <xref:System.Data.DataTable>. Questa funzionalità è usata spesso nelle applicazioni di associazione dati. Utilizzando un **DataView**, è possibile esporre i dati in una tabella con diversi tipi di ordinamento ed è possibile filtrare i dati dello stato o in base a un'espressione di filtro di riga.  
  
 Oggetto **DataView** offre una visualizzazione dinamica dei dati nell'oggetto sottostante **DataTable**: contenuto, l'ordinamento e l'appartenenza riflettono le modifiche che si verificano. Questo comportamento è diverso dal **selezionare** metodo il **DataTable**, che restituisce un <xref:System.Data.DataRow> matrice da una tabella in base a un particolare ordine di filtro e/o di ordinamento: thiscontent riflette le modifiche apportate il sottostante nella tabella, ma l'appartenenza e di ordinamento restano statici. Le funzionalità dinamiche del **DataView** rendono ideale per applicazioni di associazione dati.  
  
 Oggetto **DataView** offre una visualizzazione dinamica di un singolo set di dati, analogamente a una vista di database, a cui è possibile applicare diverse di ordinamento e criteri di filtro. A differenza di una vista di database, tuttavia, un **DataView** non può essere considerato come una tabella e non fornisce una visualizzazione di tabelle unite in join. Inoltre, non è possibile escludere colonne presenti nella tabella di origine, né aggiungere colonne, quali le colonne computazionali, che non sono presenti nella tabella di origine.  
  
 È possibile utilizzare un <xref:System.Data.DataView.DataViewManager%2A> per gestire le impostazioni di visualizzazione per tutte le tabelle in un **DataSet**. Il **DataViewManager** offre un modo pratico per gestire le impostazioni di visualizzazione predefinito per ogni tabella. Quando si associa un controllo a più di una tabella di un **DataSet**, associazione a un **DataViewManager** è la scelta ideale.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di un oggetto DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 Viene descritto come creare un **DataView** per un **DataTable**.  
  
 [Ordinamento e applicazione di filtri ai dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 Viene descritto come impostare le proprietà di un **DataView** per restituire subset di righe di dati che soddisfano i criteri di filtro specifici o per restituire dati in un particolare tipo di ordinamento.  
  
 [Oggetti DataRow e DataRowView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 Viene descritto come accedere ai dati esposti dal **DataView**.  
  
 [Ricerca di righe](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 Viene descritto come trovare una determinata riga in un **DataView**.  
  
 [Oggetti ChildView e relazioni](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 Viene descritto come creare visualizzazioni dei dati da una relazione padre-figlio tramite un **DataView**.  
  
 [Modifica di oggetti DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 Viene descritto come modificare i dati nell'oggetto sottostante **DataTable** tramite il **DataView**, inclusa l'abilitazione o disabilitazione degli aggiornamenti.  
  
 [Gestione di eventi DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 Viene descritto come utilizzare il **ListChanged** eventi per ricevere notifiche quando il contenuto o l'ordine di un **DataView** viene aggiornata.  
  
 [Gestione di oggetti DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 Viene descritto come utilizzare un **DataViewManager** per gestire **DataView** le impostazioni per ogni tabella in un **DataSet**.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Applicazioni Web ASP.NET](http://msdn.microsoft.com/library/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 Vengono fornite informazioni generali e procedure passo passo dettagliate per la creazione di applicazioni, Web Form e servizi Web ASP.NET.  
  
 [Applicazioni Windows](http://msdn.microsoft.com/library/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 Vengono fornite informazioni dettagliate sull'utilizzo di Windows Form e di applicazioni console.  
  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Viene descritto il **DataSet** oggetto e come è possibile usarlo per gestire i dati dell'applicazione.  
  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Viene descritto il **DataTable** oggetto e come è possibile utilizzare per gestire i dati dell'applicazione da solo o come parte di un **DataSet**.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Vengono descritti l'architettura e i componenti di ADO.NET e come usare ADO.NET per l'accesso alle origini dati esistenti e per la gestione dei dati dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
