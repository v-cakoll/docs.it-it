---
title: 'Procedura: modificare controlli compositi'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 42ea424507b89576df8099fd4849dd2665135a55
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459431"
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="cc6db-102">Procedura: creare controlli compositi</span><span class="sxs-lookup"><span data-stu-id="cc6db-102">How to: Author composite controls</span></span>

<span data-ttu-id="cc6db-103">I controlli compositi possono essere usati in molti modi.</span><span class="sxs-lookup"><span data-stu-id="cc6db-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="cc6db-104">È possibile crearli come parte di un progetto applicazione desktop di Windows e usarli solo sui form del progetto.</span><span class="sxs-lookup"><span data-stu-id="cc6db-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="cc6db-105">Oppure è possibile crearli in un progetto libreria di controlli Windows, compilare il progetto in un assembly e usare i controlli in altri progetti.</span><span class="sxs-lookup"><span data-stu-id="cc6db-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="cc6db-106">È anche possibile ereditare da essi e usare l'ereditarietà visiva per personalizzarli rapidamente per scopi specifici.</span><span class="sxs-lookup"><span data-stu-id="cc6db-106">You can even inherit from them and use visual inheritance to customize them quickly for special purposes.</span></span>

## <a name="to-author-a-composite-control"></a><span data-ttu-id="cc6db-107">Per creare un controllo composito</span><span class="sxs-lookup"><span data-stu-id="cc6db-107">To author a composite control</span></span>

1. <span data-ttu-id="cc6db-108">In Visual Studio creare un nuovo progetto di **applicazione Windows** e denominarlo **DemoControlHost**.</span><span class="sxs-lookup"><span data-stu-id="cc6db-108">In Visual Studio, create a new **Windows Application** project, and name it **DemoControlHost**.</span></span>

2. <span data-ttu-id="cc6db-109">Nel menu **Progetto** fare clic su **Aggiungi controllo utente**.</span><span class="sxs-lookup"><span data-stu-id="cc6db-109">On the **Project** menu, click **Add User Control**.</span></span>

3. <span data-ttu-id="cc6db-110">Nella finestra di dialogo **Aggiungi nuovo elemento** assegnare al file di classe (file con estensione .vb o .cs) il nome che si desidera assegnare al controllo composito.</span><span class="sxs-lookup"><span data-stu-id="cc6db-110">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>

4. <span data-ttu-id="cc6db-111">Selezionare il pulsante **Aggiungi** per creare il file di classe per il controllo composito.</span><span class="sxs-lookup"><span data-stu-id="cc6db-111">Select the **Add** button to create the class file for the composite control.</span></span>

5. <span data-ttu-id="cc6db-112">Aggiungere controlli dalla **Casella degli strumenti** alla superficie del controllo composito.</span><span class="sxs-lookup"><span data-stu-id="cc6db-112">Add controls from the **Toolbox** to the composite control surface.</span></span>

6. <span data-ttu-id="cc6db-113">Inserire codice nella routine evento per gestire gli eventi generati dal controllo composito o dai relativi controlli costitutivi.</span><span class="sxs-lookup"><span data-stu-id="cc6db-113">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>

7. <span data-ttu-id="cc6db-114">Chiudere la finestra di progettazione per il controllo composito e salvare il file quando viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="cc6db-114">Close the designer for the composite control, and save the file when you are prompted.</span></span>

8. <span data-ttu-id="cc6db-115">Scegliere **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="cc6db-115">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="cc6db-116">Il progetto deve essere compilato affinché i controlli personalizzati siano visualizzati nella **Casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="cc6db-116">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>

9. <span data-ttu-id="cc6db-117">Usare la scheda **DemoControlHost** della **Casella degli strumenti** per aggiungere istanze del controllo a `Form1`.</span><span class="sxs-lookup"><span data-stu-id="cc6db-117">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>

## <a name="to-author-a-control-class-library"></a><span data-ttu-id="cc6db-118">Per creare una libreria di classi del controllo</span><span class="sxs-lookup"><span data-stu-id="cc6db-118">To author a control class library</span></span>

1. <span data-ttu-id="cc6db-119">Aprire un nuovo progetto **Libreria di controlli Windows**.</span><span class="sxs-lookup"><span data-stu-id="cc6db-119">Open a new **Windows Control Library** project.</span></span>

     <span data-ttu-id="cc6db-120">Per impostazione predefinita, il progetto contiene un controllo composito.</span><span class="sxs-lookup"><span data-stu-id="cc6db-120">By default, the project contains a composite control.</span></span>

2. <span data-ttu-id="cc6db-121">Aggiungere controlli e codice, come descritto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="cc6db-121">Add controls and code as described in the procedure above.</span></span>

3. <span data-ttu-id="cc6db-122">Scegliere un controllo che non si desidera venga modificato dalle classi che ereditano e impostare la proprietà **Modifiers** del controllo su **Private**.</span><span class="sxs-lookup"><span data-stu-id="cc6db-122">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>

4. <span data-ttu-id="cc6db-123">Compilare la DLL.</span><span class="sxs-lookup"><span data-stu-id="cc6db-123">Build the DLL.</span></span>

## <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="cc6db-124">Per ereditare da un controllo composito in una libreria di classi del controllo</span><span class="sxs-lookup"><span data-stu-id="cc6db-124">To inherit from a composite control in a control class library</span></span>

1. <span data-ttu-id="cc6db-125">Nel menu **File** puntare su **Aggiungi** e selezionare **Nuovo progetto** per aggiungere un nuovo progetto **Windows Application** alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="cc6db-125">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>

2. <span data-ttu-id="cc6db-126">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sulla cartella **Riferimenti** del nuovo progetto e scegliere **Aggiungi riferimento** per aprire la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="cc6db-126">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

3. <span data-ttu-id="cc6db-127">Selezionare la scheda **Progetti** e fare doppio clic sul progetto libreria di controlli.</span><span class="sxs-lookup"><span data-stu-id="cc6db-127">Select the **Projects** tab and double-click your control library project.</span></span>

4. <span data-ttu-id="cc6db-128">Scegliere **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="cc6db-128">On the **Build** menu, click **Build Solution**.</span></span>

5. <span data-ttu-id="cc6db-129">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto libreria di controlli e selezionare **Aggiungi nuovo elemento** nel menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="cc6db-129">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>

6. <span data-ttu-id="cc6db-130">Selezionare il modello **Controllo utente ereditato** dalla finestra di dialogo **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="cc6db-130">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>

7. <span data-ttu-id="cc6db-131">Nella finestra di dialogo **Selezione ereditarietà** fare doppio clic sul controllo da cui si desidera ereditare.</span><span class="sxs-lookup"><span data-stu-id="cc6db-131">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>

     <span data-ttu-id="cc6db-132">Un nuovo controllo viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="cc6db-132">A new control is added to your project.</span></span>

8. <span data-ttu-id="cc6db-133">Aprire la finestra di progettazione visiva per il nuovo controllo e aggiungere altri controlli costitutivi.</span><span class="sxs-lookup"><span data-stu-id="cc6db-133">Open the visual designer for the new control and add additional constituent controls.</span></span>

     <span data-ttu-id="cc6db-134">È possibile visualizzare i controlli costitutivi ereditati dal controllo composito nella DLL ed è possibile modificare le proprietà dei controlli la cui proprietà **Modifiers** è **Public**.</span><span class="sxs-lookup"><span data-stu-id="cc6db-134">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="cc6db-135">Non è possibile modificare le proprietà del controllo la cui proprietà **Modifiers** è **Private**.</span><span class="sxs-lookup"><span data-stu-id="cc6db-135">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc6db-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc6db-136">See also</span></span>

- [<span data-ttu-id="cc6db-137">Procedura dettagliata: modifica di un controllo composito</span><span class="sxs-lookup"><span data-stu-id="cc6db-137">Walkthrough: Authoring a Composite Control</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [<span data-ttu-id="cc6db-138">Procedura dettagliata: eredità da un controllo Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc6db-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [<span data-ttu-id="cc6db-139">Consigli sui tipi di controlli</span><span class="sxs-lookup"><span data-stu-id="cc6db-139">Control Type Recommendations</span></span>](control-type-recommendations.md)
- [<span data-ttu-id="cc6db-140">Procedura: Creare controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="cc6db-140">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="cc6db-141">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="cc6db-141">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
