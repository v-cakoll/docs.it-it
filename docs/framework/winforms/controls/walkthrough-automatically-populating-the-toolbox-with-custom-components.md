---
title: 'Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: d446ab84cfe135e56483b8b309b696f7f15044fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540046"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="3d06f-102">Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="3d06f-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>
<span data-ttu-id="3d06f-103">Se i componenti sono definiti da un progetto nella soluzione attualmente aperta, verrà automaticamente visualizzato nel **della casella degli strumenti**, senza interventi da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3d06f-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="3d06f-104">È anche possibile inserire manualmente il **della casella degli strumenti** con componenti personalizzati usando il [Scegli elementi della finestra della casella (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), ma la **della casella degli strumenti** tiene conto elementi della soluzione di output con le seguenti caratteristiche di compilazione:</span><span class="sxs-lookup"><span data-stu-id="3d06f-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>  
  
-   <span data-ttu-id="3d06f-105">Implementa <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="3d06f-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>  
  
-   <span data-ttu-id="3d06f-106">Non dispone <xref:System.ComponentModel.ToolboxItemAttribute> impostato su `false`;</span><span class="sxs-lookup"><span data-stu-id="3d06f-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>  
  
-   <span data-ttu-id="3d06f-107">Non dispone <xref:System.ComponentModel.DesignTimeVisibleAttribute> impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="3d06f-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d06f-108">Il **della casella degli strumenti** segue le catene di riferimento, quindi non visualizzerà gli elementi che non vengono compilati da un progetto nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="3d06f-108">The **Toolbox** does not follow reference chains, so it will not display items that are not built by a project in your solution.</span></span>  
  
 <span data-ttu-id="3d06f-109">Questa procedura dettagliata illustra come un componente personalizzato viene automaticamente visualizzata nel **della casella degli strumenti** una volta creato il componente.</span><span class="sxs-lookup"><span data-stu-id="3d06f-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="3d06f-110">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d06f-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="3d06f-111">Creazione di un progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="3d06f-111">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="3d06f-112">Creazione di un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3d06f-112">Creating a custom component.</span></span>  
  
-   <span data-ttu-id="3d06f-113">Creazione di un'istanza di un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3d06f-113">Creating an instance of a custom component.</span></span>  
  
-   <span data-ttu-id="3d06f-114">Scaricare e ricaricare un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3d06f-114">Unloading and reloading a custom component.</span></span>  
  
 <span data-ttu-id="3d06f-115">Al termine, si noterà che il **della casella degli strumenti** viene popolato con un componente che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="3d06f-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d06f-116">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="3d06f-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3d06f-117">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="3d06f-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3d06f-118">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="3d06f-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="3d06f-119">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="3d06f-119">Creating the Project</span></span>  
 <span data-ttu-id="3d06f-120">Il primo passaggio indica come creare il progetto e impostare il modulo.</span><span class="sxs-lookup"><span data-stu-id="3d06f-120">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="3d06f-121">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="3d06f-121">To create the project</span></span>  
  
1.  <span data-ttu-id="3d06f-122">Creare un progetto di applicazione basata su Windows chiamato `ToolboxExample`.</span><span class="sxs-lookup"><span data-stu-id="3d06f-122">Create a Windows-based application project called `ToolboxExample`.</span></span>  
  
     <span data-ttu-id="3d06f-123">Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione Windows Form](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="3d06f-123">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="3d06f-124">Aggiungere un nuovo componente al progetto.</span><span class="sxs-lookup"><span data-stu-id="3d06f-124">Add a new component to the project.</span></span> <span data-ttu-id="3d06f-125">Chiamarlo `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="3d06f-125">Call it `DemoComponent`.</span></span>  
  
     <span data-ttu-id="3d06f-126">Per ulteriori informazioni, vedere [NIB: procedura: aggiungere nuovi elementi di progetto](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span><span class="sxs-lookup"><span data-stu-id="3d06f-126">For more information, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span>  
  
3.  <span data-ttu-id="3d06f-127">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="3d06f-127">Build the project.</span></span>  
  
4.  <span data-ttu-id="3d06f-128">Dal **strumenti** menu, fare clic su di **opzioni** elemento.</span><span class="sxs-lookup"><span data-stu-id="3d06f-128">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="3d06f-129">Fare clic su **generale** sotto il **Progettazione Windows Form** e verificare che il **AutoToolboxPopulate** opzione è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="3d06f-129">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>  
  
## <a name="creating-an-instance-of-a-custom-component"></a><span data-ttu-id="3d06f-130">Creazione di un'istanza di un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="3d06f-130">Creating an Instance of a Custom Component</span></span>  
 <span data-ttu-id="3d06f-131">Il passaggio successivo consiste nel creare un'istanza del componente personalizzato nel modulo.</span><span class="sxs-lookup"><span data-stu-id="3d06f-131">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="3d06f-132">Poiché il **della casella degli strumenti** automaticamente gli account per il nuovo componente, il codice è semplice come la creazione di qualsiasi altro componente o controllo.</span><span class="sxs-lookup"><span data-stu-id="3d06f-132">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a><span data-ttu-id="3d06f-133">Per creare un'istanza di un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="3d06f-133">To create an instance of a custom component</span></span>  
  
1.  <span data-ttu-id="3d06f-134">Aprire il form del progetto nel **progettazione form**.</span><span class="sxs-lookup"><span data-stu-id="3d06f-134">Open the project's form in the **Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="3d06f-135">Nel **della casella degli strumenti**, fare clic sulla scheda nuovo chiamata **Componenti ToolboxExample**.</span><span class="sxs-lookup"><span data-stu-id="3d06f-135">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>  
  
     <span data-ttu-id="3d06f-136">Dopo aver selezionato la scheda, verrà visualizzato **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="3d06f-136">Once you click the tab, you will see **DemoComponent**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d06f-137">Per motivi di prestazioni, i componenti nell'area di popolati automaticamente il **della casella degli strumenti** non visualizzano le bitmap personalizzate e <xref:System.Drawing.ToolboxBitmapAttribute> non è supportata.</span><span class="sxs-lookup"><span data-stu-id="3d06f-137">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="3d06f-138">Per visualizzare un'icona per un componente personalizzato nel **della casella degli strumenti**, utilizzare il **Scegli elementi della casella degli strumenti** finestra di dialogo per caricare il componente.</span><span class="sxs-lookup"><span data-stu-id="3d06f-138">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>  
  
3.  <span data-ttu-id="3d06f-139">Trascinare il componente al form.</span><span class="sxs-lookup"><span data-stu-id="3d06f-139">Drag your component onto your form.</span></span>  
  
     <span data-ttu-id="3d06f-140">Viene aggiunta a un'istanza del componente di **sulla barra dei componenti**.</span><span class="sxs-lookup"><span data-stu-id="3d06f-140">An instance of the component is created and added to the **Component Tray**.</span></span>  
  
## <a name="unloading-and-reloading-a-custom-component"></a><span data-ttu-id="3d06f-141">Scaricare e ricaricare un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="3d06f-141">Unloading and Reloading a Custom Component</span></span>  
 <span data-ttu-id="3d06f-142">Il **della casella degli strumenti** tengano conto dei componenti in ogni progetto di caricamento e quando un progetto viene scaricato, rimuove i riferimenti ai componenti del progetto.</span><span class="sxs-lookup"><span data-stu-id="3d06f-142">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a><span data-ttu-id="3d06f-143">Per sperimentare l'effetto della casella degli strumenti di scaricare e ricaricare i componenti</span><span class="sxs-lookup"><span data-stu-id="3d06f-143">To experiment with the effect on the Toolbox of unloading and reloading components</span></span>  
  
1.  <span data-ttu-id="3d06f-144">Scaricare il progetto dalla soluzione.</span><span class="sxs-lookup"><span data-stu-id="3d06f-144">Unload the project from the solution.</span></span>  
  
     <span data-ttu-id="3d06f-145">Per ulteriori informazioni sullo scaricamento dei progetti, vedere [NIB: procedura: scaricare e ricaricare i progetti](http://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span><span class="sxs-lookup"><span data-stu-id="3d06f-145">For more information about unloading projects, see [NIB:How to: Unload and Reload Projects](http://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span></span> <span data-ttu-id="3d06f-146">Se viene chiesto di salvare, scegliere **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3d06f-146">If you are prompted to save, choose **Yes**.</span></span>  
  
2.  <span data-ttu-id="3d06f-147">Aggiungere un nuovo **applicazione Windows** progetto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="3d06f-147">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="3d06f-148">Aprire il form nel **progettazione**.</span><span class="sxs-lookup"><span data-stu-id="3d06f-148">Open the form in the **Designer**.</span></span>  
  
     <span data-ttu-id="3d06f-149">Il **Componenti ToolboxExample** scheda dal progetto precedente è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="3d06f-149">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>  
  
3.  <span data-ttu-id="3d06f-150">Ricarica il `ToolboxExample` progetto.</span><span class="sxs-lookup"><span data-stu-id="3d06f-150">Reload the `ToolboxExample` project.</span></span>  
  
     <span data-ttu-id="3d06f-151">Il **Componenti ToolboxExample** scheda ora viene visualizzato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="3d06f-151">The **ToolboxExample Components** tab now reappears.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3d06f-152">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3d06f-152">Next Steps</span></span>  
 <span data-ttu-id="3d06f-153">Questa procedura dettagliata viene dimostrato che la **della casella degli strumenti** tiene conto dei componenti di un progetto, ma la **della casella degli strumenti** è anche dei controlli.</span><span class="sxs-lookup"><span data-stu-id="3d06f-153">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="3d06f-154">Sperimentare controlli personalizzati aggiungendo e rimuovendo i progetti di controllo dalla soluzione.</span><span class="sxs-lookup"><span data-stu-id="3d06f-154">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d06f-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d06f-155">See Also</span></span>  
 [<span data-ttu-id="3d06f-156">Generale, Progettazione Windows Form, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="3d06f-156">General, Windows Forms Designer, Options Dialog Box</span></span>](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="3d06f-157">Procedura: modificare le schede della Casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="3d06f-157">How to: Manipulate Toolbox Tabs</span></span>](http://msdn.microsoft.com/library/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [<span data-ttu-id="3d06f-158">Finestra di dialogo Scegli elementi della Casella degli strumenti (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="3d06f-158">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="3d06f-159">Inserimento di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="3d06f-159">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
