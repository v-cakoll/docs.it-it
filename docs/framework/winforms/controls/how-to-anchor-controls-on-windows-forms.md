---
title: 'Procedura: agganciare i controlli in Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ceaacc250d48e7199d7224f95aa91ed976c097e0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="77343-102">Procedura: agganciare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="77343-102">How to: Anchor Controls on Windows Forms</span></span>
<span data-ttu-id="77343-103">Se si progetta un form che l'utente può ridimensionare in fase di esecuzione, i controlli sul form devono ridimensionare e riposizionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="77343-103">If you are designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="77343-104">Per ridimensionare i controlli in modo dinamico con il modulo, è possibile utilizzare il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà dei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="77343-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="77343-105">Il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà definisce una posizione di ancoraggio per il controllo.</span><span class="sxs-lookup"><span data-stu-id="77343-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="77343-106">Quando un controllo viene ancorato a un modulo e il form viene ridimensionato, il controllo mantiene la distanza tra il controllo e la posizione di ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="77343-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="77343-107">Ad esempio, se dispone di un <xref:System.Windows.Forms.TextBox> controllo è ancorato il sinistro, destro e inferiore del form, come il form viene ridimensionato, il <xref:System.Windows.Forms.TextBox> controllo viene ridimensionato orizzontalmente in modo che mantiene la stessa distanza i lati destro e sinistro del form.</span><span class="sxs-lookup"><span data-stu-id="77343-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="77343-108">Inoltre, il controllo si posizionerà verticalmente in modo che il percorso è sempre la stessa distanza dal bordo inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="77343-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="77343-109">Se un controllo non è ancorato e viene ridimensionato il form, la posizione del controllo in relazione i bordi del form viene modificata.</span><span class="sxs-lookup"><span data-stu-id="77343-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>  
  
 <span data-ttu-id="77343-110">Il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà interagisce con il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="77343-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="77343-111">Per ulteriori informazioni, vedere [Cenni preliminari sulla proprietà AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="77343-111">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77343-112">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="77343-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="77343-113">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="77343-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="77343-114">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="77343-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-anchor-a-control-on-a-form"></a><span data-ttu-id="77343-115">Per ancorare un controllo in un form</span><span class="sxs-lookup"><span data-stu-id="77343-115">To anchor a control on a form</span></span>  
  
1.  <span data-ttu-id="77343-116">Selezionare il controllo che si desidera ancorare.</span><span class="sxs-lookup"><span data-stu-id="77343-116">Select the control you want to anchor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77343-117">È possibile ancorare più controlli contemporaneamente tenendo premuto CTRL, fare clic su ogni controllo per selezionarlo e quindi seguendo il resto di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="77343-117">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>  
  
2.  <span data-ttu-id="77343-118">Nel **proprietà** finestra, fare clic sulla freccia a destra della <xref:System.Windows.Forms.Control.Anchor%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="77343-118">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>  
  
     <span data-ttu-id="77343-119">Viene visualizzato un editor con una croce.</span><span class="sxs-lookup"><span data-stu-id="77343-119">An editor is displayed that shows a cross.</span></span>  
  
3.  <span data-ttu-id="77343-120">Per impostare un punto di ancoraggio, fare clic su sezione inferiore della croce, alto, a sinistra o destra.</span><span class="sxs-lookup"><span data-stu-id="77343-120">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>  
  
     <span data-ttu-id="77343-121">I controlli ancorati nella parte superiore e sinistra per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="77343-121">Controls are anchored to the top and left by default.</span></span>  
  
4.  <span data-ttu-id="77343-122">Per cancellare un lato del controllo che è stato ancorato, fare clic su tale parte della croce.</span><span class="sxs-lookup"><span data-stu-id="77343-122">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>  
  
5.  <span data-ttu-id="77343-123">Per chiudere il <xref:System.Windows.Forms.Control.Anchor%2A> editor proprietà scegliere il <xref:System.Windows.Forms.Control.Anchor%2A> nuovo nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="77343-123">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>  
  
 <span data-ttu-id="77343-124">Quando il form viene visualizzato in fase di esecuzione, il controllo viene ridimensionato per rimanere posizionato alla stessa distanza dal bordo del form.</span><span class="sxs-lookup"><span data-stu-id="77343-124">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="77343-125">La distanza dal bordo agganciato resta sempre la stessa alla distanza definita quando il controllo viene posizionato in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="77343-125">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77343-126">Alcuni controlli, ad esempio il <xref:System.Windows.Forms.ComboBox> , presentano un limite di altezza.</span><span class="sxs-lookup"><span data-stu-id="77343-126">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="77343-127">Il controllo nella parte inferiore del form o contenitore di ancoraggio non è possibile forzare il controllo di superare il limite di altezza.</span><span class="sxs-lookup"><span data-stu-id="77343-127">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>  
  
 <span data-ttu-id="77343-128">I controlli ereditati devono essere `Protected` per poter essere ancorato.</span><span class="sxs-lookup"><span data-stu-id="77343-128">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="77343-129">Per modificare il livello di accesso di un controllo, impostare il relativo `Modifiers` proprietà il **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="77343-129">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77343-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77343-130">See Also</span></span>  
 [<span data-ttu-id="77343-131">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="77343-131">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="77343-132">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="77343-132">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="77343-133">Panoramica sulla proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="77343-133">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="77343-134">Procedura: Ancorare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="77343-134">How to: Dock Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [<span data-ttu-id="77343-135">Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="77343-135">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="77343-136">Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="77343-136">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="77343-137">Procedura dettagliata: disposizione di controlli Windows Form usando spaziatura, margini e la proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="77343-137">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
