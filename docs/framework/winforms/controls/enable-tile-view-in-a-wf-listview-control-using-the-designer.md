---
title: 'Procedura: abilitare la visualizzazione affiancata in un controllo ListView Windows Form mediante la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 4f51d3a596bc3358942cdfd654b3e4515d96cd07
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960104"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Procedura: abilitare la visualizzazione affiancata in un controllo ListView Windows Form mediante la finestra di progettazione
La caratteristica visualizzazione affiancata del controllo <xref:System.Windows.Forms.ListView> consente di fornire un equilibrio visivo tra informazioni grafiche e testuali. Le informazioni testuali visualizzate per un elemento nella visualizzazione affiancata corrisponde alle informazioni della colonna definite per la visualizzazione dettagli. Funzioni di visualizzazione affiancate in combinazione con le funzionalità di raggruppamento o di contrassegno di inserimento nel controllo <xref:System.Windows.Forms.ListView>.

 La visualizzazione affiancata usa un'icona 32 x 32 e varie righe di testo, come illustrato nella figura seguente.

 ![Visualizzazione affiancata in un controllo ListView](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Icone e testo di visualizzazione affiancata")

 Le proprietà e i metodi della visualizzazione affiancata consentono di specificare i campi di colonna da visualizzare per ogni elemento e di controllare collettivamente le dimensioni e l'aspetto di tutti gli elementi all'interno di una finestra di visualizzazione affiancata. Per maggiore chiarezza, la prima riga di testo in una sezione è sempre il nome dell'elemento; non può essere modificato.

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.ListView>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-set-tile-view-in-the-designer"></a>Per impostare la visualizzazione affiancata nella finestra di progettazione

1. In Visual Studio selezionare il controllo <xref:System.Windows.Forms.ListView> sul form.

2. Nella finestra **Proprietà** selezionare la proprietà <xref:System.Windows.Forms.ListView.View%2A> e scegliere **riquadro**.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
