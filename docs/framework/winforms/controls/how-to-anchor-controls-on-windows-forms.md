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
ms.openlocfilehash: 28cee4e1aa989ef4df902907c09645a1a0400475
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072994"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="17364-102">Procedura: Agganciare i controlli in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="17364-102">How to: Anchor Controls on Windows Forms</span></span>
<span data-ttu-id="17364-103">Se si progetta un form che l'utente può ridimensionare in fase di esecuzione, i controlli sul form devono ridimensionare e riposizionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="17364-103">If you are designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="17364-104">Per ridimensionare i controlli in modo dinamico con il modulo, è possibile usare il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà dei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="17364-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="17364-105">Il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà definisce una posizione di ancoraggio del controllo.</span><span class="sxs-lookup"><span data-stu-id="17364-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="17364-106">Quando un controllo è agganciato a un modulo e il form viene ridimensionato, il controllo gestisce la distanza tra il controllo e la posizione di ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="17364-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="17364-107">Ad esempio, se si dispone di un <xref:System.Windows.Forms.TextBox> controllo è agganciato ai bordi inferiore del form e sinistro, destro, quando il form viene ridimensionato, la <xref:System.Windows.Forms.TextBox> controllo deve essere ridimensionato orizzontalmente in modo che mantiene la stessa distanza dai lati destro e sinistro del form.</span><span class="sxs-lookup"><span data-stu-id="17364-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="17364-108">Inoltre, il controllo si posizionerà verticalmente in modo che il percorso è sempre la stessa distanza dal bordo inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="17364-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="17364-109">Se un controllo è agganciato non e il form viene ridimensionato, viene modificata la posizione del controllo in relazione i bordi del form.</span><span class="sxs-lookup"><span data-stu-id="17364-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>  
  
 <span data-ttu-id="17364-110">Il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà interagisce con il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="17364-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="17364-111">Per altre informazioni, vedere [Cenni preliminari sulle proprietà AutoSize](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="17364-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17364-112">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="17364-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="17364-113">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="17364-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="17364-114">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="17364-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-anchor-a-control-on-a-form"></a><span data-ttu-id="17364-115">Per ancorare un controllo in un form</span><span class="sxs-lookup"><span data-stu-id="17364-115">To anchor a control on a form</span></span>  
  
1.  <span data-ttu-id="17364-116">Selezionare il controllo che si desidera ancorare.</span><span class="sxs-lookup"><span data-stu-id="17364-116">Select the control you want to anchor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="17364-117">È possibile ancorare più controlli contemporaneamente tenendo premuto CTRL, facendo clic su ogni controllo per selezionarla e quindi seguendo il resto di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="17364-117">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>  
  
2.  <span data-ttu-id="17364-118">Nel **delle proprietà** finestra, fare clic sulla freccia a destra del <xref:System.Windows.Forms.Control.Anchor%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="17364-118">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>  
  
     <span data-ttu-id="17364-119">Viene visualizzato un editor che mostra una croce.</span><span class="sxs-lookup"><span data-stu-id="17364-119">An editor is displayed that shows a cross.</span></span>  
  
3.  <span data-ttu-id="17364-120">Per impostare un punto di ancoraggio, fare clic su alto, a sinistra, destra, ovvero nella sezione inferiore della finestra di tra.</span><span class="sxs-lookup"><span data-stu-id="17364-120">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>  
  
     <span data-ttu-id="17364-121">I controlli ancorati nella parte superiore e sinistra per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="17364-121">Controls are anchored to the top and left by default.</span></span>  
  
4.  <span data-ttu-id="17364-122">Per cancellare un lato del controllo che è stato ancorato, fare clic su tale parte della croce.</span><span class="sxs-lookup"><span data-stu-id="17364-122">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>  
  
5.  <span data-ttu-id="17364-123">Per chiudere la <xref:System.Windows.Forms.Control.Anchor%2A> editor di proprietà, fare clic su di <xref:System.Windows.Forms.Control.Anchor%2A> nuovo nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="17364-123">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>  
  
 <span data-ttu-id="17364-124">Quando il form viene visualizzato in fase di esecuzione, il controllo viene ridimensionato per rimanere posizionato alla stessa distanza dal bordo del form.</span><span class="sxs-lookup"><span data-stu-id="17364-124">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="17364-125">La distanza dal bordo ancorato rimane sempre lo stesso come distanza definito quando viene posizionato il controllo in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="17364-125">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17364-126">Alcuni controlli, ad esempio il <xref:System.Windows.Forms.ComboBox> , dispongono di un limite all'altezza.</span><span class="sxs-lookup"><span data-stu-id="17364-126">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="17364-127">Il controllo nella parte inferiore del form o contenitore di ancoraggio non è possibile forzare il controllo di superare il limite di altezza.</span><span class="sxs-lookup"><span data-stu-id="17364-127">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>  
  
 <span data-ttu-id="17364-128">I controlli ereditati devono essere `Protected` per poter essere ancorata.</span><span class="sxs-lookup"><span data-stu-id="17364-128">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="17364-129">Per modificare il livello di accesso di un controllo, impostare il relativo `Modifiers` proprietà nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="17364-129">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17364-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17364-130">See also</span></span>

- [<span data-ttu-id="17364-131">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="17364-131">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="17364-132">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="17364-132">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="17364-133">Cenni preliminari sulla proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="17364-133">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="17364-134">Procedura: Ancorare i controlli in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="17364-134">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="17364-135">Procedura dettagliata: Disposizione dei controlli in Windows Forms usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="17364-135">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="17364-136">Procedura dettagliata: Disposizione dei controlli in Windows Forms usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="17364-136">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="17364-137">Procedura dettagliata: Disposizione dei controlli Windows Forms con spaziatura interna, margini e la proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="17364-137">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
