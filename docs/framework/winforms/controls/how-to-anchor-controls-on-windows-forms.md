---
title: 'Procedura: Agganciare i controlli in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
ms.openlocfilehash: b48761bda2baad4f7d1e6db9b41d73d6d54bc081
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211265"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="c3579-102">Procedura: Agganciare i controlli in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c3579-102">How to: Anchor Controls on Windows Forms</span></span>

<span data-ttu-id="c3579-103">Se si sta progettando un form che l'utente può ridimensionare in fase di esecuzione, i controlli sul form devono ridimensionare e riposizionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="c3579-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="c3579-104">Per ridimensionare i controlli in modo dinamico con il modulo, è possibile usare il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà dei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c3579-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="c3579-105">Il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà definisce una posizione di ancoraggio del controllo.</span><span class="sxs-lookup"><span data-stu-id="c3579-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="c3579-106">Quando un controllo è agganciato a un modulo e il form viene ridimensionato, il controllo gestisce la distanza tra il controllo e la posizione di ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="c3579-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="c3579-107">Ad esempio, se si dispone di un <xref:System.Windows.Forms.TextBox> controllo è agganciato ai bordi inferiore del form e sinistro, destro, quando il form viene ridimensionato, la <xref:System.Windows.Forms.TextBox> controllo deve essere ridimensionato orizzontalmente in modo che mantiene la stessa distanza dai lati destro e sinistro del form.</span><span class="sxs-lookup"><span data-stu-id="c3579-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="c3579-108">Inoltre, il controllo si posizionerà verticalmente in modo che il percorso è sempre la stessa distanza dal bordo inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="c3579-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="c3579-109">Se un controllo è agganciato non e il form viene ridimensionato, viene modificata la posizione del controllo in relazione i bordi del form.</span><span class="sxs-lookup"><span data-stu-id="c3579-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="c3579-110">Il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà interagisce con il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c3579-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="c3579-111">Per altre informazioni, vedere [Cenni preliminari sulle proprietà AutoSize](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c3579-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="c3579-112">Ancoraggio di un controllo in un form</span><span class="sxs-lookup"><span data-stu-id="c3579-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="c3579-113">In Visual Studio, selezionare il controllo che si desidera ancorare.</span><span class="sxs-lookup"><span data-stu-id="c3579-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3579-114">È possibile ancorare più controlli contemporaneamente tenendo premuto CTRL, facendo clic su ogni controllo per selezionarla e quindi seguendo il resto di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="c3579-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="c3579-115">Nel **delle proprietà** finestra, fare clic sulla freccia a destra del <xref:System.Windows.Forms.Control.Anchor%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c3579-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="c3579-116">Viene visualizzato un editor che mostra una croce.</span><span class="sxs-lookup"><span data-stu-id="c3579-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="c3579-117">Per impostare un punto di ancoraggio, fare clic su alto, a sinistra, destra, ovvero nella sezione inferiore della finestra di tra.</span><span class="sxs-lookup"><span data-stu-id="c3579-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="c3579-118">I controlli ancorati nella parte superiore e sinistra per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c3579-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="c3579-119">Per cancellare un lato del controllo che è stato ancorato, fare clic su tale parte della croce.</span><span class="sxs-lookup"><span data-stu-id="c3579-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="c3579-120">Per chiudere la <xref:System.Windows.Forms.Control.Anchor%2A> editor di proprietà, fare clic su di <xref:System.Windows.Forms.Control.Anchor%2A> nuovo nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c3579-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="c3579-121">Quando il form viene visualizzato in fase di esecuzione, il controllo viene ridimensionato per rimanere posizionato alla stessa distanza dal bordo del form.</span><span class="sxs-lookup"><span data-stu-id="c3579-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="c3579-122">La distanza dal bordo ancorato rimane sempre lo stesso come distanza definito quando viene posizionato il controllo in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c3579-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="c3579-123">Alcuni controlli, ad esempio il <xref:System.Windows.Forms.ComboBox> , dispongono di un limite all'altezza.</span><span class="sxs-lookup"><span data-stu-id="c3579-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="c3579-124">Il controllo nella parte inferiore del form o contenitore di ancoraggio non è possibile forzare il controllo di superare il limite di altezza.</span><span class="sxs-lookup"><span data-stu-id="c3579-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="c3579-125">I controlli ereditati devono essere `Protected` per poter essere ancorata.</span><span class="sxs-lookup"><span data-stu-id="c3579-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="c3579-126">Per modificare il livello di accesso di un controllo, impostare il relativo `Modifiers` proprietà nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="c3579-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3579-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3579-127">See also</span></span>

- [<span data-ttu-id="c3579-128">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="c3579-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="c3579-129">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c3579-129">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="c3579-130">Panoramica sulla proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="c3579-130">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="c3579-131">Procedura: Ancorare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c3579-131">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="c3579-132">Procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c3579-132">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="c3579-133">Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c3579-133">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="c3579-134">Procedura dettagliata: Definire il layout dei Windows Form usando spaziatura, margini e la proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="c3579-134">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
