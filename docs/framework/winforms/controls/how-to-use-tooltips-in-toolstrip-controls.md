---
title: 'Procedura: Usare le descrizioni comando nei controlli ToolStrip'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: ffaf859fafc87131de525f7bf2f52db421a208c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316999"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>Procedura: Usare le descrizioni comando nei controlli ToolStrip
È possibile visualizzare un <xref:System.Windows.Forms.ToolTip> per il <xref:System.Windows.Forms.ToolStrip> controllo mediante l'impostazione del controllo cui si desidera <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà `true`.  
  
### <a name="to-display-a-tooltip"></a>Per visualizzare una descrizione comando  
  
-   Impostare il <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del controllo da `true`.  
  
     Il valore predefinito <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> viene `true`e il valore predefinito <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> è `false`.  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>Usare la proprietà ToolTipText per il testo della descrizione comando di un oggetto ToolStripButton  
  
1. Impostare il <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del pulsante su `true`.  
  
2. Impostare il <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> proprietà del pulsante su `false`.  
  
     Il `AutoToolTip` proprietà viene `true` per impostazione predefinita <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, e <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
     Oggetto <xref:System.Windows.Forms.ToolStripButton> Usa relativi `Text` proprietà per il <xref:System.Windows.Forms.ToolTip> testo per impostazione predefinita. Utilizzare questa procedura per visualizzare il testo personalizzato in un <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>.  
  
> [!NOTE]
>  Se si imposta <xref:System.Windows.Forms.ToolStripItemDisplayStyle> al <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, verrà visualizzato alcun testo sul pulsante, ma viene comunque visualizzata la descrizione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [Panoramica sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
