---
title: Debug di controlli personalizzati in fase di progettazione
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9e292a1219c24571bcb35db2fe357b0197c8812
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740192"
---
# <a name="walkthrough-debug-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="04be7-102">Procedura dettagliata: debug di controlli di Windows Forms personalizzati in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="04be7-102">Walkthrough: Debug Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="04be7-103">Quando si crea un controllo personalizzato, sarà spesso necessario eseguire il debug del comportamento in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="04be7-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="04be7-104">Questo vale soprattutto se si crea una finestra di progettazione personalizzata per il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="04be7-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="04be7-105">Per informazioni dettagliate, vedere [procedura dettagliata: creazione di un controllo Windows Forms che sfrutta le funzionalità della fase di progettazione di Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="04be7-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="04be7-106">È possibile eseguire il debug dei controlli personalizzati con Visual Studio, proprio come per qualsiasi altra classe .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="04be7-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="04be7-107">La differenza è che si eseguirà il debug di un'istanza separata di Visual Studio che esegue il codice del controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="04be7-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="04be7-108">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="04be7-108">Create the project</span></span>

<span data-ttu-id="04be7-109">Il primo passaggio consiste nel creare il progetto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="04be7-109">The first step is to create the application project.</span></span> <span data-ttu-id="04be7-110">Questo progetto verrà usato per compilare l'applicazione che ospita il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="04be7-110">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="04be7-111">In Visual Studio creare un progetto di applicazione Windows e denominarlo **DebuggingExample**.</span><span class="sxs-lookup"><span data-stu-id="04be7-111">In Visual Studio, create a Windows Application project, and name it **DebuggingExample**.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="04be7-112">Creare il progetto di libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="04be7-112">Create the control library project</span></span>

1. <span data-ttu-id="04be7-113">Aggiungere un progetto **libreria di controlli Windows** alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="04be7-113">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="04be7-114">Aggiungere un nuovo elemento **UserControl** al progetto DebugControlLibrary.</span><span class="sxs-lookup"><span data-stu-id="04be7-114">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="04be7-115">Denominarlo **DebugControl**.</span><span class="sxs-lookup"><span data-stu-id="04be7-115">Name it **DebugControl**.</span></span>

3. <span data-ttu-id="04be7-116">In **Esplora soluzioni**eliminare il controllo predefinito del progetto eliminando il file di codice con un nome di base di UserControl1.</span><span class="sxs-lookup"><span data-stu-id="04be7-116">In **Solution Explorer**, delete the project's default control by deleting the code file with a base name of UserControl1.</span></span>

4. <span data-ttu-id="04be7-117">Compila la soluzione.</span><span class="sxs-lookup"><span data-stu-id="04be7-117">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="04be7-118">Punto di controllo</span><span class="sxs-lookup"><span data-stu-id="04be7-118">Checkpoint</span></span>

<span data-ttu-id="04be7-119">A questo punto, sarà possibile visualizzare il controllo personalizzato nella **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="04be7-119">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="04be7-120">Per controllare lo stato di avanzamento, trovare la nuova scheda denominata **DebugControlLibrary Components** e fare clic per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="04be7-120">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="04be7-121">Quando si apre, il controllo verrà visualizzato come **DebugControl** con l'icona predefinita accanto.</span><span class="sxs-lookup"><span data-stu-id="04be7-121">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="04be7-122">Aggiungere una proprietà al controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="04be7-122">Add a property to your custom control</span></span>

<span data-ttu-id="04be7-123">Per dimostrare che il codice del controllo personalizzato viene eseguito in fase di progettazione, si aggiungerà una proprietà e si imposterà un punto di interruzione nel codice che implementa la proprietà.</span><span class="sxs-lookup"><span data-stu-id="04be7-123">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="04be7-124">Aprire **DebugControl** nell' **editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="04be7-124">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="04be7-125">Aggiungere il codice seguente alla definizione della classe:</span><span class="sxs-lookup"><span data-stu-id="04be7-125">Add the following code to the class definition:</span></span>

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

2. <span data-ttu-id="04be7-126">Compila la soluzione.</span><span class="sxs-lookup"><span data-stu-id="04be7-126">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="04be7-127">Aggiungere il controllo personalizzato al modulo host</span><span class="sxs-lookup"><span data-stu-id="04be7-127">Add your custom control to the host form</span></span>

<span data-ttu-id="04be7-128">Per eseguire il debug del comportamento in fase di progettazione del controllo personalizzato, è necessario inserire un'istanza della classe del controllo personalizzato in un form host.</span><span class="sxs-lookup"><span data-stu-id="04be7-128">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="04be7-129">Nel progetto "DebuggingExample" aprire Form1 nel **Progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="04be7-129">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="04be7-130">Nella **casella degli strumenti**aprire la scheda **componenti di DebugControlLibrary** e trascinare un'istanza di **DebugControl** nel form.</span><span class="sxs-lookup"><span data-stu-id="04be7-130">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="04be7-131">Trovare la proprietà personalizzata `DemoString` nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="04be7-131">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="04be7-132">Si noti che è possibile modificare il valore come qualsiasi altra proprietà.</span><span class="sxs-lookup"><span data-stu-id="04be7-132">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="04be7-133">Si noti inoltre che quando si seleziona la proprietà `DemoString`, la stringa di descrizione della proprietà viene visualizzata nella parte inferiore della finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="04be7-133">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="04be7-134">Configurare il progetto per il debug in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="04be7-134">Set up the project for design-time debugging</span></span>

<span data-ttu-id="04be7-135">Per eseguire il debug del comportamento in fase di progettazione del controllo personalizzato, si eseguirà il debug di un'istanza separata di Visual Studio che esegue il codice del controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="04be7-135">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="04be7-136">Fare clic con il pulsante destro del mouse sul progetto **DebugControlLibrary** nel **Esplora soluzioni** e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="04be7-136">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="04be7-137">Nella finestra delle proprietà di **DebugControlLibrary** selezionare la scheda **debug** .</span><span class="sxs-lookup"><span data-stu-id="04be7-137">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="04be7-138">Nella sezione **azione di avvio** selezionare **Avvia programma esterno**.</span><span class="sxs-lookup"><span data-stu-id="04be7-138">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="04be7-139">Si eseguirà il debug di un'istanza separata di Visual Studio, quindi fare clic sui puntini di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante Finestra Proprietà di Visual Studio](./media/visual-studio-ellipsis-button.png)) per cercare l'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04be7-139">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="04be7-140">Il nome del file eseguibile è **devenv. exe**e, se è stato installato nel percorso predefinito, il percorso è *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\\\<Edition > \Common7\IDE*.</span><span class="sxs-lookup"><span data-stu-id="04be7-140">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\\\<edition>\Common7\IDE*.</span></span>

3. <span data-ttu-id="04be7-141">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="04be7-141">Select **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="04be7-142">Fare clic con il pulsante destro del mouse sul progetto **DebugControlLibrary** e selezionare **Imposta come progetto di avvio** per abilitare questa configurazione di debug.</span><span class="sxs-lookup"><span data-stu-id="04be7-142">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="04be7-143">Eseguire il debug del controllo personalizzato in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="04be7-143">Debug your custom control at design time</span></span>

<span data-ttu-id="04be7-144">A questo punto si è pronti per eseguire il debug del controllo personalizzato durante l'esecuzione in modalità progettazione.</span><span class="sxs-lookup"><span data-stu-id="04be7-144">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="04be7-145">Quando si avvia la sessione di debug, viene creata una nuova istanza di Visual Studio che verrà utilizzata per caricare la soluzione "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="04be7-145">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="04be7-146">Quando si apre Form1 in **progettazione form**, verrà creata un'istanza del controllo personalizzato che inizierà a essere in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="04be7-146">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="04be7-147">Aprire il file di origine **DebugControl** nell' **editor di codice** e inserire un punto di interruzione nella funzione di accesso `Set` della proprietà `DemoString`.</span><span class="sxs-lookup"><span data-stu-id="04be7-147">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="04be7-148">Premere **F5** per avviare la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="04be7-148">Press **F5** to start the debugging session.</span></span> <span data-ttu-id="04be7-149">Viene creata una nuova istanza di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04be7-149">A new instance of Visual Studio is created.</span></span> <span data-ttu-id="04be7-150">È possibile distinguere tra le istanze in due modi:</span><span class="sxs-lookup"><span data-stu-id="04be7-150">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="04be7-151">Nell'istanza di debug è presente la parola in **esecuzione** nella relativa barra del titolo.</span><span class="sxs-lookup"><span data-stu-id="04be7-151">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="04be7-152">L'istanza di debug dispone del pulsante **Avvia** sulla barra degli strumenti di **debug** disabilitata</span><span class="sxs-lookup"><span data-stu-id="04be7-152">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

   <span data-ttu-id="04be7-153">Il punto di interruzione viene impostato nell'istanza di debug.</span><span class="sxs-lookup"><span data-stu-id="04be7-153">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="04be7-154">Nella nuova istanza di Visual Studio aprire la soluzione "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="04be7-154">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="04be7-155">È possibile trovare facilmente la soluzione selezionando **progetti recenti** dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="04be7-155">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="04be7-156">Il file di soluzione "DebuggingExample. sln" verrà elencato come file usato più di recente.</span><span class="sxs-lookup"><span data-stu-id="04be7-156">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="04be7-157">Aprire Form1 in **progettazione form** e selezionare il controllo **DebugControl** .</span><span class="sxs-lookup"><span data-stu-id="04be7-157">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="04be7-158">Modificare il valore della proprietà `DemoString` .</span><span class="sxs-lookup"><span data-stu-id="04be7-158">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="04be7-159">Quando si esegue il commit della modifica, l'istanza di debug di Visual Studio acquisisce lo stato attivo e l'esecuzione si arresta in corrispondenza del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="04be7-159">When you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="04be7-160">È possibile eseguire la funzione di accesso alla proprietà solo come qualsiasi altro codice.</span><span class="sxs-lookup"><span data-stu-id="04be7-160">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="04be7-161">Per arrestare il debug, chiudere l'istanza ospitata di Visual Studio oppure selezionare il pulsante **Interrompi debug** nell'istanza di debug.</span><span class="sxs-lookup"><span data-stu-id="04be7-161">To stop debugging, exit the hosted instance of Visual Studio or select the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="04be7-162">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="04be7-162">Next steps</span></span>

<span data-ttu-id="04be7-163">Ora che è possibile eseguire il debug dei controlli personalizzati in fase di progettazione, esistono molte possibilità per espandere l'interazione del controllo con l'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04be7-163">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="04be7-164">È possibile utilizzare la proprietà <xref:System.ComponentModel.Component.DesignMode%2A> della classe <xref:System.ComponentModel.Component> per scrivere codice che verrà eseguito solo in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="04be7-164">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="04be7-165">Per informazioni dettagliate, vedere <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="04be7-165">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="04be7-166">Sono disponibili diversi attributi che è possibile applicare alle proprietà del controllo per modificare l'interazione del controllo personalizzato con la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="04be7-166">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="04be7-167">È possibile trovare questi attributi nello spazio dei nomi <xref:System.ComponentModel?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="04be7-167">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="04be7-168">È possibile scrivere una finestra di progettazione personalizzata per il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="04be7-168">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="04be7-169">Questo consente di controllare completamente l'esperienza di progettazione usando l'infrastruttura di progettazione estendibile esposta da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04be7-169">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="04be7-170">Per informazioni dettagliate, vedere [procedura dettagliata: creazione di un controllo Windows Forms che sfrutta le funzionalità della fase di progettazione di Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="04be7-170">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="04be7-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04be7-171">See also</span></span>

- [<span data-ttu-id="04be7-172">Procedura dettagliata: Creazione di un controllo Windows Form che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="04be7-172">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
