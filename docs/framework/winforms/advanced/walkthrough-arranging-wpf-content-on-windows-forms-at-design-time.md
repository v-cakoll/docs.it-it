---
title: Disponi contenuto WPF in Windows Forms in fase di progettazione
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5a6b12def45052e117fb149555946ea42d6cd3c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746826"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="2d113-102">Procedura dettagliata: disposizione del contenuto WPF in Windows Forms in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="2d113-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="2d113-103">Questo articolo illustra come usare le funzionalità di layout di Windows Forms, ad esempio l'ancoraggio e le guide di allineamento, per disporre i controlli Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="2d113-103">This article shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d113-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2d113-104">Prerequisites</span></span>

<span data-ttu-id="2d113-105">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2d113-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="2d113-106">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="2d113-106">Create the project</span></span>

<span data-ttu-id="2d113-107">Aprire Visual Studio e creare un nuovo progetto di applicazione Windows Forms in Visual Basic o C# in un oggetto visivo denominato `ArrangeElementHost`.</span><span class="sxs-lookup"><span data-stu-id="2d113-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="2d113-108">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2d113-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="2d113-109">Creare il controllo WPF</span><span class="sxs-lookup"><span data-stu-id="2d113-109">Create the WPF control</span></span>

<span data-ttu-id="2d113-110">Dopo avere aggiunto un controllo WPF al progetto, è possibile disporlo sul form.</span><span class="sxs-lookup"><span data-stu-id="2d113-110">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="2d113-111">Aggiungere un nuovo <xref:System.Windows.Controls.UserControl> WPF al progetto.</span><span class="sxs-lookup"><span data-stu-id="2d113-111">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="2d113-112">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="2d113-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="2d113-113">Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovi contenuti WPF in Windows Forms in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="2d113-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="2d113-114">In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="2d113-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="2d113-115">Nella finestra **Proprietà** impostare il valore delle proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> su **200**.</span><span class="sxs-lookup"><span data-stu-id="2d113-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="2d113-116">Impostare il valore della proprietà <xref:System.Windows.Controls.Control.Background%2A> su **blu**.</span><span class="sxs-lookup"><span data-stu-id="2d113-116">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

5. <span data-ttu-id="2d113-117">Compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="2d113-117">Build the project.</span></span>

## <a name="host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="2d113-118">Ospitare controlli WPF in un pannello di layout</span><span class="sxs-lookup"><span data-stu-id="2d113-118">Host WPF controls in a layout panel</span></span>

<span data-ttu-id="2d113-119">È possibile usare i controlli WPF nei pannelli di layout nello stesso modo in cui si usano gli altri controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="2d113-119">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

1. <span data-ttu-id="2d113-120">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="2d113-120">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="2d113-121">Nella **casella degli strumenti**trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> sul form.</span><span class="sxs-lookup"><span data-stu-id="2d113-121">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="2d113-122">Nel pannello smart tag del controllo <xref:System.Windows.Forms.TableLayoutPanel> selezionare **Rimuovi ultima riga**.</span><span class="sxs-lookup"><span data-stu-id="2d113-122">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="2d113-123">Ridimensionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> impostando una larghezza e un'altezza maggiori.</span><span class="sxs-lookup"><span data-stu-id="2d113-123">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="2d113-124">Nella **casella degli strumenti**fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nella prima cella del controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="2d113-124">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="2d113-125">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="2d113-125">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="2d113-126">Nella **casella degli strumenti**fare doppio clic su `UserControl1` per creare un'altra istanza nella seconda cella del controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="2d113-126">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="2d113-127">Nella finestra **struttura documento** selezionare `tableLayoutPanel1`.</span><span class="sxs-lookup"><span data-stu-id="2d113-127">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span>

8. <span data-ttu-id="2d113-128">Nella finestra **Proprietà** impostare il valore della proprietà <xref:System.Windows.Forms.Control.Padding%2A> su 10, 10 **, 10, 10**.</span><span class="sxs-lookup"><span data-stu-id="2d113-128">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to **10, 10, 10, 10**.</span></span>

   <span data-ttu-id="2d113-129">Entrambi i controlli <xref:System.Windows.Forms.Integration.ElementHost> vengono ridimensionati per essere adattati al nuovo layout.</span><span class="sxs-lookup"><span data-stu-id="2d113-129">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="2d113-130">Utilizzare le guide di allineamento per allineare i controlli WPF</span><span class="sxs-lookup"><span data-stu-id="2d113-130">Use snaplines to align WPF controls</span></span>

<span data-ttu-id="2d113-131">Le guide di allineamento semplificano l'allineamento dei controlli su un form.</span><span class="sxs-lookup"><span data-stu-id="2d113-131">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="2d113-132">È possibile usare le guide di allineamento anche per allineare i controlli WPF.</span><span class="sxs-lookup"><span data-stu-id="2d113-132">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="2d113-133">Per ulteriori informazioni, vedere [procedura dettagliata: disposizione dei controlli su Windows Forms mediante guide di allineamento](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="2d113-133">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

1. <span data-ttu-id="2d113-134">Dalla **casella degli strumenti**trascinare un'istanza di `UserControl1` nel form e posizionarla nello spazio sotto il controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="2d113-134">From the **Toolbox**, drag an instance of `UserControl1` onto the form, and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="2d113-135">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="2d113-135">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="2d113-136">Tramite le guide di allineamento allineare il bordo sinistro di `elementHost3` al bordo sinistro del controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="2d113-136">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="2d113-137">Tramite le guide di allineamento ridimensionare `elementHost3` impostando la stessa larghezza del controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="2d113-137">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="2d113-138">Spostare `elementHost3` verso il controllo <xref:System.Windows.Forms.TableLayoutPanel> finché non viene visualizzata una guida di allineamento centrale tra i due controlli.</span><span class="sxs-lookup"><span data-stu-id="2d113-138">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="2d113-139">Nella finestra **Proprietà** impostare il valore della proprietà Margin su **20, 20, 20, 20**.</span><span class="sxs-lookup"><span data-stu-id="2d113-139">In the **Properties** window, set the value of the Margin property to **20, 20, 20, 20**.</span></span>

6. <span data-ttu-id="2d113-140">Spostare `elementHost3` dal controllo <xref:System.Windows.Forms.TableLayoutPanel> finché non viene di nuovo visualizzata la guida di allineamento centrale.</span><span class="sxs-lookup"><span data-stu-id="2d113-140">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="2d113-141">La guida di allineamento centrale indica ora un margine di 20.</span><span class="sxs-lookup"><span data-stu-id="2d113-141">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="2d113-142">Spostare `elementHost3` a destra finché il bordo sinistro non è allineato al bordo sinistro del `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="2d113-142">Move `elementHost3` to the right until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="2d113-143">Modificare la larghezza di `elementHost3` finché il bordo destro non è allineato a quello destro di `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="2d113-143">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchor-and-dock-wpf-controls"></a><span data-ttu-id="2d113-144">Ancorare e ancorare controlli WPF</span><span class="sxs-lookup"><span data-stu-id="2d113-144">Anchor and dock WPF controls</span></span>

<span data-ttu-id="2d113-145">Un controllo WPF incluso in un form è soggetto alle stesse regole di ancoraggio e aggancio degli altri controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="2d113-145">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

1. <span data-ttu-id="2d113-146">Selezionare `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="2d113-146">Select `elementHost1`.</span></span>

2. <span data-ttu-id="2d113-147">Nella finestra **Proprietà** impostare la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> su in **alto, in basso, a sinistra, a destra**.</span><span class="sxs-lookup"><span data-stu-id="2d113-147">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="2d113-148">Ridimensionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> impostando dimensioni superiori.</span><span class="sxs-lookup"><span data-stu-id="2d113-148">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

   <span data-ttu-id="2d113-149">Il controllo `elementHost1` verrà ridimensionato fino ad occupare l'intera cella.</span><span class="sxs-lookup"><span data-stu-id="2d113-149">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="2d113-150">Selezionare `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="2d113-150">Select `elementHost2`.</span></span>

5. <span data-ttu-id="2d113-151">Nella finestra **Proprietà** impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="2d113-151">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="2d113-152">Il controllo `elementHost2` verrà ridimensionato fino ad occupare l'intera cella.</span><span class="sxs-lookup"><span data-stu-id="2d113-152">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="2d113-153">Selezionare il controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="2d113-153">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="2d113-154">Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Top>.</span><span class="sxs-lookup"><span data-stu-id="2d113-154">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="2d113-155">Selezionare `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="2d113-155">Select `elementHost3`.</span></span>

9. <span data-ttu-id="2d113-156">Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="2d113-156">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="2d113-157">Il controllo `elementHost3` verrà ridimensionato fino a occupare lo spazio rimanente sul form.</span><span class="sxs-lookup"><span data-stu-id="2d113-157">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="2d113-158">Ridimensionare il form.</span><span class="sxs-lookup"><span data-stu-id="2d113-158">Resize the form.</span></span>

    <span data-ttu-id="2d113-159">Tutti e tre i controlli <xref:System.Windows.Forms.Integration.ElementHost> verranno ridimensionati in maniera appropriata.</span><span class="sxs-lookup"><span data-stu-id="2d113-159">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

    <span data-ttu-id="2d113-160">Per altre informazioni, vedere [procedura: ancorare e ancorare controlli figlio in un controllo TableLayoutPanel](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span><span class="sxs-lookup"><span data-stu-id="2d113-160">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2d113-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d113-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="2d113-162">Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="2d113-162">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="2d113-163">Procedura: Allineare un controllo ai bordi dei form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="2d113-163">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="2d113-164">Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="2d113-164">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="2d113-165">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="2d113-165">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="2d113-166">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="2d113-166">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="2d113-167">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2d113-167">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
