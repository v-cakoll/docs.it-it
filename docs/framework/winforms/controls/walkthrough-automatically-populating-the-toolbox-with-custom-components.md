---
title: 'Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 488d51e748ea17b09e61b982db7abadc34f8e311
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43671891"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="8cbb5-102">Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="8cbb5-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>
<span data-ttu-id="8cbb5-103">Se i componenti vengono definiti da un progetto nella soluzione attualmente aperta, verranno automaticamente visualizzati nei **casella degli strumenti**, senza alcun intervento da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="8cbb5-104">È anche possibile inserire manualmente il **casella degli strumenti** con i componenti personalizzati usando la [Scegli elementi della finestra della casella (Visual Studio)](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), ma il **della casella degli strumenti** tengano conto elementi della soluzione di output con tutte le caratteristiche seguenti di compilazione:</span><span class="sxs-lookup"><span data-stu-id="8cbb5-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>  
  
-   <span data-ttu-id="8cbb5-105">Implementa <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="8cbb5-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>  
  
-   <span data-ttu-id="8cbb5-106">Non dispone <xref:System.ComponentModel.ToolboxItemAttribute> impostato su `false`;</span><span class="sxs-lookup"><span data-stu-id="8cbb5-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>  
  
-   <span data-ttu-id="8cbb5-107">Non dispone <xref:System.ComponentModel.DesignTimeVisibleAttribute> impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cbb5-108">Il **casella degli strumenti** non rispetta le catene di riferimento, in modo da non visualizzerà gli elementi che non vengono compilati da un progetto nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-108">The **Toolbox** does not follow reference chains, so it will not display items that are not built by a project in your solution.</span></span>  
  
 <span data-ttu-id="8cbb5-109">Questa procedura dettagliata illustra come un componente personalizzato viene visualizzato automaticamente nel **casella degli strumenti** dopo aver compilato il componente.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="8cbb5-110">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cbb5-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="8cbb5-111">Creazione di un progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-111">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="8cbb5-112">Creazione di un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-112">Creating a custom component.</span></span>  
  
-   <span data-ttu-id="8cbb5-113">Creazione di un'istanza di un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-113">Creating an instance of a custom component.</span></span>  
  
-   <span data-ttu-id="8cbb5-114">Scaricare e ricaricare un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-114">Unloading and reloading a custom component.</span></span>  
  
 <span data-ttu-id="8cbb5-115">Al termine, si noterà che il **casella degli strumenti** viene popolato con un componente che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cbb5-116">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8cbb5-117">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="8cbb5-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8cbb5-118">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="8cbb5-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="8cbb5-119">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="8cbb5-119">Creating the Project</span></span>  
 <span data-ttu-id="8cbb5-120">Il primo passaggio indica come creare il progetto e impostare il modulo.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-120">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="8cbb5-121">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="8cbb5-121">To create the project</span></span>  
  
1.  <span data-ttu-id="8cbb5-122">Creare un progetto di applicazione basata su Windows denominato `ToolboxExample` (**File** > **New** > **progetto**  >  **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="8cbb5-122">Create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="8cbb5-123">Aggiungere un nuovo componente al progetto.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-123">Add a new component to the project.</span></span> <span data-ttu-id="8cbb5-124">Chiamarlo `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-124">Call it `DemoComponent`.</span></span>  
  
     <span data-ttu-id="8cbb5-125">Per altre informazioni, vedere [NIB: procedura: aggiungere nuovi elementi di progetto](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span><span class="sxs-lookup"><span data-stu-id="8cbb5-125">For more information, see [NIB:How to: Add New Project Items](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span>  
  
3.  <span data-ttu-id="8cbb5-126">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-126">Build the project.</span></span>  
  
4.  <span data-ttu-id="8cbb5-127">Dal **degli strumenti** menu, fare clic sul **opzioni** elemento.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-127">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="8cbb5-128">Fare clic su **generali** sotto il **progettazione di Windows Form** e verificare che il **AutoToolboxPopulate** opzione è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-128">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>  
  
## <a name="creating-an-instance-of-a-custom-component"></a><span data-ttu-id="8cbb5-129">Creazione di un'istanza di un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="8cbb5-129">Creating an Instance of a Custom Component</span></span>  
 <span data-ttu-id="8cbb5-130">Il passaggio successivo consiste nel creare un'istanza del componente personalizzato nel modulo.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-130">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="8cbb5-131">Poiché il **casella degli strumenti** automaticamente gli account per il nuovo componente, è semplice come la creazione di qualsiasi altro componente o controllo.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-131">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a><span data-ttu-id="8cbb5-132">Per creare un'istanza di un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="8cbb5-132">To create an instance of a custom component</span></span>  
  
1.  <span data-ttu-id="8cbb5-133">Aprire il form del progetto nel **progettazione form**.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-133">Open the project's form in the **Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="8cbb5-134">Nel **casella degli strumenti**, fare clic sulla scheda nuovo chiamata **Componenti ToolboxExample**.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-134">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>  
  
     <span data-ttu-id="8cbb5-135">Dopo aver selezionato la scheda, si noterà **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-135">Once you click the tab, you will see **DemoComponent**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8cbb5-136">Per motivi di prestazioni, i componenti nell'area popolato automaticamente della **casella degli strumenti** non vengono visualizzate le bitmap personalizzate e <xref:System.Drawing.ToolboxBitmapAttribute> non è supportato.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-136">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="8cbb5-137">Per visualizzare un'icona per un componente personalizzato nella **casella degli strumenti**, utilizzare il **Scegli elementi della casella degli strumenti** finestra di dialogo per caricare il componente.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-137">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>  
  
3.  <span data-ttu-id="8cbb5-138">Trascinare il componente al form.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-138">Drag your component onto your form.</span></span>  
  
     <span data-ttu-id="8cbb5-139">Viene creata e aggiunto a un'istanza del componente di **sulla barra dei componenti**.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-139">An instance of the component is created and added to the **Component Tray**.</span></span>  
  
## <a name="unloading-and-reloading-a-custom-component"></a><span data-ttu-id="8cbb5-140">Scaricare e ricaricare un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="8cbb5-140">Unloading and Reloading a Custom Component</span></span>  
 <span data-ttu-id="8cbb5-141">Il **casella degli strumenti** tengano conto dei componenti in ogni progetto di caricamento e quando viene scaricato un progetto, vengono rimossi i riferimenti ai componenti del progetto.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-141">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a><span data-ttu-id="8cbb5-142">Per sperimentare l'effetto della casella degli strumenti di scaricamento e il ricaricamento di componenti</span><span class="sxs-lookup"><span data-stu-id="8cbb5-142">To experiment with the effect on the Toolbox of unloading and reloading components</span></span>  
  
1.  <span data-ttu-id="8cbb5-143">Scaricare il progetto dalla soluzione.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-143">Unload the project from the solution.</span></span>  
  
     <span data-ttu-id="8cbb5-144">Per altre informazioni sullo scaricamento dei progetti, vedere [NIB: procedura: scaricare e ricaricare i progetti](https://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span><span class="sxs-lookup"><span data-stu-id="8cbb5-144">For more information about unloading projects, see [NIB:How to: Unload and Reload Projects](https://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span></span> <span data-ttu-id="8cbb5-145">Se viene chiesto di salvare, scegliere **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-145">If you are prompted to save, choose **Yes**.</span></span>  
  
2.  <span data-ttu-id="8cbb5-146">Aggiungere un nuovo **applicazioni Windows** progetto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-146">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="8cbb5-147">Aprire il form nel **progettazione**.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-147">Open the form in the **Designer**.</span></span>  
  
     <span data-ttu-id="8cbb5-148">Il **Componenti ToolboxExample** scheda dal progetto precedente è stata ancora attivo.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-148">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>  
  
3.  <span data-ttu-id="8cbb5-149">Ricarica il `ToolboxExample` progetto.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-149">Reload the `ToolboxExample` project.</span></span>  
  
     <span data-ttu-id="8cbb5-150">Il **Componenti ToolboxExample** scheda ora viene visualizzata di nuovo.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-150">The **ToolboxExample Components** tab now reappears.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8cbb5-151">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8cbb5-151">Next Steps</span></span>  
 <span data-ttu-id="8cbb5-152">Questa procedura dettagliata viene dimostrato che la **casella degli strumenti** prende in considerazione i componenti di un progetto, ma la **della casella degli strumenti** è anche dei controlli.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-152">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="8cbb5-153">Sperimentare con i controlli personalizzati aggiungendo e rimuovendo i progetti di controllo dalla soluzione.</span><span class="sxs-lookup"><span data-stu-id="8cbb5-153">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cbb5-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cbb5-154">See Also</span></span>  
 [<span data-ttu-id="8cbb5-155">Generale, finestra di progettazione di Windows Form, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="8cbb5-155">General, Windows Forms Designer, Options Dialog Box</span></span>](https://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="8cbb5-156">Procedura: modificare le schede della Casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="8cbb5-156">How to: Manipulate Toolbox Tabs</span></span>](https://msdn.microsoft.com/library/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [<span data-ttu-id="8cbb5-157">Finestra di dialogo Scegli elementi della Casella degli strumenti (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="8cbb5-157">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="8cbb5-158">Inserimento di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="8cbb5-158">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
