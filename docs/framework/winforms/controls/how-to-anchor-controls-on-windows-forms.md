---
title: Ancorare i controlli (Anchor)
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7c307d8c5b3bc32e15e6de048c434854ef1bbc65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747189"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="8d0b5-102">Procedura: ancorare i controlli in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d0b5-102">How to: Anchor controls on Windows Forms</span></span>

<span data-ttu-id="8d0b5-103">Se si progetta un modulo che l'utente può ridimensionare in fase di esecuzione, i controlli sul form devono essere ridimensionati e riposizionati correttamente.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="8d0b5-104">Per ridimensionare i controlli in modo dinamico con il modulo, è possibile usare la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> dei controlli Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="8d0b5-105">La proprietà <xref:System.Windows.Forms.Control.Anchor%2A> definisce una posizione di ancoraggio per il controllo.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="8d0b5-106">Quando un controllo è ancorato a un form e il form viene ridimensionato, il controllo mantiene la distanza tra il controllo e le posizioni di ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="8d0b5-107">Se, ad esempio, si dispone di un controllo <xref:System.Windows.Forms.TextBox> ancorato ai bordi sinistro, destro e inferiore del form, quando il form viene ridimensionato, il controllo <xref:System.Windows.Forms.TextBox> viene ridimensionato orizzontalmente in modo da mantenere la stessa distanza dai lati destro e sinistro del form.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="8d0b5-108">Inoltre, il controllo si posiziona verticalmente in modo che la posizione sia sempre la stessa a distanza dal bordo inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="8d0b5-109">Se un controllo non è ancorato e il form viene ridimensionato, la posizione del controllo rispetto ai bordi del form viene modificata.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="8d0b5-110">La proprietà <xref:System.Windows.Forms.Control.Anchor%2A> interagisce con la proprietà <xref:System.Windows.Forms.Control.AutoSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="8d0b5-111">Per ulteriori informazioni, vedere [Panoramica delle proprietà AutoSize](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8d0b5-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="8d0b5-112">Ancoraggio di un controllo in un form</span><span class="sxs-lookup"><span data-stu-id="8d0b5-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="8d0b5-113">In Visual Studio selezionare il controllo che si vuole ancorare.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8d0b5-114">È possibile ancorare più controlli simultaneamente premendo il tasto CTRL, facendo clic su ogni controllo per selezionarlo e quindi attenendosi al resto della procedura.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="8d0b5-115">Nella finestra **Proprietà** fare clic sulla freccia a destra della proprietà <xref:System.Windows.Forms.Control.Anchor%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="8d0b5-116">Viene visualizzato un editor che mostra una croce.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="8d0b5-117">Per impostare un ancoraggio, fare clic sulla sezione superiore, a sinistra, a destra o in basso della Croce.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="8d0b5-118">Per impostazione predefinita, i controlli sono ancorati nella parte superiore e sinistra.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="8d0b5-119">Per cancellare un lato del controllo che è stato ancorato, fare clic su tale ARM della Croce.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="8d0b5-120">Per chiudere l'editor proprietà <xref:System.Windows.Forms.Control.Anchor%2A>, fare di nuovo clic sul nome della proprietà <xref:System.Windows.Forms.Control.Anchor%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="8d0b5-121">Quando il form viene visualizzato in fase di esecuzione, il controllo viene ridimensionato in modo che rimanga posizionato alla stessa distanza dal bordo del form.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="8d0b5-122">La distanza dal bordo ancorato rimane sempre uguale alla distanza definita quando il controllo è posizionato nell'Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="8d0b5-123">Alcuni controlli, ad esempio il controllo <xref:System.Windows.Forms.ComboBox>, hanno un limite per l'altezza.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="8d0b5-124">L'ancoraggio del controllo nella parte inferiore del form o del contenitore non può forzare il superamento del limite di altezza del controllo.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="8d0b5-125">I controlli ereditati devono essere `Protected` per poter essere ancorati.</span><span class="sxs-lookup"><span data-stu-id="8d0b5-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="8d0b5-126">Per modificare il livello di accesso di un controllo, impostarne la proprietà `Modifiers` nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="8d0b5-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d0b5-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d0b5-127">See also</span></span>

- [<span data-ttu-id="8d0b5-128">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d0b5-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="8d0b5-129">Panoramica sulla proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="8d0b5-129">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="8d0b5-130">Procedura: Ancorare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="8d0b5-130">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="8d0b5-131">Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8d0b5-131">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="8d0b5-132">Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8d0b5-132">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="8d0b5-133">Procedura dettagliata: disposizione di controlli Windows Form usando spaziatura, margini e la proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="8d0b5-133">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
