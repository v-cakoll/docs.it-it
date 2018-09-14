---
title: 'Procedura: allineare un controllo ai bordi dei form in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: 513029c1bd5cc4af52fcee97f7fab961729e613c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45597602"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a>Procedura: allineare un controllo ai bordi dei form in fase di progettazione
È possibile allineare un controllo per il bordo dei form impostando la <xref:System.Windows.Forms.Control.Dock%2A>. che designa la posizione del controllo nel form. La proprietà <xref:System.Windows.Forms.Control.Dock%2A> può essere impostata su uno dei valori riportati di seguito:  
  
|Impostazione|Effetto sul controllo|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|Il controllo viene ancorato alla parte inferiore del form.|  
|<xref:System.Windows.Forms.DockStyle.Fill>|Il controllo occupa tutto lo spazio rimanente nel form.|  
|<xref:System.Windows.Forms.DockStyle.Left>|Il controllo viene ancorato al lato sinistro del form.|  
|<xref:System.Windows.Forms.DockStyle.None>|Non viene ancorato e viene visualizzato nella posizione specificata dal relativo <xref:System.Windows.Forms.Control.Location%2A>.|  
|<xref:System.Windows.Forms.DockStyle.Right>|Il controllo viene ancorato al lato destro del form.|  
|<xref:System.Windows.Forms.DockStyle.Top>|Il controllo viene ancorato alla parte superiore del form.|  
  
 Questi valori possono anche essere impostati nel codice. Per altre informazioni, vedere [procedura: allineare un controllo ai bordi dei form](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-the-dock-property-for-your-control-at-design-time"></a>Per impostare la proprietà Dock del controllo in fase di progettazione  
  
1.  Nella finestra di progettazione Windows Form, selezionare il controllo.  
  
2.  Nel **delle proprietà** fare clic sulla casella di elenco a discesa accanto al <xref:System.Windows.Forms.Control.Dock%2A> proprietà.  
  
     Un'interfaccia grafica che rappresenta le sei possibili <xref:System.Windows.Forms.Control.Dock%2A> impostazioni viene visualizzata.  
  
3.  Scegliere l'impostazione appropriata.  
  
4.  Il controllo verrà ancorato nel modo specificato dall'impostazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>  
 [Procedura: Allineare un controllo ai bordi dei form](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)  
 [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Procedura: Agganciare i controlli in Windows Form](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)  
 [Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Sviluppo di controlli Windows Form in fase di progettazione](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
