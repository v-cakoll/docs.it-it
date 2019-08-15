---
title: 'Procedura: Abilitare la visualizzazione affiancata in un controllo ListView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 8a45a8a484bd373f53585b1b113a51e59b30fca2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040360"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Procedura: Abilitare la visualizzazione affiancata in un controllo ListView di Windows Forms usando la finestra di progettazione
La funzionalità di visualizzazione affiancata <xref:System.Windows.Forms.ListView> del controllo consente di fornire un equilibrio visivo tra informazioni grafiche e testuali. Le informazioni testuali visualizzate per un elemento nella visualizzazione affiancata corrisponde alle informazioni della colonna definite per la visualizzazione dettagli. Funzioni di visualizzazione affiancate in combinazione con le funzionalità di raggruppamento o di contrassegno di <xref:System.Windows.Forms.ListView> inserimento nel controllo.

 La visualizzazione affiancata usa un'icona 32 x 32 e varie righe di testo, come illustrato nella figura seguente.

 ![Visualizzazione affiancata in un controllo ListView](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Icone e testo di visualizzazione affiancata")

 Le proprietà e i metodi della visualizzazione affiancata consentono di specificare i campi di colonna da visualizzare per ogni elemento e di controllare collettivamente le dimensioni e l'aspetto di tutti gli elementi all'interno di una finestra di visualizzazione affiancata. Per maggiore chiarezza, la prima riga di testo in una sezione è sempre il nome dell'elemento; non può essere modificato.

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.ListView> modulo contenente un controllo. Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).

> [!NOTE]
> La visualizzazione affiancata è disponibile solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Nei sistemi operativi precedenti, qualsiasi codice correlato alla visualizzazione affiancata non ha alcun effetto e il controllo <xref:System.Windows.Forms.ListView> viene visualizzato nella visualizzazione Icone grandi. Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.

## <a name="to-set-tile-view-in-the-designer"></a>Per impostare la visualizzazione affiancata nella finestra di progettazione

1. In Visual Studio selezionare il <xref:System.Windows.Forms.ListView> controllo nel form.

2. Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.ListView.View%2A> proprietà e scegliere **riquadro**.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
