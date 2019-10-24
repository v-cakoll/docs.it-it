---
title: DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: 1b202af052c05ed9dc671fa20c9c366f280ec5c7
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774169"
---
# <a name="dataviews"></a>DataView
Un oggetto <xref:System.Data.DataView> consente di creare diverse visualizzazioni dei dati archiviati in un oggetto <xref:System.Data.DataTable>. Questa funzionalità è usata spesso nelle applicazioni di associazione dati. Utilizzando un oggetto **DataView**, è possibile esporre i dati in una tabella con diversi ordinamenti ed è possibile filtrare i dati in base allo stato della riga o in base a un'espressione di filtro.

 Un oggetto **DataView** fornisce una visualizzazione dinamica dei dati nell' **oggetto DataTable**sottostante: il contenuto, l'ordinamento e l'appartenenza riflettono le modifiche non appena si verificano. Questo comportamento è diverso dal metodo **Select** dell' **oggetto DataTable**, che restituisce una matrice di <xref:System.Data.DataRow> da una tabella basata su un filtro e/o un ordinamento specifici: questo contenuto riflette le modifiche apportate alla tabella sottostante, ma l'appartenenza e l'ordinamento rimanere statici. Le funzionalità dinamiche del **DataView** lo rendono ideale per le applicazioni di data binding.

 Un **DataView** offre una visualizzazione dinamica di un singolo set di dati, analogamente a una vista di database, a cui è possibile applicare criteri di ordinamento e di filtro diversi. Diversamente da una vista di database, tuttavia, un **DataView** non può essere considerato come una tabella e non può fornire una vista delle tabelle unite in join. Non è inoltre possibile escludere le colonne presenti nella tabella di origine o accodare colonne che non esistono nella tabella di origine, ad esempio le colonne computazionali.

 È possibile utilizzare un <xref:System.Data.DataView.DataViewManager%2A> per gestire le impostazioni di visualizzazione per tutte le tabelle in un **set di dati**. **DataViewManager** fornisce un modo pratico per gestire le impostazioni di visualizzazione predefinite per ogni tabella. Quando si associa un controllo a più di una tabella di un **set di dati**, l'associazione a un **DataViewManager** è la scelta ideale.

## <a name="in-this-section"></a>Contenuto della sezione
 [Creazione di un oggetto DataView](creating-a-dataview.md) Viene descritto come creare un **DataView** per una **DataTable**.

 [Ordinamento e filtro dei dati](sorting-and-filtering-data.md) Viene descritto come impostare le proprietà di un oggetto **DataView** per restituire subset di righe di dati che soddisfano criteri di filtro specifici o per restituire dati in un ordinamento specifico.

 [DataRows e DataRowView](datarows-and-datarowviews.md) Viene descritto come accedere ai dati esposti dal **DataView**.

 [Ricerca di righe](finding-rows.md) Viene descritto come trovare una riga specifica in un oggetto **DataView**.

 [Oggetti ChildView e relazioni](childviews-and-relations.md) Viene descritto come creare visualizzazioni di dati da una relazione padre-figlio utilizzando un oggetto **DataView**.

 [Modifica di visualizzazioni di visualizzazione](modifying-dataviews.md) Viene descritto come modificare i dati nell' **oggetto DataTable** sottostante tramite **DataView**, inclusa l'abilitazione o la disabilitazione degli aggiornamenti.

 [Gestione degli eventi DataView](handling-dataview-events.md) Viene descritto come utilizzare l'evento **ListChanged** per ricevere una notifica quando il contenuto o l'ordine di un **DataView** viene aggiornato.

 [Gestione di visualizzazioni di visualizzazione](managing-dataviews.md) Viene descritto come utilizzare **DataViewManager** per gestire le impostazioni **DataView** per ogni tabella in un **set di dati**.

## <a name="related-sections"></a>Sezioni correlate
 [Applicazioni Web ASP.NET](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100)) Vengono fornite panoramiche e procedure dettagliate per la creazione di applicazioni ASP.NET, Web Form e servizi Web.

 [Applicazioni Windows](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100)) Vengono fornite informazioni dettagliate sull'utilizzo di Windows Forms e delle applicazioni console.

 [DataSet, DataTable e DataViews](index.md) Descrive l'oggetto **DataSet** e il modo in cui è possibile usarlo per gestire i dati dell'applicazione.

 [DataTable](datatables.md) Descrive l'oggetto **DataTable** e come è possibile usarlo per gestire i dati dell'applicazione da solo o come parte di un **set**di dati.

 [ADO.NET](../index.md) Vengono descritti l'architettura e i componenti di ADO.NET e viene illustrato come utilizzare ADO.NET per accedere alle origini dati esistenti e gestire i dati dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](../ado-net-overview.md)
