---
title: DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: 8a06accb11631f2dce6b0d39587d7274223c0e68
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786354"
---
# <a name="dataviews"></a>DataView
Un oggetto <xref:System.Data.DataView> consente di creare diverse visualizzazioni dei dati archiviati in un oggetto <xref:System.Data.DataTable>. Questa funzionalità è usata spesso nelle applicazioni di associazione dati. Utilizzando un oggetto **DataView**, è possibile esporre i dati in una tabella con diversi ordinamenti ed è possibile filtrare i dati in base allo stato della riga o in base a un'espressione di filtro.  
  
 Un oggetto **DataView** fornisce una visualizzazione dinamica dei dati nell' **oggetto DataTable**sottostante: il contenuto, l'ordinamento e l'appartenenza riflettono le modifiche non appena si verificano. Questo comportamento è diverso dal metodo **Select** dell' **oggetto DataTable**, che restituisce una <xref:System.Data.DataRow> matrice da una tabella in base a un filtro e/o un ordinamento specifici: questo contenuto riflette le modifiche apportate alla tabella sottostante, ma l'appartenenza e l'ordinamento rimane statico. Le funzionalità dinamiche del **DataView** lo rendono ideale per le applicazioni di data binding.  
  
 Un **DataView** offre una visualizzazione dinamica di un singolo set di dati, analogamente a una vista di database, a cui è possibile applicare criteri di ordinamento e di filtro diversi. Diversamente da una vista di database, tuttavia, un **DataView** non può essere considerato come una tabella e non può fornire una vista delle tabelle unite in join. Inoltre, non è possibile escludere colonne presenti nella tabella di origine, né aggiungere colonne, quali le colonne computazionali, che non sono presenti nella tabella di origine.  
  
 È possibile utilizzare un <xref:System.Data.DataView.DataViewManager%2A> oggetto per gestire le impostazioni di visualizzazione per tutte le tabelle in un **set di dati**. **DataViewManager** fornisce un modo pratico per gestire le impostazioni di visualizzazione predefinite per ogni tabella. Quando si associa un controllo a più di una tabella di un **set di dati**, l'associazione a un **DataViewManager** è la scelta ideale.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di un oggetto DataView](creating-a-dataview.md)  
 Viene descritto come creare un **DataView** per una **DataTable**.  
  
 [Ordinamento e applicazione di filtri ai dati](sorting-and-filtering-data.md)  
 Viene descritto come impostare le proprietà di un oggetto **DataView** per restituire subset di righe di dati che soddisfano criteri di filtro specifici o per restituire dati in un ordinamento specifico.  
  
 [Oggetti DataRow e DataRowView](datarows-and-datarowviews.md)  
 Viene descritto come accedere ai dati esposti dal **DataView**.  
  
 [Ricerca di righe](finding-rows.md)  
 Viene descritto come trovare una riga specifica in un oggetto **DataView**.  
  
 [Oggetti ChildView e relazioni](childviews-and-relations.md)  
 Viene descritto come creare visualizzazioni di dati da una relazione padre-figlio utilizzando un oggetto **DataView**.  
  
 [Modifica di oggetti DataView](modifying-dataviews.md)  
 Viene descritto come modificare i dati nell' **oggetto DataTable** sottostante tramite **DataView**, inclusa l'abilitazione o la disabilitazione degli aggiornamenti.  
  
 [Gestione di eventi DataView](handling-dataview-events.md)  
 Viene descritto come utilizzare l'evento **ListChanged** per ricevere una notifica quando il contenuto o l'ordine di un **DataView** viene aggiornato.  
  
 [Gestione di oggetti DataView](managing-dataviews.md)  
 Viene descritto come utilizzare **DataViewManager** per gestire le impostazioni **DataView** per ogni tabella in un **set di dati**.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Applicazioni Web ASP.NET](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))  
 Vengono fornite informazioni generali e procedure passo passo dettagliate per la creazione di applicazioni, Web Form e servizi Web ASP.NET.  
  
 [Applicazioni Windows](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))  
 Vengono fornite informazioni dettagliate sull'utilizzo di Windows Form e di applicazioni console.  
  
 [Oggetti DataSet, DataTable e DataView](index.md)  
 Descrive l'oggetto **DataSet** e il modo in cui è possibile usarlo per gestire i dati dell'applicazione.  
  
 [DataTable](datatables.md)  
 Descrive l'oggetto **DataTable** e come è possibile usarlo per gestire i dati dell'applicazione da solo o come parte di un **set**di dati.  
  
 [ADO.NET](../index.md)  
 Vengono descritti l'architettura e i componenti di ADO.NET e come usare ADO.NET per l'accesso alle origini dati esistenti e per la gestione dei dati dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](../ado-net-overview.md)
