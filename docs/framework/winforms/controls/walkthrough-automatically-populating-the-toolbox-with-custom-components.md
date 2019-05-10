---
title: 'Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 876de650f9c182c0f82a02d1c5b356faa4f7f118
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211152"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="f93cd-102">Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="f93cd-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>

<span data-ttu-id="f93cd-103">Se i componenti vengono definiti da un progetto nella soluzione attualmente aperta, verranno automaticamente visualizzati nei **casella degli strumenti**, senza alcun intervento da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f93cd-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="f93cd-104">È anche possibile inserire manualmente il **casella degli strumenti** con i componenti personalizzati usando la [Scegli elementi della finestra della casella (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), ma il **della casella degli strumenti** tengano conto elementi della soluzione di output con tutte le caratteristiche seguenti di compilazione:</span><span class="sxs-lookup"><span data-stu-id="f93cd-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>

- <span data-ttu-id="f93cd-105">Implementa <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="f93cd-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>

- <span data-ttu-id="f93cd-106">Non dispone <xref:System.ComponentModel.ToolboxItemAttribute> impostato su `false`;</span><span class="sxs-lookup"><span data-stu-id="f93cd-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>

- <span data-ttu-id="f93cd-107">Non dispone <xref:System.ComponentModel.DesignTimeVisibleAttribute> impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="f93cd-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>

> [!NOTE]
> <span data-ttu-id="f93cd-108">Il **casella degli strumenti** non rispetta le catene di riferimento, in modo che non verrà visualizzati gli elementi che non vengono compilati da un progetto nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="f93cd-108">The **Toolbox** does not follow reference chains, so it won't display items that are not built by a project in your solution.</span></span>

<span data-ttu-id="f93cd-109">Questa procedura dettagliata illustra come un componente personalizzato viene visualizzato automaticamente nel **casella degli strumenti** dopo aver compilato il componente.</span><span class="sxs-lookup"><span data-stu-id="f93cd-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="f93cd-110">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="f93cd-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="f93cd-111">Creazione di un progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f93cd-111">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="f93cd-112">Creazione di un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f93cd-112">Creating a custom component.</span></span>

- <span data-ttu-id="f93cd-113">Creazione di un'istanza di un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f93cd-113">Creating an instance of a custom component.</span></span>

- <span data-ttu-id="f93cd-114">Scaricare e ricaricare un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f93cd-114">Unloading and reloading a custom component.</span></span>

<span data-ttu-id="f93cd-115">Al termine, si noterà che il **casella degli strumenti** viene popolato con un componente che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="f93cd-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="f93cd-116">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="f93cd-116">Create the project</span></span>

1. <span data-ttu-id="f93cd-117">In Visual Studio, creare un progetto di applicazione basata su Windows denominato `ToolboxExample` (**File** > **New** > **progetto**  >  **Visual C#**  oppure **Visual Basic** > **Desktop classico** > **Windows Form Applicazione**).</span><span class="sxs-lookup"><span data-stu-id="f93cd-117">In Visual Studio, create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="f93cd-118">Aggiungere un nuovo componente al progetto.</span><span class="sxs-lookup"><span data-stu-id="f93cd-118">Add a new component to the project.</span></span> <span data-ttu-id="f93cd-119">nominarla `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="f93cd-119">Call it `DemoComponent`.</span></span>

     <span data-ttu-id="f93cd-120">Per altre informazioni, vedere [Procedura: Aggiungere nuovi elementi di progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f93cd-120">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>

3. <span data-ttu-id="f93cd-121">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="f93cd-121">Build the project.</span></span>

4. <span data-ttu-id="f93cd-122">Dal **degli strumenti** menu, fare clic sul **opzioni** elemento.</span><span class="sxs-lookup"><span data-stu-id="f93cd-122">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="f93cd-123">Fare clic su **generali** sotto il **progettazione di Windows Form** e verificare che il **AutoToolboxPopulate** opzione è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="f93cd-123">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>

## <a name="create-an-instance-of-a-custom-component"></a><span data-ttu-id="f93cd-124">Creare un'istanza di un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="f93cd-124">Create an instance of a custom component</span></span>

<span data-ttu-id="f93cd-125">Il passaggio successivo consiste nel creare un'istanza del componente personalizzato nel modulo.</span><span class="sxs-lookup"><span data-stu-id="f93cd-125">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="f93cd-126">Poiché il **casella degli strumenti** automaticamente gli account per il nuovo componente, è semplice come la creazione di qualsiasi altro componente o controllo.</span><span class="sxs-lookup"><span data-stu-id="f93cd-126">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>

1. <span data-ttu-id="f93cd-127">Aprire il form del progetto nel **progettazione form**.</span><span class="sxs-lookup"><span data-stu-id="f93cd-127">Open the project's form in the **Forms Designer**.</span></span>

2. <span data-ttu-id="f93cd-128">Nel **casella degli strumenti**, fare clic sulla scheda nuovo chiamata **Componenti ToolboxExample**.</span><span class="sxs-lookup"><span data-stu-id="f93cd-128">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>

     <span data-ttu-id="f93cd-129">Dopo aver selezionato la scheda, si noterà **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="f93cd-129">Once you click the tab, you will see **DemoComponent**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f93cd-130">Per motivi di prestazioni, i componenti nell'area popolato automaticamente della **casella degli strumenti** non vengono visualizzate le bitmap personalizzate e <xref:System.Drawing.ToolboxBitmapAttribute> non è supportato.</span><span class="sxs-lookup"><span data-stu-id="f93cd-130">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="f93cd-131">Per visualizzare un'icona per un componente personalizzato nella **casella degli strumenti**, utilizzare il **Scegli elementi della casella degli strumenti** finestra di dialogo per caricare il componente.</span><span class="sxs-lookup"><span data-stu-id="f93cd-131">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>

3. <span data-ttu-id="f93cd-132">Trascinare il componente al form.</span><span class="sxs-lookup"><span data-stu-id="f93cd-132">Drag your component onto your form.</span></span>

     <span data-ttu-id="f93cd-133">Viene creata e aggiunto a un'istanza del componente di **sulla barra dei componenti**.</span><span class="sxs-lookup"><span data-stu-id="f93cd-133">An instance of the component is created and added to the **Component Tray**.</span></span>

## <a name="unload-and-reload-a-custom-component"></a><span data-ttu-id="f93cd-134">Scaricare e ricaricare un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="f93cd-134">Unload and reload a custom component</span></span>

<span data-ttu-id="f93cd-135">Il **casella degli strumenti** tengano conto dei componenti in ogni progetto di caricamento e quando viene scaricato un progetto, vengono rimossi i riferimenti ai componenti del progetto.</span><span class="sxs-lookup"><span data-stu-id="f93cd-135">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>

1. <span data-ttu-id="f93cd-136">Scaricare il progetto dalla soluzione.</span><span class="sxs-lookup"><span data-stu-id="f93cd-136">Unload the project from the solution.</span></span>

     <span data-ttu-id="f93cd-137">Per altre informazioni sullo scaricamento dei progetti, vedere [come: Scaricare e ricaricare i progetti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f93cd-137">For more information about unloading projects, see [How to: Unload and Reload Projects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="f93cd-138">Se viene chiesto di salvare, scegliere **Sì**.</span><span class="sxs-lookup"><span data-stu-id="f93cd-138">If you are prompted to save, choose **Yes**.</span></span>

2. <span data-ttu-id="f93cd-139">Aggiungere un nuovo **applicazioni Windows** progetto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="f93cd-139">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="f93cd-140">Aprire il form nel **progettazione**.</span><span class="sxs-lookup"><span data-stu-id="f93cd-140">Open the form in the **Designer**.</span></span>

     <span data-ttu-id="f93cd-141">Il **Componenti ToolboxExample** scheda dal progetto precedente è stata ancora attivo.</span><span class="sxs-lookup"><span data-stu-id="f93cd-141">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>

3. <span data-ttu-id="f93cd-142">Ricarica il `ToolboxExample` progetto.</span><span class="sxs-lookup"><span data-stu-id="f93cd-142">Reload the `ToolboxExample` project.</span></span>

     <span data-ttu-id="f93cd-143">Il **Componenti ToolboxExample** scheda ora viene visualizzata di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f93cd-143">The **ToolboxExample Components** tab now reappears.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f93cd-144">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f93cd-144">Next steps</span></span>

<span data-ttu-id="f93cd-145">Questa procedura dettagliata viene dimostrato che la **casella degli strumenti** prende in considerazione i componenti di un progetto, ma la **della casella degli strumenti** è anche dei controlli.</span><span class="sxs-lookup"><span data-stu-id="f93cd-145">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="f93cd-146">Sperimentare con i controlli personalizzati aggiungendo e rimuovendo i progetti di controllo dalla soluzione.</span><span class="sxs-lookup"><span data-stu-id="f93cd-146">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>

## <a name="see-also"></a><span data-ttu-id="f93cd-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f93cd-147">See also</span></span>

- <span data-ttu-id="f93cd-148">[Generale, finestra di progettazione di Windows Form, finestra di dialogo Opzioni](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f93cd-148">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="f93cd-149">[Procedura: modificare le schede della Casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f93cd-149">[How to: Manipulate Toolbox Tabs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="f93cd-150">[Finestra di dialogo Scegli elementi della Casella degli strumenti (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f93cd-150">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="f93cd-151">Inserimento di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f93cd-151">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
