---
title: Introduzione al controllo DataRepeater (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- repeating data
- DataRepeater, overview
- DataRepeater
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
ms.openlocfilehash: fc0cf9c358faf3e738eb3b24ec61577b88dbce4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="introduction-to-the-datarepeater-control-visual-studio"></a>Introduzione al controllo DataRepeater (Visual Studio)
Il controllo Visual Basic PowerPacks <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> è un contenitore scorrevole per controlli che visualizzano dati ripetuti, ad esempio le righe in una tabella di database. Può essere usato come alternativa al controllo <xref:System.Windows.Forms.DataGridView> quando è necessario maggiore controllo sul layout dei dati. Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> "ripete" un gruppo di controlli correlati mediante la creazione di più istanze in una visualizzazione a scorrimento. Ciò consente agli utenti di visualizzare più record contemporaneamente.  
  
## <a name="overview"></a>Panoramica  
 In fase di progettazione di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo è costituito da due sezioni. La sezione esterna è di *viewport*, in cui i dati di scorrimento verranno visualizzati in fase di esecuzione. La sezione (superiore) interna, nota come il *modello di elemento*, è dove vengono posizionati i controlli che verranno ripetuti in fase di esecuzione, in genere un controllo per ogni campo nell'origine dati. Le proprietà e i controlli nel modello di elemento vengono incapsulati nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> proprietà.  
  
 In fase di esecuzione di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> viene copiato un virtuale <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> oggetto utilizzato per visualizzare i dati quando si scorre ogni record nella visualizzazione. È possibile personalizzare la visualizzazione dei singoli record di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> evento, ad esempio, l'evidenziazione di un campo in base al valore in esso contenuti. Per ulteriori informazioni, vedere [procedura: modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 L'utilizzo più comune per un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo consiste nel visualizzare i dati da una tabella di database o altra origine dati associata. Oltre a [!INCLUDE[vstecado](~/includes/vstecado-md.md)] oggetti dati, il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo è possibile associare a qualsiasi classe che implementa il <xref:System.Collections.IList> interfaccia (incluse le matrici), qualsiasi classe che implementa il <xref:System.ComponentModel.IListSource> interfaccia, qualsiasi classe che implementa il <xref:System.ComponentModel.IBindingList> interfaccia o qualsiasi classe che implementa il <xref:System.ComponentModel.IBindingListView> interfaccia.  
  
### <a name="data-binding"></a>Data binding  
 In genere, eseguire l'associazione di dati trascinando i campi dal **origini dati** finestra il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Per ulteriori informazioni, vedere [procedura: visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
 Quando si lavora con grandi quantità di dati, è possibile impostare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> proprietà `True` per visualizzare un subset di dati disponibili. Modalità virtuale richiede l'implementazione di una cache di dati da cui il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> è popolato, ed è necessario controllare tutte le interazioni con la cache dei dati in fase di esecuzione. Per ulteriori informazioni, vedere [modalità virtuale nel controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 È anche possibile visualizzare i controlli non associati in un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Ad esempio, è possibile visualizzare un'immagine che viene ripetuta per ogni elemento. Per ulteriori informazioni, vedere [procedura: visualizzare i controlli non associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
### <a name="events"></a>Eventi  
 Gli eventi più importanti per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo sono di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> evento, viene generato quando vengono scorsi nuovi elementi nella visualizzazione, e <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> evento, viene generato quando viene selezionato un elemento. È possibile utilizzare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> evento per modificare l'aspetto dell'elemento. Ad esempio, è possibile evidenziare i valori negativi. Utilizzare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> evento per accedere ai valori dei controlli quando viene selezionato un elemento.  
  
 Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo espone tutti gli eventi di controllo standard nell'Editor di codice. Tuttavia, alcuni degli eventi non devono essere utilizzati. Tastiera e mouse, ad esempio gli eventi `KeyDown`, `Click`, e `MouseDown` non verrà generato in fase di esecuzione perché il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo stesso non ha mai lo stato attivo.  
  
 Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> non espone eventi in fase di progettazione perché viene creato solo in fase di esecuzione. Se si desidera gestire gli eventi di tastiera e mouse, è possibile aggiungere un <xref:System.Windows.Forms.Panel> controllo il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> in fase di progettazione e quindi gestire gli eventi per il <xref:System.Windows.Forms.Panel>. Per ulteriori informazioni, vedere [risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md).  
  
### <a name="customizations"></a>Personalizzazioni  
 Esistono diversi modi per personalizzare l'aspetto e il comportamento del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllare, sia in fase di esecuzione sia in fase di progettazione. Per modificare i colori, nascondere o modificare le intestazioni degli elementi, modificare l'orientamento da verticale a orizzontale e molto altro ancora, è possono impostare le proprietà. Per ulteriori informazioni, vedere [come: modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [procedura: visualizzare le intestazioni degli elementi in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md), e [come: modificare il Layout di un Controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md).  
  
 Si noti che alcune proprietà valide per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo stesso, mentre altre sono valide solo per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>. Assicurarsi di avere la sezione corretta del controllo selezionato prima di impostare le proprietà. Per ulteriori informazioni, vedere [procedura: modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Altre personalizzazioni includono la possibilità di aggiungere o eliminare record di controllo, l'aggiunta di funzionalità di ricerca e visualizzazione dei dati correlati in un formato master e di dettaglio. Per ulteriori informazioni, vedere [procedura: disabilitare l'aggiunta e l'eliminazione di elementi DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [come: dati di ricerca in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md), e [come: creare un Form Master-Details per utilizzando due Controlli DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)  
 [Procedura dettagliata: Visualizzazione di dati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)  
 [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
