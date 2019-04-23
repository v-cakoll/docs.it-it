---
title: 'Procedura: Abilitare la visualizzazione affiancata in un controllo ListView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: f8c8a1b2e3d2adfa7daadd609051ffc304150efe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300593"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Procedura: Abilitare la visualizzazione affiancata in un controllo ListView di Windows Forms usando la finestra di progettazione
La funzionalità di visualizzazione affiancata del <xref:System.Windows.Forms.ListView> controllo consente di fornire un equilibrio visivo tra informazioni grafiche e testuali. Le informazioni testuali visualizzate per un elemento nella visualizzazione affiancata corrisponde alle informazioni della colonna definite per la visualizzazione dettagli. Funzioni di visualizzazione affiancata in combinazione con il raggruppamento oppure dall'inserimento contrassegnare le funzionalità di <xref:System.Windows.Forms.ListView> controllo.  
  
 La visualizzazione affiancata Usa un' 32x32 icona e alcune righe di testo, come illustrato nell'immagine seguente.  
  
 ![Visualizzazione affiancata in un controllo ListView](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "riquadro Visualizza icone e testo")  
  
 Riquadro proprietà e metodi consentono di specificare i campi colonna da visualizzare per ogni elemento, nonché di controllare le dimensioni e l'aspetto di tutti gli elementi all'interno di una finestra di visualizzazione del riquadro di visualizzazione. Per maggiore chiarezza, la prima riga del testo in un riquadro è sempre il nome dell'elemento; non può essere modificato.  
  
 La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.ListView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  La visualizzazione affiancata è disponibile solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Nei sistemi operativi precedenti, qualsiasi codice correlato alla visualizzazione affiancata non ha alcun effetto e il controllo <xref:System.Windows.Forms.ListView> viene visualizzato nella visualizzazione Icone grandi. Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.  
>   
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-tile-view-in-the-designer"></a>Per impostare la visualizzazione affiancata nella finestra di progettazione  
  
1. Selezionare il <xref:System.Windows.Forms.ListView> controllo sul form.  
  
2. Nel **delle proprietà** finestra, seleziona la <xref:System.Windows.Forms.ListView.View%2A> proprietà e scegliere **riquadro**.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
