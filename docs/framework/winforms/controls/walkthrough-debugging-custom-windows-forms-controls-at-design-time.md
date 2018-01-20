---
title: 'Procedura dettagliata: debug di controlli di Windows Form personalizzati in fase di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4dfdc102a5aeb2e3eaccde28a8ce57a1878141e4
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="5201c-102">Procedura dettagliata: debug di controlli di Windows Form personalizzati in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="5201c-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="5201c-103">Quando si crea un controllo personalizzato, si sarà spesso che sia necessario eseguire il debug il comportamento in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="5201c-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="5201c-104">Ciò vale soprattutto per la creazione di una finestra di progettazione personalizzata per il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5201c-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="5201c-105">Per informazioni dettagliate, vedere [procedura dettagliata: creazione di un Windows Form controllo che accetta vantaggio di Visual Studio in fase di progettazione funzionalità](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="5201c-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
 <span data-ttu-id="5201c-106">È possibile eseguire il debug dei controlli personalizzati in Visual Studio, esattamente come si trattasse del debug di altre classi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5201c-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="5201c-107">La differenza è che si eseguirà il debug di un'istanza separata di Visual Studio che è in esecuzione il codice del controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="5201c-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>  
  
 <span data-ttu-id="5201c-108">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="5201c-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="5201c-109">Creazione di un progetto Windows Form per ospitare il controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="5201c-109">Creating a Windows Forms project to host your custom control</span></span>  
  
-   <span data-ttu-id="5201c-110">Creazione di un progetto libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="5201c-110">Creating a control library project</span></span>  
  
-   <span data-ttu-id="5201c-111">Aggiunta di una proprietà al controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="5201c-111">Adding a property to your custom control</span></span>  
  
-   <span data-ttu-id="5201c-112">Aggiunta del controllo personalizzato per il form host</span><span class="sxs-lookup"><span data-stu-id="5201c-112">Adding your custom control to the host form</span></span>  
  
-   <span data-ttu-id="5201c-113">Impostazione del progetto per il debug in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="5201c-113">Setting up the project for design-time debugging</span></span>  
  
-   <span data-ttu-id="5201c-114">Debug del controllo personalizzato in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="5201c-114">Debugging your custom control at design time</span></span>  
  
 <span data-ttu-id="5201c-115">Al termine, si avrà una migliore comprensione delle attività necessarie per il debug del comportamento in fase di progettazione di un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5201c-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5201c-116">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="5201c-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5201c-117">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="5201c-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5201c-118">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="5201c-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="5201c-119">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="5201c-119">Creating the Project</span></span>  
 <span data-ttu-id="5201c-120">Il primo passaggio consiste nel creare il progetto di applicazione.</span><span class="sxs-lookup"><span data-stu-id="5201c-120">The first step is to create the application project.</span></span> <span data-ttu-id="5201c-121">Questo progetto verrà utilizzato per compilare l'applicazione che ospita il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5201c-121">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="5201c-122">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="5201c-122">To create the project</span></span>  
  
-   <span data-ttu-id="5201c-123">Creare un progetto di applicazione Windows denominato "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="5201c-123">Create a Windows Application project called "DebuggingExample".</span></span> <span data-ttu-id="5201c-124">Per informazioni dettagliate, vedere [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="5201c-124">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="5201c-125">Creazione di un progetto libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="5201c-125">Creating a Control Library Project</span></span>  
 <span data-ttu-id="5201c-126">Il passaggio successivo consiste nel creare il progetto libreria di controlli e impostare il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5201c-126">The next step is to create the control library project and set up the custom control.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="5201c-127">Per creare il progetto libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="5201c-127">To create the control library project</span></span>  
  
1.  <span data-ttu-id="5201c-128">Aggiungere un **libreria di controlli Windows** progetto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="5201c-128">Add a **Windows Control Library** project to the solution.</span></span>  
  
2.  <span data-ttu-id="5201c-129">Aggiungere un nuovo **UserControl** elemento al progetto DebugControlLibrary.</span><span class="sxs-lookup"><span data-stu-id="5201c-129">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="5201c-130">Per informazioni dettagliate, vedere [NIB: procedura: aggiungere nuovi elementi di progetto](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span><span class="sxs-lookup"><span data-stu-id="5201c-130">For details, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span> <span data-ttu-id="5201c-131">Assegnare il nuovo file di origine di un nome di base di "DebugControl".</span><span class="sxs-lookup"><span data-stu-id="5201c-131">Give the new source file a base name of "DebugControl".</span></span>  
  
3.  <span data-ttu-id="5201c-132">Utilizzando il **Esplora**, eliminare il controllo del progetto predefinita eliminando il file di codice con il nome di base "`UserControl1`".</span><span class="sxs-lookup"><span data-stu-id="5201c-132">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="5201c-133">Per informazioni dettagliate, vedere [NIB: procedura: escludere elementi, eliminazione e Rimuovi](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span><span class="sxs-lookup"><span data-stu-id="5201c-133">For details, see [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
4.  <span data-ttu-id="5201c-134">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="5201c-134">Build the solution.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="5201c-135">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="5201c-135">Checkpoint</span></span>  
 <span data-ttu-id="5201c-136">A questo punto, sarà in grado di visualizzare il controllo personalizzato nel **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="5201c-136">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>  
  
#### <a name="to-check-your-progress"></a><span data-ttu-id="5201c-137">Per controllare lo stato di avanzamento</span><span class="sxs-lookup"><span data-stu-id="5201c-137">To check your progress</span></span>  
  
-   <span data-ttu-id="5201c-138">Individuare la nuova scheda **Componenti DebugControlLibrary** e fare clic per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="5201c-138">Find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="5201c-139">Quando si apre, verrà visualizzato il controllo elencato come **DebugControl** con accanto l'icona predefinita.</span><span class="sxs-lookup"><span data-stu-id="5201c-139">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>  
  
## <a name="adding-a-property-to-your-custom-control"></a><span data-ttu-id="5201c-140">Aggiunta di una proprietà al controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="5201c-140">Adding a Property to Your Custom Control</span></span>  
 <span data-ttu-id="5201c-141">Per dimostrare che il codice del controllo personalizzato è in esecuzione in fase di progettazione, si verrà aggiunta una proprietà e impostare un punto di interruzione nel codice che implementa la proprietà.</span><span class="sxs-lookup"><span data-stu-id="5201c-141">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>  
  
#### <a name="to-add-a-property-to-your-custom-control"></a><span data-ttu-id="5201c-142">Per aggiungere una proprietà al controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="5201c-142">To add a property to your custom control</span></span>  
  
1.  <span data-ttu-id="5201c-143">Aprire **DebugControl** nel **Editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="5201c-143">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="5201c-144">Aggiungere il codice seguente alla definizione di classe:</span><span class="sxs-lookup"><span data-stu-id="5201c-144">Add the following code to the class definition:</span></span>  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  <span data-ttu-id="5201c-145">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="5201c-145">Build the solution.</span></span>  
  
## <a name="adding-your-custom-control-to-the-host-form"></a><span data-ttu-id="5201c-146">Aggiunta del controllo personalizzato per il Form Host</span><span class="sxs-lookup"><span data-stu-id="5201c-146">Adding Your Custom Control to the Host Form</span></span>  
 <span data-ttu-id="5201c-147">Per eseguire il debug il comportamento in fase di progettazione del controllo personalizzato, si inserirà un'istanza della classe del controllo personalizzato in un form di host.</span><span class="sxs-lookup"><span data-stu-id="5201c-147">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a><span data-ttu-id="5201c-148">Per aggiungere il controllo personalizzato per il form host</span><span class="sxs-lookup"><span data-stu-id="5201c-148">To add your custom control to the host form</span></span>  
  
1.  <span data-ttu-id="5201c-149">Nel progetto "DebuggingExample", aprire Form1 nel **Progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="5201c-149">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="5201c-150">Nel **della casella degli strumenti**, aprire il **Componenti DebugControlLibrary** scheda e trascinare un **DebugControl** istanza nel form.</span><span class="sxs-lookup"><span data-stu-id="5201c-150">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>  
  
3.  <span data-ttu-id="5201c-151">Trovare il `DemoString` proprietà personalizzata di **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="5201c-151">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="5201c-152">Si noti che è possibile modificare il relativo valore come si farebbe con qualsiasi altra proprietà.</span><span class="sxs-lookup"><span data-stu-id="5201c-152">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="5201c-153">Si noti inoltre che quando il `DemoString` proprietà è selezionata, la stringa di descrizione della proprietà viene visualizzata nella parte inferiore del **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="5201c-153">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="5201c-154">Impostazione del progetto per il debug in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="5201c-154">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="5201c-155">Per eseguire il debug di comportamento in fase di progettazione del controllo personalizzato, si eseguirà il debug di un'istanza separata di Visual Studio che è in esecuzione il codice del controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5201c-155">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="5201c-156">Per impostare il progetto per il debug in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="5201c-156">To set up the project for design-time debugging</span></span>  
  
1.  <span data-ttu-id="5201c-157">Fare clic su di **DebugControlLibrary** nel progetto di **Esplora** e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5201c-157">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="5201c-158">Nel **DebugControlLibrary** finestra delle proprietà, seleziona il **Debug** scheda.</span><span class="sxs-lookup"><span data-stu-id="5201c-158">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>  
  
     <span data-ttu-id="5201c-159">Nel **azione di avvio** selezionare **Avvia programma esterno**.</span><span class="sxs-lookup"><span data-stu-id="5201c-159">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="5201c-160">Sarà il debug di un'istanza separata di Visual Studio, quindi fare clic sui puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) per cercare l'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5201c-160">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="5201c-161">Il nome del file eseguibile è **devenv.exe**, e se è installato nel percorso predefinito, il relativo percorso %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span><span class="sxs-lookup"><span data-stu-id="5201c-161">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
3.  <span data-ttu-id="5201c-162">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="5201c-162">Click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="5201c-163">Fare doppio clic su di **DebugControlLibrary** del progetto e selezionare **imposta come progetto di avvio** per abilitare la configurazione di debug.</span><span class="sxs-lookup"><span data-stu-id="5201c-163">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>  
  
## <a name="debugging-your-custom-control-at-design-time"></a><span data-ttu-id="5201c-164">Debug del controllo personalizzato in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="5201c-164">Debugging Your Custom Control at Design Time</span></span>  
 <span data-ttu-id="5201c-165">A questo punto si è pronti per eseguire il debug del controllo personalizzato in fase di esecuzione in modalità progettazione.</span><span class="sxs-lookup"><span data-stu-id="5201c-165">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="5201c-166">Quando si avvia la sessione di debug, verrà creata una nuova istanza di Visual Studio e si utilizzerà per caricare la soluzione "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="5201c-166">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="5201c-167">Quando si apre Form1 nel **progettazione form**, verrà creata e inizierà l'esecuzione di un'istanza del controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5201c-167">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a><span data-ttu-id="5201c-168">Per eseguire il debug del controllo personalizzato in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="5201c-168">To debug your custom control at design time</span></span>  
  
1.  <span data-ttu-id="5201c-169">Aprire il **DebugControl** file di origine il **Editor di codice** e inserire un punto di interruzione il `Set` funzione di accesso del `DemoString` proprietà.</span><span class="sxs-lookup"><span data-stu-id="5201c-169">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>  
  
2.  <span data-ttu-id="5201c-170">Premere F5 per avviare la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="5201c-170">Press F5 to start the debugging session.</span></span> <span data-ttu-id="5201c-171">Si noti che viene creata una nuova istanza di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5201c-171">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="5201c-172">È possibile distinguere tra le istanze in due modi:</span><span class="sxs-lookup"><span data-stu-id="5201c-172">You can distinguish between the instances in two ways:</span></span>  
  
    -   <span data-ttu-id="5201c-173">Istanza di debug contiene la parola **esecuzione** nella barra del titolo</span><span class="sxs-lookup"><span data-stu-id="5201c-173">The debugging instance has the word **Running** in its title bar</span></span>  
  
    -   <span data-ttu-id="5201c-174">Istanza di debug contiene il **avviare** pulsante relativo **Debug** barra degli strumenti disabilitato</span><span class="sxs-lookup"><span data-stu-id="5201c-174">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>  
  
     <span data-ttu-id="5201c-175">Il punto di interruzione è impostato nell'istanza di debug.</span><span class="sxs-lookup"><span data-stu-id="5201c-175">Your breakpoint is set in the debugging instance.</span></span>  
  
3.  <span data-ttu-id="5201c-176">Nella nuova istanza di Visual Studio, aprire la soluzione "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="5201c-176">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="5201c-177">È possibile trovare facilmente la soluzione selezionando **progetti recenti** dal **File** menu.</span><span class="sxs-lookup"><span data-stu-id="5201c-177">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="5201c-178">Il file della soluzione "DebuggingExample" verrà elencato come più file utilizzati di recente.</span><span class="sxs-lookup"><span data-stu-id="5201c-178">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>  
  
4.  <span data-ttu-id="5201c-179">Aprire Form1 nella **progettazione form** e selezionare il **DebugControl** controllo.</span><span class="sxs-lookup"><span data-stu-id="5201c-179">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>  
  
5.  <span data-ttu-id="5201c-180">Modificare il valore della `DemoString` proprietà.</span><span class="sxs-lookup"><span data-stu-id="5201c-180">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="5201c-181">Si noti che quando si esegue il commit della modifica, l'istanza di debug di Visual Studio acquisisce lo stato attivo e l'esecuzione si ferma in corrispondenza del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="5201c-181">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="5201c-182">È possibile passo a passo la funzione di accesso della proprietà come il sarebbe qualsiasi altro codice.</span><span class="sxs-lookup"><span data-stu-id="5201c-182">You can single-step through the property accessor just as your would any other code.</span></span>  
  
6.  <span data-ttu-id="5201c-183">Quando si è terminato la sessione di debug, è possibile uscire chiudendo l'istanza host di Visual Studio o facendo clic di **Termina debug** pulsante nell'istanza di debug.</span><span class="sxs-lookup"><span data-stu-id="5201c-183">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5201c-184">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5201c-184">Next Steps</span></span>  
 <span data-ttu-id="5201c-185">Ora che è possibile eseguire il debug dei controlli personalizzati in fase di progettazione, esistono diverse possibilità per espandere l'interazione del controllo con l'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5201c-185">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>  
  
-   <span data-ttu-id="5201c-186">È possibile utilizzare il <xref:System.ComponentModel.Component.DesignMode%2A> proprietà la <xref:System.ComponentModel.Component> classe per scrivere codice che verrà eseguito solo in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="5201c-186">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="5201c-187">Per informazioni dettagliate, vedere <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="5201c-187">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>  
  
-   <span data-ttu-id="5201c-188">Esistono numerosi attributi è possibile applicare alle proprietà del controllo per modificare l'interazione del controllo personalizzato con la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="5201c-188">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="5201c-189">È possibile trovare questi attributi di <xref:System.ComponentModel?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5201c-189">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>  
  
-   <span data-ttu-id="5201c-190">È possibile scrivere una finestra di progettazione personalizzata per il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5201c-190">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="5201c-191">In questo modo il controllo completo della fase di progettazione utilizzando l'infrastruttura della finestra di progettazione estendibile esposta da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5201c-191">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="5201c-192">Per informazioni dettagliate, vedere [procedura dettagliata: creazione di un Windows Form controllo che accetta vantaggio di Visual Studio in fase di progettazione funzionalità](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="5201c-192">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5201c-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5201c-193">See Also</span></span>  
 [<span data-ttu-id="5201c-194">Procedura dettagliata: Creazione di un controllo Windows Form che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="5201c-194">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [<span data-ttu-id="5201c-195">Procedura: accedere ai servizi in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="5201c-195">How to: Access Design-Time Services</span></span>](http://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [<span data-ttu-id="5201c-196">Procedura: Accedere al supporto in fase di progettazione in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5201c-196">How to: Access Design-Time Support in Windows Forms</span></span>](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
