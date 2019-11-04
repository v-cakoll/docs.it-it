---
title: 'Procedura: eseguire il test del comportamento in fase di esecuzione di UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: be6c913c43e3559806bc9f38a9c3152b544e4c07
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455532"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="f67f9-102">Procedura: testare il comportamento della fase di esecuzione di UserControl</span><span class="sxs-lookup"><span data-stu-id="f67f9-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="f67f9-103">Quando si sviluppa una <xref:System.Windows.Forms.UserControl>, è necessario testarne il comportamento in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f67f9-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="f67f9-104">È possibile creare un progetto di applicazione basato su Windows separato e inserire il controllo in un form di test, ma questa procedura non è praticabile.</span><span class="sxs-lookup"><span data-stu-id="f67f9-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="f67f9-105">Un modo più rapido e semplice consiste nell'usare il **contenitore di test UserControl** fornito da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f67f9-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="f67f9-106">Questo contenitore di test viene avviato direttamente dal progetto libreria di controlli Windows.</span><span class="sxs-lookup"><span data-stu-id="f67f9-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f67f9-107">Affinché il contenitore di test carichi il <xref:System.Windows.Forms.UserControl>, il controllo deve avere almeno un costruttore pubblico.</span><span class="sxs-lookup"><span data-stu-id="f67f9-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="f67f9-108">Non è C++ possibile testare un controllo visivo utilizzando il **contenitore di test UserControl**.</span><span class="sxs-lookup"><span data-stu-id="f67f9-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="f67f9-109">Testare il comportamento in fase di esecuzione di un UserControl</span><span class="sxs-lookup"><span data-stu-id="f67f9-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="f67f9-110">In Visual Studio creare un progetto libreria di controlli Windows e denominarlo **EsempioTestContainer**.</span><span class="sxs-lookup"><span data-stu-id="f67f9-110">In Visual Studio, create a Windows control library project, and name it **TestContainerExample**.</span></span>

2. <span data-ttu-id="f67f9-111">Nella **Progettazione Windows Form**trascinare un controllo <xref:System.Windows.Forms.Label> dalla **casella degli strumenti** nell'area di progettazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="f67f9-111">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="f67f9-112">Premere <kbd>F5</kbd> per compilare il progetto ed eseguire il **contenitore di test UserControl**.</span><span class="sxs-lookup"><span data-stu-id="f67f9-112">Press <kbd>F5</kbd> to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="f67f9-113">Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nel riquadro di **Anteprima** .</span><span class="sxs-lookup"><span data-stu-id="f67f9-113">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="f67f9-114">Selezionare la proprietà <xref:System.Windows.Forms.Control.BackColor%2A> visualizzata nel controllo <xref:System.Windows.Forms.PropertyGrid> a destra del riquadro di **Anteprima** .</span><span class="sxs-lookup"><span data-stu-id="f67f9-114">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="f67f9-115">Modificare il valore in **ControlDark**.</span><span class="sxs-lookup"><span data-stu-id="f67f9-115">Change its value to **ControlDark**.</span></span> <span data-ttu-id="f67f9-116">Osservare che il controllo viene modificato in un colore più scuro.</span><span class="sxs-lookup"><span data-stu-id="f67f9-116">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="f67f9-117">Provare a modificare altri valori di proprietà e osservare l'effetto sul controllo.</span><span class="sxs-lookup"><span data-stu-id="f67f9-117">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="f67f9-118">Fare clic sulla casella di **controllo Dock Fill User Control** sotto il riquadro di **Anteprima** .</span><span class="sxs-lookup"><span data-stu-id="f67f9-118">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="f67f9-119">Si noti che il controllo viene ridimensionato per riempire il riquadro.</span><span class="sxs-lookup"><span data-stu-id="f67f9-119">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="f67f9-120">Ridimensionare il contenitore di test e osservare che il controllo viene ridimensionato con il riquadro.</span><span class="sxs-lookup"><span data-stu-id="f67f9-120">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="f67f9-121">Chiudere il contenitore di test.</span><span class="sxs-lookup"><span data-stu-id="f67f9-121">Close the test container.</span></span>

7. <span data-ttu-id="f67f9-122">Aggiungere un altro controllo utente al progetto **EsempioTestContainer** .</span><span class="sxs-lookup"><span data-stu-id="f67f9-122">Add another user control to the **TestContainerExample** project.</span></span>

8. <span data-ttu-id="f67f9-123">Nella **Progettazione Windows Form**trascinare un controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nell'area di progettazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="f67f9-123">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="f67f9-124">Premere <kbd>F5</kbd> per compilare il progetto ed eseguire il contenitore di test.</span><span class="sxs-lookup"><span data-stu-id="f67f9-124">Press <kbd>F5</kbd> to build the project and run the test container.</span></span>

10. <span data-ttu-id="f67f9-125">Fare clic sull'<xref:System.Windows.Forms.ComboBox> **selezionare il controllo utente** per passare tra i due controlli utente.</span><span class="sxs-lookup"><span data-stu-id="f67f9-125">Click the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="f67f9-126">Testare i controlli utente da un altro progetto</span><span class="sxs-lookup"><span data-stu-id="f67f9-126">Test user controls from another project</span></span>

<span data-ttu-id="f67f9-127">È possibile testare i controlli utente da altri progetti nel contenitore di test del progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="f67f9-127">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="f67f9-128">In Visual Studio creare un progetto libreria di controlli Windows e denominarlo **EsempioTestContainer2**.</span><span class="sxs-lookup"><span data-stu-id="f67f9-128">In Visual Studio, create a Windows control library project, and name it **TestContainerExample2**.</span></span>

2. <span data-ttu-id="f67f9-129">Nella **Progettazione Windows Form**trascinare un controllo <xref:System.Windows.Forms.RadioButton> dalla **casella degli strumenti** nell'area di progettazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="f67f9-129">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="f67f9-130">Premere <kbd>F5</kbd> per compilare il progetto ed eseguire il contenitore di test.</span><span class="sxs-lookup"><span data-stu-id="f67f9-130">Press <kbd>F5</kbd> to build the project and run the test container.</span></span> <span data-ttu-id="f67f9-131">Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nel riquadro di **Anteprima** .</span><span class="sxs-lookup"><span data-stu-id="f67f9-131">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="f67f9-132">Fare clic sul pulsante **carica** .</span><span class="sxs-lookup"><span data-stu-id="f67f9-132">Click the **Load** button.</span></span>

5. <span data-ttu-id="f67f9-133">Nella finestra di dialogo **Apri** passare a *EsempioTestContainer. dll*compilato nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="f67f9-133">In the **Open** dialog box, navigate to *TestContainerExample.dll*, which you built in the previous procedure.</span></span> <span data-ttu-id="f67f9-134">Selezionare *EsempioTestContainer. dll* e fare clic sul pulsante **Apri** per caricare i controlli utente.</span><span class="sxs-lookup"><span data-stu-id="f67f9-134">Select *TestContainerExample.dll* and click the **Open** button to load the user controls.</span></span>

6. <span data-ttu-id="f67f9-135">Usare il <xref:System.Windows.Forms.ComboBox> **selezionare il controllo utente** per passare tra i due controlli utente dal progetto **EsempioTestContainer** .</span><span class="sxs-lookup"><span data-stu-id="f67f9-135">Use the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="f67f9-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f67f9-136">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="f67f9-137">Procedura: Modificare controlli compositi</span><span class="sxs-lookup"><span data-stu-id="f67f9-137">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="f67f9-138">Procedura dettagliata: modifica di un controllo composito</span><span class="sxs-lookup"><span data-stu-id="f67f9-138">Walkthrough: Authoring a Composite Control</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="f67f9-139">[Progettazione controllo utente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f67f9-139">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
