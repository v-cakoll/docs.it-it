---
title: 'Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 6ecf69350b8337dc6049b73251809192b47dc2fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59338098"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="c4150-102">Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="c4150-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>
<span data-ttu-id="c4150-103">Se i componenti vengono definiti da un progetto nella soluzione attualmente aperta, verranno automaticamente visualizzati nei **casella degli strumenti**, senza alcun intervento da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c4150-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="c4150-104">È anche possibile inserire manualmente il **casella degli strumenti** con i componenti personalizzati usando la [Scegli elementi della finestra della casella (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), ma il **della casella degli strumenti** tengano conto elementi della soluzione di output con tutte le caratteristiche seguenti di compilazione:</span><span class="sxs-lookup"><span data-stu-id="c4150-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>  
  
-   <span data-ttu-id="c4150-105">Implementa <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="c4150-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>  
  
-   <span data-ttu-id="c4150-106">Non dispone <xref:System.ComponentModel.ToolboxItemAttribute> impostato su `false`;</span><span class="sxs-lookup"><span data-stu-id="c4150-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>  
  
-   <span data-ttu-id="c4150-107">Non dispone <xref:System.ComponentModel.DesignTimeVisibleAttribute> impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="c4150-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4150-108">Il **casella degli strumenti** non rispetta le catene di riferimento, in modo da non visualizzerà gli elementi che non vengono compilati da un progetto nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="c4150-108">The **Toolbox** does not follow reference chains, so it will not display items that are not built by a project in your solution.</span></span>  
  
 <span data-ttu-id="c4150-109">Questa procedura dettagliata illustra come un componente personalizzato viene visualizzato automaticamente nel **casella degli strumenti** dopo aver compilato il componente.</span><span class="sxs-lookup"><span data-stu-id="c4150-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="c4150-110">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4150-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="c4150-111">Creazione di un progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c4150-111">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="c4150-112">Creazione di un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c4150-112">Creating a custom component.</span></span>  
  
-   <span data-ttu-id="c4150-113">Creazione di un'istanza di un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c4150-113">Creating an instance of a custom component.</span></span>  
  
-   <span data-ttu-id="c4150-114">Scaricare e ricaricare un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c4150-114">Unloading and reloading a custom component.</span></span>  
  
 <span data-ttu-id="c4150-115">Al termine, si noterà che il **casella degli strumenti** viene popolato con un componente che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="c4150-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4150-116">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="c4150-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c4150-117">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="c4150-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c4150-118">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="c4150-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="c4150-119">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="c4150-119">Creating the Project</span></span>  
 <span data-ttu-id="c4150-120">Il primo passaggio indica come creare il progetto e impostare il modulo.</span><span class="sxs-lookup"><span data-stu-id="c4150-120">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="c4150-121">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="c4150-121">To create the project</span></span>  
  
1. <span data-ttu-id="c4150-122">Creare un progetto di applicazione basata su Windows denominato `ToolboxExample` (**File** > **New** > **progetto**  >  **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="c4150-122">Create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="c4150-123">Aggiungere un nuovo componente al progetto.</span><span class="sxs-lookup"><span data-stu-id="c4150-123">Add a new component to the project.</span></span> <span data-ttu-id="c4150-124">nominarla `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="c4150-124">Call it `DemoComponent`.</span></span>  
  
     <span data-ttu-id="c4150-125">Per altre informazioni, vedere [Procedura: Aggiungere nuovi elementi di progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c4150-125">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>  
  
3. <span data-ttu-id="c4150-126">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="c4150-126">Build the project.</span></span>  
  
4. <span data-ttu-id="c4150-127">Dal **degli strumenti** menu, fare clic sul **opzioni** elemento.</span><span class="sxs-lookup"><span data-stu-id="c4150-127">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="c4150-128">Fare clic su **generali** sotto il **progettazione di Windows Form** e verificare che il **AutoToolboxPopulate** opzione è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="c4150-128">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>  
  
## <a name="creating-an-instance-of-a-custom-component"></a><span data-ttu-id="c4150-129">Creazione di un'istanza di un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="c4150-129">Creating an Instance of a Custom Component</span></span>  
 <span data-ttu-id="c4150-130">Il passaggio successivo consiste nel creare un'istanza del componente personalizzato nel modulo.</span><span class="sxs-lookup"><span data-stu-id="c4150-130">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="c4150-131">Poiché il **casella degli strumenti** automaticamente gli account per il nuovo componente, è semplice come la creazione di qualsiasi altro componente o controllo.</span><span class="sxs-lookup"><span data-stu-id="c4150-131">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a><span data-ttu-id="c4150-132">Per creare un'istanza di un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="c4150-132">To create an instance of a custom component</span></span>  
  
1. <span data-ttu-id="c4150-133">Aprire il form del progetto nel **progettazione form**.</span><span class="sxs-lookup"><span data-stu-id="c4150-133">Open the project's form in the **Forms Designer**.</span></span>  
  
2. <span data-ttu-id="c4150-134">Nel **casella degli strumenti**, fare clic sulla scheda nuovo chiamata **Componenti ToolboxExample**.</span><span class="sxs-lookup"><span data-stu-id="c4150-134">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>  
  
     <span data-ttu-id="c4150-135">Dopo aver selezionato la scheda, si noterà **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="c4150-135">Once you click the tab, you will see **DemoComponent**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4150-136">Per motivi di prestazioni, i componenti nell'area popolato automaticamente della **casella degli strumenti** non vengono visualizzate le bitmap personalizzate e <xref:System.Drawing.ToolboxBitmapAttribute> non è supportato.</span><span class="sxs-lookup"><span data-stu-id="c4150-136">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="c4150-137">Per visualizzare un'icona per un componente personalizzato nella **casella degli strumenti**, utilizzare il **Scegli elementi della casella degli strumenti** finestra di dialogo per caricare il componente.</span><span class="sxs-lookup"><span data-stu-id="c4150-137">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>  
  
3. <span data-ttu-id="c4150-138">Trascinare il componente al form.</span><span class="sxs-lookup"><span data-stu-id="c4150-138">Drag your component onto your form.</span></span>  
  
     <span data-ttu-id="c4150-139">Viene creata e aggiunto a un'istanza del componente di **sulla barra dei componenti**.</span><span class="sxs-lookup"><span data-stu-id="c4150-139">An instance of the component is created and added to the **Component Tray**.</span></span>  
  
## <a name="unloading-and-reloading-a-custom-component"></a><span data-ttu-id="c4150-140">Scaricare e ricaricare un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="c4150-140">Unloading and Reloading a Custom Component</span></span>  
 <span data-ttu-id="c4150-141">Il **casella degli strumenti** tengano conto dei componenti in ogni progetto di caricamento e quando viene scaricato un progetto, vengono rimossi i riferimenti ai componenti del progetto.</span><span class="sxs-lookup"><span data-stu-id="c4150-141">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a><span data-ttu-id="c4150-142">Per sperimentare l'effetto della casella degli strumenti di scaricamento e il ricaricamento di componenti</span><span class="sxs-lookup"><span data-stu-id="c4150-142">To experiment with the effect on the Toolbox of unloading and reloading components</span></span>  
  
1. <span data-ttu-id="c4150-143">Scaricare il progetto dalla soluzione.</span><span class="sxs-lookup"><span data-stu-id="c4150-143">Unload the project from the solution.</span></span>  
  
     <span data-ttu-id="c4150-144">Per altre informazioni sullo scaricamento dei progetti, vedere [come: Scaricare e ricaricare i progetti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c4150-144">For more information about unloading projects, see [How to: Unload and Reload Projects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="c4150-145">Se viene chiesto di salvare, scegliere **Sì**.</span><span class="sxs-lookup"><span data-stu-id="c4150-145">If you are prompted to save, choose **Yes**.</span></span>  
  
2. <span data-ttu-id="c4150-146">Aggiungere un nuovo **applicazioni Windows** progetto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="c4150-146">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="c4150-147">Aprire il form nel **progettazione**.</span><span class="sxs-lookup"><span data-stu-id="c4150-147">Open the form in the **Designer**.</span></span>  
  
     <span data-ttu-id="c4150-148">Il **Componenti ToolboxExample** scheda dal progetto precedente è stata ancora attivo.</span><span class="sxs-lookup"><span data-stu-id="c4150-148">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>  
  
3. <span data-ttu-id="c4150-149">Ricarica il `ToolboxExample` progetto.</span><span class="sxs-lookup"><span data-stu-id="c4150-149">Reload the `ToolboxExample` project.</span></span>  
  
     <span data-ttu-id="c4150-150">Il **Componenti ToolboxExample** scheda ora viene visualizzata di nuovo.</span><span class="sxs-lookup"><span data-stu-id="c4150-150">The **ToolboxExample Components** tab now reappears.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c4150-151">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c4150-151">Next Steps</span></span>  
 <span data-ttu-id="c4150-152">Questa procedura dettagliata viene dimostrato che la **casella degli strumenti** prende in considerazione i componenti di un progetto, ma la **della casella degli strumenti** è anche dei controlli.</span><span class="sxs-lookup"><span data-stu-id="c4150-152">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="c4150-153">Sperimentare con i controlli personalizzati aggiungendo e rimuovendo i progetti di controllo dalla soluzione.</span><span class="sxs-lookup"><span data-stu-id="c4150-153">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4150-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4150-154">See also</span></span>

- <span data-ttu-id="c4150-155">[Generale, finestra di progettazione di Windows Form, finestra di dialogo Opzioni](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c4150-155">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="c4150-156">[Procedura: Organizzare le schede della casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c4150-156">[How to: Manipulate Toolbox Tabs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="c4150-157">[Finestra di dialogo Scegli elementi della Casella degli strumenti (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c4150-157">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="c4150-158">Inserimento di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c4150-158">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
