---
title: 'Procedura: Usare le descrizioni comando nei controlli ToolStrip'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 3f383b6cccba7825637ea65a0e13280b91b406c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939738"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>Procedura: Usare le descrizioni comando nei controlli ToolStrip
È possibile visualizzare un <xref:System.Windows.Forms.ToolTip> oggetto per <xref:System.Windows.Forms.ToolStrip> il controllo desiderato impostando la <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del controllo su `true`.  
  
### <a name="to-display-a-tooltip"></a>Per visualizzare una descrizione comando  
  
- Impostare la <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del controllo su `true`.  
  
     Il valore predefinito di <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> è `true`e il valore predefinito di <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> è `false`.  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>Per utilizzare la proprietà ToolTipText per il testo della descrizione comando di un oggetto ToolStripButton  
  
1. Impostare la <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del pulsante su `true`.  
  
2. Impostare la <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> proprietà del pulsante su `false`.  
  
     Per `AutoToolTip` impostazione predefinita `true` , la proprietà <xref:System.Windows.Forms.ToolStripButton>è <xref:System.Windows.Forms.ToolStripDropDownButton>per, <xref:System.Windows.Forms.ToolStripSplitButton>e.  
  
     Per impostazione predefinita `Text` , <xref:System.Windows.Forms.ToolTip> usa la proprietà per il testo. <xref:System.Windows.Forms.ToolStripButton> Usare questa procedura per visualizzare il testo personalizzato in <xref:System.Windows.Forms.ToolStripButton>un oggetto. <xref:System.Windows.Forms.ToolTip>  
  
> [!NOTE]
> Se si imposta <xref:System.Windows.Forms.ToolStripItemDisplayStyle> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> su o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, non verrà visualizzato alcun testo sul pulsante, ma verrà ancora visualizzata la descrizione comando.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [Panoramica sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
