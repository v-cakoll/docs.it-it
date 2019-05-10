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
ms.openlocfilehash: 48531ab1ef3b30b6516e3f2e7b5858a8884cbfe8
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211698"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="04999-102">Procedura: Testare il comportamento in fase di esecuzione di UserControl</span><span class="sxs-lookup"><span data-stu-id="04999-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="04999-103">Quando si sviluppa un <xref:System.Windows.Forms.UserControl>, è necessario testarne il comportamento in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="04999-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="04999-104">È possibile creare un progetto di applicazione basata su Windows separato e posizionare il controllo in un modulo di test, ma questa procedura non è pratica.</span><span class="sxs-lookup"><span data-stu-id="04999-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="04999-105">Un modo più veloce e più semplice consiste nell'usare la **UserControl Test Container** offerte da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04999-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="04999-106">Questo contenitore di test viene avviata direttamente dal progetto di libreria di controlli Windows.</span><span class="sxs-lookup"><span data-stu-id="04999-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04999-107">Per il contenitore di test caricare il <xref:System.Windows.Forms.UserControl>, il controllo deve avere almeno un costruttore pubblico.</span><span class="sxs-lookup"><span data-stu-id="04999-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="04999-108">Non è possibile testare un controllo di Visual C++ utilizzando la **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="04999-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="04999-109">Testare il comportamento in fase di esecuzione di UserControl</span><span class="sxs-lookup"><span data-stu-id="04999-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="04999-110">In Visual Studio, creare un progetto di libreria di controlli di Windows denominato **EsempioTestContainer**.</span><span class="sxs-lookup"><span data-stu-id="04999-110">In Visual Studio, create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="04999-111">Per informazioni dettagliate, vedere [modello di libreria di controllo di Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="04999-111">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="04999-112">Nel **finestra di progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.Label> controllare dal **casella degli strumenti** nell'area di progettazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="04999-112">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="04999-113">Premere **F5** per compilare il progetto ed eseguire il **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="04999-113">Press **F5** to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="04999-114">Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nella **anteprima** riquadro.</span><span class="sxs-lookup"><span data-stu-id="04999-114">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="04999-115">Selezionare il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà visualizzata nel <xref:System.Windows.Forms.PropertyGrid> a destra del controllo il **anteprima** riquadro.</span><span class="sxs-lookup"><span data-stu-id="04999-115">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="04999-116">Modificare il relativo valore su `ControlDark`.</span><span class="sxs-lookup"><span data-stu-id="04999-116">Change its value to `ControlDark`.</span></span> <span data-ttu-id="04999-117">Osservare che modifica un colore più scuro del controllo.</span><span class="sxs-lookup"><span data-stu-id="04999-117">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="04999-118">Provare a modificare altri valori di proprietà e osservare gli effetti sul controllo.</span><span class="sxs-lookup"><span data-stu-id="04999-118">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="04999-119">Fare clic sul **controllo utente Dock Fill** casella di controllo sotto il **anteprima** riquadro.</span><span class="sxs-lookup"><span data-stu-id="04999-119">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="04999-120">Osservare che il controllo viene ridimensionato per riempire il riquadro.</span><span class="sxs-lookup"><span data-stu-id="04999-120">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="04999-121">Ridimensionare il contenitore di test e osservare che il controllo viene ridimensionato con il riquadro.</span><span class="sxs-lookup"><span data-stu-id="04999-121">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="04999-122">Chiudere il contenitore di test.</span><span class="sxs-lookup"><span data-stu-id="04999-122">Close the test container.</span></span>

7. <span data-ttu-id="04999-123">Aggiungere un altro controllo utente per il **EsempioTestContainer** progetto.</span><span class="sxs-lookup"><span data-stu-id="04999-123">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="04999-124">Per informazioni dettagliate, vedere [Procedura: Aggiungere elementi esistenti a un progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="04999-124">For details, see [How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span></span>

8. <span data-ttu-id="04999-125">Nel **finestra di progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** nell'area di progettazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="04999-125">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="04999-126">Premere F5 per compilare il progetto ed eseguire il contenitore di test.</span><span class="sxs-lookup"><span data-stu-id="04999-126">Press F5 to build the project and run the test container.</span></span>

10. <span data-ttu-id="04999-127">Scegliere il **selezionare controllo utente** <xref:System.Windows.Forms.ComboBox> passare tra i due controlli utente.</span><span class="sxs-lookup"><span data-stu-id="04999-127">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="04999-128">Controlli utente di test da un altro progetto</span><span class="sxs-lookup"><span data-stu-id="04999-128">Test user controls from another project</span></span>

<span data-ttu-id="04999-129">È possibile testare i controlli utente da altri progetti nel contenitore di test del progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="04999-129">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="04999-130">Creare un progetto di libreria di controlli di Windows denominato **Esempiotestcontainer2**.</span><span class="sxs-lookup"><span data-stu-id="04999-130">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="04999-131">Per informazioni dettagliate, vedere [modello di libreria di controllo di Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="04999-131">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="04999-132">Nel **finestra di progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.RadioButton> controllare dal **casella degli strumenti** nell'area di progettazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="04999-132">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="04999-133">Premere F5 per compilare il progetto ed eseguire il contenitore di test.</span><span class="sxs-lookup"><span data-stu-id="04999-133">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="04999-134">Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nella **anteprima** riquadro.</span><span class="sxs-lookup"><span data-stu-id="04999-134">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="04999-135">Scegliere il **carico** pulsante.</span><span class="sxs-lookup"><span data-stu-id="04999-135">Click the **Load** button.</span></span>

5. <span data-ttu-id="04999-136">Nel **aperto** finestra di dialogo passare alla **EsempioTestContainer**. dll, che è stata compilata nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="04999-136">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="04999-137">Selezionare **EsempioTestContainer**DLL e fare clic sui **Open** pulsante per caricare i controlli utente</span><span class="sxs-lookup"><span data-stu-id="04999-137">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>

6. <span data-ttu-id="04999-138">Usare la **selezionare controllo utente** <xref:System.Windows.Forms.ComboBox> per passare tra i due controlli utente dal **EsempioTestContainer** progetto.</span><span class="sxs-lookup"><span data-stu-id="04999-138">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="04999-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04999-139">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="04999-140">Procedura: Modificare controlli compositi</span><span class="sxs-lookup"><span data-stu-id="04999-140">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="04999-141">Procedura dettagliata: Modifica di un controllo composito con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04999-141">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="04999-142">Procedura dettagliata: Modifica di un controllo composito con VisualC#</span><span class="sxs-lookup"><span data-stu-id="04999-142">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="04999-143">[Progettazione controllo utente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="04999-143">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
