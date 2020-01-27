---
title: Memorizzare nella cache i dati dell'app
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: b7d999f94e2f2ae410a16e537d51c0f890def4e1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728063"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="3ce7f-102">Procedura dettagliata: memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="3ce7f-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="3ce7f-103">La memorizzazione nella cache consente di inserire i dati in memoria per l'accesso rapido.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="3ce7f-104">Quando accedono nuovamente ai dati, le applicazioni possono recuperarli dalla cache anziché dall'origine.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="3ce7f-105">In questo modo si possono ottenere migliori prestazioni e scalabilità.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-105">This can improve performance and scalability.</span></span> <span data-ttu-id="3ce7f-106">Inoltre, se si memorizzano i dati nella cache, questi sono accessibili anche quando l'origine dati è temporaneamente non disponibile.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="3ce7f-107">Il .NET Framework fornisce classi che consentono di usare la memorizzazione nella cache nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-107">The .NET Framework provides classes that enable you to use caching in .NET Framework applications.</span></span> <span data-ttu-id="3ce7f-108">Queste classi si trovano nello spazio dei nomi <xref:System.Runtime.Caching>.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="3ce7f-109">Lo spazio dei nomi <xref:System.Runtime.Caching> è nuovo in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-109">The <xref:System.Runtime.Caching> namespace is new in the .NET Framework 4.</span></span> <span data-ttu-id="3ce7f-110">Questo spazio dei nomi rende disponibile la memorizzazione nella cache per tutte le applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-110">This namespace makes caching is available to all .NET Framework applications.</span></span> <span data-ttu-id="3ce7f-111">Nelle versioni precedenti del .NET Framework, la memorizzazione nella cache era disponibile solo nello spazio dei nomi <xref:System.Web> e pertanto richiedeva una dipendenza dalle classi ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-111">In previous versions of the .NET Framework, caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="3ce7f-112">In questa procedura dettagliata viene illustrato come utilizzare la funzionalità di memorizzazione nella cache disponibile nel .NET Framework come parte di un'applicazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ce7f-112">This walkthrough shows you how to use the caching functionality that is available in the .NET Framework as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="3ce7f-113">Nella procedura dettagliata viene memorizzato nella cache il contenuto di un file di testo.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="3ce7f-114">Di seguito vengono illustrate le attività incluse nella procedura dettagliata:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-114">Tasks illustrated in this walkthrough include the following:</span></span>

- <span data-ttu-id="3ce7f-115">Creazione di un progetto di applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-115">Creating a WPF application project.</span></span>

- <span data-ttu-id="3ce7f-116">Aggiunta di un riferimento al .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-116">Adding a reference to the .NET Framework 4.</span></span>

- <span data-ttu-id="3ce7f-117">Inizializzazione di una cache.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-117">Initializing a cache.</span></span>

- <span data-ttu-id="3ce7f-118">Aggiunta di una voce della cache che contiene il contenuto di un file di testo.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-118">Adding a cache entry that contains the contents of a text file.</span></span>

- <span data-ttu-id="3ce7f-119">Fornire un criterio di rimozione per la voce della cache.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-119">Providing an eviction policy for the cache entry.</span></span>

- <span data-ttu-id="3ce7f-120">Monitoraggio del percorso del file memorizzato nella cache e notifica all'istanza della cache le modifiche apportate all'elemento monitorato.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ce7f-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3ce7f-121">Prerequisites</span></span>
 <span data-ttu-id="3ce7f-122">Per completare questa procedura dettagliata, è necessario:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-122">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="3ce7f-123">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-123">Visual Studio 2010.</span></span>

- <span data-ttu-id="3ce7f-124">Un file di testo che contiene una piccola quantità di testo.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="3ce7f-125">Il contenuto del file di testo viene visualizzato in una finestra di messaggio. Il codice illustrato nella procedura dettagliata presuppone che si stia utilizzando il file seguente:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="3ce7f-126">Tuttavia, è possibile usare qualsiasi file di testo e apportare piccole modifiche al codice in questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="3ce7f-127">Creazione di un progetto di applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="3ce7f-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="3ce7f-128">Si inizierà creando un progetto di applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="3ce7f-129">Per creare un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="3ce7f-129">To create a WPF application</span></span>

1. <span data-ttu-id="3ce7f-130">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-130">Start Visual Studio.</span></span>

2. <span data-ttu-id="3ce7f-131">Scegliere **nuovo**dal menu **file** , quindi fare clic su **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="3ce7f-132">Verrà visualizzata la finestra di dialogo **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-132">The **New Project** dialog box is displayed.</span></span>

3. <span data-ttu-id="3ce7f-133">In **modelli installati**selezionare il linguaggio di programmazione che si desidera utilizzare (**Visual Basic** o **oggetto C#visivo** ).</span><span class="sxs-lookup"><span data-stu-id="3ce7f-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4. <span data-ttu-id="3ce7f-134">Nella finestra di dialogo **nuovo progetto** selezionare **applicazione WPF**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ce7f-135">Se il modello **applicazione WPF** non è visibile, assicurarsi che la destinazione sia una versione del .NET Framework che supporta WPF.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the .NET Framework that supports WPF.</span></span> <span data-ttu-id="3ce7f-136">Nella finestra di dialogo **nuovo progetto** selezionare .NET Framework 4 nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-136">In the **New Project** dialog box, select .NET Framework 4 from the list.</span></span>

5. <span data-ttu-id="3ce7f-137">Nella casella di testo **nome** immettere un nome per il progetto.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="3ce7f-138">Ad esempio, è possibile immettere **WPFCaching**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-138">For example, you can enter **WPFCaching**.</span></span>

6. <span data-ttu-id="3ce7f-139">Selezionare la casella di controllo **Crea directory per soluzione**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-139">Select the **Create directory for solution** check box.</span></span>

7. <span data-ttu-id="3ce7f-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-140">Click **OK**.</span></span>

     <span data-ttu-id="3ce7f-141">WPF Designer viene aperto in visualizzazione **progettazione** e visualizza il file MainWindow. XAML.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="3ce7f-142">Visual Studio crea la cartella del **progetto** , il file Application. XAML e il file MainWindow. XAML.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="3ce7f-143">Destinazione della .NET Framework e aggiunta di un riferimento agli assembly di memorizzazione nella cache</span><span class="sxs-lookup"><span data-stu-id="3ce7f-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="3ce7f-144">Per impostazione predefinita, le applicazioni WPF sono destinate al profilo client di .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-144">By default, WPF applications target the .NET Framework 4 Client Profile.</span></span> <span data-ttu-id="3ce7f-145">Per utilizzare lo spazio dei nomi <xref:System.Runtime.Caching> in un'applicazione WPF, è necessario che l'applicazione sia destinata al .NET Framework 4 (non al profilo client .NET Framework 4) e che includa un riferimento allo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the .NET Framework 4 (not the .NET Framework 4 Client Profile) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="3ce7f-146">Il passaggio successivo consiste quindi nel modificare la destinazione .NET Framework e aggiungere un riferimento allo spazio dei nomi <xref:System.Runtime.Caching>.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="3ce7f-147">La procedura per la modifica della destinazione .NET Framework è diversa in un progetto Visual Basic e in un C# progetto visuale.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="3ce7f-148">Per modificare la .NET Framework di destinazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3ce7f-148">To change the target .NET Framework in Visual Basic</span></span>

1. <span data-ttu-id="3ce7f-149">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="3ce7f-150">Verrà visualizzata la finestra proprietà per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-150">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="3ce7f-151">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-151">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="3ce7f-152">Nella parte inferiore della finestra fare clic su **Opzioni di compilazione avanzate**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="3ce7f-153">Viene visualizzata la finestra di dialogo **impostazioni del compilatore avanzate** .</span><span class="sxs-lookup"><span data-stu-id="3ce7f-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4. <span data-ttu-id="3ce7f-154">Nell'elenco **Framework di destinazione (tutte le configurazioni)** selezionare .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-154">In the **Target framework (all configurations)** list, select .NET Framework 4.</span></span> <span data-ttu-id="3ce7f-155">(Non selezionare .NET Framework 4 profilo client).</span><span class="sxs-lookup"><span data-stu-id="3ce7f-155">(Do not select .NET Framework 4 Client Profile.)</span></span>

5. <span data-ttu-id="3ce7f-156">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-156">Click **OK**.</span></span>

     <span data-ttu-id="3ce7f-157">Viene visualizzata la finestra di dialogo **Modifica del framework di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-157">The **Target Framework Change** dialog box is displayed.</span></span>

6. <span data-ttu-id="3ce7f-158">Nella finestra di dialogo **modifica Framework di destinazione** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="3ce7f-159">Il progetto viene chiuso e quindi riaperto.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-159">The project is closed and is then reopened.</span></span>

7. <span data-ttu-id="3ce7f-160">Aggiungere un riferimento all'assembly di Caching attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-160">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="3ce7f-161">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto, quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="3ce7f-162">Selezionare la scheda **.NET** , selezionare `System.Runtime.Caching`e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="3ce7f-163">Per modificare la .NET Framework di destinazione in un C# progetto Visual</span><span class="sxs-lookup"><span data-stu-id="3ce7f-163">To change the target .NET Framework in a Visual C# project</span></span>

1. <span data-ttu-id="3ce7f-164">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="3ce7f-165">Verrà visualizzata la finestra proprietà per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-165">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="3ce7f-166">Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="3ce7f-166">Click the **Application** tab.</span></span>

3. <span data-ttu-id="3ce7f-167">Nell'elenco **Framework di destinazione** selezionare .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-167">In the **Target framework** list, select .NET Framework 4.</span></span> <span data-ttu-id="3ce7f-168">(Non selezionare **.NET Framework 4 profilo client**).</span><span class="sxs-lookup"><span data-stu-id="3ce7f-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4. <span data-ttu-id="3ce7f-169">Aggiungere un riferimento all'assembly di Caching attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-169">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="3ce7f-170">Fare clic con il pulsante destro del mouse sulla cartella **riferimenti** , quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="3ce7f-171">Selezionare la scheda **.NET** , selezionare `System.Runtime.Caching`e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="3ce7f-172">Aggiunta di un pulsante alla finestra WPF</span><span class="sxs-lookup"><span data-stu-id="3ce7f-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="3ce7f-173">Successivamente, si aggiungerà un controllo Button e si creerà un gestore eventi per l'evento `Click` del pulsante.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="3ce7f-174">Successivamente, quando si fa clic sul pulsante viene aggiunto il codice, il contenuto del file di testo viene memorizzato nella cache e visualizzato.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="3ce7f-175">Per aggiungere un controllo Button</span><span class="sxs-lookup"><span data-stu-id="3ce7f-175">To add a button control</span></span>

1. <span data-ttu-id="3ce7f-176">In **Esplora soluzioni**fare doppio clic sul file MainWindow. XAML per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2. <span data-ttu-id="3ce7f-177">Dalla **casella degli strumenti**, sotto **controlli WPF comuni**trascinare un controllo `Button` nella finestra di `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3. <span data-ttu-id="3ce7f-178">Nella finestra **Proprietà** impostare la proprietà `Content` del controllo `Button` per **ottenere la cache**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="3ce7f-179">Inizializzazione della cache e memorizzazione nella cache di una voce</span><span class="sxs-lookup"><span data-stu-id="3ce7f-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="3ce7f-180">Successivamente, verrà aggiunto il codice per eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-180">Next, you will add the code to perform the following tasks:</span></span>

- <span data-ttu-id="3ce7f-181">Creare un'istanza della classe cache, ovvero si creerà un'istanza di un nuovo oggetto <xref:System.Runtime.Caching.MemoryCache>.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

- <span data-ttu-id="3ce7f-182">Consente di specificare che la cache utilizza un oggetto <xref:System.Runtime.Caching.HostFileChangeMonitor> per monitorare le modifiche nel file di testo.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

- <span data-ttu-id="3ce7f-183">Leggere il file di testo e memorizzare nella cache il relativo contenuto come voce della cache.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-183">Read the text file and cache its contents as a cache entry.</span></span>

- <span data-ttu-id="3ce7f-184">Visualizza il contenuto del file di testo memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="3ce7f-185">Per creare l'oggetto cache</span><span class="sxs-lookup"><span data-stu-id="3ce7f-185">To create the cache object</span></span>

1. <span data-ttu-id="3ce7f-186">Fare doppio clic sul pulsante appena aggiunto per creare un gestore eventi nel file MainWindow.xaml.cs o MainWindow. XAML. vb.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2. <span data-ttu-id="3ce7f-187">Nella parte superiore del file (prima della dichiarazione di classe) aggiungere le seguenti istruzioni `Imports` (Visual Basic) o `using` (C#):</span><span class="sxs-lookup"><span data-stu-id="3ce7f-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. <span data-ttu-id="3ce7f-188">Nel gestore eventi aggiungere il codice seguente per creare un'istanza dell'oggetto cache:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="3ce7f-189">La classe <xref:System.Runtime.Caching.ObjectCache> è una classe incorporata che fornisce una cache di oggetti in memoria.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4. <span data-ttu-id="3ce7f-190">Aggiungere il codice seguente per leggere il contenuto di una voce della cache denominata `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. <span data-ttu-id="3ce7f-191">Aggiungere il codice seguente per verificare se la voce della cache denominata `filecontents` esiste:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="3ce7f-192">Se la voce della cache specificata non esiste, è necessario leggere il file di testo e aggiungerlo come voce della cache alla cache.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6. <span data-ttu-id="3ce7f-193">Nel blocco `if/then` aggiungere il codice seguente per creare un nuovo oggetto <xref:System.Runtime.Caching.CacheItemPolicy> che specifichi che la voce della cache scade dopo 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="3ce7f-194">Se non viene fornita alcuna informazione di rimozione o scadenza, il valore predefinito è <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, il che significa che le voci della cache non scadono mai in base a un tempo assoluto.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="3ce7f-195">Al contrario, le voci della cache scadono solo quando si verifica un numero eccessivo di richieste di memoria.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="3ce7f-196">Come procedura consigliata, è consigliabile specificare sempre in modo esplicito una scadenza assoluta o variabile.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7. <span data-ttu-id="3ce7f-197">All'interno del blocco `if/then` e dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per creare una raccolta per i percorsi di file che si desidera monitorare e per aggiungere il percorso del file di testo alla raccolta:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    > <span data-ttu-id="3ce7f-198">Se il file di testo che si desidera utilizzare non è `c:\cache\cacheText.txt`, specificare il percorso in cui si desidera utilizzare il file di testo.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8. <span data-ttu-id="3ce7f-199">Dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per aggiungere un nuovo oggetto <xref:System.Runtime.Caching.HostFileChangeMonitor> alla raccolta di monitoraggi delle modifiche per la voce della cache:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="3ce7f-200">L'oggetto <xref:System.Runtime.Caching.HostFileChangeMonitor> monitora il percorso del file di testo e invia una notifica alla cache se si verificano modifiche.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="3ce7f-201">In questo esempio, la voce della cache scadrà se il contenuto del file viene modificato.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="3ce7f-202">Dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per leggere il contenuto del file di testo:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="3ce7f-203">Viene aggiunto il timestamp di data e ora in modo che sia possibile visualizzare la scadenza della voce della cache.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="3ce7f-204">Dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per inserire il contenuto del file nell'oggetto cache come istanza di <xref:System.Runtime.Caching.CacheItem>:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="3ce7f-205">Specificare le informazioni sulla modalità di eliminazione della voce della cache passando l'oggetto <xref:System.Runtime.Caching.CacheItemPolicy> creato in precedenza come parametro.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="3ce7f-206">Dopo il blocco `if/then` aggiungere il codice seguente per visualizzare il contenuto del file memorizzato nella cache in una finestra di messaggio:</span><span class="sxs-lookup"><span data-stu-id="3ce7f-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="3ce7f-207">Scegliere **Compila WPFCaching** dal menu **Compila** per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="3ce7f-208">Test della memorizzazione nella cache nell'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="3ce7f-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="3ce7f-209">È ora possibile eseguire il test dell’applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="3ce7f-210">Per testare la memorizzazione nella cache nell'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="3ce7f-210">To test caching in the WPF application</span></span>

1. <span data-ttu-id="3ce7f-211">Premere CTRL+F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="3ce7f-212">Viene visualizzata la finestra `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-212">The `MainWindow` window is displayed.</span></span>

2. <span data-ttu-id="3ce7f-213">Fare clic su **Ottieni cache**.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="3ce7f-214">Il contenuto memorizzato nella cache del file di testo viene visualizzato in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="3ce7f-215">Si noti il timestamp del file.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-215">Notice the timestamp on the file.</span></span>

3. <span data-ttu-id="3ce7f-216">Chiudere la finestra di messaggio e quindi fare di nuovo clic su **Get cache** .</span><span class="sxs-lookup"><span data-stu-id="3ce7f-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="3ce7f-217">Il timestamp è invariato.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-217">The timestamp is unchanged.</span></span> <span data-ttu-id="3ce7f-218">Indica che viene visualizzato il contenuto memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-218">This indicates the cached content is displayed.</span></span>

4. <span data-ttu-id="3ce7f-219">Attendere 10 secondi o più, quindi fare di nuovo clic su **Ottieni cache** .</span><span class="sxs-lookup"><span data-stu-id="3ce7f-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="3ce7f-220">Questa volta viene visualizzato un nuovo timestamp.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="3ce7f-221">Ciò indica che i criteri consentono la scadenza della voce della cache e che viene visualizzato il nuovo contenuto memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5. <span data-ttu-id="3ce7f-222">In un editor di testo aprire il file di testo creato.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="3ce7f-223">Non apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-223">Do not make any changes yet.</span></span>

6. <span data-ttu-id="3ce7f-224">Chiudere la finestra di messaggio e quindi fare di nuovo clic su **Get cache** .</span><span class="sxs-lookup"><span data-stu-id="3ce7f-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="3ce7f-225">Si noti di nuovo il timestamp.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-225">Notice the timestamp again.</span></span>

7. <span data-ttu-id="3ce7f-226">Apportare una modifica al file di testo e quindi salvare il file.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-226">Make a change to the text file and then save the file.</span></span>

8. <span data-ttu-id="3ce7f-227">Chiudere la finestra di messaggio e quindi fare di nuovo clic su **Get cache** .</span><span class="sxs-lookup"><span data-stu-id="3ce7f-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="3ce7f-228">Questa finestra di messaggio contiene il contenuto aggiornato del file di testo e un nuovo timestamp.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="3ce7f-229">Ciò indica che il monitoraggio delle modifiche del file host ha rimosso la voce della cache immediatamente quando è stato modificato il file, anche se il periodo di timeout assoluto non è scaduto.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ce7f-230">È possibile aumentare il tempo di rimozione a 20 secondi o più per consentire più tempo per apportare modifiche al file.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="3ce7f-231">Esempio di codice</span><span class="sxs-lookup"><span data-stu-id="3ce7f-231">Code Example</span></span>
 <span data-ttu-id="3ce7f-232">Al termine di questa procedura dettagliata, il codice per il progetto creato sarà simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3ce7f-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="3ce7f-233">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ce7f-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="3ce7f-234">Memorizzazione nella cache in applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3ce7f-234">Caching in .NET Framework Applications</span></span>](../../performance/caching-in-net-framework-applications.md)
