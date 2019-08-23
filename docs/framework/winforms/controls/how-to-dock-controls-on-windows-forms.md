---
title: 'Procedura: Ancorare i controlli in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: dc514fd8b9b7a17bf07a878e42729db4187d2b82
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963620"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Procedura: Ancorare i controlli in Windows Forms
È possibile ancorare i controlli ai bordi del form oppure fare in modo che riempiano il contenitore del controllo, ovvero un form o un controllo contenitore. Ad esempio, Esplora risorse ancora <xref:System.Windows.Forms.TreeView> il controllo al lato sinistro della finestra e il relativo <xref:System.Windows.Forms.ListView> controllo sul lato destro della finestra. Usare la <xref:System.Windows.Forms.Control.Dock%2A> proprietà per tutti i controlli di Windows Forms visibili per definire la modalità di ancoraggio.  
  
> [!NOTE]
> I controlli sono ancorati nell'ordine z inverso.  
  
 La <xref:System.Windows.Forms.Control.Dock%2A> proprietà interagisce con la <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà. Per ulteriori informazioni, vedere [Panoramica delle proprietà AutoSize](autosize-property-overview.md).  
  
### <a name="to-dock-a-control"></a>Per ancorare un controllo  
  
1. Selezionare il controllo che si desidera ancorare.  
  
2. Nella finestra Proprietà fare clic sulla freccia a destra della <xref:System.Windows.Forms.Control.Dock%2A> proprietà.  
  
     Viene visualizzato un editor che mostra una serie di caselle che rappresentano i bordi e il centro del form.  
  
3. Fare clic sul pulsante che rappresenta il bordo del form in cui si desidera ancorare il controllo. Per riempire il contenuto del form o del controllo contenitore del controllo, fare clic sulla casella al centro. Per disabilitare l'ancoraggio, fare clic su **(nessuno)** .  
  
     Il controllo viene ridimensionato automaticamente per adattarsi ai limiti del bordo ancorato.  
  
    > [!NOTE]
    > I controlli ereditati `Protected` devono essere in grado di essere ancorati. Per modificare il livello di accesso di un controllo, impostarne la proprietà **Modifier** nell'finestra Proprietà.  
  
## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Disposizione di controlli in Windows Form](arranging-controls-on-windows-forms.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
- [Procedura: Ancoraggio e ancoraggio di controlli figlio in un controllo FlowLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Procedura: Ancoraggio e ancoraggio di controlli figlio in un controllo TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Panoramica sulla proprietà AutoSize](autosize-property-overview.md)
- [Procedura: Ancoraggio di controlli in Windows Forms](how-to-anchor-controls-on-windows-forms.md)
