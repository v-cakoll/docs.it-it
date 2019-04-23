---
title: 'Procedura: Abilitare il riordino di elementi ToolStrip in fase di esecuzione in Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: daff9d6d351db514d552225853f977775f8e3204
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220405"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="30a68-102">Procedura: Abilitare il riordino di elementi ToolStrip in fase di esecuzione in Windows Form</span><span class="sxs-lookup"><span data-stu-id="30a68-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="30a68-103">È possibile consentire all'utente di riordinare <xref:System.Windows.Forms.ToolStripItem> ai controlli di <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="30a68-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="30a68-104">Per abilitare il riordino di ToolStripItem in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="30a68-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
-   <span data-ttu-id="30a68-105">Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="30a68-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="30a68-106">Per impostazione predefinita <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="30a68-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="30a68-107">In fase di esecuzione, l'utente tiene premuto il tasto ALT e il pulsante sinistro del mouse per trascinare un <xref:System.Windows.Forms.ToolStripItem> in una posizione diversa sul <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="30a68-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="30a68-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30a68-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [<span data-ttu-id="30a68-109">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="30a68-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="30a68-110">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="30a68-110">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="30a68-111">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="30a68-111">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
