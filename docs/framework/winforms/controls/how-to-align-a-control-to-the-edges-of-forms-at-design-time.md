---
title: 'Procedura: Allineare un controllo ai bordi dei moduli in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: b08e01eb9adb984a32a8fc435cf1f3b93b159a14
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210373"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a><span data-ttu-id="afce9-102">Procedura: Allineare un controllo ai bordi dei moduli in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="afce9-102">How to: Align a Control to the Edges of Forms at Design Time</span></span>

<span data-ttu-id="afce9-103">È possibile allineare un controllo per il bordo dei form impostando il valore della <xref:System.Windows.Forms.Control.Dock%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="afce9-103">You can make your control align to the edge of your forms by setting the value of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="afce9-104">che designa la posizione del controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="afce9-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="afce9-105">La proprietà <xref:System.Windows.Forms.Control.Dock%2A> può essere impostata su uno dei valori riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="afce9-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>

|<span data-ttu-id="afce9-106">Impostazione</span><span class="sxs-lookup"><span data-stu-id="afce9-106">Setting</span></span>|<span data-ttu-id="afce9-107">Effetto sul controllo</span><span class="sxs-lookup"><span data-stu-id="afce9-107">Effect on your control</span></span>|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="afce9-108">Il controllo viene ancorato alla parte inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="afce9-108">Docks to the bottom of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="afce9-109">Il controllo occupa tutto lo spazio rimanente nel form.</span><span class="sxs-lookup"><span data-stu-id="afce9-109">Fills all remaining space in the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="afce9-110">Il controllo viene ancorato al lato sinistro del form.</span><span class="sxs-lookup"><span data-stu-id="afce9-110">Docks to the left side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="afce9-111">Non viene ancorato e viene visualizzato nella posizione specificata dal relativo <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="afce9-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A>.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="afce9-112">Il controllo viene ancorato al lato destro del form.</span><span class="sxs-lookup"><span data-stu-id="afce9-112">Docks to the right side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="afce9-113">Il controllo viene ancorato alla parte superiore del form.</span><span class="sxs-lookup"><span data-stu-id="afce9-113">Docks to the top of the form.</span></span>|

<span data-ttu-id="afce9-114">Questi valori possono anche essere impostati nel codice.</span><span class="sxs-lookup"><span data-stu-id="afce9-114">These values can also be set in code.</span></span> <span data-ttu-id="afce9-115">Per altre informazioni, vedere [Procedura: Allineare un controllo ai bordi dei form](how-to-align-a-control-to-the-edges-of-forms.md).</span><span class="sxs-lookup"><span data-stu-id="afce9-115">For more information, see [How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md).</span></span>

## <a name="set-the-dock-property-for-your-control-at-design-time"></a><span data-ttu-id="afce9-116">Impostare la proprietà Dock del controllo in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="afce9-116">Set the Dock property for your control at design time</span></span>

1. <span data-ttu-id="afce9-117">In Progettazione Windows Form in Visual Studio, selezionare il controllo.</span><span class="sxs-lookup"><span data-stu-id="afce9-117">In the Windows Forms Designer in Visual Studio, select your control.</span></span>

2. <span data-ttu-id="afce9-118">Nel **delle proprietà** fare clic sulla casella di elenco a discesa accanto al <xref:System.Windows.Forms.Control.Dock%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="afce9-118">In the **Properties** window, click the drop-down box next to the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>

     <span data-ttu-id="afce9-119">Un'interfaccia grafica che rappresenta le sei possibili <xref:System.Windows.Forms.Control.Dock%2A> impostazioni viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="afce9-119">A graphical interface representing the six possible <xref:System.Windows.Forms.Control.Dock%2A> settings is displayed.</span></span>

3. <span data-ttu-id="afce9-120">Scegliere l'impostazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="afce9-120">Choose the appropriate setting.</span></span>

4. <span data-ttu-id="afce9-121">Il controllo verrà ancorato nel modo specificato dall'impostazione.</span><span class="sxs-lookup"><span data-stu-id="afce9-121">Your control will now dock in the manner specified by the setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="afce9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afce9-122">See also</span></span>

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="afce9-123">Procedura: Allineare un controllo ai bordi dei form</span><span class="sxs-lookup"><span data-stu-id="afce9-123">How to: Align a Control to the Edges of Forms</span></span>](how-to-align-a-control-to-the-edges-of-forms.md)
- [<span data-ttu-id="afce9-124">Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="afce9-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="afce9-125">Procedura: Ancoraggio dei controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="afce9-125">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
- [<span data-ttu-id="afce9-126">Procedura: Ancorare e agganciare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="afce9-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="afce9-127">Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="afce9-127">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="afce9-128">Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="afce9-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="afce9-129">Procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="afce9-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="afce9-130">Sviluppo di controlli Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="afce9-130">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
