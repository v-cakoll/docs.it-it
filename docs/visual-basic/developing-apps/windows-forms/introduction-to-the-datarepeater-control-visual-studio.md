---
title: Introduzione al controllo DataRepeater (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- repeating data
- DataRepeater, overview
- DataRepeater
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
ms.openlocfilehash: c9d95f41e9857d70e81cafc94e5e3bffd4cbc3d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580707"
---
# <a name="introduction-to-the-datarepeater-control-visual-studio"></a>Introduzione al controllo DataRepeater (Visual Studio)
Il controllo Visual Basic PowerPacks <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> è un contenitore scorrevole per controlli che visualizzano dati ripetuti, ad esempio le righe in una tabella di database. Può essere usato come alternativa al controllo <xref:System.Windows.Forms.DataGridView> quando è necessario maggiore controllo sul layout dei dati. Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> "ripete" un gruppo di controlli correlati mediante la creazione di più istanze in una visualizzazione a scorrimento. Ciò consente agli utenti di visualizzare diversi record contemporaneamente.  
  
## <a name="overview"></a>Panoramica  
 In fase di progettazione di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo è costituito da due sezioni. La sezione esterna è il *viewport*, in cui verranno visualizzati i dati di scorrimento in fase di esecuzione. La sezione (superiore) interna, nota come le *modello di elemento*, è dove vengono posizionati i controlli che verranno ripetuti in fase di esecuzione, in genere a un controllo per ogni campo nell'origine dati. Le proprietà e i controlli nel modello di elemento sono incapsulati nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> proprietà.  
  
 In fase di esecuzione, il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> viene copiato in una virtual <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> oggetto utilizzato per visualizzare i dati quando si scorre ogni record nella visualizzazione. È possibile personalizzare la visualizzazione dei singoli record di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> evento, ad esempio, l'evidenziazione di un campo in base al valore in esso contenuti. Per altre informazioni, vedere [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 L'uso più comune per un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo consiste nel visualizzare i dati da una tabella di database o un'altra origine dati associata. Oltre a [!INCLUDE[vstecado](~/includes/vstecado-md.md)] oggetti dati, il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo può eseguire l'associazione a qualsiasi classe che implementa il <xref:System.Collections.IList> interfaccia (incluse le matrici), qualsiasi classe che implementa il <xref:System.ComponentModel.IListSource> interfaccia, qualsiasi classe che implementa il <xref:System.ComponentModel.IBindingList> interfaccia o qualsiasi classe che implementa il <xref:System.ComponentModel.IBindingListView> interfaccia.  
  
### <a name="data-binding"></a>Data binding  
 In genere, eseguire l'associazione dati, trascinare i campi dal **Zdroje dat** finestra nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Per altre informazioni, vedere [Procedura: Visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
 Quando si lavora con grandi quantità di dati, è possibile impostare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> proprietà `True` per visualizzare un subset di dati disponibili. Modalità virtuale richiede l'implementazione di una cache di dati da cui il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> è popolato, ed è necessario controllare tutte le interazioni con la cache dei dati in fase di esecuzione. Per altre informazioni, vedere [modalità virtuale nel controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 È anche possibile visualizzare i controlli non associati in un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Ad esempio, è possibile visualizzare un'immagine che viene ripetuta in ogni elemento. Per altre informazioni, vedere [Procedura: Visualizzare non associati a controlli in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
### <a name="events"></a>Eventi  
 Gli eventi più importanti per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo sono le <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> evento, che viene generato quando vengono scorsi i nuovi elementi nella visualizzazione, e il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> evento, che viene generato quando viene selezionato un elemento. È possibile usare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> evento per modificare l'aspetto dell'elemento. Ad esempio, è possibile evidenziare i valori negativi. Usare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> eventi per i valori dei controlli di accesso quando viene selezionato un elemento.  
  
 Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo espone tutti gli eventi di controllo standard nell'Editor del codice. Tuttavia, alcuni degli eventi non devono essere utilizzati. Della tastiera e mouse, ad esempio gli eventi `KeyDown`, `Click`, e `MouseDown` non verrà generato in fase di esecuzione perché il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> stesso controllo non ha mai lo stato attivo.  
  
 Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> non espone eventi in fase di progettazione perché è creato solo in fase di esecuzione. Se si desidera gestire gli eventi di tastiera e mouse, è possibile aggiungere un <xref:System.Windows.Forms.Panel> controllare per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> in fase di progettazione e quindi gestire gli eventi per il <xref:System.Windows.Forms.Panel>. Per altre informazioni, vedere [risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md).  
  
### <a name="customizations"></a>Personalizzazioni  
 Esistono diversi modi per personalizzare l'aspetto e il comportamento del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllare, entrambi in fase di esecuzione e in fase di progettazione. Proprietà possono essere impostate per modificare i colori, nascondere o modificare le intestazioni degli elementi, modificare l'orientamento da verticale a orizzontale e molto altro ancora. Per altre informazioni, vedere [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [come: Visualizzare le intestazioni degli elementi in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md), e [come: Modificare il Layout di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md).  
  
 Si noti che alcune proprietà si applicano per la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> stesso controllo mentre altre si applicano solo al <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>. Assicurarsi di avere la sezione corretta del controllo selezionato prima di impostare le proprietà. Per altre informazioni, vedere [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Altre personalizzazioni includono la possibilità di aggiungere o eliminare i record di controllo, aggiungendo le funzionalità di ricerca e visualizzazione dei dati correlati in un formato master e di dettaglio. Per altre informazioni, vedere [Procedura: Disabilitare l'aggiunta e l'eliminazione di elementi DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [come: Cercare dati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md), e [come: Creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md).  
  
## <a name="see-also"></a>Vedere anche
- [Controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)
- [Procedura dettagliata: Visualizzazione dei dati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)
- [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
