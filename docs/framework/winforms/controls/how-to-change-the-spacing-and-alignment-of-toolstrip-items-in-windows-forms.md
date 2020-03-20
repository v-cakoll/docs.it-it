---
title: "Procedura: modificare la spaziatura e l'allineamento degli elementi ToolStripHow to: Change the Spacing and Alignment of ToolStrip Items"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182234"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="adb2d-102">Procedura: modificare la spaziatura e l'allineamento degli elementi ToolStrip in Windows Form</span><span class="sxs-lookup"><span data-stu-id="adb2d-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="adb2d-103">Il <xref:System.Windows.Forms.ToolStrip> controllo supporta completamente le funzionalità di layout, ad esempio il ridimensionamento, la spaziatura dei <xref:System.Windows.Forms.ToolStripItem> controlli l'uno rispetto all'altro, la disposizione dei controlli in <xref:System.Windows.Forms.ToolStrip>, e la spaziatura dei controlli rispetto a <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="adb2d-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="adb2d-104">Poiché il valore <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> predefinito `true`della proprietà è , <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> i `false`controlli vengono ridimensionati automaticamente a meno che non si imposti la proprietà su .</span><span class="sxs-lookup"><span data-stu-id="adb2d-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="adb2d-105">Per ridimensionare manualmente un ToolStripItemTo manually size a ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="adb2d-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="adb2d-106">Impostare <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> la `false` proprietà su per il controllo associato.</span><span class="sxs-lookup"><span data-stu-id="adb2d-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="adb2d-107">Impostare <xref:System.Windows.Forms.ToolStripItem.Size%2A> la proprietà nel modo <xref:System.Windows.Forms.ToolStripItem>desiderato per l'oggetto associato.</span><span class="sxs-lookup"><span data-stu-id="adb2d-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="adb2d-108">Per impostare la spaziatura di un ToolStripItemTo set the spacing of a ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="adb2d-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="adb2d-109">Inserire i valori desiderati, in <xref:System.Windows.Forms.ToolStripItem.Margin%2A> pixel, nella proprietà del controllo associato.</span><span class="sxs-lookup"><span data-stu-id="adb2d-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="adb2d-110">I valori <xref:System.Windows.Forms.ToolStripItem.Margin%2A> della proprietà specificano la spaziatura tra l'elemento e gli elementi adiacenti nell'ordine seguente: Left, Top, Right e Bottom.</span><span class="sxs-lookup"><span data-stu-id="adb2d-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="adb2d-111">To align a ToolStripItem to the right side of the ToolStrip</span><span class="sxs-lookup"><span data-stu-id="adb2d-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="adb2d-112">Impostare <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> la <xref:System.Windows.Forms.ToolStripItemAlignment.Right> proprietà su per il controllo associato.</span><span class="sxs-lookup"><span data-stu-id="adb2d-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="adb2d-113">Per impostazione predefinita, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> è impostato su <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, che <xref:System.Windows.Forms.ToolStrip>allinea i controlli al lato sinistro del file .</span><span class="sxs-lookup"><span data-stu-id="adb2d-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="adb2d-114">Per disporre gli elementi ToolStrip in ToolStripTo arrange ToolStrip items on the ToolStrip</span><span class="sxs-lookup"><span data-stu-id="adb2d-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="adb2d-115">Impostare <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> la proprietà <xref:System.Windows.Forms.ToolStripLayoutStyle> sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="adb2d-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="adb2d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adb2d-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="adb2d-117">Cenni preliminari sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="adb2d-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="adb2d-118">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="adb2d-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="adb2d-119">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="adb2d-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
