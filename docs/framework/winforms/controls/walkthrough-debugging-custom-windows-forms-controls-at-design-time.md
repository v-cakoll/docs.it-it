---
title: 'Procedura dettagliata: debug di controlli di Windows Form personalizzati in fase di progettazione'
ms.date: 03/30/2017
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
ms.openlocfilehash: 824c1e47cf50dc13a3a986e48a49158b15dbb935
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45677331"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="f8809-102">Procedura dettagliata: debug di controlli di Windows Form personalizzati in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f8809-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="f8809-103">Quando si crea un controllo personalizzato, è spesso risulterà necessario per eseguire il debug relativo comportamento in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="f8809-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="f8809-104">Ciò è particolarmente vero se si crea una finestra di progettazione personalizzata per il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f8809-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="f8809-105">Per informazioni dettagliate, vedere [procedura dettagliata: creazione di un Windows Form controllo che accetta i vantaggi di Visual Studio in fase di progettazione funzionalità](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="f8809-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
 <span data-ttu-id="f8809-106">È possibile eseguire il debug dei controlli personalizzati utilizzando Visual Studio, esattamente come si potrebbero eseguire il debug di eventuali altre classi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f8809-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="f8809-107">La differenza è che si eseguirà il debug di un'istanza separata di Visual Studio che codice del controllo personalizzato in esecuzione</span><span class="sxs-lookup"><span data-stu-id="f8809-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>  
  
 <span data-ttu-id="f8809-108">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8809-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="f8809-109">Creazione di un progetto Windows Form per ospitare il controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="f8809-109">Creating a Windows Forms project to host your custom control</span></span>  
  
-   <span data-ttu-id="f8809-110">Creazione di un progetto di libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="f8809-110">Creating a control library project</span></span>  
  
-   <span data-ttu-id="f8809-111">Aggiunta di una proprietà del controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="f8809-111">Adding a property to your custom control</span></span>  
  
-   <span data-ttu-id="f8809-112">Aggiunta del controllo personalizzato al modulo host</span><span class="sxs-lookup"><span data-stu-id="f8809-112">Adding your custom control to the host form</span></span>  
  
-   <span data-ttu-id="f8809-113">Impostazione del progetto per il debug in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f8809-113">Setting up the project for design-time debugging</span></span>  
  
-   <span data-ttu-id="f8809-114">Debug del controllo personalizzato in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f8809-114">Debugging your custom control at design time</span></span>  
  
 <span data-ttu-id="f8809-115">Al termine, si avrà una conoscenza delle attività necessarie per il debug del comportamento in fase di progettazione di un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f8809-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8809-116">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="f8809-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f8809-117">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="f8809-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f8809-118">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f8809-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="f8809-119">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="f8809-119">Creating the Project</span></span>  
 <span data-ttu-id="f8809-120">Il primo passaggio consiste nel creare il progetto di applicazione.</span><span class="sxs-lookup"><span data-stu-id="f8809-120">The first step is to create the application project.</span></span> <span data-ttu-id="f8809-121">Si userà questo progetto per compilare l'applicazione che ospita il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f8809-121">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="f8809-122">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="f8809-122">To create the project</span></span>  
  
-   <span data-ttu-id="f8809-123">Creare un progetto di applicazione Windows denominato "DynamicLayout" (**File** > **New** > **progetto**  >  **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="f8809-123">Create a Windows Application project called "DebuggingExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="f8809-124">Creazione di un progetto di libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="f8809-124">Creating a Control Library Project</span></span>  
 <span data-ttu-id="f8809-125">Il passaggio successivo è creare il progetto di libreria di controlli e impostare il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f8809-125">The next step is to create the control library project and set up the custom control.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="f8809-126">Per creare il progetto di libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="f8809-126">To create the control library project</span></span>  
  
1.  <span data-ttu-id="f8809-127">Aggiungere un **libreria di controlli Windows** progetto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="f8809-127">Add a **Windows Control Library** project to the solution.</span></span>  
  
2.  <span data-ttu-id="f8809-128">Aggiungere un nuovo **UserControl** elemento al progetto DebugControlLibrary.</span><span class="sxs-lookup"><span data-stu-id="f8809-128">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="f8809-129">Per informazioni dettagliate, vedere [NIB: procedura: aggiungere nuovi elementi di progetto](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span><span class="sxs-lookup"><span data-stu-id="f8809-129">For details, see [NIB:How to: Add New Project Items](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span> <span data-ttu-id="f8809-130">Assegnare al nuovo file di origine di un nome di base di "DebugControl".</span><span class="sxs-lookup"><span data-stu-id="f8809-130">Give the new source file a base name of "DebugControl".</span></span>  
  
3.  <span data-ttu-id="f8809-131">Usando il **Esplora soluzioni**, eliminare il controllo del progetto predefinita eliminando il file di codice con il nome di base "`UserControl1`".</span><span class="sxs-lookup"><span data-stu-id="f8809-131">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="f8809-132">Per informazioni dettagliate, vedere [NIB: procedura: rimozione, eliminazione ed escludere elementi](https://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span><span class="sxs-lookup"><span data-stu-id="f8809-132">For details, see [NIB:How to: Remove, Delete, and Exclude Items](https://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
4.  <span data-ttu-id="f8809-133">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="f8809-133">Build the solution.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="f8809-134">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="f8809-134">Checkpoint</span></span>  
 <span data-ttu-id="f8809-135">A questo punto, sarà in grado di visualizzare il controllo personalizzato nel **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="f8809-135">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>  
  
#### <a name="to-check-your-progress"></a><span data-ttu-id="f8809-136">Per controllare lo stato di avanzamento</span><span class="sxs-lookup"><span data-stu-id="f8809-136">To check your progress</span></span>  
  
-   <span data-ttu-id="f8809-137">Trovare la nuova scheda denominata **Componenti DebugControlLibrary** e fare clic per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="f8809-137">Find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="f8809-138">Quando si apre, verrà visualizzato il controllo elencato come **DebugControl** con accanto l'icona predefinita.</span><span class="sxs-lookup"><span data-stu-id="f8809-138">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>  
  
## <a name="adding-a-property-to-your-custom-control"></a><span data-ttu-id="f8809-139">Aggiunta di una proprietà del controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="f8809-139">Adding a Property to Your Custom Control</span></span>  
 <span data-ttu-id="f8809-140">Per dimostrare che il codice del controllo personalizzato sia in esecuzione in fase di progettazione, si verrà aggiunta una proprietà e impostare un punto di interruzione nel codice che implementa la proprietà.</span><span class="sxs-lookup"><span data-stu-id="f8809-140">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>  
  
#### <a name="to-add-a-property-to-your-custom-control"></a><span data-ttu-id="f8809-141">Per aggiungere una proprietà del controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="f8809-141">To add a property to your custom control</span></span>  
  
1.  <span data-ttu-id="f8809-142">Aprire **DebugControl** nel **Editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="f8809-142">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="f8809-143">Aggiungere il codice seguente alla definizione della classe:</span><span class="sxs-lookup"><span data-stu-id="f8809-143">Add the following code to the class definition:</span></span>  
  
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
  
2.  <span data-ttu-id="f8809-144">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="f8809-144">Build the solution.</span></span>  
  
## <a name="adding-your-custom-control-to-the-host-form"></a><span data-ttu-id="f8809-145">Aggiunta del controllo personalizzato al modulo Host</span><span class="sxs-lookup"><span data-stu-id="f8809-145">Adding Your Custom Control to the Host Form</span></span>  
 <span data-ttu-id="f8809-146">Per eseguire il debug di comportamento in fase di progettazione del controllo personalizzato, si inserirà un'istanza della classe del controllo personalizzato in un form di host.</span><span class="sxs-lookup"><span data-stu-id="f8809-146">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a><span data-ttu-id="f8809-147">Per aggiungere il controllo personalizzato al modulo host</span><span class="sxs-lookup"><span data-stu-id="f8809-147">To add your custom control to the host form</span></span>  
  
1.  <span data-ttu-id="f8809-148">Aprire Form1 nel progetto "DynamicLayout", il **finestra di progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="f8809-148">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="f8809-149">Nel **casella degli strumenti**, aprire il **DebugControlLibrary componenti** scheda e trascinare un' **DebugControl** istanza nel form.</span><span class="sxs-lookup"><span data-stu-id="f8809-149">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>  
  
3.  <span data-ttu-id="f8809-150">Trovare il `DemoString` proprietà personalizzata nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="f8809-150">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="f8809-151">Si noti che è possibile modificare il relativo valore come si farebbe con qualsiasi altra proprietà.</span><span class="sxs-lookup"><span data-stu-id="f8809-151">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="f8809-152">Si noti inoltre che quando la `DemoString` viene selezionata una proprietà, stringa di descrizione della proprietà viene visualizzata nella parte inferiore della **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="f8809-152">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="f8809-153">Impostazione del progetto per il debug in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f8809-153">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="f8809-154">Per eseguire il debug di comportamento in fase di progettazione del controllo personalizzato, si eseguirà il debug di un'istanza separata di Visual Studio che codice del controllo personalizzato in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f8809-154">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="f8809-155">Per configurare il progetto per il debug in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f8809-155">To set up the project for design-time debugging</span></span>  
  
1.  <span data-ttu-id="f8809-156">Fare clic sui **DebugControlLibrary** del progetto nel **Esplora soluzioni** e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f8809-156">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f8809-157">Nel **DebugControlLibrary** delle proprietà, selezionare la **Debug** scheda.</span><span class="sxs-lookup"><span data-stu-id="f8809-157">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>  
  
     <span data-ttu-id="f8809-158">Nel **azione di avvio** sezione, selezionare **Avvia programma esterno**.</span><span class="sxs-lookup"><span data-stu-id="f8809-158">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="f8809-159">Sarà pertanto il debug di un'istanza separata di Visual Studio, fare clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) per cercare l'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f8809-159">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="f8809-160">È il nome del file eseguibile **devenv.exe**, e se è installato nel percorso predefinito, il percorso è %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span><span class="sxs-lookup"><span data-stu-id="f8809-160">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
3.  <span data-ttu-id="f8809-161">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="f8809-161">Click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="f8809-162">Fare doppio clic il **DebugControlLibrary** del progetto e selezionare **imposta come progetto di avvio** per abilitare la configurazione di debug.</span><span class="sxs-lookup"><span data-stu-id="f8809-162">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>  
  
## <a name="debugging-your-custom-control-at-design-time"></a><span data-ttu-id="f8809-163">Debug del controllo personalizzato in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f8809-163">Debugging Your Custom Control at Design Time</span></span>  
 <span data-ttu-id="f8809-164">A questo punto si è pronti per eseguire il debug del controllo personalizzato che viene eseguito in modalità progettazione.</span><span class="sxs-lookup"><span data-stu-id="f8809-164">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="f8809-165">Quando si avvia la sessione di debug, una nuova istanza di Visual Studio verrà creata e si userà per caricare la soluzione "DynamicLayout".</span><span class="sxs-lookup"><span data-stu-id="f8809-165">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="f8809-166">Quando si apre Form1 nel **progettazione form**, verrà creata e verrà avviata l'esecuzione di un'istanza del controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f8809-166">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a><span data-ttu-id="f8809-167">Per eseguire il debug del controllo personalizzato in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f8809-167">To debug your custom control at design time</span></span>  
  
1.  <span data-ttu-id="f8809-168">Aprire il **DebugControl** file di origine il **Editor di codice** e inserire un punto di interruzione nel `Set` funzione di accesso del `DemoString` proprietà.</span><span class="sxs-lookup"><span data-stu-id="f8809-168">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>  
  
2.  <span data-ttu-id="f8809-169">Premere F5 per avviare la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="f8809-169">Press F5 to start the debugging session.</span></span> <span data-ttu-id="f8809-170">Si noti che viene creata una nuova istanza di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f8809-170">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="f8809-171">È possibile distinguere tra le istanze in due modi:</span><span class="sxs-lookup"><span data-stu-id="f8809-171">You can distinguish between the instances in two ways:</span></span>  
  
    -   <span data-ttu-id="f8809-172">L'istanza di debug è presente la parola **in esecuzione** nella barra del titolo</span><span class="sxs-lookup"><span data-stu-id="f8809-172">The debugging instance has the word **Running** in its title bar</span></span>  
  
    -   <span data-ttu-id="f8809-173">L'istanza di debug ha il **avviare** sul pulsante relativo **Debug** disabilitata sulla barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="f8809-173">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>  
  
     <span data-ttu-id="f8809-174">Il punto di interruzione viene impostato nell'istanza di debug.</span><span class="sxs-lookup"><span data-stu-id="f8809-174">Your breakpoint is set in the debugging instance.</span></span>  
  
3.  <span data-ttu-id="f8809-175">Nella nuova istanza di Visual Studio, aprire la soluzione "DynamicLayout".</span><span class="sxs-lookup"><span data-stu-id="f8809-175">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="f8809-176">È possibile trovare facilmente la soluzione selezionando **progetti recenti** dalle **File** menu.</span><span class="sxs-lookup"><span data-stu-id="f8809-176">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="f8809-177">Il file della soluzione "DebuggingExample" verrà elencato come più i file usati di recente.</span><span class="sxs-lookup"><span data-stu-id="f8809-177">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>  
  
4.  <span data-ttu-id="f8809-178">Aprire Form1 nel **progettazione form** e selezionare il **DebugControl** controllo.</span><span class="sxs-lookup"><span data-stu-id="f8809-178">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>  
  
5.  <span data-ttu-id="f8809-179">Modificare il valore della `DemoString` proprietà.</span><span class="sxs-lookup"><span data-stu-id="f8809-179">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="f8809-180">Si noti che quando si esegue il commit della modifica, l'istanza di debug di Visual Studio acquisisce lo stato attivo e l'esecuzione si arresta in corrispondenza del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="f8809-180">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="f8809-181">È possibile passo a passo la funzione di accesso di proprietà come il sarebbe qualsiasi altro codice.</span><span class="sxs-lookup"><span data-stu-id="f8809-181">You can single-step through the property accessor just as your would any other code.</span></span>  
  
6.  <span data-ttu-id="f8809-182">Dopo averli completati con la sessione di debug, è possibile uscire chiudendo l'istanza host di Visual Studio o facendo clic la **arresta debug** pulsante nell'istanza di debug.</span><span class="sxs-lookup"><span data-stu-id="f8809-182">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f8809-183">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f8809-183">Next Steps</span></span>  
 <span data-ttu-id="f8809-184">Ora che è possibile eseguire il debug di controlli personalizzati in fase di progettazione, esistono diverse possibilità per espandere l'interazione del controllo con l'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f8809-184">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>  
  
-   <span data-ttu-id="f8809-185">È possibile usare la <xref:System.ComponentModel.Component.DesignMode%2A> proprietà del <xref:System.ComponentModel.Component> classe per scrivere codice che verrà eseguito solo in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="f8809-185">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="f8809-186">Per informazioni dettagliate, vedere <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="f8809-186">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>  
  
-   <span data-ttu-id="f8809-187">Esistono diversi attributi è possibile applicare alle proprietà del controllo per modificare l'interazione del controllo personalizzato con la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="f8809-187">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="f8809-188">È possibile trovare questi attributi nel <xref:System.ComponentModel?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f8809-188">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>  
  
-   <span data-ttu-id="f8809-189">È possibile scrivere una finestra di progettazione personalizzata per il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f8809-189">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="f8809-190">Ciò consente il controllo completo della fase di progettazione utilizzando l'infrastruttura della finestra di progettazione extensible esposta da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f8809-190">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="f8809-191">Per informazioni dettagliate, vedere [procedura dettagliata: creazione di un Windows Form controllo che accetta i vantaggi di Visual Studio in fase di progettazione funzionalità](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="f8809-191">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8809-192">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8809-192">See Also</span></span>  
 [<span data-ttu-id="f8809-193">Procedura dettagliata: Creazione di un controllo Windows Form che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f8809-193">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [<span data-ttu-id="f8809-194">Procedura: accedere ai servizi in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f8809-194">How to: Access Design-Time Services</span></span>](https://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [<span data-ttu-id="f8809-195">Procedura: Accedere al supporto in fase di progettazione in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8809-195">How to: Access Design-Time Support in Windows Forms</span></span>](https://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
