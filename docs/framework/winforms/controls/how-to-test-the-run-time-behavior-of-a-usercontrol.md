---
title: 'Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 15b37c71e6643b588c0378510965a9a3e7cb56e9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321770"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="e7b79-102">Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl</span><span class="sxs-lookup"><span data-stu-id="e7b79-102">How to: Test the Run-Time Behavior of a UserControl</span></span>
<span data-ttu-id="e7b79-103">Quando si sviluppa un <xref:System.Windows.Forms.UserControl>, è necessario testarne il comportamento in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e7b79-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="e7b79-104">È possibile creare un progetto di applicazione basata su Windows separato e posizionare il controllo in un modulo di test, ma questa procedura non è pratica.</span><span class="sxs-lookup"><span data-stu-id="e7b79-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="e7b79-105">Un modo più veloce e più semplice consiste nell'usare la **UserControl Test Container** offerte da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e7b79-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="e7b79-106">Questo contenitore di test viene avviata direttamente dal progetto di libreria di controlli Windows.</span><span class="sxs-lookup"><span data-stu-id="e7b79-106">This test container starts directly from your Windows control library project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e7b79-107">Per il contenitore di test caricare il <xref:System.Windows.Forms.UserControl>, il controllo deve avere almeno un costruttore pubblico.</span><span class="sxs-lookup"><span data-stu-id="e7b79-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7b79-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="e7b79-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e7b79-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="e7b79-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e7b79-110">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="e7b79-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7b79-111">Non è possibile testare un controllo di Visual C++ utilizzando la **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="e7b79-111">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="e7b79-112">Per testare il comportamento in fase di esecuzione di UserControl</span><span class="sxs-lookup"><span data-stu-id="e7b79-112">To test the run-time behavior of a UserControl</span></span>  
  
1. <span data-ttu-id="e7b79-113">Creare un progetto di libreria di controlli di Windows denominato **EsempioTestContainer**.</span><span class="sxs-lookup"><span data-stu-id="e7b79-113">Create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="e7b79-114">Per informazioni dettagliate, vedere [modello di libreria di controllo di Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e7b79-114">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="e7b79-115">Nel **finestra di progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.Label> controllare dal **casella degli strumenti** nell'area di progettazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="e7b79-115">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3. <span data-ttu-id="e7b79-116">Premere F5 per compilare il progetto ed eseguire la **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="e7b79-116">Press F5 to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="e7b79-117">Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nella **anteprima** riquadro.</span><span class="sxs-lookup"><span data-stu-id="e7b79-117">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4. <span data-ttu-id="e7b79-118">Selezionare il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà visualizzata nel <xref:System.Windows.Forms.PropertyGrid> a destra del controllo il **anteprima** riquadro.</span><span class="sxs-lookup"><span data-stu-id="e7b79-118">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="e7b79-119">Modificare il relativo valore su `ControlDark`.</span><span class="sxs-lookup"><span data-stu-id="e7b79-119">Change its value to `ControlDark`.</span></span> <span data-ttu-id="e7b79-120">Osservare che modifica un colore più scuro del controllo.</span><span class="sxs-lookup"><span data-stu-id="e7b79-120">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="e7b79-121">Provare a modificare altri valori di proprietà e osservare gli effetti sul controllo.</span><span class="sxs-lookup"><span data-stu-id="e7b79-121">Try changing other property values and observe the effect on your control.</span></span>  
  
5. <span data-ttu-id="e7b79-122">Fare clic sul **controllo utente Dock Fill** casella di controllo sotto il **anteprima** riquadro.</span><span class="sxs-lookup"><span data-stu-id="e7b79-122">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="e7b79-123">Osservare che il controllo viene ridimensionato per riempire il riquadro.</span><span class="sxs-lookup"><span data-stu-id="e7b79-123">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="e7b79-124">Ridimensionare il contenitore di test e osservare che il controllo viene ridimensionato con il riquadro.</span><span class="sxs-lookup"><span data-stu-id="e7b79-124">Resize the test container and observe that the control is resized with the pane.</span></span>  
  
6. <span data-ttu-id="e7b79-125">Chiudere il contenitore di test.</span><span class="sxs-lookup"><span data-stu-id="e7b79-125">Close the test container.</span></span>  
  
7. <span data-ttu-id="e7b79-126">Aggiungere un altro controllo utente per il **EsempioTestContainer** progetto.</span><span class="sxs-lookup"><span data-stu-id="e7b79-126">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="e7b79-127">Per informazioni dettagliate, vedere [Procedura: Aggiungere elementi esistenti a un progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e7b79-127">For details, see [How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span></span>  
  
8. <span data-ttu-id="e7b79-128">Nel **finestra di progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** nell'area di progettazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="e7b79-128">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>  
  
9. <span data-ttu-id="e7b79-129">Premere F5 per compilare il progetto ed eseguire il contenitore di test.</span><span class="sxs-lookup"><span data-stu-id="e7b79-129">Press F5 to build the project and run the test container.</span></span>  
  
10. <span data-ttu-id="e7b79-130">Scegliere il **selezionare controllo utente** <xref:System.Windows.Forms.ComboBox> passare tra i due controlli utente.</span><span class="sxs-lookup"><span data-stu-id="e7b79-130">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>  
  
## <a name="testing-user-controls-from-another-project"></a><span data-ttu-id="e7b79-131">Controlli utente da un altro progetto di test</span><span class="sxs-lookup"><span data-stu-id="e7b79-131">Testing User Controls from Another Project</span></span>  
 <span data-ttu-id="e7b79-132">È possibile testare i controlli utente da altri progetti nel contenitore di test del progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="e7b79-132">You can test user controls from other projects in your current project's test container.</span></span>  
  
#### <a name="to-test-user-controls-from-another-project"></a><span data-ttu-id="e7b79-133">Per testare i controlli utente da un altro progetto</span><span class="sxs-lookup"><span data-stu-id="e7b79-133">To test user controls from another project</span></span>  
  
1. <span data-ttu-id="e7b79-134">Creare un progetto di libreria di controlli di Windows denominato **Esempiotestcontainer2**.</span><span class="sxs-lookup"><span data-stu-id="e7b79-134">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="e7b79-135">Per informazioni dettagliate, vedere [modello di libreria di controllo di Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e7b79-135">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="e7b79-136">Nel **finestra di progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.RadioButton> controllare dal **casella degli strumenti** nell'area di progettazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="e7b79-136">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3. <span data-ttu-id="e7b79-137">Premere F5 per compilare il progetto ed eseguire il contenitore di test.</span><span class="sxs-lookup"><span data-stu-id="e7b79-137">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="e7b79-138">Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nella **anteprima** riquadro.</span><span class="sxs-lookup"><span data-stu-id="e7b79-138">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4. <span data-ttu-id="e7b79-139">Scegliere il **carico** pulsante.</span><span class="sxs-lookup"><span data-stu-id="e7b79-139">Click the **Load** button.</span></span>  
  
5. <span data-ttu-id="e7b79-140">Nel **aperto** finestra di dialogo passare alla **EsempioTestContainer**. dll, che è stata compilata nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="e7b79-140">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="e7b79-141">Selezionare **EsempioTestContainer**DLL e fare clic sui **Open** pulsante per caricare i controlli utente</span><span class="sxs-lookup"><span data-stu-id="e7b79-141">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>  
  
6. <span data-ttu-id="e7b79-142">Usare la **selezionare controllo utente** <xref:System.Windows.Forms.ComboBox> per passare tra i due controlli utente dal **EsempioTestContainer** progetto.</span><span class="sxs-lookup"><span data-stu-id="e7b79-142">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b79-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7b79-143">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="e7b79-144">Procedura: Creare controlli compositi</span><span class="sxs-lookup"><span data-stu-id="e7b79-144">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="e7b79-145">Procedura dettagliata: Creazione di un controllo composito con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b79-145">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="e7b79-146">Procedura dettagliata: Modifica di un controllo composito con Visual C#</span><span class="sxs-lookup"><span data-stu-id="e7b79-146">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [<span data-ttu-id="e7b79-147">Progettazione controllo utente</span><span class="sxs-lookup"><span data-stu-id="e7b79-147">User Control Designer</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))
