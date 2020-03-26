---
title: "Procedura dettagliata: Localizzazione di un'applicazione ibrida"
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 69aa5ae145ffe378b7a4547e5a33826965bf7894
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111114"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="420ef-102">Procedura dettagliata: Localizzazione di un'applicazione ibrida</span><span class="sxs-lookup"><span data-stu-id="420ef-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="420ef-103">In questa procedura dettagliata [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene illustrato come localizzare gli elementi in un'applicazione ibrida basata su Windows Form.This walkthrough shows you how to localize elements in a Windows Forms-based hybrid application.</span><span class="sxs-lookup"><span data-stu-id="420ef-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a Windows Forms-based hybrid application.</span></span>

<span data-ttu-id="420ef-104">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="420ef-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="420ef-105">Creazione del progetto host Windows Form.</span><span class="sxs-lookup"><span data-stu-id="420ef-105">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="420ef-106">Aggiunta di contenuto localizzabile.</span><span class="sxs-lookup"><span data-stu-id="420ef-106">Adding localizable content.</span></span>

- <span data-ttu-id="420ef-107">Abilitazione della localizzazione.</span><span class="sxs-lookup"><span data-stu-id="420ef-107">Enabling localization.</span></span>

- <span data-ttu-id="420ef-108">Assegnazione di identificatori di risorsa.</span><span class="sxs-lookup"><span data-stu-id="420ef-108">Assigning resource identifiers.</span></span>

- <span data-ttu-id="420ef-109">Utilizzo dello strumento LocBaml per produrre un assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="420ef-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="420ef-110">Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Localizzazione di un esempio](https://go.microsoft.com/fwlink/?LinkID=160015)di applicazione ibrida .</span><span class="sxs-lookup"><span data-stu-id="420ef-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="420ef-111">Al termine, sarà disponibile un'applicazione ibrida localizzata.</span><span class="sxs-lookup"><span data-stu-id="420ef-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="420ef-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="420ef-112">Prerequisites</span></span>

<span data-ttu-id="420ef-113">Per completare questa procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="420ef-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="420ef-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="420ef-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="420ef-115">Creazione del progetto host Windows Form</span><span class="sxs-lookup"><span data-stu-id="420ef-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="420ef-116">Il primo passaggio consiste nel creare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] progetto di applicazione Windows Form e aggiungere un elemento con contenuto che verrà localizzato.</span><span class="sxs-lookup"><span data-stu-id="420ef-116">The first step is to create the Windows Forms application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="420ef-117">Per creare il progetto host</span><span class="sxs-lookup"><span data-stu-id="420ef-117">To create the host project</span></span>

1. <span data-ttu-id="420ef-118">Creare un progetto `LocalizingWpfInWf`di app **WPF** denominato .</span><span class="sxs-lookup"><span data-stu-id="420ef-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="420ef-119">(**File** > **Nuovo** > **progetto** > Visual**Cè** o Visual **Basic** > Classic**Desktop** > WPF**Application**).</span><span class="sxs-lookup"><span data-stu-id="420ef-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="420ef-120">Aggiungere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> un `SimpleControl` elemento chiamato al progetto.</span><span class="sxs-lookup"><span data-stu-id="420ef-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="420ef-121">Utilizzare <xref:System.Windows.Forms.Integration.ElementHost> il controllo `SimpleControl` per inserire un elemento nel form.</span><span class="sxs-lookup"><span data-stu-id="420ef-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="420ef-122">Per altre informazioni, vedere [Procedura dettagliata: hosting di un controllo composito WPF 3D in Windows Form.For more information, see Walkthrough: Hosting a 3D WPF Composite Control in Windows Forms.](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="420ef-122">For more information, see [Walkthrough: Hosting a 3D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="420ef-123">Aggiunta di contenuto localizzabile</span><span class="sxs-lookup"><span data-stu-id="420ef-123">Adding Localizable Content</span></span>

<span data-ttu-id="420ef-124">Successivamente, si aggiungerà un controllo etichetta [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Windows Form e si imposterà il contenuto dell'elemento su una stringa localizzabile.</span><span class="sxs-lookup"><span data-stu-id="420ef-124">Next, you will add a Windows Forms label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="420ef-125">Per aggiungere contenuto localizzabile</span><span class="sxs-lookup"><span data-stu-id="420ef-125">To add localizable content</span></span>

1. <span data-ttu-id="420ef-126">In **Esplora soluzioni**fare doppio clic su **SimpleControl.xaml** per aprirlo in Progettazione WPF.</span><span class="sxs-lookup"><span data-stu-id="420ef-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the WPF Designer.</span></span>

2. <span data-ttu-id="420ef-127">Impostare il <xref:System.Windows.Controls.Button> contenuto del controllo utilizzando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="420ef-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="420ef-128">In **Esplora soluzioni**fare doppio clic su **Form1** per aprirlo in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="420ef-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="420ef-129">Aprire la **Casella degli strumenti** e fare doppio clic su **Etichetta** per aggiungere un controllo etichetta al form.</span><span class="sxs-lookup"><span data-stu-id="420ef-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="420ef-130">Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Text%2A> su `"Hello"`.</span><span class="sxs-lookup"><span data-stu-id="420ef-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="420ef-131">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="420ef-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="420ef-132">Sia `SimpleControl` l'elemento che il controllo etichetta visualizzano il testo **"Hello".**</span><span class="sxs-lookup"><span data-stu-id="420ef-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="420ef-133">Abilitazione della localizzazione</span><span class="sxs-lookup"><span data-stu-id="420ef-133">Enabling Localization</span></span>

<span data-ttu-id="420ef-134">Progettazione Windows Form fornisce le impostazioni per abilitare la localizzazione in un assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="420ef-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="420ef-135">Per abilitare la localizzazione</span><span class="sxs-lookup"><span data-stu-id="420ef-135">To enable localization</span></span>

1. <span data-ttu-id="420ef-136">In **Esplora soluzioni**fare doppio clic su **Form1.cs** per aprirla in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="420ef-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="420ef-137">Nella finestra **Proprietà** impostare il valore della proprietà **Localizable** del form su `true`.</span><span class="sxs-lookup"><span data-stu-id="420ef-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="420ef-138">Nella finestra **Proprietà** impostare il valore della proprietà **Language** su **Spagnolo (Spagna)**.</span><span class="sxs-lookup"><span data-stu-id="420ef-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="420ef-139">In Progettazione Windows Form selezionare il controllo etichetta.</span><span class="sxs-lookup"><span data-stu-id="420ef-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="420ef-140">Nella finestra **Proprietà** impostare il <xref:System.Windows.Forms.Control.Text%2A> valore `"Hola"`della proprietà su .</span><span class="sxs-lookup"><span data-stu-id="420ef-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="420ef-141">Un nuovo file di risorse denominato Form1.es-ES.resx verrà aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="420ef-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="420ef-142">In **Esplora soluzioni**fare clic con il pulsante destro del mouse **su Form1.cs** e scegliere Visualizza **codice** per aprirlo nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="420ef-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="420ef-143">Copiare il codice `Form1` seguente nel costruttore, prima della chiamata a `InitializeComponent`.</span><span class="sxs-lookup"><span data-stu-id="420ef-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="420ef-144">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **LocalizingWpfInWf** e scegliere **Scarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="420ef-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="420ef-145">Il nome del progetto è etichettato **(non disponibile).**</span><span class="sxs-lookup"><span data-stu-id="420ef-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="420ef-146">Fare clic con il pulsante destro del mouse su **LocalizingWpfInWf**e **scegliere Modifica LocalizingWpfInWf.csproj**.</span><span class="sxs-lookup"><span data-stu-id="420ef-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="420ef-147">Il file di progetto verrà aperto nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="420ef-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="420ef-148">Copiare la riga `PropertyGroup` seguente nella prima nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="420ef-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="420ef-149">Salvare e chiudere il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="420ef-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="420ef-150">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **LocalizingWpfInWf** e scegliere **Ricarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="420ef-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="420ef-151">Assegnazione di identificatori di risorsa</span><span class="sxs-lookup"><span data-stu-id="420ef-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="420ef-152">È possibile eseguire il mapping del contenuto localizzabile agli assembly di risorse usando identificatori di risorsa.</span><span class="sxs-lookup"><span data-stu-id="420ef-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="420ef-153">L'applicazione MsBuild.exe assegna automaticamente gli identificatori di risorsa quando si specifica l'opzione. `updateuid`</span><span class="sxs-lookup"><span data-stu-id="420ef-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="420ef-154">Per assegnare identificatori di risorsa</span><span class="sxs-lookup"><span data-stu-id="420ef-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="420ef-155">Dal menu Start aprire il prompt dei comandi per gli sviluppatori per Visual Studio.From the Start Menu, open the Developer Command Prompt for Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="420ef-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="420ef-156">Per assegnare identificatori di risorsa al contenuto localizzabile, usare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="420ef-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="420ef-157">In **Esplora soluzioni**fare doppio clic su **SimpleControl.xaml** per aprirlo nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="420ef-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="420ef-158">Si noterà `msbuild` che il `Uid` comando ha aggiunto l'attributo a tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="420ef-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="420ef-159">In tal modo si semplifica la localizzazione mediante l'assegnazione di identificatori di risorsa.</span><span class="sxs-lookup"><span data-stu-id="420ef-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="420ef-160">Premere **F6** per compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="420ef-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="420ef-161">Utilizzo dello strumento LocBaml per produrre un assembly satellite</span><span class="sxs-lookup"><span data-stu-id="420ef-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="420ef-162">Il contenuto localizzato viene archiviato in un *assembly satellite*di sole risorse.</span><span class="sxs-lookup"><span data-stu-id="420ef-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="420ef-163">Utilizzare lo strumento da riga di comando LocBaml.exe per produrre un assembly localizzato per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto.</span><span class="sxs-lookup"><span data-stu-id="420ef-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="420ef-164">Per produrre un assembly satellite</span><span class="sxs-lookup"><span data-stu-id="420ef-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="420ef-165">Copiare LocBaml.exe nella cartella obj\Debug del progetto.</span><span class="sxs-lookup"><span data-stu-id="420ef-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="420ef-166">Per ulteriori informazioni, vedere [Localizzare un'applicazione](how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="420ef-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="420ef-167">Nella finestra del prompt dei comandi usare il comando seguente per estrarre stringhe di risorsa in un file temporaneo.</span><span class="sxs-lookup"><span data-stu-id="420ef-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="420ef-168">Aprire il file temp.csv con Visual Studio o un altro editor di testo.</span><span class="sxs-lookup"><span data-stu-id="420ef-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="420ef-169">Sostituire la `"Hello"` stringa con `"Hola"`la relativa traduzione in spagnolo, .</span><span class="sxs-lookup"><span data-stu-id="420ef-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="420ef-170">Salvare il file temp.csv.</span><span class="sxs-lookup"><span data-stu-id="420ef-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="420ef-171">Per generare il file di risorse localizzato, usare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="420ef-171">Use the following command to generate the localized resource file.</span></span>

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="420ef-172">Il file LocalizingWpfInWf.g.es-ES.resources viene creato nella cartella obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="420ef-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="420ef-173">Per compilare l'assembly satellite localizzato, usare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="420ef-173">Use the following command to build the localized satellite assembly.</span></span>

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="420ef-174">Il file LocalizingWpfInWf.resources.dll viene creato nella cartella obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="420ef-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="420ef-175">Copiare il file LocalizingWpfInWf.resources.dll nella cartella bin\Debug\es-ES del progetto.</span><span class="sxs-lookup"><span data-stu-id="420ef-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="420ef-176">Sostituire il file esistente.</span><span class="sxs-lookup"><span data-stu-id="420ef-176">Replace the existing file.</span></span>

8. <span data-ttu-id="420ef-177">Eseguire LocalizingWpfInWf.exe, situato nella cartella bin\Debug del progetto.</span><span class="sxs-lookup"><span data-stu-id="420ef-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="420ef-178">Non ricompilare l'applicazione altrimenti l'assembly satellite verrà sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="420ef-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="420ef-179">Nell'applicazione vengono visualizzate le stringhe localizzate invece delle stringhe in inglese.</span><span class="sxs-lookup"><span data-stu-id="420ef-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="420ef-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="420ef-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="420ef-181">Localizzare un'applicazione</span><span class="sxs-lookup"><span data-stu-id="420ef-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- <span data-ttu-id="420ef-182">[Procedura dettagliata: localizzazione di Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="420ef-182">[Walkthrough: Localizing Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span></span>
- [<span data-ttu-id="420ef-183">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="420ef-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
