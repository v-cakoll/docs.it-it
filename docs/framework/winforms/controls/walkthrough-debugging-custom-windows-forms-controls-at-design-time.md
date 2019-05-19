---
title: 'Procedura dettagliata: Debug di controlli di Windows Form personalizzati in fase di progettazione'
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
ms.openlocfilehash: 39adcbd6d915f8b086df7e425efbe08ae8680a45
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882456"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="31b0e-102">Procedura dettagliata: Debug di controlli di Windows Form personalizzati in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="31b0e-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="31b0e-103">Quando si crea un controllo personalizzato, è spesso risulterà necessario per eseguire il debug relativo comportamento in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="31b0e-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="31b0e-104">Ciò è particolarmente vero se si crea una finestra di progettazione personalizzata per il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="31b0e-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="31b0e-105">Per informazioni dettagliate, vedere [procedura dettagliata: Creazione di un Windows Form di controllo che consente di sfruttare le funzionalità in fase di progettazione di Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="31b0e-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="31b0e-106">È possibile eseguire il debug dei controlli personalizzati utilizzando Visual Studio, esattamente come si potrebbero eseguire il debug di eventuali altre classi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="31b0e-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="31b0e-107">La differenza è che si eseguirà il debug di un'istanza separata di Visual Studio che codice del controllo personalizzato in esecuzione</span><span class="sxs-lookup"><span data-stu-id="31b0e-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>

<span data-ttu-id="31b0e-108">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="31b0e-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="31b0e-109">Creazione di un progetto Windows Form per ospitare il controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="31b0e-109">Creating a Windows Forms project to host your custom control</span></span>

- <span data-ttu-id="31b0e-110">Creazione di un progetto di libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="31b0e-110">Creating a control library project</span></span>

- <span data-ttu-id="31b0e-111">Aggiunta di una proprietà del controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="31b0e-111">Adding a property to your custom control</span></span>

- <span data-ttu-id="31b0e-112">Aggiunta del controllo personalizzato al modulo host</span><span class="sxs-lookup"><span data-stu-id="31b0e-112">Adding your custom control to the host form</span></span>

- <span data-ttu-id="31b0e-113">Impostazione del progetto per il debug in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="31b0e-113">Setting up the project for design-time debugging</span></span>

- <span data-ttu-id="31b0e-114">Debug del controllo personalizzato in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="31b0e-114">Debugging your custom control at design time</span></span>

<span data-ttu-id="31b0e-115">Al termine, si avrà una conoscenza delle attività necessarie per il debug del comportamento in fase di progettazione di un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="31b0e-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="31b0e-116">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="31b0e-116">Create the project</span></span>

<span data-ttu-id="31b0e-117">Il primo passaggio consiste nel creare il progetto di applicazione.</span><span class="sxs-lookup"><span data-stu-id="31b0e-117">The first step is to create the application project.</span></span> <span data-ttu-id="31b0e-118">Si userà questo progetto per compilare l'applicazione che ospita il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="31b0e-118">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="31b0e-119">In Visual Studio, creare un progetto applicazione Windows denominato "DynamicLayout" (**File** > **New** > **progetto**  >  **Visual C#**  oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="31b0e-119">In Visual Studio, create a Windows Application project called "DebuggingExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="31b0e-120">Creare il progetto di libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="31b0e-120">Create the control library project</span></span>

1. <span data-ttu-id="31b0e-121">Aggiungere un **libreria di controlli Windows** progetto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="31b0e-121">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="31b0e-122">Aggiungere un nuovo **UserControl** elemento al progetto DebugControlLibrary.</span><span class="sxs-lookup"><span data-stu-id="31b0e-122">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="31b0e-123">Per informazioni dettagliate, vedere [Procedura: Aggiungere nuovi elementi di progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="31b0e-123">For details, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span> <span data-ttu-id="31b0e-124">Assegnare al nuovo file di origine di un nome di base di "DebugControl".</span><span class="sxs-lookup"><span data-stu-id="31b0e-124">Give the new source file a base name of "DebugControl".</span></span>

3. <span data-ttu-id="31b0e-125">Usando il **Esplora soluzioni**, eliminare il controllo del progetto predefinita eliminando il file di codice con il nome di base "`UserControl1`".</span><span class="sxs-lookup"><span data-stu-id="31b0e-125">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="31b0e-126">Per informazioni dettagliate, vedere [Procedura: Rimuovere, eliminare ed escludere elementi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="31b0e-126">For details, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

4. <span data-ttu-id="31b0e-127">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="31b0e-127">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="31b0e-128">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="31b0e-128">Checkpoint</span></span>

<span data-ttu-id="31b0e-129">A questo punto, sarà in grado di visualizzare il controllo personalizzato nel **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="31b0e-129">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="31b0e-130">Per controllare lo stato di avanzamento, individuare la nuova scheda denominata **Componenti DebugControlLibrary** e fare clic per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="31b0e-130">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="31b0e-131">Quando si apre, verrà visualizzato il controllo elencato come **DebugControl** con accanto l'icona predefinita.</span><span class="sxs-lookup"><span data-stu-id="31b0e-131">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="31b0e-132">Aggiungere una proprietà del controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="31b0e-132">Add a property to your custom control</span></span>

<span data-ttu-id="31b0e-133">Per dimostrare che il codice del controllo personalizzato sia in esecuzione in fase di progettazione, si verrà aggiunta una proprietà e impostare un punto di interruzione nel codice che implementa la proprietà.</span><span class="sxs-lookup"><span data-stu-id="31b0e-133">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="31b0e-134">Aprire **DebugControl** nel **Editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="31b0e-134">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="31b0e-135">Aggiungere il codice seguente alla definizione della classe:</span><span class="sxs-lookup"><span data-stu-id="31b0e-135">Add the following code to the class definition:</span></span>

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

2. <span data-ttu-id="31b0e-136">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="31b0e-136">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="31b0e-137">Aggiungi controllo personalizzato al modulo host</span><span class="sxs-lookup"><span data-stu-id="31b0e-137">Add your custom control to the host form</span></span>

<span data-ttu-id="31b0e-138">Per eseguire il debug di comportamento in fase di progettazione del controllo personalizzato, si inserirà un'istanza della classe del controllo personalizzato in un form di host.</span><span class="sxs-lookup"><span data-stu-id="31b0e-138">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="31b0e-139">Aprire Form1 nel progetto "DynamicLayout", il **finestra di progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="31b0e-139">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="31b0e-140">Nel **casella degli strumenti**, aprire il **DebugControlLibrary componenti** scheda e trascinare un' **DebugControl** istanza nel form.</span><span class="sxs-lookup"><span data-stu-id="31b0e-140">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="31b0e-141">Trovare il `DemoString` proprietà personalizzata nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="31b0e-141">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="31b0e-142">Si noti che è possibile modificare il relativo valore come si farebbe con qualsiasi altra proprietà.</span><span class="sxs-lookup"><span data-stu-id="31b0e-142">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="31b0e-143">Si noti inoltre che quando la `DemoString` viene selezionata una proprietà, stringa di descrizione della proprietà viene visualizzata nella parte inferiore della **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="31b0e-143">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="31b0e-144">Configurare il progetto per il debug in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="31b0e-144">Set up the project for design-time debugging</span></span>

<span data-ttu-id="31b0e-145">Per eseguire il debug di comportamento in fase di progettazione del controllo personalizzato, si eseguirà il debug di un'istanza separata di Visual Studio che codice del controllo personalizzato in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="31b0e-145">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="31b0e-146">Fare clic sui **DebugControlLibrary** del progetto nel **Esplora soluzioni** e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="31b0e-146">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="31b0e-147">Nel **DebugControlLibrary** delle proprietà, selezionare la **Debug** scheda.</span><span class="sxs-lookup"><span data-stu-id="31b0e-147">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="31b0e-148">Nel **azione di avvio** sezione, selezionare **Avvia programma esterno**.</span><span class="sxs-lookup"><span data-stu-id="31b0e-148">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="31b0e-149">Sarà pertanto il debug di un'istanza separata di Visual Studio, fare clic sui puntini di sospensione (![The puntini di sospensione nella finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) per cercare l'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31b0e-149">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="31b0e-150">È il nome del file eseguibile **devenv.exe**, e se è installato nel percorso predefinito, il percorso è %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span><span class="sxs-lookup"><span data-stu-id="31b0e-150">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>

3. <span data-ttu-id="31b0e-151">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="31b0e-151">Click **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="31b0e-152">Fare doppio clic il **DebugControlLibrary** del progetto e selezionare **imposta come progetto di avvio** per abilitare la configurazione di debug.</span><span class="sxs-lookup"><span data-stu-id="31b0e-152">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="31b0e-153">Eseguire il debug del controllo personalizzato in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="31b0e-153">Debug your custom control at design time</span></span>

<span data-ttu-id="31b0e-154">A questo punto si è pronti per eseguire il debug del controllo personalizzato che viene eseguito in modalità progettazione.</span><span class="sxs-lookup"><span data-stu-id="31b0e-154">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="31b0e-155">Quando si avvia la sessione di debug, una nuova istanza di Visual Studio verrà creata e si userà per caricare la soluzione "DynamicLayout".</span><span class="sxs-lookup"><span data-stu-id="31b0e-155">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="31b0e-156">Quando si apre Form1 nel **progettazione form**, verrà creata e verrà avviata l'esecuzione di un'istanza del controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="31b0e-156">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="31b0e-157">Aprire il **DebugControl** file di origine il **Editor di codice** e inserire un punto di interruzione nel `Set` funzione di accesso del `DemoString` proprietà.</span><span class="sxs-lookup"><span data-stu-id="31b0e-157">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="31b0e-158">Premere F5 per avviare la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="31b0e-158">Press F5 to start the debugging session.</span></span> <span data-ttu-id="31b0e-159">Si noti che viene creata una nuova istanza di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31b0e-159">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="31b0e-160">È possibile distinguere tra le istanze in due modi:</span><span class="sxs-lookup"><span data-stu-id="31b0e-160">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="31b0e-161">L'istanza di debug è presente la parola **in esecuzione** nella barra del titolo</span><span class="sxs-lookup"><span data-stu-id="31b0e-161">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="31b0e-162">L'istanza di debug ha il **avviare** sul pulsante relativo **Debug** disabilitata sulla barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="31b0e-162">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

     <span data-ttu-id="31b0e-163">Il punto di interruzione viene impostato nell'istanza di debug.</span><span class="sxs-lookup"><span data-stu-id="31b0e-163">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="31b0e-164">Nella nuova istanza di Visual Studio, aprire la soluzione "DynamicLayout".</span><span class="sxs-lookup"><span data-stu-id="31b0e-164">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="31b0e-165">È possibile trovare facilmente la soluzione selezionando **progetti recenti** dalle **File** menu.</span><span class="sxs-lookup"><span data-stu-id="31b0e-165">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="31b0e-166">Il file della soluzione "DebuggingExample" verrà elencato come più i file usati di recente.</span><span class="sxs-lookup"><span data-stu-id="31b0e-166">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="31b0e-167">Aprire Form1 nel **progettazione form** e selezionare il **DebugControl** controllo.</span><span class="sxs-lookup"><span data-stu-id="31b0e-167">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="31b0e-168">Modificare il valore della proprietà `DemoString` .</span><span class="sxs-lookup"><span data-stu-id="31b0e-168">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="31b0e-169">Si noti che quando si esegue il commit della modifica, l'istanza di debug di Visual Studio acquisisce lo stato attivo e l'esecuzione si arresta in corrispondenza del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="31b0e-169">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="31b0e-170">È possibile passo a passo la funzione di accesso di proprietà come il sarebbe qualsiasi altro codice.</span><span class="sxs-lookup"><span data-stu-id="31b0e-170">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="31b0e-171">Dopo averli completati con la sessione di debug, è possibile uscire chiudendo l'istanza host di Visual Studio o facendo clic la **arresta debug** pulsante nell'istanza di debug.</span><span class="sxs-lookup"><span data-stu-id="31b0e-171">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="31b0e-172">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="31b0e-172">Next steps</span></span>

<span data-ttu-id="31b0e-173">Ora che è possibile eseguire il debug di controlli personalizzati in fase di progettazione, esistono diverse possibilità per espandere l'interazione del controllo con l'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31b0e-173">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="31b0e-174">È possibile usare la <xref:System.ComponentModel.Component.DesignMode%2A> proprietà del <xref:System.ComponentModel.Component> classe per scrivere codice che verrà eseguito solo in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="31b0e-174">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="31b0e-175">Per informazioni dettagliate, vedere <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="31b0e-175">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="31b0e-176">Esistono diversi attributi è possibile applicare alle proprietà del controllo per modificare l'interazione del controllo personalizzato con la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="31b0e-176">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="31b0e-177">È possibile trovare questi attributi nel <xref:System.ComponentModel?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="31b0e-177">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="31b0e-178">È possibile scrivere una finestra di progettazione personalizzata per il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="31b0e-178">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="31b0e-179">Ciò consente il controllo completo della fase di progettazione utilizzando l'infrastruttura della finestra di progettazione extensible esposta da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31b0e-179">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="31b0e-180">Per informazioni dettagliate, vedere [procedura dettagliata: Creazione di un Windows Form di controllo che consente di sfruttare le funzionalità in fase di progettazione di Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="31b0e-180">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="31b0e-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31b0e-181">See also</span></span>

- [<span data-ttu-id="31b0e-182">Procedura dettagliata: Creazione di un controllo di Windows Form che consente di sfruttare le funzionalità in fase di progettazione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="31b0e-182">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
- <span data-ttu-id="31b0e-183">[Procedura: Servizi di accesso in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="31b0e-183">[How to: Access Design-Time Services](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span></span>
- <span data-ttu-id="31b0e-184">[Procedura: Supporto dell'accesso in fase di progettazione in Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="31b0e-184">[How to: Access Design-Time Support in Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span></span>
