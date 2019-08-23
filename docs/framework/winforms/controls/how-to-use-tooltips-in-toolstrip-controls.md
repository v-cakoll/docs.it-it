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
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="66755-102">Procedura: Usare le descrizioni comando nei controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="66755-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="66755-103">È possibile visualizzare un <xref:System.Windows.Forms.ToolTip> oggetto per <xref:System.Windows.Forms.ToolStrip> il controllo desiderato impostando la <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del controllo su `true`.</span><span class="sxs-lookup"><span data-stu-id="66755-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="66755-104">Per visualizzare una descrizione comando</span><span class="sxs-lookup"><span data-stu-id="66755-104">To display a ToolTip</span></span>  
  
- <span data-ttu-id="66755-105">Impostare la <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del controllo su `true`.</span><span class="sxs-lookup"><span data-stu-id="66755-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="66755-106">Il valore predefinito di <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> è `true`e il valore predefinito di <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> è `false`.</span><span class="sxs-lookup"><span data-stu-id="66755-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="66755-107">Per utilizzare la proprietà ToolTipText per il testo della descrizione comando di un oggetto ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="66755-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1. <span data-ttu-id="66755-108">Impostare la <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del pulsante su `true`.</span><span class="sxs-lookup"><span data-stu-id="66755-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2. <span data-ttu-id="66755-109">Impostare la <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> proprietà del pulsante su `false`.</span><span class="sxs-lookup"><span data-stu-id="66755-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="66755-110">Per `AutoToolTip` impostazione predefinita `true` , la proprietà <xref:System.Windows.Forms.ToolStripButton>è <xref:System.Windows.Forms.ToolStripDropDownButton>per, <xref:System.Windows.Forms.ToolStripSplitButton>e.</span><span class="sxs-lookup"><span data-stu-id="66755-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="66755-111">Per impostazione predefinita `Text` , <xref:System.Windows.Forms.ToolTip> usa la proprietà per il testo. <xref:System.Windows.Forms.ToolStripButton></span><span class="sxs-lookup"><span data-stu-id="66755-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="66755-112">Usare questa procedura per visualizzare il testo personalizzato in <xref:System.Windows.Forms.ToolStripButton>un oggetto. <xref:System.Windows.Forms.ToolTip></span><span class="sxs-lookup"><span data-stu-id="66755-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66755-113">Se si imposta <xref:System.Windows.Forms.ToolStripItemDisplayStyle> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> su o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, non verrà visualizzato alcun testo sul pulsante, ma verrà ancora visualizzata la descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="66755-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66755-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66755-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="66755-115">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="66755-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
