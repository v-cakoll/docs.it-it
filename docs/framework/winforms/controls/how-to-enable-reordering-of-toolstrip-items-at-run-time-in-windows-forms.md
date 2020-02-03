---
title: 'Procedura: abilitare il riordino di elementi ToolStrip in fase di esecuzione'
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
ms.openlocfilehash: 44b52bf997819f090569d08eb395d8af18f61370
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745481"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="d5645-102">Procedura: Abilitare il riordino degli elementi di ToolStrip in fase di esecuzione in Windows Form</span><span class="sxs-lookup"><span data-stu-id="d5645-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="d5645-103">È possibile consentire all'utente di ridisporre i controlli <xref:System.Windows.Forms.ToolStripItem> nel <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="d5645-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="d5645-104">Per abilitare la riorganizzazione di ToolStripItem in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="d5645-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
- <span data-ttu-id="d5645-105">Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="d5645-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="d5645-106">Per impostazione predefinita, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="d5645-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="d5645-107">In fase di esecuzione, l'utente deve tenere premuto il tasto ALT e il pulsante sinistro del mouse per trascinare un <xref:System.Windows.Forms.ToolStripItem> in un percorso diverso nel <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="d5645-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d5645-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5645-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [<span data-ttu-id="d5645-109">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d5645-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="d5645-110">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d5645-110">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="d5645-111">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d5645-111">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
