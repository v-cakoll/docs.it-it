---
title: "Procedura: modificare la spaziatura e l'allineamento degli elementi ToolStrip"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 805fbac5fe33071006f29692d503e5c57eacd765
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746554"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="eb0e5-102">Procedura: Modificare la spaziatura e l'allineamento degli elementi ToolStrip in Windows Form</span><span class="sxs-lookup"><span data-stu-id="eb0e5-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="eb0e5-103">Il controllo <xref:System.Windows.Forms.ToolStrip> supporta completamente le funzionalità di layout, ad esempio il ridimensionamento, la spaziatura dei controlli <xref:System.Windows.Forms.ToolStripItem> relativi tra loro, la disposizione dei controlli sul <xref:System.Windows.Forms.ToolStrip>e la spaziatura dei controlli relativi alla <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="eb0e5-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="eb0e5-104">Poiché il valore predefinito della proprietà <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> è `true`, i controlli vengono ridimensionati automaticamente a meno che non si imposti la proprietà <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="eb0e5-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="eb0e5-105">Per ridimensionare manualmente un oggetto ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="eb0e5-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="eb0e5-106">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> su `false` per il controllo associato.</span><span class="sxs-lookup"><span data-stu-id="eb0e5-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="eb0e5-107">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Size%2A> nel modo desiderato per il <xref:System.Windows.Forms.ToolStripItem>associato.</span><span class="sxs-lookup"><span data-stu-id="eb0e5-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="eb0e5-108">Per impostare la spaziatura di un oggetto ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="eb0e5-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="eb0e5-109">Inserire i valori desiderati, in pixel, nella proprietà <xref:System.Windows.Forms.ToolStripItem.Margin%2A> del controllo associato.</span><span class="sxs-lookup"><span data-stu-id="eb0e5-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="eb0e5-110">I valori della proprietà <xref:System.Windows.Forms.ToolStripItem.Margin%2A> specificano la spaziatura tra l'elemento e gli elementi adiacenti in questo ordine: Left, top, Right e Bottom.</span><span class="sxs-lookup"><span data-stu-id="eb0e5-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="eb0e5-111">Per allineare un oggetto ToolStripItem al lato destro di ToolStrip</span><span class="sxs-lookup"><span data-stu-id="eb0e5-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="eb0e5-112">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> su <xref:System.Windows.Forms.ToolStripItemAlignment.Right> per il controllo associato.</span><span class="sxs-lookup"><span data-stu-id="eb0e5-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="eb0e5-113">Per impostazione predefinita, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> è impostato su <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, che allinea i controlli al lato sinistro della <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="eb0e5-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="eb0e5-114">Per disporre gli elementi ToolStrip in ToolStrip</span><span class="sxs-lookup"><span data-stu-id="eb0e5-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="eb0e5-115">Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> sul valore di <xref:System.Windows.Forms.ToolStripLayoutStyle> desiderato.</span><span class="sxs-lookup"><span data-stu-id="eb0e5-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eb0e5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb0e5-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="eb0e5-117">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="eb0e5-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="eb0e5-118">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="eb0e5-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="eb0e5-119">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="eb0e5-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
