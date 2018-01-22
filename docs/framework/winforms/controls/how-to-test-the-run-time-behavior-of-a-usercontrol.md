---
title: 'Procedura: eseguire il test del comportamento in fase di esecuzione di UserControl'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48b7c47a14f27439c60280a5c4202e9f4af76397
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="cf45f-102">Procedura: eseguire il test del comportamento in fase di esecuzione di UserControl</span><span class="sxs-lookup"><span data-stu-id="cf45f-102">How to: Test the Run-Time Behavior of a UserControl</span></span>
<span data-ttu-id="cf45f-103">Quando si sviluppa un <xref:System.Windows.Forms.UserControl>, è necessario testare il comportamento in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cf45f-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="cf45f-104">È possibile creare un progetto di applicazione separata basati su Windows e inserire il controllo in un form di test, ma questa procedura non è pratica.</span><span class="sxs-lookup"><span data-stu-id="cf45f-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="cf45f-105">Un modo più veloce e più semplice consiste nell'usare il **UserControl Test Container** fornite da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cf45f-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="cf45f-106">Questo contenitore di test viene avviata direttamente dal progetto libreria di controllo di Windows.</span><span class="sxs-lookup"><span data-stu-id="cf45f-106">This test container starts directly from your Windows control library project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf45f-107">Per il contenitore di test caricare il <xref:System.Windows.Forms.UserControl>, il controllo deve avere almeno un costruttore pubblico.</span><span class="sxs-lookup"><span data-stu-id="cf45f-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf45f-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="cf45f-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="cf45f-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="cf45f-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="cf45f-110">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="cf45f-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf45f-111">Non è possibile testare un controllo di Visual C++ tramite la **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="cf45f-111">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="cf45f-112">Per testare il comportamento in fase di esecuzione di UserControl</span><span class="sxs-lookup"><span data-stu-id="cf45f-112">To test the run-time behavior of a UserControl</span></span>  
  
1.  <span data-ttu-id="cf45f-113">Creare un progetto libreria di controlli Windows denominato **EsempioTestContainer**.</span><span class="sxs-lookup"><span data-stu-id="cf45f-113">Create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="cf45f-114">Per informazioni dettagliate, vedere [modello libreria di controlli Windows](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span><span class="sxs-lookup"><span data-stu-id="cf45f-114">For details, see [Windows Control Library Template](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="cf45f-115">Nel **Progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.Label> controllo il **della casella degli strumenti** nell'area di progettazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="cf45f-115">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3.  <span data-ttu-id="cf45f-116">Premere F5 per compilare il progetto ed eseguire il **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="cf45f-116">Press F5 to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="cf45f-117">Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nel **anteprima** riquadro.</span><span class="sxs-lookup"><span data-stu-id="cf45f-117">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4.  <span data-ttu-id="cf45f-118">Selezionare il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà visualizzata nella <xref:System.Windows.Forms.PropertyGrid> controllo a destra del **anteprima** riquadro.</span><span class="sxs-lookup"><span data-stu-id="cf45f-118">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="cf45f-119">Modificare il valore su `ControlDark`.</span><span class="sxs-lookup"><span data-stu-id="cf45f-119">Change its value to `ControlDark`.</span></span> <span data-ttu-id="cf45f-120">Osservare che il controllo di modifica di un colore più scuro.</span><span class="sxs-lookup"><span data-stu-id="cf45f-120">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="cf45f-121">Provare a modificare altri valori di proprietà e osservare l'effetto sul controllo.</span><span class="sxs-lookup"><span data-stu-id="cf45f-121">Try changing other property values and observe the effect on your control.</span></span>  
  
5.  <span data-ttu-id="cf45f-122">Fare clic su di **controllo utente Dock Fill** seguente casella di controllo di **anteprima** riquadro.</span><span class="sxs-lookup"><span data-stu-id="cf45f-122">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="cf45f-123">Osservare che il controllo viene ridimensionato per riempire il riquadro.</span><span class="sxs-lookup"><span data-stu-id="cf45f-123">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="cf45f-124">Ridimensionare il contenitore di test e osservare che il controllo viene ridimensionato con il riquadro.</span><span class="sxs-lookup"><span data-stu-id="cf45f-124">Resize the test container and observe that the control is resized with the pane.</span></span>  
  
6.  <span data-ttu-id="cf45f-125">Chiudere il contenitore di test.</span><span class="sxs-lookup"><span data-stu-id="cf45f-125">Close the test container.</span></span>  
  
7.  <span data-ttu-id="cf45f-126">Aggiungere un altro controllo utente per il **EsempioTestContainer** progetto.</span><span class="sxs-lookup"><span data-stu-id="cf45f-126">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="cf45f-127">Per informazioni dettagliate, vedere [NIB: procedura: aggiungere elementi esistenti a un progetto](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span><span class="sxs-lookup"><span data-stu-id="cf45f-127">For details, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span>  
  
8.  <span data-ttu-id="cf45f-128">Nel **Progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nell'area di progettazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="cf45f-128">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>  
  
9. <span data-ttu-id="cf45f-129">Premere F5 per compilare il progetto ed eseguire il test container.</span><span class="sxs-lookup"><span data-stu-id="cf45f-129">Press F5 to build the project and run the test container.</span></span>  
  
10. <span data-ttu-id="cf45f-130">Fare clic su di **Seleziona controllo utente** <xref:System.Windows.Forms.ComboBox> per passare tra i due controlli utente.</span><span class="sxs-lookup"><span data-stu-id="cf45f-130">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>  
  
## <a name="testing-user-controls-from-another-project"></a><span data-ttu-id="cf45f-131">Controlli utente da un altro progetto di test</span><span class="sxs-lookup"><span data-stu-id="cf45f-131">Testing User Controls from Another Project</span></span>  
 <span data-ttu-id="cf45f-132">È possibile testare i controlli utente da altri progetti nel contenitore di test del progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="cf45f-132">You can test user controls from other projects in your current project's test container.</span></span>  
  
#### <a name="to-test-user-controls-from-another-project"></a><span data-ttu-id="cf45f-133">Per testare i controlli utente da un altro progetto</span><span class="sxs-lookup"><span data-stu-id="cf45f-133">To test user controls from another project</span></span>  
  
1.  <span data-ttu-id="cf45f-134">Creare un progetto libreria di controlli Windows denominato **Esempiotestcontainer2**.</span><span class="sxs-lookup"><span data-stu-id="cf45f-134">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="cf45f-135">Per informazioni dettagliate, vedere [modello libreria di controlli Windows](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span><span class="sxs-lookup"><span data-stu-id="cf45f-135">For details, see [Windows Control Library Template](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="cf45f-136">Nel **Progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.RadioButton> controllo il **della casella degli strumenti** nell'area di progettazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="cf45f-136">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3.  <span data-ttu-id="cf45f-137">Premere F5 per compilare il progetto ed eseguire il test container.</span><span class="sxs-lookup"><span data-stu-id="cf45f-137">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="cf45f-138">Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nel **anteprima** riquadro.</span><span class="sxs-lookup"><span data-stu-id="cf45f-138">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4.  <span data-ttu-id="cf45f-139">Fare clic su di **carico** pulsante.</span><span class="sxs-lookup"><span data-stu-id="cf45f-139">Click the **Load** button.</span></span>  
  
5.  <span data-ttu-id="cf45f-140">Nel **aprire** finestra di dialogo passare a **EsempioTestContainer**. dll, che è incorporato nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="cf45f-140">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="cf45f-141">Selezionare **EsempioTestContainer**DLL e scegliere il **aprire** per caricare i controlli utente</span><span class="sxs-lookup"><span data-stu-id="cf45f-141">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>  
  
6.  <span data-ttu-id="cf45f-142">Utilizzare il **Seleziona controllo utente** <xref:System.Windows.Forms.ComboBox> per passare tra i due controlli utente dal **EsempioTestContainer** progetto.</span><span class="sxs-lookup"><span data-stu-id="cf45f-142">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf45f-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf45f-143">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 [<span data-ttu-id="cf45f-144">Procedura: Modificare controlli compositi</span><span class="sxs-lookup"><span data-stu-id="cf45f-144">How to: Author Composite Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [<span data-ttu-id="cf45f-145">Procedura dettagliata: modifica di un controllo composito con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf45f-145">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="cf45f-146">Procedura dettagliata: modifica di un controllo composito con Visual C#</span><span class="sxs-lookup"><span data-stu-id="cf45f-146">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [<span data-ttu-id="cf45f-147">Finestra di progettazione controlli utente</span><span class="sxs-lookup"><span data-stu-id="cf45f-147">User Control Designer</span></span>](http://msdn.microsoft.com/library/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)
