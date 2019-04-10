---
title: 'Procedura: Allineare un controllo ai bordi dei moduli'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
ms.openlocfilehash: beb8881dbd2aedaefe66510c2942ce6c082b9729
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329973"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a>Procedura: Allineare un controllo ai bordi dei moduli
È possibile allineare un controllo al bordo dei form impostando la proprietà <xref:System.Windows.Forms.Control.Dock%2A> che designa la posizione del controllo nel form. La proprietà <xref:System.Windows.Forms.Control.Dock%2A> può essere impostata su uno dei valori riportati di seguito:  
  
|Impostazione|Effetto sul controllo|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|Il controllo viene ancorato alla parte inferiore del form.|  
|<xref:System.Windows.Forms.DockStyle.Fill>|Il controllo occupa tutto lo spazio rimanente nel form.|  
|<xref:System.Windows.Forms.DockStyle.Left>|Il controllo viene ancorato al lato sinistro del form.|  
|<xref:System.Windows.Forms.DockStyle.None>|Il controllo non viene ancorato e viene visualizzato nella posizione specificata dalla relativa proprietà <xref:System.Windows.Forms.Control.Location%2A>.|  
|<xref:System.Windows.Forms.DockStyle.Right>|Il controllo viene ancorato al lato destro del form.|  
|<xref:System.Windows.Forms.DockStyle.Top>|Il controllo viene ancorato alla parte superiore del form.|  
  
 È disponibile supporto in fase di progettazione per questa funzionalità in Visual Studio.  
  
### <a name="to-set-the-dock-property-for-your-control-at-run-time"></a>Per impostare la proprietà Dock del controllo in fase di esecuzione  
  
1. Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> sul valore appropriato nel codice.  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [Sviluppo di controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)
- [Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Procedura: Ancorare e agganciare controlli figlio in un controllo TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Cenni preliminari sulla proprietà AutoSize](autosize-property-overview.md)
