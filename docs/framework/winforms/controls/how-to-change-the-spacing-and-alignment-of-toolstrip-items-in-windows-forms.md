---
title: "Procedura: modificare la spaziatura e l'allineamento degli elementi ToolStrip in Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 7951a545fd8cbd0ae30907922551216161171a8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531264"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="c0396-102">Procedura: modificare la spaziatura e l'allineamento degli elementi ToolStrip in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c0396-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="c0396-103">Il <xref:System.Windows.Forms.ToolStrip> controllo supporta pienamente le funzionalità di layout, ad esempio il ridimensionamento, la spaziatura di <xref:System.Windows.Forms.ToolStripItem> ai controlli reciprocamente, la disposizione dei controlli il <xref:System.Windows.Forms.ToolStrip>e la spaziatura tra i controlli rispetto al <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="c0396-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="c0396-104">Poiché il valore predefinito del <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> proprietà è `true`, i controlli vengono ridimensionati automaticamente a meno che non si imposta la <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="c0396-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="c0396-105">Per ridimensionare manualmente un ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="c0396-105">To manually size a ToolStripItem</span></span>  
  
1.  <span data-ttu-id="c0396-106">Impostare il <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> proprietà `false` per il controllo associato.</span><span class="sxs-lookup"><span data-stu-id="c0396-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2.  <span data-ttu-id="c0396-107">Impostare il <xref:System.Windows.Forms.ToolStripItem.Size%2A> proprietà nel modo desiderato per la proprietà associata <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="c0396-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="c0396-108">Per impostare la spaziatura di un controllo ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="c0396-108">To set the spacing of a ToolStripItem</span></span>  
  
1.  <span data-ttu-id="c0396-109">Inserire i valori desiderati, in pixel, di <xref:System.Windows.Forms.ToolStripItem.Margin%2A> proprietà del controllo associato.</span><span class="sxs-lookup"><span data-stu-id="c0396-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="c0396-110">I valori del <xref:System.Windows.Forms.ToolStripItem.Margin%2A> proprietà specificare la spaziatura tra l'elemento e gli elementi adiacenti nell'ordine indicato: sinistro, superiore, destro e inferiore.</span><span class="sxs-lookup"><span data-stu-id="c0396-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="c0396-111">Per allineare un controllo ToolStripItem sul lato destro dell'oggetto ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c0396-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1.  <span data-ttu-id="c0396-112">Impostare il <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> proprietà <xref:System.Windows.Forms.ToolStripItemAlignment.Right> per il controllo associato.</span><span class="sxs-lookup"><span data-stu-id="c0396-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="c0396-113">Per impostazione predefinita, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> è impostato su <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, quali controlli sono allineati a sinistra del <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="c0396-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="c0396-114">Per disporre gli elementi di ToolStrip di ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c0396-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
-   <span data-ttu-id="c0396-115">Impostare il <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> il valore di proprietà <xref:System.Windows.Forms.ToolStripLayoutStyle> desiderati.</span><span class="sxs-lookup"><span data-stu-id="c0396-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c0396-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0396-116">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.Layout>  
 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>  
 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>  
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Placement%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [<span data-ttu-id="c0396-117">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c0396-117">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="c0396-118">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c0396-118">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="c0396-119">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c0396-119">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
