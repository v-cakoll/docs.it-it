---
title: 'Procedura dettagliata: Disposizione del contenuto WPF in Windows Form in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7858ffd708c78d6397d533f613ccc2ea78d6cbed
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658515"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="d0e90-102">Procedura dettagliata: Disponi contenuto WPF in Windows Forms in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="d0e90-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="d0e90-103">Questo articolo illustra come usare le funzionalità di layout di Windows Forms, ad esempio l'ancoraggio e le guide di allineamento, per disporre i controlli Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="d0e90-103">This article shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0e90-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d0e90-104">Prerequisites</span></span>

<span data-ttu-id="d0e90-105">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d0e90-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="d0e90-106">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="d0e90-106">Create the project</span></span>

<span data-ttu-id="d0e90-107">Aprire Visual Studio e creare un nuovo progetto di applicazione Windows Forms in Visual Basic o C# in `ArrangeElementHost`un oggetto visivo denominato.</span><span class="sxs-lookup"><span data-stu-id="d0e90-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="d0e90-108">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d0e90-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="d0e90-109">Creare il controllo WPF</span><span class="sxs-lookup"><span data-stu-id="d0e90-109">Create the WPF control</span></span>

<span data-ttu-id="d0e90-110">Dopo avere aggiunto un controllo WPF al progetto, è possibile disporlo sul form.</span><span class="sxs-lookup"><span data-stu-id="d0e90-110">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="d0e90-111">Aggiungere un nuovo <xref:System.Windows.Controls.UserControl> WPF al progetto.</span><span class="sxs-lookup"><span data-stu-id="d0e90-111">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="d0e90-112">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="d0e90-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="d0e90-113">Per altre informazioni, vedere [Procedura dettagliata: Creazione di nuovo contenuto WPF in Windows Forms in fase](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d0e90-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="d0e90-114">In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="d0e90-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="d0e90-115">Nella finestra **Proprietà** impostare il valore delle <xref:System.Windows.FrameworkElement.Width%2A> proprietà e <xref:System.Windows.FrameworkElement.Height%2A> su **200**.</span><span class="sxs-lookup"><span data-stu-id="d0e90-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="d0e90-116">Impostare il valore della <xref:System.Windows.Controls.Control.Background%2A> proprietà su **blu**.</span><span class="sxs-lookup"><span data-stu-id="d0e90-116">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

5. <span data-ttu-id="d0e90-117">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="d0e90-117">Build the project.</span></span>

## <a name="host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="d0e90-118">Ospitare controlli WPF in un pannello di layout</span><span class="sxs-lookup"><span data-stu-id="d0e90-118">Host WPF controls in a layout panel</span></span>

<span data-ttu-id="d0e90-119">È possibile usare i controlli WPF nei pannelli di layout nello stesso modo in cui si usano gli altri controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="d0e90-119">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

1. <span data-ttu-id="d0e90-120">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="d0e90-120">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="d0e90-121">Nella **casella degli strumenti**trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo sul form.</span><span class="sxs-lookup"><span data-stu-id="d0e90-121">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="d0e90-122">Nel pannello <xref:System.Windows.Forms.TableLayoutPanel> smart tag del controllo selezionare **Rimuovi ultima riga**.</span><span class="sxs-lookup"><span data-stu-id="d0e90-122">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="d0e90-123">Ridimensionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> impostando una larghezza e un'altezza maggiori.</span><span class="sxs-lookup"><span data-stu-id="d0e90-123">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="d0e90-124">Nella **casella degli strumenti**fare doppio clic `UserControl1` su per creare un'istanza `UserControl1` di nella prima cella del <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="d0e90-124">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="d0e90-125">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="d0e90-125">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="d0e90-126">Nella **casella degli strumenti**fare doppio clic `UserControl1` su per creare un'altra istanza nella <xref:System.Windows.Forms.TableLayoutPanel> seconda cella del controllo.</span><span class="sxs-lookup"><span data-stu-id="d0e90-126">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="d0e90-127">Nella finestra **struttura documento** selezionare `tableLayoutPanel1`.</span><span class="sxs-lookup"><span data-stu-id="d0e90-127">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span>

8. <span data-ttu-id="d0e90-128">Nella finestra **Proprietà** impostare il valore della <xref:System.Windows.Forms.Control.Padding%2A> proprietà su 10, **10, 10, 10**.</span><span class="sxs-lookup"><span data-stu-id="d0e90-128">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to **10, 10, 10, 10**.</span></span>

   <span data-ttu-id="d0e90-129">Entrambi i controlli <xref:System.Windows.Forms.Integration.ElementHost> vengono ridimensionati per essere adattati al nuovo layout.</span><span class="sxs-lookup"><span data-stu-id="d0e90-129">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="d0e90-130">Utilizzare le guide di allineamento per allineare i controlli WPF</span><span class="sxs-lookup"><span data-stu-id="d0e90-130">Use snaplines to align WPF controls</span></span>

<span data-ttu-id="d0e90-131">Le guide di allineamento semplificano l'allineamento dei controlli su un form.</span><span class="sxs-lookup"><span data-stu-id="d0e90-131">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="d0e90-132">È possibile usare le guide di allineamento anche per allineare i controlli WPF.</span><span class="sxs-lookup"><span data-stu-id="d0e90-132">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="d0e90-133">Per altre informazioni, vedere [Procedura dettagliata: Disposizione di controlli su Windows Forms mediante guide](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)di allineamento.</span><span class="sxs-lookup"><span data-stu-id="d0e90-133">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

1. <span data-ttu-id="d0e90-134">Dalla **casella degli strumenti**trascinare un'istanza di `UserControl1` nel form e posizionarla nello spazio sotto il <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="d0e90-134">From the **Toolbox**, drag an instance of `UserControl1` onto the form, and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="d0e90-135">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="d0e90-135">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="d0e90-136">Tramite le guide di allineamento allineare il bordo sinistro di `elementHost3` al bordo sinistro del controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d0e90-136">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="d0e90-137">Tramite le guide di allineamento ridimensionare `elementHost3` impostando la stessa larghezza del controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d0e90-137">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="d0e90-138">Spostare `elementHost3` verso il controllo <xref:System.Windows.Forms.TableLayoutPanel> finché non viene visualizzata una guida di allineamento centrale tra i due controlli.</span><span class="sxs-lookup"><span data-stu-id="d0e90-138">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="d0e90-139">Nella finestra **Proprietà** impostare il valore della proprietà Margin su **20, 20, 20, 20**.</span><span class="sxs-lookup"><span data-stu-id="d0e90-139">In the **Properties** window, set the value of the Margin property to **20, 20, 20, 20**.</span></span>

6. <span data-ttu-id="d0e90-140">Spostare `elementHost3` dal controllo <xref:System.Windows.Forms.TableLayoutPanel> finché non viene di nuovo visualizzata la guida di allineamento centrale.</span><span class="sxs-lookup"><span data-stu-id="d0e90-140">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="d0e90-141">La guida di allineamento centrale indica ora un margine di 20.</span><span class="sxs-lookup"><span data-stu-id="d0e90-141">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="d0e90-142">Spostarsi `elementHost3` a destra fino a quando il bordo sinistro è allineato al bordo `elementHost1`sinistro di.</span><span class="sxs-lookup"><span data-stu-id="d0e90-142">Move `elementHost3` to the right until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="d0e90-143">Modificare la larghezza di `elementHost3` finché il bordo destro non è allineato a quello destro di `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="d0e90-143">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchor-and-dock-wpf-controls"></a><span data-ttu-id="d0e90-144">Ancorare e ancorare controlli WPF</span><span class="sxs-lookup"><span data-stu-id="d0e90-144">Anchor and dock WPF controls</span></span>

<span data-ttu-id="d0e90-145">Un controllo WPF incluso in un form è soggetto alle stesse regole di ancoraggio e aggancio degli altri controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="d0e90-145">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

1. <span data-ttu-id="d0e90-146">Selezionare `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="d0e90-146">Select `elementHost1`.</span></span>

2. <span data-ttu-id="d0e90-147">Nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.Control.Anchor%2A> proprietà su in **alto, in basso, a sinistra, a destra**.</span><span class="sxs-lookup"><span data-stu-id="d0e90-147">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="d0e90-148">Ridimensionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> impostando dimensioni superiori.</span><span class="sxs-lookup"><span data-stu-id="d0e90-148">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

   <span data-ttu-id="d0e90-149">Il controllo `elementHost1` verrà ridimensionato fino ad occupare l'intera cella.</span><span class="sxs-lookup"><span data-stu-id="d0e90-149">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="d0e90-150">Selezionare `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="d0e90-150">Select `elementHost2`.</span></span>

5. <span data-ttu-id="d0e90-151">Nella finestra **Proprietà** impostare il valore della <xref:System.Windows.Forms.Control.Dock%2A> proprietà su. <xref:System.Windows.Forms.DockStyle.Fill></span><span class="sxs-lookup"><span data-stu-id="d0e90-151">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="d0e90-152">Il controllo `elementHost2` verrà ridimensionato fino ad occupare l'intera cella.</span><span class="sxs-lookup"><span data-stu-id="d0e90-152">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="d0e90-153">Selezionare il controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d0e90-153">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="d0e90-154">Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Top>.</span><span class="sxs-lookup"><span data-stu-id="d0e90-154">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="d0e90-155">Selezionare `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="d0e90-155">Select `elementHost3`.</span></span>

9. <span data-ttu-id="d0e90-156">Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="d0e90-156">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="d0e90-157">Il controllo `elementHost3` verrà ridimensionato fino a occupare lo spazio rimanente sul form.</span><span class="sxs-lookup"><span data-stu-id="d0e90-157">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="d0e90-158">Ridimensionare il form.</span><span class="sxs-lookup"><span data-stu-id="d0e90-158">Resize the form.</span></span>

    <span data-ttu-id="d0e90-159">Tutti e tre i controlli <xref:System.Windows.Forms.Integration.ElementHost> verranno ridimensionati in maniera appropriata.</span><span class="sxs-lookup"><span data-stu-id="d0e90-159">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

    <span data-ttu-id="d0e90-160">Per altre informazioni, vedere [Procedura: Ancoraggio e ancoraggio di controlli figlio in un controllo](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)TableLayoutPanel.</span><span class="sxs-lookup"><span data-stu-id="d0e90-160">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d0e90-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0e90-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="d0e90-162">Procedura: Ancoraggio e ancoraggio di controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d0e90-162">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="d0e90-163">Procedura: Allineare un controllo ai bordi dei form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="d0e90-163">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="d0e90-164">Procedura dettagliata: Disposizione di controlli in Windows Forms mediante guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="d0e90-164">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="d0e90-165">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="d0e90-165">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="d0e90-166">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="d0e90-166">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="d0e90-167">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d0e90-167">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
