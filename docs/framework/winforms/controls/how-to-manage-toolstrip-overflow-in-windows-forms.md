---
title: "Procedura: gestire l'overflow di ToolStrip"
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
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736153"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="084cf-102">Procedura: Gestire l'overflow di ToolStrip in Windows Form</span><span class="sxs-lookup"><span data-stu-id="084cf-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>

<span data-ttu-id="084cf-103">Quando tutti gli elementi di un controllo <xref:System.Windows.Forms.ToolStrip> non rientrano nello spazio allocato, è possibile abilitare la funzionalità di overflow sul <xref:System.Windows.Forms.ToolStrip> e determinare il comportamento di overflow di <xref:System.Windows.Forms.ToolStripItem>s specifici.</span><span class="sxs-lookup"><span data-stu-id="084cf-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>

<span data-ttu-id="084cf-104">Quando si aggiungono <xref:System.Windows.Forms.ToolStripItem>che richiedono più spazio rispetto a quello assegnato al <xref:System.Windows.Forms.ToolStrip> in base alle dimensioni correnti del modulo, viene visualizzato un <xref:System.Windows.Forms.ToolStripOverflowButton> automaticamente sul <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="084cf-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="084cf-105">Viene visualizzato il <xref:System.Windows.Forms.ToolStripOverflowButton> e gli elementi abilitati per l'overflow vengono spostati nel menu a discesa di overflow.</span><span class="sxs-lookup"><span data-stu-id="084cf-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="084cf-106">In questo modo è possibile personalizzare e definire le priorità per adattare correttamente gli elementi <xref:System.Windows.Forms.ToolStrip> alle dimensioni del modulo diverse.</span><span class="sxs-lookup"><span data-stu-id="084cf-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="084cf-107">È anche possibile modificare l'aspetto degli elementi quando entrano nell'overflow usando le proprietà <xref:System.Windows.Forms.ToolStripItem.Placement%2A> e <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> e l'evento <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>.</span><span class="sxs-lookup"><span data-stu-id="084cf-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="084cf-108">Se si ingrandisce il form in fase di progettazione o in fase di esecuzione, è possibile visualizzare più <xref:System.Windows.Forms.ToolStripItem>s nel <xref:System.Windows.Forms.ToolStrip> principale e il <xref:System.Windows.Forms.ToolStripOverflowButton> potrebbe persino scomparire fino a quando non si diminuiscono le dimensioni del form.</span><span class="sxs-lookup"><span data-stu-id="084cf-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>

## <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="084cf-109">Per abilitare l'overflow su un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="084cf-109">To enable overflow on a ToolStrip control</span></span>

- <span data-ttu-id="084cf-110">Verificare che la proprietà <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> non sia impostata su `false` per il <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="084cf-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="084cf-111">Il valore predefinito è `True`.</span><span class="sxs-lookup"><span data-stu-id="084cf-111">The default is `True`.</span></span>

     <span data-ttu-id="084cf-112">Quando <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> viene `True` (impostazione predefinita), viene inviato un <xref:System.Windows.Forms.ToolStripItem> al menu a discesa di overflow quando il contenuto del <xref:System.Windows.Forms.ToolStripItem> supera la larghezza di un <xref:System.Windows.Forms.ToolStrip> orizzontale o l'altezza di una <xref:System.Windows.Forms.ToolStrip>verticale.</span><span class="sxs-lookup"><span data-stu-id="084cf-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="084cf-113">Per specificare il comportamento di overflow di un oggetto ToolStripItem specifico</span><span class="sxs-lookup"><span data-stu-id="084cf-113">To specify overflow behavior of a specific ToolStripItem</span></span>

- <span data-ttu-id="084cf-114">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> del <xref:System.Windows.Forms.ToolStripItem> sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="084cf-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="084cf-115">Le possibilità sono `Always`, `Never`e `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="084cf-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="084cf-116">Il valore predefinito è `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="084cf-116">The default is `AsNeeded`.</span></span>

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a><span data-ttu-id="084cf-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="084cf-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="084cf-118">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="084cf-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="084cf-119">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="084cf-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="084cf-120">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="084cf-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
