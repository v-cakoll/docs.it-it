---
title: "Procedura: Gestire l'Overflow di ToolStrip in Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 5f26217c92aef1d568349aefb87dd5a882a0cf28
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541157"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>Procedura: Gestire l'Overflow di ToolStrip in Windows Form
Quando tutti gli elementi in un <xref:System.Windows.Forms.ToolStrip> controllo non rientrano nello spazio disponibile, è possibile abilitare la funzionalità di overflow nel <xref:System.Windows.Forms.ToolStrip> e determinare il comportamento di overflow di specifico <xref:System.Windows.Forms.ToolStripItem>s.  
  
 Quando si aggiungono <xref:System.Windows.Forms.ToolStripItem>che richiedono più spazio di quello assegnato al <xref:System.Windows.Forms.ToolStrip> dimensioni correnti del form, un <xref:System.Windows.Forms.ToolStripOverflowButton> viene visualizzato automaticamente nella <xref:System.Windows.Forms.ToolStrip>. Il <xref:System.Windows.Forms.ToolStripOverflowButton> viene visualizzata, gli elementi di overflow abilitato vengono spostati nel menu di overflow di elenco a discesa. In questo modo è possibile personalizzare e definire le priorità come il <xref:System.Windows.Forms.ToolStrip> elementi adattano alle dimensioni di forma diversi. È anche possibile modificare l'aspetto degli elementi quando rientrano l'overflow utilizzando la <xref:System.Windows.Forms.ToolStripItem.Placement%2A> e <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> delle proprietà e il <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento. Se si ingrandisce il form in fase di progettazione o in fase di esecuzione più <xref:System.Windows.Forms.ToolStripItem>s possono essere visualizzati sul principale <xref:System.Windows.Forms.ToolStrip> e il <xref:System.Windows.Forms.ToolStripOverflowButton> potrebbero scomparire anche fino a quando non è ridurre le dimensioni del form.  
  
### <a name="to-enable-overflow-on-a-toolstrip-control"></a>Per attivare l'overflow in un controllo ToolStrip  
  
-   Verificare che il <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> proprietà non è impostata su `false` per il <xref:System.Windows.Forms.ToolStrip>. Il valore predefinito è `True`.  
  
     Quando <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> viene `True` (impostazione predefinita), un <xref:System.Windows.Forms.ToolStripItem> viene inviato al menu di overflow di elenco a discesa quando il contenuto del <xref:System.Windows.Forms.ToolStripItem> supera la larghezza di un controllo orizzontale <xref:System.Windows.Forms.ToolStrip> o l'altezza di un parametro vertical <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>Per specificare il comportamento di overflow di un oggetto ToolStripItem specifico  
  
-   Impostare il <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> proprietà del <xref:System.Windows.Forms.ToolStripItem> sul valore desiderato. I valori possibili sono `Always`, `Never`, e `AsNeeded`. Il defaultis `AsNeeded`.  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
    ```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [Panoramica sul controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
