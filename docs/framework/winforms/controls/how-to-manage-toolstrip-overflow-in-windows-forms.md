---
title: 'Procedura: gestire l''overflow di ToolStrip in Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b1ae4172dbdf82b4bd5bdd9a7f8afc1901fcfa3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="4e035-102">Procedura: gestire l'overflow di ToolStrip in Windows Form</span><span class="sxs-lookup"><span data-stu-id="4e035-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>
<span data-ttu-id="4e035-103">Quando tutti gli elementi in un <xref:System.Windows.Forms.ToolStrip> controllo non rientrano nello spazio disponibile, è possibile abilitare la funzionalità di overflow nel <xref:System.Windows.Forms.ToolStrip> e determinare il comportamento di overflow di specifico <xref:System.Windows.Forms.ToolStripItem>s.</span><span class="sxs-lookup"><span data-stu-id="4e035-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>  
  
 <span data-ttu-id="4e035-104">Quando si aggiungono <xref:System.Windows.Forms.ToolStripItem>che richiedono più spazio rispetto a cui è consentita per il <xref:System.Windows.Forms.ToolStrip> dimensioni correnti del form, un <xref:System.Windows.Forms.ToolStripOverflowButton> viene visualizzato automaticamente nella <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="4e035-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="4e035-105">Il <xref:System.Windows.Forms.ToolStripOverflowButton> viene visualizzato, e l'overflow abilitato elementi vengono spostati nel menu di overflow di riepilogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="4e035-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="4e035-106">Ciò consente di personalizzare e assegnare priorità come il <xref:System.Windows.Forms.ToolStrip> elementi regolati correttamente alle dimensioni del modulo diverso.</span><span class="sxs-lookup"><span data-stu-id="4e035-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="4e035-107">È inoltre possibile modificare l'aspetto degli elementi quando incorrono l'overflow utilizzando la <xref:System.Windows.Forms.ToolStripItem.Placement%2A> e <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> proprietà e <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="4e035-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="4e035-108">Se si ingrandisce il form in fase di progettazione o in fase di esecuzione più <xref:System.Windows.Forms.ToolStripItem>s possono essere visualizzati nella principale <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.ToolStripOverflowButton> potrebbero scomparire anche fino a quando le dimensioni del form.</span><span class="sxs-lookup"><span data-stu-id="4e035-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>  
  
### <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="4e035-109">Per attivare l'overflow in un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4e035-109">To enable overflow on a ToolStrip control</span></span>  
  
-   <span data-ttu-id="4e035-110">Verificare che il <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> proprietà non è impostata su `false` per il <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="4e035-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="4e035-111">Il valore predefinito è `True`.</span><span class="sxs-lookup"><span data-stu-id="4e035-111">The default is `True`.</span></span>  
  
     <span data-ttu-id="4e035-112">Quando <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> è `True` (impostazione predefinita), un <xref:System.Windows.Forms.ToolStripItem> viene inviato al menu di overflow di riepilogo a discesa quando il contenuto del <xref:System.Windows.Forms.ToolStripItem> supera la larghezza di un controllo orizzontale <xref:System.Windows.Forms.ToolStrip> o l'altezza di un controllo verticale <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="4e035-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="4e035-113">Per specificare il comportamento di overflow di un controllo specifico ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="4e035-113">To specify overflow behavior of a specific ToolStripItem</span></span>  
  
-   <span data-ttu-id="4e035-114">Impostare il <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> proprietà del <xref:System.Windows.Forms.ToolStripItem> sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="4e035-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="4e035-115">I valori possibili sono `Always`, `Never`, e `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="4e035-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="4e035-116">Il defaultis `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="4e035-116">The defaultis `AsNeeded`.</span></span>  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4e035-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e035-117">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripOverflowButton>  
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [<span data-ttu-id="4e035-118">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4e035-118">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="4e035-119">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4e035-119">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="4e035-120">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4e035-120">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
