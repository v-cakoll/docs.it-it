---
title: 'Procedura dettagliata: disposizione del contenuto WPF in Windows Form in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
ms.openlocfilehash: 062b9b943d187ccd4105f3772688c563f540d696
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48266676"
---
# <a name="walkthrough-arranging-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="66b83-102">Procedura dettagliata: disposizione del contenuto WPF in Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="66b83-102">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="66b83-103">Questa procedura dettagliata illustra come usare le funzionalità di layout di Windows Form, ad esempio l'ancoraggio e le guide di allineamento, per disporre i controlli di Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="66b83-103">This walkthrough shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

 <span data-ttu-id="66b83-104">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="66b83-104">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="66b83-105">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="66b83-105">Create the project.</span></span>

-   <span data-ttu-id="66b83-106">Creare il controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="66b83-106">Create the WPF control.</span></span>

-   <span data-ttu-id="66b83-107">Ospitare i controlli WPF in un pannello di layout.</span><span class="sxs-lookup"><span data-stu-id="66b83-107">Host WPF controls in a layout panel.</span></span>

-   <span data-ttu-id="66b83-108">Allineare i controlli WPF mediante le guide di allineamento.</span><span class="sxs-lookup"><span data-stu-id="66b83-108">Use snaplines to align WPF controls.</span></span>

-   <span data-ttu-id="66b83-109">Ancorare e agganciare i controlli WPF.</span><span class="sxs-lookup"><span data-stu-id="66b83-109">Anchor and dock WPF controls.</span></span>

> [!NOTE]
>  <span data-ttu-id="66b83-110">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="66b83-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="66b83-111">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="66b83-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="66b83-112">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="66b83-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="66b83-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="66b83-113">Prerequisites</span></span>  
 <span data-ttu-id="66b83-114">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="66b83-114">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="66b83-115">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="66b83-115">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="66b83-116">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="66b83-116">Creating the Project</span></span>  
 <span data-ttu-id="66b83-117">Il primo passaggio consiste nella creazione del progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="66b83-117">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66b83-118">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="66b83-118">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="66b83-119">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="66b83-119">To create the project</span></span>  
  
-   <span data-ttu-id="66b83-120">Creare un nuovo progetto Windows Forms Application in Visual Basic o Visual c# denominato `ArrangeElementHost`.</span><span class="sxs-lookup"><span data-stu-id="66b83-120">Create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>  
  
## <a name="creating-the-wpf-control"></a><span data-ttu-id="66b83-121">Creazione del controllo WPF</span><span class="sxs-lookup"><span data-stu-id="66b83-121">Creating the WPF Control</span></span>  
 <span data-ttu-id="66b83-122">Dopo avere aggiunto un controllo WPF al progetto, è possibile disporlo sul form.</span><span class="sxs-lookup"><span data-stu-id="66b83-122">After you add a WPF control to the project, you can arrange it on the form.</span></span>  
  
#### <a name="to-create-wpf-controls"></a><span data-ttu-id="66b83-123">Per creare controlli WPF</span><span class="sxs-lookup"><span data-stu-id="66b83-123">To create WPF controls</span></span>  
  
1.  <span data-ttu-id="66b83-124">Aggiungere un nuovo <xref:System.Windows.Controls.UserControl> WPF al progetto.</span><span class="sxs-lookup"><span data-stu-id="66b83-124">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="66b83-125">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="66b83-125">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="66b83-126">Per altre informazioni, vedere [procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="66b83-126">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="66b83-127">In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="66b83-127">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="66b83-128">Per altre informazioni, vedere [procedura: selezionare e spostare elementi nella finestra di progettazione](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="66b83-128">For more information, see [How to: Select and Move Elements on the Design Surface](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="66b83-129">Nel **le proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà da `200`.</span><span class="sxs-lookup"><span data-stu-id="66b83-129">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="66b83-130">Impostare il valore della proprietà <xref:System.Windows.Controls.Control.Background%2A> su `Blue`.</span><span class="sxs-lookup"><span data-stu-id="66b83-130">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
5.  <span data-ttu-id="66b83-131">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="66b83-131">Build the project.</span></span>  
  
## <a name="hosting-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="66b83-132">Hosting di controlli WPF in un pannello di layout</span><span class="sxs-lookup"><span data-stu-id="66b83-132">Hosting WPF Controls in a Layout Panel</span></span>  
 <span data-ttu-id="66b83-133">È possibile usare i controlli WPF nei pannelli di layout nello stesso modo in cui si usano gli altri controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="66b83-133">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>  
  
#### <a name="to-host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="66b83-134">Per ospitare controlli WPF in un pannello di layout</span><span class="sxs-lookup"><span data-stu-id="66b83-134">To host WPF controls in a layout panel</span></span>  
  
1.  <span data-ttu-id="66b83-135">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="66b83-135">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="66b83-136">Nel **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="66b83-136">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>  
  
3.  <span data-ttu-id="66b83-137">Nel <xref:System.Windows.Forms.TableLayoutPanel> pannello smart tag del controllo, seleziona **Rimuovi ultima riga**.</span><span class="sxs-lookup"><span data-stu-id="66b83-137">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>  
  
4.  <span data-ttu-id="66b83-138">Ridimensionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> impostando una larghezza e un'altezza maggiori.</span><span class="sxs-lookup"><span data-stu-id="66b83-138">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>  
  
5.  <span data-ttu-id="66b83-139">Nel **casella degli strumenti**, fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nella prima cella del <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="66b83-139">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
     <span data-ttu-id="66b83-140">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="66b83-140">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
6.  <span data-ttu-id="66b83-141">Nel **casella degli strumenti**, fare doppio clic su `UserControl1` per creare un'altra istanza nella seconda cella del <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="66b83-141">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
7.  <span data-ttu-id="66b83-142">Nel **struttura documento** finestra selezionare `tableLayoutPanel1`.</span><span class="sxs-lookup"><span data-stu-id="66b83-142">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span> <span data-ttu-id="66b83-143">Per altre informazioni, vedere [finestra Struttura documento](https://msdn.microsoft.com/library/9054f2bc-f6f8-4242-9fe0-be71089b12f8).</span><span class="sxs-lookup"><span data-stu-id="66b83-143">For more information, see [Document Outline Window](https://msdn.microsoft.com/library/9054f2bc-f6f8-4242-9fe0-be71089b12f8).</span></span>  
  
8.  <span data-ttu-id="66b83-144">Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.Forms.Control.Padding%2A> proprietà `10, 10, 10, 10`.</span><span class="sxs-lookup"><span data-stu-id="66b83-144">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to `10, 10, 10, 10`.</span></span>  
  
     <span data-ttu-id="66b83-145">Entrambi i controlli <xref:System.Windows.Forms.Integration.ElementHost> vengono ridimensionati per essere adattati al nuovo layout.</span><span class="sxs-lookup"><span data-stu-id="66b83-145">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>  
  
## <a name="using-snaplines-to-align-wpf-controls"></a><span data-ttu-id="66b83-146">Allineamento dei controlli WPF mediante le guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="66b83-146">Using Snaplines to Align WPF Controls</span></span>  
 <span data-ttu-id="66b83-147">Le guide di allineamento semplificano l'allineamento dei controlli su un form.</span><span class="sxs-lookup"><span data-stu-id="66b83-147">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="66b83-148">È possibile usare le guide di allineamento anche per allineare i controlli WPF.</span><span class="sxs-lookup"><span data-stu-id="66b83-148">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="66b83-149">Per altre informazioni, vedere [procedura dettagliata: disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="66b83-149">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
#### <a name="to-use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="66b83-150">Per usare le guide di allineamento per allineare i controlli WPF</span><span class="sxs-lookup"><span data-stu-id="66b83-150">To use snaplines to align WPF controls</span></span>  
  
1.  <span data-ttu-id="66b83-151">Dal **casella degli strumenti**, trascinare un'istanza di `UserControl1` nel form e posizionarla nello spazio sotto la <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="66b83-151">From the **Toolbox**, drag an instance of `UserControl1` onto the form and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
     <span data-ttu-id="66b83-152">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="66b83-152">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>  
  
2.  <span data-ttu-id="66b83-153">Tramite le guide di allineamento allineare il bordo sinistro di `elementHost3` al bordo sinistro del controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="66b83-153">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3.  <span data-ttu-id="66b83-154">Tramite le guide di allineamento ridimensionare `elementHost3` impostando la stessa larghezza del controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="66b83-154">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
4.  <span data-ttu-id="66b83-155">Spostare `elementHost3` verso il controllo <xref:System.Windows.Forms.TableLayoutPanel> finché non viene visualizzata una guida di allineamento centrale tra i due controlli.</span><span class="sxs-lookup"><span data-stu-id="66b83-155">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>  
  
5.  <span data-ttu-id="66b83-156">Nel **delle proprietà** finestra, impostare il valore della proprietà Margin su `20, 20, 20, 20`.</span><span class="sxs-lookup"><span data-stu-id="66b83-156">In the **Properties** window, set the value of the Margin property to `20, 20, 20, 20`.</span></span>  
  
6.  <span data-ttu-id="66b83-157">Spostare `elementHost3` dal controllo <xref:System.Windows.Forms.TableLayoutPanel> finché non viene di nuovo visualizzata la guida di allineamento centrale.</span><span class="sxs-lookup"><span data-stu-id="66b83-157">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="66b83-158">La guida di allineamento centrale indica ora un margine di 20.</span><span class="sxs-lookup"><span data-stu-id="66b83-158">The center snapline now indicates a margin of 20.</span></span>  
  
7.  <span data-ttu-id="66b83-159">Spostare `elementHost3` verso destra fino ad allineare il bordo sinistro a quello di `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="66b83-159">Move `elementHost3` to the right, until its left edge aligns with the left edge of `elementHost1`.</span></span>  
  
8.  <span data-ttu-id="66b83-160">Modificare la larghezza di `elementHost3` finché il bordo destro non è allineato a quello destro di `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="66b83-160">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>  
  
## <a name="anchoring-and-docking-wpf-controls"></a><span data-ttu-id="66b83-161">Ancoraggio e aggancio di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="66b83-161">Anchoring and Docking WPF Controls</span></span>  
 <span data-ttu-id="66b83-162">Un controllo WPF incluso in un form è soggetto alle stesse regole di ancoraggio e aggancio degli altri controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="66b83-162">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>  
  
#### <a name="to-anchor-and-dock-wpf-controls"></a><span data-ttu-id="66b83-163">Per ancorare e agganciare i controlli WPF</span><span class="sxs-lookup"><span data-stu-id="66b83-163">To anchor and dock WPF controls</span></span>  
  
1.  <span data-ttu-id="66b83-164">Selezionare `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="66b83-164">Select `elementHost1`.</span></span>  
  
2.  <span data-ttu-id="66b83-165">Nel **le proprietà** impostare nella finestra di <xref:System.Windows.Forms.Control.Anchor%2A> proprietà **Top, Bottom, Left, Right**.</span><span class="sxs-lookup"><span data-stu-id="66b83-165">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>  
  
3.  <span data-ttu-id="66b83-166">Ridimensionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> impostando dimensioni superiori.</span><span class="sxs-lookup"><span data-stu-id="66b83-166">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>  
  
     <span data-ttu-id="66b83-167">Il controllo `elementHost1` verrà ridimensionato fino ad occupare l'intera cella.</span><span class="sxs-lookup"><span data-stu-id="66b83-167">The `elementHost1` control resizes to fill the cell.</span></span>  
  
4.  <span data-ttu-id="66b83-168">Selezionare `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="66b83-168">Select `elementHost2`.</span></span>  
  
5.  <span data-ttu-id="66b83-169">Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="66b83-169">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
     <span data-ttu-id="66b83-170">Il controllo `elementHost2` verrà ridimensionato fino ad occupare l'intera cella.</span><span class="sxs-lookup"><span data-stu-id="66b83-170">The `elementHost2` control resizes to fill the cell.</span></span>  
  
6.  <span data-ttu-id="66b83-171">Selezionare il controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="66b83-171">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
7.  <span data-ttu-id="66b83-172">Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Top>.</span><span class="sxs-lookup"><span data-stu-id="66b83-172">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>  
  
8.  <span data-ttu-id="66b83-173">Selezionare `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="66b83-173">Select `elementHost3`.</span></span>  
  
9. <span data-ttu-id="66b83-174">Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="66b83-174">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
     <span data-ttu-id="66b83-175">Il controllo `elementHost3` verrà ridimensionato fino a occupare lo spazio rimanente sul form.</span><span class="sxs-lookup"><span data-stu-id="66b83-175">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>  
  
10. <span data-ttu-id="66b83-176">Ridimensionare il form.</span><span class="sxs-lookup"><span data-stu-id="66b83-176">Resize the form.</span></span>  
  
     <span data-ttu-id="66b83-177">Tutti e tre i controlli <xref:System.Windows.Forms.Integration.ElementHost> verranno ridimensionati in maniera appropriata.</span><span class="sxs-lookup"><span data-stu-id="66b83-177">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>  
  
     <span data-ttu-id="66b83-178">Per altre informazioni, vedere [procedura: ancoraggio e ancorare controlli figlio in un controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span><span class="sxs-lookup"><span data-stu-id="66b83-178">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66b83-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66b83-179">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="66b83-180">Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="66b83-180">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="66b83-181">Procedura: Allineare un controllo ai bordi dei form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="66b83-181">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [<span data-ttu-id="66b83-182">Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="66b83-182">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="66b83-183">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="66b83-183">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="66b83-184">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="66b83-184">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="66b83-185">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="66b83-185">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
