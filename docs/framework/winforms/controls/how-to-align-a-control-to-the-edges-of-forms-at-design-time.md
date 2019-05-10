---
title: 'Procedura: Allineare un controllo ai bordi dei moduli in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: b08e01eb9adb984a32a8fc435cf1f3b93b159a14
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210373"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a>Procedura: Allineare un controllo ai bordi dei moduli in fase di progettazione

È possibile allineare un controllo per il bordo dei form impostando il valore della <xref:System.Windows.Forms.Control.Dock%2A> proprietà. che designa la posizione del controllo nel form. La proprietà <xref:System.Windows.Forms.Control.Dock%2A> può essere impostata su uno dei valori riportati di seguito:

|Impostazione|Effetto sul controllo|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|Il controllo viene ancorato alla parte inferiore del form.|
|<xref:System.Windows.Forms.DockStyle.Fill>|Il controllo occupa tutto lo spazio rimanente nel form.|
|<xref:System.Windows.Forms.DockStyle.Left>|Il controllo viene ancorato al lato sinistro del form.|
|<xref:System.Windows.Forms.DockStyle.None>|Non viene ancorato e viene visualizzato nella posizione specificata dal relativo <xref:System.Windows.Forms.Control.Location%2A>.|
|<xref:System.Windows.Forms.DockStyle.Right>|Il controllo viene ancorato al lato destro del form.|
|<xref:System.Windows.Forms.DockStyle.Top>|Il controllo viene ancorato alla parte superiore del form.|

Questi valori possono anche essere impostati nel codice. Per altre informazioni, vedere [Procedura: Allineare un controllo ai bordi dei form](how-to-align-a-control-to-the-edges-of-forms.md).

## <a name="set-the-dock-property-for-your-control-at-design-time"></a>Impostare la proprietà Dock del controllo in fase di progettazione

1. In Progettazione Windows Form in Visual Studio, selezionare il controllo.

2. Nel **delle proprietà** fare clic sulla casella di elenco a discesa accanto al <xref:System.Windows.Forms.Control.Dock%2A> proprietà.

     Un'interfaccia grafica che rappresenta le sei possibili <xref:System.Windows.Forms.Control.Dock%2A> impostazioni viene visualizzata.

3. Scegliere l'impostazione appropriata.

4. Il controllo verrà ancorato nel modo specificato dall'impostazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [Procedura: Allineare un controllo ai bordi dei form](how-to-align-a-control-to-the-edges-of-forms.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Procedura: Ancoraggio dei controlli in Windows Form](how-to-anchor-controls-on-windows-forms.md)
- [Procedura: Ancorare e agganciare controlli figlio in un controllo TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md)
