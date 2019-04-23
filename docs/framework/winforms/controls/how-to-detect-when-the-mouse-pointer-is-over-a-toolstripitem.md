---
title: 'Procedura: Rilevare quando il puntatore del mouse si trova sopra un ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 09fd9f2f9b8cc44b6c04b829bf2854bea4aa8cf7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220046"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="5a7f6-102">Procedura: Rilevare quando il puntatore del mouse si trova sopra un ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="5a7f6-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="5a7f6-103">Usare la procedura seguente per rilevare quando il puntatore del mouse è posizionato sopra un <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="5a7f6-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="5a7f6-104">Per rilevare quando il puntatore si trova sopra un ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="5a7f6-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="5a7f6-105">Usare la <xref:System.Windows.Forms.ToolStripItem.Selected%2A> proprietà per gli elementi in cui <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="5a7f6-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="5a7f6-106">Ciò impedirà è la necessità di sincronizzare le <xref:System.Windows.Forms.ToolStripItem.MouseEnter> e <xref:System.Windows.Forms.ToolStripItem.MouseLeave> eventi.</span><span class="sxs-lookup"><span data-stu-id="5a7f6-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a7f6-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a7f6-107">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="5a7f6-108">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5a7f6-108">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
