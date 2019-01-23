---
title: 'Procedura: Utilizzare le descrizioni comandi nei controlli ToolStrip'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 60d024dcb023b3d6cfafb68263291acefb38e14a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519164"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="dc6d5-102">Procedura: Utilizzare le descrizioni comandi nei controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="dc6d5-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="dc6d5-103">È possibile visualizzare un <xref:System.Windows.Forms.ToolTip> per il <xref:System.Windows.Forms.ToolStrip> controllo mediante l'impostazione del controllo cui si desidera <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="dc6d5-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="dc6d5-104">Per visualizzare una descrizione comando</span><span class="sxs-lookup"><span data-stu-id="dc6d5-104">To display a ToolTip</span></span>  
  
-   <span data-ttu-id="dc6d5-105">Impostare il <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del controllo da `true`.</span><span class="sxs-lookup"><span data-stu-id="dc6d5-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="dc6d5-106">Il valore predefinito <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> viene `true`e il valore predefinito <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> è `false`.</span><span class="sxs-lookup"><span data-stu-id="dc6d5-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="dc6d5-107">Usare la proprietà ToolTipText per il testo della descrizione comando di un oggetto ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="dc6d5-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1.  <span data-ttu-id="dc6d5-108">Impostare il <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del pulsante su `true`.</span><span class="sxs-lookup"><span data-stu-id="dc6d5-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2.  <span data-ttu-id="dc6d5-109">Impostare il <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> proprietà del pulsante su `false`.</span><span class="sxs-lookup"><span data-stu-id="dc6d5-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="dc6d5-110">Il `AutoToolTip` proprietà viene `true` per impostazione predefinita <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, e <xref:System.Windows.Forms.ToolStripSplitButton>.</span><span class="sxs-lookup"><span data-stu-id="dc6d5-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="dc6d5-111">Oggetto <xref:System.Windows.Forms.ToolStripButton> Usa relativi `Text` proprietà per il <xref:System.Windows.Forms.ToolTip> testo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="dc6d5-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="dc6d5-112">Utilizzare questa procedura per visualizzare il testo personalizzato in un <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="dc6d5-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc6d5-113">Se si imposta <xref:System.Windows.Forms.ToolStripItemDisplayStyle> al <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, verrà visualizzato alcun testo sul pulsante, ma viene comunque visualizzata la descrizione.</span><span class="sxs-lookup"><span data-stu-id="dc6d5-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6d5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc6d5-114">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="dc6d5-115">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="dc6d5-115">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
