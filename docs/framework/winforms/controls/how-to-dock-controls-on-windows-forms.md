---
title: Ancorare i controlli (Dock)
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 02f1c26dcb322a39c41781c83d8c820bd2fd27e0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745518"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Procedura: ancorare i controlli in Windows Forms

È possibile ancorare i controlli ai bordi del form oppure fare in modo che riempiano il contenitore del controllo, ovvero un form o un controllo contenitore. Esplora risorse, ad esempio, ancora il controllo <xref:System.Windows.Forms.TreeView> al lato sinistro della finestra e il relativo controllo <xref:System.Windows.Forms.ListView> sul lato destro della finestra. Usare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> per tutti i controlli Windows Forms visibili per definire la modalità di ancoraggio.

> [!NOTE]
> I controlli sono ancorati nell'ordine z inverso.

La proprietà <xref:System.Windows.Forms.Control.Dock%2A> interagisce con la proprietà <xref:System.Windows.Forms.Control.AutoSize%2A>. Per ulteriori informazioni, vedere [Panoramica delle proprietà AutoSize](autosize-property-overview.md).

## <a name="to-dock-a-control"></a>Per ancorare un controllo

1. In Visual Studio selezionare il controllo che si desidera ancorare.

2. Nella finestra **Proprietà** fare clic sulla freccia a destra della proprietà <xref:System.Windows.Forms.Control.Dock%2A>.

   Viene visualizzato un editor che mostra una serie di caselle che rappresentano i bordi e il centro del form.

3. Fare clic sul pulsante che rappresenta il bordo del form in cui si desidera ancorare il controllo. Per riempire il contenuto del form o del controllo contenitore del controllo, fare clic sulla casella al centro. Per disabilitare l'ancoraggio, fare clic su **(nessuno)** .

   Il controllo viene ridimensionato automaticamente per adattarsi ai limiti del bordo ancorato.

   > [!NOTE]
   > I controlli ereditati devono essere `Protected` per poter essere ancorati. Per modificare il livello di accesso di un controllo, impostarne la proprietà **Modifier** nella finestra **Proprietà** .

## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
- [Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Panoramica sulla proprietà AutoSize](autosize-property-overview.md)
- [Procedura: Agganciare i controlli in Windows Form](how-to-anchor-controls-on-windows-forms.md)
