---
title: 'Procedura: utilizzare descrizioni comandi nei controlli ToolStrip'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 2b10b3fcf3930d5848f1d7a9602cfcc945bc8975
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534073"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="7b67c-102">Procedura: utilizzare descrizioni comandi nei controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7b67c-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="7b67c-103">È possibile visualizzare un <xref:System.Windows.Forms.ToolTip> per il <xref:System.Windows.Forms.ToolStrip> controllo impostando il controllo di cui si desidera <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="7b67c-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="7b67c-104">Per visualizzare una descrizione</span><span class="sxs-lookup"><span data-stu-id="7b67c-104">To display a ToolTip</span></span>  
  
-   <span data-ttu-id="7b67c-105">Impostare il <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del controllo da `true`.</span><span class="sxs-lookup"><span data-stu-id="7b67c-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="7b67c-106">Il valore predefinito di <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> è `true`e il valore predefinito di <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> è `false`.</span><span class="sxs-lookup"><span data-stu-id="7b67c-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="7b67c-107">Utilizzare la proprietà ToolTipText per il testo della descrizione di un oggetto di ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="7b67c-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1.  <span data-ttu-id="7b67c-108">Impostare il <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del pulsante su `true`.</span><span class="sxs-lookup"><span data-stu-id="7b67c-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2.  <span data-ttu-id="7b67c-109">Impostare il <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> proprietà del pulsante su `false`.</span><span class="sxs-lookup"><span data-stu-id="7b67c-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="7b67c-110">Il `AutoToolTip` proprietà `true` per impostazione predefinita per <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, e <xref:System.Windows.Forms.ToolStripSplitButton>.</span><span class="sxs-lookup"><span data-stu-id="7b67c-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="7b67c-111">Oggetto <xref:System.Windows.Forms.ToolStripButton> utilizza relativo `Text` proprietà per il <xref:System.Windows.Forms.ToolTip> testo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7b67c-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="7b67c-112">Utilizzare questa procedura per visualizzare il testo personalizzato in un <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="7b67c-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b67c-113">Se si imposta <xref:System.Windows.Forms.ToolStripItemDisplayStyle> a <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, sul pulsante verrà visualizzato alcun testo, ma verrà comunque visualizzata la descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="7b67c-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b67c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b67c-114">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>  
 <xref:System.Windows.Forms.ToolStripButton>  
 <xref:System.Windows.Forms.ToolStripDropDownButton>  
 <xref:System.Windows.Forms.ToolStripSplitButton>  
 [<span data-ttu-id="7b67c-115">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7b67c-115">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
