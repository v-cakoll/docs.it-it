---
title: Layout di controlli Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windows Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
ms.openlocfilehash: a184eea8fd6804848cf7dfa324ef1430746ff7e9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503294"
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="f206e-102">Layout di controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="f206e-102">Layout in Windows Forms Controls</span></span>

<span data-ttu-id="f206e-103">Per molte applicazioni è estremamente importante la sistemazione precisa dei controlli nel form.</span><span class="sxs-lookup"><span data-stu-id="f206e-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="f206e-104">Il <xref:System.Windows.Forms?displayProperty=nameWithType> dello spazio dei nomi offre molti strumenti di layout per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="f206e-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f206e-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="f206e-105">In This Section</span></span>

<span data-ttu-id="f206e-106">[Cenni preliminari sulle proprietà AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)\\</span><span class="sxs-lookup"><span data-stu-id="f206e-106">[AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md)\\</span></span>
<span data-ttu-id="f206e-107">Viene descritto il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà e il suo ruolo nel layout.</span><span class="sxs-lookup"><span data-stu-id="f206e-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>

<span data-ttu-id="f206e-108">[Margini e spaziatura nei controlli Windows Form](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)\\</span><span class="sxs-lookup"><span data-stu-id="f206e-108">[Margin and Padding in Windows Forms Controls](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)\\</span></span>
<span data-ttu-id="f206e-109">Descrive la <xref:System.Windows.Forms.Control.Margin%2A> e <xref:System.Windows.Forms.Control.Padding%2A> proprietà e i relativi ruoli nel layout.</span><span class="sxs-lookup"><span data-stu-id="f206e-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>

<span data-ttu-id="f206e-110">[Procedura: Allineare un controllo ai bordi dei form](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="f206e-110">[How to: Align a Control to the Edges of Forms](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)\\</span></span>
<span data-ttu-id="f206e-111">Viene illustrato come utilizzare il <xref:System.Windows.Forms.Control.Dock%2A> proprietà per allineare il controllo al bordo del form occupato.</span><span class="sxs-lookup"><span data-stu-id="f206e-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="f206e-112">[Procedura: Creare un bordo intorno a un controllo Windows Form usando il riempimento di controllo](../../../../docs/framework/winforms/controls/how-to-create-a-border-around-a-windows-forms-control-using-padding.md)\\</span><span class="sxs-lookup"><span data-stu-id="f206e-112">[How to: Create a Border Around a Windows Forms Control Using Padding](../../../../docs/framework/winforms/controls/how-to-create-a-border-around-a-windows-forms-control-using-padding.md)\\</span></span>
<span data-ttu-id="f206e-113">Viene illustrato come utilizzare il <xref:System.Windows.Forms.Control.Padding%2A> proprietà descrive un controllo.</span><span class="sxs-lookup"><span data-stu-id="f206e-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>

<span data-ttu-id="f206e-114">[Procedura: Implementare un motore di Layout personalizzati](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-layout-engine.md)\\</span><span class="sxs-lookup"><span data-stu-id="f206e-114">[How to: Implement a Custom Layout Engine](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-layout-engine.md)\\</span></span>
<span data-ttu-id="f206e-115">Viene illustrato come implementare un <xref:System.Windows.Forms.Layout.LayoutEngine> per la disposizione di controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f206e-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>

## <a name="reference"></a><span data-ttu-id="f206e-116">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="f206e-116">Reference</span></span>

<xref:System.Windows.Forms.TableLayoutPanel>\
<span data-ttu-id="f206e-117">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="f206e-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

<xref:System.Windows.Forms.FlowLayoutPanel>\
<span data-ttu-id="f206e-118">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="f206e-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="f206e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f206e-119">See also</span></span>

- [<span data-ttu-id="f206e-120">Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="f206e-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="f206e-121">Procedura: Ancorare e agganciare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="f206e-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="f206e-122">Procedura: Progettare un Layout di Windows Form che risponda correttamente alla localizzazione</span><span class="sxs-lookup"><span data-stu-id="f206e-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="f206e-123">Comportamento di AutoSize nel controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="f206e-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)
