---
title: "Procedura dettagliata: memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: 1eddf3ad52bab6ef4665d7c3691353fa9c54574c
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2018
ms.locfileid: "48263998"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="3b87e-102">Procedura dettagliata: memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="3b87e-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="3b87e-103">La memorizzazione nella cache consente di inserire i dati in memoria per l'accesso rapido.</span><span class="sxs-lookup"><span data-stu-id="3b87e-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="3b87e-104">Quando i dati sono accessibili anche in questo caso, le applicazioni possono ottenere i dati dalla cache anziché recuperarli dall'origine dati originale.</span><span class="sxs-lookup"><span data-stu-id="3b87e-104">When the data is accessed again, applications can get the data from the cache instead retrieving it from the original source.</span></span> <span data-ttu-id="3b87e-105">In questo modo si possono ottenere migliori prestazioni e scalabilità.</span><span class="sxs-lookup"><span data-stu-id="3b87e-105">This can improve performance and scalability.</span></span> <span data-ttu-id="3b87e-106">Inoltre, se si memorizzano i dati nella cache, questi sono accessibili anche quando l'origine dati è temporaneamente non disponibile.</span><span class="sxs-lookup"><span data-stu-id="3b87e-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="3b87e-107">Il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] fornisce le classi che consentono di usare la memorizzazione nella cache [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3b87e-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides classes that enable you to use caching in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="3b87e-108">Queste classi si trovano nel <xref:System.Runtime.Caching> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3b87e-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="3b87e-109">Il <xref:System.Runtime.Caching> dello spazio dei nomi è una novità di [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b87e-109">The <xref:System.Runtime.Caching> namespace is new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="3b87e-110">Questo spazio dei nomi rende la memorizzazione nella cache è disponibile per tutti [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3b87e-110">This namespace makes caching is available to all [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="3b87e-111">Nelle versioni precedenti di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] la memorizzazione nella cache è disponibile solo nello spazio dei nomi <xref:System.Web> e pertanto richiede una dipendenza dalle classi ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3b87e-111">In previous versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="3b87e-112">Questa procedura dettagliata illustra come usare le funzionalità di memorizzazione nella cache sono disponibile nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] come parte di un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3b87e-112">This walkthrough shows you how to use the caching functionality that is available in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="3b87e-113">Nella procedura dettagliata, si memorizzano nella cache il contenuto di un file di testo.</span><span class="sxs-lookup"><span data-stu-id="3b87e-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="3b87e-114">Di seguito vengono illustrate le attività incluse nella procedura dettagliata:</span><span class="sxs-lookup"><span data-stu-id="3b87e-114">Tasks illustrated in this walkthrough include the following:</span></span>

-   <span data-ttu-id="3b87e-115">Creazione di un progetto di applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="3b87e-115">Creating a WPF application project.</span></span>

-   <span data-ttu-id="3b87e-116">Aggiunge un riferimento al [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b87e-116">Adding a reference to the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>

-   <span data-ttu-id="3b87e-117">Inizializzazione di una cache.</span><span class="sxs-lookup"><span data-stu-id="3b87e-117">Initializing a cache.</span></span>

-   <span data-ttu-id="3b87e-118">Aggiunta di una voce della cache che contiene il contenuto di un file di testo.</span><span class="sxs-lookup"><span data-stu-id="3b87e-118">Adding a cache entry that contains the contents of a text file.</span></span>

-   <span data-ttu-id="3b87e-119">Fornire un criterio di rimozione della voce della cache.</span><span class="sxs-lookup"><span data-stu-id="3b87e-119">Providing an eviction policy for the cache entry.</span></span>

-   <span data-ttu-id="3b87e-120">Il percorso del file memorizzato nella cache di monitoraggio e la notifica l'istanza della cache sulla modifica dell'elemento monitorato.</span><span class="sxs-lookup"><span data-stu-id="3b87e-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3b87e-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3b87e-121">Prerequisites</span></span>
 <span data-ttu-id="3b87e-122">Per completare questa procedura dettagliata, è necessario:</span><span class="sxs-lookup"><span data-stu-id="3b87e-122">In order to complete this walkthrough, you will need:</span></span>

-   <span data-ttu-id="3b87e-123">Microsoft Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="3b87e-123">Microsoft Visual Studio 2010.</span></span>

-   <span data-ttu-id="3b87e-124">Un file di testo che contiene una piccola quantità di testo.</span><span class="sxs-lookup"><span data-stu-id="3b87e-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="3b87e-125">(Si verrà visualizzato il contenuto del file di testo in una finestra di messaggio). Il codice illustrato nella procedura dettagliata si presuppone che si lavora con il file seguente:</span><span class="sxs-lookup"><span data-stu-id="3b87e-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="3b87e-126">Tuttavia, è possibile usare qualsiasi file di testo e apportare piccole modifiche al codice in questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="3b87e-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="3b87e-127">Creazione di un progetto di applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="3b87e-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="3b87e-128">Inizierà creando un progetto di applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="3b87e-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="3b87e-129">Per creare un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="3b87e-129">To create a WPF application</span></span>

1.  <span data-ttu-id="3b87e-130">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3b87e-130">Start Visual Studio.</span></span>

2.  <span data-ttu-id="3b87e-131">Nel **File** menu, fare clic su **New**, quindi fare clic su **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="3b87e-132">Verrà visualizzata la finestra di dialogo **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-132">The **New Project** dialog box is displayed.</span></span>

3.  <span data-ttu-id="3b87e-133">Sotto **modelli installati**, selezionare il linguaggio di programmazione da usare (**Visual Basic** oppure **Visual c#**).</span><span class="sxs-lookup"><span data-stu-id="3b87e-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4.  <span data-ttu-id="3b87e-134">Nel **nuovo progetto** finestra di dialogo **applicazione WPF**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="3b87e-135">Se non viene visualizzato il **applicazione WPF** modello, assicurarsi che si intende utilizzare una versione del [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] che supporta WPF.</span><span class="sxs-lookup"><span data-stu-id="3b87e-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] that supports WPF.</span></span> <span data-ttu-id="3b87e-136">Nel **nuovo progetto** finestra di dialogo [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="3b87e-136">In the **New Project** dialog box, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] from the list.</span></span>

5.  <span data-ttu-id="3b87e-137">Nel **nome** testo casella, immettere un nome per il progetto.</span><span class="sxs-lookup"><span data-stu-id="3b87e-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="3b87e-138">Ad esempio, è possibile immettere **WPFCaching**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-138">For example, you can enter **WPFCaching**.</span></span>

6.  <span data-ttu-id="3b87e-139">Selezionare il **Crea directory per soluzione** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="3b87e-139">Select the **Create directory for solution** check box.</span></span>

7.  <span data-ttu-id="3b87e-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-140">Click **OK**.</span></span>

     <span data-ttu-id="3b87e-141">Viene aperta WPF **progettazione** consente di visualizzare e visualizza il file MainWindow. Xaml.</span><span class="sxs-lookup"><span data-stu-id="3b87e-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="3b87e-142">Visual Studio crea il **My Project** cartella, il file Application. XAML e il file MainWindow. Xaml.</span><span class="sxs-lookup"><span data-stu-id="3b87e-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="3b87e-143">Sviluppare per .NET Framework e aggiungere un riferimento all'assembly di memorizzazione nella cache</span><span class="sxs-lookup"><span data-stu-id="3b87e-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="3b87e-144">Per impostazione predefinita, sono destinate le applicazioni WPF di [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b87e-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="3b87e-145">Usare la <xref:System.Runtime.Caching> dello spazio dei nomi in un'applicazione WPF, l'applicazione deve avere come destinazione il [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (non il [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) e deve includere un riferimento allo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3b87e-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="3b87e-146">Pertanto, il passaggio successivo è modificare la destinazione di .NET Framework e aggiungere un riferimento al <xref:System.Runtime.Caching> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3b87e-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="3b87e-147">La procedura per la modifica della destinazione di .NET Framework è diversa in un progetto Visual Basic e in un progetto Visual c#.</span><span class="sxs-lookup"><span data-stu-id="3b87e-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="3b87e-148">Per modificare la destinazione di .NET Framework in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3b87e-148">To change the target .NET Framework in Visual Basic</span></span>

1.  <span data-ttu-id="3b87e-149">Nelle **Esplora soluzioni**, fare clic sul nome del progetto e quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="3b87e-150">Viene visualizzata la finestra delle proprietà per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3b87e-150">The properties window for the application is displayed.</span></span>

2.  <span data-ttu-id="3b87e-151">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-151">Click the **Compile** tab.</span></span>

3.  <span data-ttu-id="3b87e-152">Nella parte inferiore della finestra, fare clic su **opzioni di compilazione avanzate...** .</span><span class="sxs-lookup"><span data-stu-id="3b87e-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="3b87e-153">Il **impostazioni del compilatore avanzate** verrà visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3b87e-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4.  <span data-ttu-id="3b87e-154">Nel **framework di destinazione (tutte le configurazioni)** elenco, selezionare [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b87e-154">In the **Target framework (all configurations)** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="3b87e-155">(Non selezionare [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="3b87e-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>

5.  <span data-ttu-id="3b87e-156">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-156">Click **OK**.</span></span>

     <span data-ttu-id="3b87e-157">Viene visualizzata la finestra di dialogo **Modifica del framework di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-157">The **Target Framework Change** dialog box is displayed.</span></span>

6.  <span data-ttu-id="3b87e-158">Nel **modifica Framework di destinazione** finestra di dialogo, fare clic su **Yes**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="3b87e-159">Il progetto viene chiuso e riaperto.</span><span class="sxs-lookup"><span data-stu-id="3b87e-159">The project is closed and is then reopened.</span></span>

7.  <span data-ttu-id="3b87e-160">Aggiungere un riferimento all'assembly di memorizzazione nella cache, seguire questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="3b87e-160">Add a reference to the caching assembly by following these steps:</span></span>

    1.  <span data-ttu-id="3b87e-161">Nelle **Esplora soluzioni**, fare doppio clic il nome del progetto e quindi fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2.  <span data-ttu-id="3b87e-162">Selezionare il **.NET** scheda, seleziona `System.Runtime.Caching`, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="3b87e-163">Per modificare la destinazione di .NET Framework in un progetto Visual c#</span><span class="sxs-lookup"><span data-stu-id="3b87e-163">To change the target .NET Framework in a Visual C# project</span></span>

1.  <span data-ttu-id="3b87e-164">Nelle **Esplora soluzioni**, fare clic sul nome del progetto e quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="3b87e-165">Viene visualizzata la finestra delle proprietà per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3b87e-165">The properties window for the application is displayed.</span></span>

2.  <span data-ttu-id="3b87e-166">Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="3b87e-166">Click the **Application** tab.</span></span>

3.  <span data-ttu-id="3b87e-167">Nel **framework di destinazione** elenco, selezionare [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b87e-167">In the **Target framework** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="3b87e-168">(Non si seleziona **.NET Framework 4 Client Profile**.)</span><span class="sxs-lookup"><span data-stu-id="3b87e-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4.  <span data-ttu-id="3b87e-169">Aggiungere un riferimento all'assembly di memorizzazione nella cache, seguire questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="3b87e-169">Add a reference to the caching assembly by following these steps:</span></span>

    1.  <span data-ttu-id="3b87e-170">Fare doppio clic il **riferimenti** cartella e quindi fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2.  <span data-ttu-id="3b87e-171">Selezionare il **.NET** scheda, seleziona `System.Runtime.Caching`, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="3b87e-172">Aggiunta di un pulsante nella finestra di WPF</span><span class="sxs-lookup"><span data-stu-id="3b87e-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="3b87e-173">Quindi si verrà aggiunto un pulsante e creare un gestore eventi per il pulsante `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="3b87e-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="3b87e-174">In seguito si aggiungerà codice a in modo che quando si fa clic sul pulsante, il contenuto del file di testo è memorizzati nella cache e visualizzato.</span><span class="sxs-lookup"><span data-stu-id="3b87e-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="3b87e-175">Per aggiungere un controllo pulsante</span><span class="sxs-lookup"><span data-stu-id="3b87e-175">To add a button control</span></span>

1.  <span data-ttu-id="3b87e-176">Nelle **Esplora soluzioni**, fare doppio clic sul file MainWindow. XAML per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="3b87e-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2.  <span data-ttu-id="3b87e-177">Dal **casella degli strumenti**, in **controlli WPF comuni**, trascinare un' `Button` il controllo al `MainWindow` finestra.</span><span class="sxs-lookup"><span data-stu-id="3b87e-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3.  <span data-ttu-id="3b87e-178">Nel **proprietà** impostare nella finestra di `Content` proprietà del `Button` il controllo a **Ottieni Cache**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="3b87e-179">Inizializzazione della Cache e la memorizzazione nella cache una voce</span><span class="sxs-lookup"><span data-stu-id="3b87e-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="3b87e-180">Successivamente, si aggiungerà il codice per eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b87e-180">Next, you will add the code to perform the following tasks:</span></span>

-   <span data-ttu-id="3b87e-181">Creare un'istanza della classe della cache, vale a dire, si creerà un nuovo <xref:System.Runtime.Caching.MemoryCache> oggetto.</span><span class="sxs-lookup"><span data-stu-id="3b87e-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

-   <span data-ttu-id="3b87e-182">Specificare che la cache utilizza un <xref:System.Runtime.Caching.HostFileChangeMonitor> oggetto per monitorare le modifiche nel file di testo.</span><span class="sxs-lookup"><span data-stu-id="3b87e-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

-   <span data-ttu-id="3b87e-183">Leggere il file di testo e il contenuto memorizzato nella cache come una voce della cache.</span><span class="sxs-lookup"><span data-stu-id="3b87e-183">Read the text file and cache its contents as a cache entry.</span></span>

-   <span data-ttu-id="3b87e-184">Visualizzare il contenuto del file di testo memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="3b87e-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="3b87e-185">Per creare l'oggetto della cache</span><span class="sxs-lookup"><span data-stu-id="3b87e-185">To create the cache object</span></span>

1.  <span data-ttu-id="3b87e-186">Fare doppio clic sul pulsante che appena aggiunta per poter creare un gestore eventi nel file XAML. vb o MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="3b87e-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2.  <span data-ttu-id="3b87e-187">Nella parte superiore del file (prima della dichiarazione di classe), aggiungere quanto segue `Imports` (Visual Basic) o `using` istruzioni (c#):</span><span class="sxs-lookup"><span data-stu-id="3b87e-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3.  <span data-ttu-id="3b87e-188">Nel gestore dell'evento, aggiungere il codice seguente per creare un'istanza di oggetto della cache:</span><span class="sxs-lookup"><span data-stu-id="3b87e-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="3b87e-189">Il <xref:System.Runtime.Caching.ObjectCache> classe è una classe incorporata che fornisce una cache oggetti in memoria.</span><span class="sxs-lookup"><span data-stu-id="3b87e-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4.  <span data-ttu-id="3b87e-190">Aggiungere il codice seguente per leggere il contenuto di una voce della cache denominata `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="3b87e-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5.  <span data-ttu-id="3b87e-191">Aggiungere il codice seguente per verificare se la voce della cache denominata `filecontents` esiste:</span><span class="sxs-lookup"><span data-stu-id="3b87e-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="3b87e-192">Se la voce della cache specificata non esiste, è necessario leggere il file di testo e aggiungerlo come una voce della cache nella cache.</span><span class="sxs-lookup"><span data-stu-id="3b87e-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6.  <span data-ttu-id="3b87e-193">Nel `if/then` blocco, aggiungere il codice seguente per creare un nuovo <xref:System.Runtime.Caching.CacheItemPolicy> oggetto che specifica che la voce della cache scade dopo 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="3b87e-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="3b87e-194">Se viene fornita alcuna informazione di eliminazione o scadenza, il valore predefinito è <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, ovvero le voci della cache senza scadenza in base solo in un tempo assoluto.</span><span class="sxs-lookup"><span data-stu-id="3b87e-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="3b87e-195">Al contrario, le voci della cache scadono solo quando sono presenti richieste di memoria.</span><span class="sxs-lookup"><span data-stu-id="3b87e-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="3b87e-196">Come procedura consigliata, è necessario fornire sempre in modo esplicito assoluto o una scadenza variabile scappare.</span><span class="sxs-lookup"><span data-stu-id="3b87e-196">As a best practice, you should always explicitly provide either an absolute or a siding expiration.</span></span>

7.  <span data-ttu-id="3b87e-197">All'interno di `if/then` in blocchi e dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per creare una raccolta per i percorsi dei file che si desidera monitorare e aggiungere il percorso del file di testo nella raccolta:</span><span class="sxs-lookup"><span data-stu-id="3b87e-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    >  <span data-ttu-id="3b87e-198">Se si desidera utilizzare il file di testo non `c:\cache\cacheText.txt`, specificare il percorso in cui il file di testo è che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="3b87e-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8.  <span data-ttu-id="3b87e-199">Dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per aggiungere un nuovo <xref:System.Runtime.Caching.HostFileChangeMonitor> oggetto alla raccolta di modifiche consente di monitorare la voce della cache:</span><span class="sxs-lookup"><span data-stu-id="3b87e-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="3b87e-200">Il <xref:System.Runtime.Caching.HostFileChangeMonitor> oggetto consente di monitorare il percorso del file di testo e invia una notifica della cache se si verificano cambiamenti.</span><span class="sxs-lookup"><span data-stu-id="3b87e-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="3b87e-201">In questo esempio, la voce della cache scadrà se il contenuto del file viene modificato.</span><span class="sxs-lookup"><span data-stu-id="3b87e-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="3b87e-202">Dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per leggere il contenuto del file di testo:</span><span class="sxs-lookup"><span data-stu-id="3b87e-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="3b87e-203">Il timestamp di data e ora viene aggiunto in modo che sarà in grado di vedere quando scade la voce della cache.</span><span class="sxs-lookup"><span data-stu-id="3b87e-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="3b87e-204">Dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per inserire il contenuto del file in oggetto cache come un <xref:System.Runtime.Caching.CacheItem> istanza:</span><span class="sxs-lookup"><span data-stu-id="3b87e-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="3b87e-205">Specificare le informazioni sulle modalità di eliminazione della voce della cache passando il <xref:System.Runtime.Caching.CacheItemPolicy> oggetto creato in precedenza come parametro.</span><span class="sxs-lookup"><span data-stu-id="3b87e-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="3b87e-206">Dopo il `if/then` blocco, aggiungere il codice seguente per visualizzare il contenuto del file memorizzato nella cache in una finestra di messaggio:</span><span class="sxs-lookup"><span data-stu-id="3b87e-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="3b87e-207">Nel **compilare** menu, fare clic su **compilare WPFCaching** per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="3b87e-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="3b87e-208">Test di memorizzazione nella cache nell'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="3b87e-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="3b87e-209">È ora possibile testare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3b87e-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="3b87e-210">Per testare la memorizzazione nella cache nell'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="3b87e-210">To test caching in the WPF application</span></span>

1.  <span data-ttu-id="3b87e-211">Premere CTRL+F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3b87e-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="3b87e-212">Il `MainWindow` viene visualizzata la finestra.</span><span class="sxs-lookup"><span data-stu-id="3b87e-212">The `MainWindow` window is displayed.</span></span>

2.  <span data-ttu-id="3b87e-213">Fare clic su **ottenere Cache**.</span><span class="sxs-lookup"><span data-stu-id="3b87e-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="3b87e-214">Il contenuto memorizzato nella cache dal file di testo viene visualizzato in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="3b87e-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="3b87e-215">Si noti che il timestamp sul file.</span><span class="sxs-lookup"><span data-stu-id="3b87e-215">Notice the timestamp on the file.</span></span>

3.  <span data-ttu-id="3b87e-216">Chiudere la finestra di messaggio e quindi fare clic su **Ottieni Cache** nuovamente **.**</span><span class="sxs-lookup"><span data-stu-id="3b87e-216">Close the message box and then click **Get Cache** again **.**</span></span>

     <span data-ttu-id="3b87e-217">Il timestamp è invariato.</span><span class="sxs-lookup"><span data-stu-id="3b87e-217">The timestamp is unchanged.</span></span> <span data-ttu-id="3b87e-218">Ciò indica che viene visualizzato il contenuto memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="3b87e-218">This indicates the cached content is displayed.</span></span>

4.  <span data-ttu-id="3b87e-219">Attendere almeno 10 secondi e quindi fare clic su **Ottieni Cache** nuovamente.</span><span class="sxs-lookup"><span data-stu-id="3b87e-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="3b87e-220">Questo tempo viene visualizzato un nuovo timestamp.</span><span class="sxs-lookup"><span data-stu-id="3b87e-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="3b87e-221">Ciò indica che i criteri consentono la voce della cache scadono e che venga visualizzato nuovo contenuto memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="3b87e-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5.  <span data-ttu-id="3b87e-222">In un editor di testo aprire il file di testo che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="3b87e-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="3b87e-223">Non apportare eventuali modifiche ancora.</span><span class="sxs-lookup"><span data-stu-id="3b87e-223">Do not make any changes yet.</span></span>

6.  <span data-ttu-id="3b87e-224">Chiudere la finestra di messaggio e quindi fare clic su **Ottieni Cache** nuovamente **.**</span><span class="sxs-lookup"><span data-stu-id="3b87e-224">Close the message box and then click **Get Cache** again **.**</span></span>

     <span data-ttu-id="3b87e-225">Si noti che il timestamp nuovamente.</span><span class="sxs-lookup"><span data-stu-id="3b87e-225">Notice the timestamp again.</span></span>

7.  <span data-ttu-id="3b87e-226">Apportare una modifica al file di testo e quindi salvare il file.</span><span class="sxs-lookup"><span data-stu-id="3b87e-226">Make a change to the text file and then save the file.</span></span>

8.  <span data-ttu-id="3b87e-227">Chiudere la finestra di messaggio e quindi fare clic su **Ottieni Cache** nuovamente.</span><span class="sxs-lookup"><span data-stu-id="3b87e-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="3b87e-228">Questa finestra di messaggio contiene il contenuto aggiornato dai file di testo e un nuovo timestamp.</span><span class="sxs-lookup"><span data-stu-id="3b87e-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="3b87e-229">Ciò indica che il monitoraggio delle modifiche file host rimosso la voce della cache immediatamente quando si modifica il file, anche se il periodo di timeout assoluto non era scaduto.</span><span class="sxs-lookup"><span data-stu-id="3b87e-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="3b87e-230">È possibile aumentare il tempo di eliminazione per almeno 20 secondi per dare più tempo per poter apportare una modifica nel file.</span><span class="sxs-lookup"><span data-stu-id="3b87e-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="3b87e-231">Esempio di codice</span><span class="sxs-lookup"><span data-stu-id="3b87e-231">Code Example</span></span>
 <span data-ttu-id="3b87e-232">Dopo aver completato questa procedura dettagliata, il codice per il progetto creato sarà simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3b87e-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="3b87e-233">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b87e-233">See Also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="3b87e-234">Memorizzazione nella cache in applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3b87e-234">Caching in .NET Framework Applications</span></span>](../../../../docs/framework/performance/caching-in-net-framework-applications.md)