---
title: WCF Web Service Reference Provider
description: Panoramica dello strumento Microsoft WCF Web Service Reference Provider che aggiunge funzionalità per i progetti .NET Core e ASP.NET Core, come Aggiungi riferimento al servizio per i progetti .NET Framework.
author: dasetser
ms.date: 10/29/2019
ms.custom: mvc
ms.openlocfilehash: cdd6b457d289dd7b752c97c5645f0797f24b72aa
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715676"
---
# <a name="use-the-wcf-web-service-reference-provider-tool"></a><span data-ttu-id="4df9e-103">Usare lo strumento WCF Web Service Reference Provider</span><span class="sxs-lookup"><span data-stu-id="4df9e-103">Use the WCF Web Service Reference Provider Tool</span></span>

<span data-ttu-id="4df9e-104">Nel corso degli anni, molti sviluppatori di Visual Studio hanno aumentato la produttività usando lo strumento [**Aggiungi riferimento al servizio**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) quando era necessario che i progetti .NET Framework accedessero ai servizi Web.</span><span class="sxs-lookup"><span data-stu-id="4df9e-104">Over the years, many Visual Studio developers have enjoyed the productivity that the [**Add Service Reference**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) tool provided when their .NET Framework projects needed to access web services.</span></span>  <span data-ttu-id="4df9e-105">Lo strumento **WCF Web Service Reference Provider** è un'estensione WCF Connected Service di Visual Studio che offre esperienza simile alla funzionalità Aggiungi riferimento al servizio per i progetti .NET Core e ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4df9e-105">The **WCF Web Service Reference** tool is a Visual Studio connected service extension that provides an experience like the Add Service Reference functionality for .NET Core and ASP.NET Core projects.</span></span> <span data-ttu-id="4df9e-106">Questo strumento consente di recuperare metadati da un servizio web nella soluzione corrente, in un percorso di rete o da un file WSDL e genera un file di origine compatibile con .NET Core contenente codice del proxy client Windows Communication Foundation (WCF) che è possibile usare per accedere al servizio Web.</span><span class="sxs-lookup"><span data-stu-id="4df9e-106">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4df9e-107">Si consiglia di fare riferimento solo a servizi provenienti da un'origine attendibile.</span><span class="sxs-lookup"><span data-stu-id="4df9e-107">You should only reference services from a trusted source.</span></span> <span data-ttu-id="4df9e-108">L'aggiunta di riferimenti da un'origine non attendibile può compromettere la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4df9e-108">Adding references from an untrusted source may compromise security.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4df9e-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4df9e-109">Prerequisites</span></span>

- <span data-ttu-id="4df9e-110">[Visual Studio 2017 versione 15,5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) o versioni successive</span><span class="sxs-lookup"><span data-stu-id="4df9e-110">[Visual Studio 2017 version 15.5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) or later versions</span></span>

## <a name="how-to-use-the-extension"></a><span data-ttu-id="4df9e-111">Come usare l'estensione</span><span class="sxs-lookup"><span data-stu-id="4df9e-111">How to use the extension</span></span>

> [!NOTE]
> <span data-ttu-id="4df9e-112">L'opzione **WCF Web Service Reference** è applicabile ai progetti creati con i modelli di progetto seguenti:</span><span class="sxs-lookup"><span data-stu-id="4df9e-112">The **WCF Web Service Reference** option is applicable to projects created using the following project templates:</span></span>
>
> - <span data-ttu-id="4df9e-113">**Visual C#**  >  **.NET Core**</span><span class="sxs-lookup"><span data-stu-id="4df9e-113">**Visual C#** > **.NET Core**</span></span>
> - <span data-ttu-id="4df9e-114">**Visual C#**  >  **.NET Standard**</span><span class="sxs-lookup"><span data-stu-id="4df9e-114">**Visual C#** > **.NET Standard**</span></span>
> - <span data-ttu-id="4df9e-115">**Visual C#**  > **Web** > **Applicazione ASP.NET Core Web**</span><span class="sxs-lookup"><span data-stu-id="4df9e-115">**Visual C#** > **Web** > **ASP.NET Core Web Application**</span></span>

<span data-ttu-id="4df9e-116">Se si usa il modello di progetto **Applicazione ASP.NET Core Web**, l'articolo illustra i passaggi per aggiungere un riferimento al servizio WFC al progetto:</span><span class="sxs-lookup"><span data-stu-id="4df9e-116">Using the **ASP.NET Core Web Application** project template as an example, this article walks you through adding a WCF service reference to the project:</span></span>

1. <span data-ttu-id="4df9e-117">In Esplora soluzioni fare doppio clic sul nodo **Servizi connessi** del progetto. Per un progetto .NET Core o .NET Standard questa opzione è disponibile facendo clic con il tasto destro del mouse sul nodo **Dipendenze** del progetto in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="4df9e-117">In Solution Explorer, double-click the **Connected Services** node of the project (for a .NET Core or .NET Standard project this option is available when you right-click on the **Dependencies** node of the project in Solution Explorer).</span></span>

    <span data-ttu-id="4df9e-118">Verrà visualizzata la pagina **Servizi connessi** come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="4df9e-118">The **Connected Services** page appears as shown in the following image:</span></span>

    ![Scheda Servizi connessi di Visual Studio per .NET Core](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. <span data-ttu-id="4df9e-120">Nella pagina **Servizi connessi** fare clic su **Microsoft WCF Web Service Reference Provider**.</span><span class="sxs-lookup"><span data-stu-id="4df9e-120">On the **Connected Services** page, click **Microsoft WCF Web Service Reference Provider**.</span></span> <span data-ttu-id="4df9e-121">Verrà visualizzata la procedura guidata**Configura riferimento al servizio Web WCF**:</span><span class="sxs-lookup"><span data-stu-id="4df9e-121">This brings up the **Configure WCF Web Service Reference** wizard:</span></span>

    ![Scheda Endpoint di servizio di Visual Studio per .NET Core](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. <span data-ttu-id="4df9e-123">Selezionare un servizio.</span><span class="sxs-lookup"><span data-stu-id="4df9e-123">Select a service.</span></span>

    <span data-ttu-id="4df9e-124">3a.</span><span class="sxs-lookup"><span data-stu-id="4df9e-124">3a.</span></span> <span data-ttu-id="4df9e-125">Nella procedura guidata **Configura riferimento al servizio Web WCF** sono disponibili diverse opzioni di ricerca dei servizi:</span><span class="sxs-lookup"><span data-stu-id="4df9e-125">There are several services search options available within the **Configure WCF Web Service Reference** wizard:</span></span>

     * <span data-ttu-id="4df9e-126">Per cercare i servizi definiti nella soluzione corrente, fare clic sul pulsante **Individua**.</span><span class="sxs-lookup"><span data-stu-id="4df9e-126">To search for services defined in the current solution, click the **Discover** button.</span></span>
     * <span data-ttu-id="4df9e-127">Per cercare i servizi ospitati all'indirizzo specificato, immettere un URL del servizio nella casella **Indirizzo** e fare clic sul pulsante **Vai**.</span><span class="sxs-lookup"><span data-stu-id="4df9e-127">To search for services hosted at a specified address, enter a service URL in the **Address** box and click the **Go** button.</span></span>
     * <span data-ttu-id="4df9e-128">Per selezionare un file WSDL contenente le informazioni sui metadati del servizio Web, fare clic sul pulsante **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="4df9e-128">To select a WSDL file that contains the web service metadata information, click the **Browse** button.</span></span>

    <span data-ttu-id="4df9e-129">3b.</span><span class="sxs-lookup"><span data-stu-id="4df9e-129">3b.</span></span> <span data-ttu-id="4df9e-130">Selezionare il servizio dall'elenco dei risultati della ricerca nella casella **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="4df9e-130">Select the service from the search results list in the **Services** box.</span></span> <span data-ttu-id="4df9e-131">Se necessario, immettere lo spazio dei nomi per il codice generato nella casella di testo **Spazio dei nomi** corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4df9e-131">If needed, enter the namespace for the generated code in the corresponding **Namespace** text box.</span></span>

    <span data-ttu-id="4df9e-132">3c.</span><span class="sxs-lookup"><span data-stu-id="4df9e-132">3c.</span></span> <span data-ttu-id="4df9e-133">Fare clic sul pulsante **Avanti** per aprire le pagine **Opzioni tipi di dati** e **Opzioni client**.</span><span class="sxs-lookup"><span data-stu-id="4df9e-133">Click the **Next** button to open the **Data Type Options** and the **Client Options** pages.</span></span> <span data-ttu-id="4df9e-134">In alternativa, fare clic sul pulsante **Fine** per usare le opzioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="4df9e-134">Alternatively, click the **Finish** button to use the default options.</span></span>

4. <span data-ttu-id="4df9e-135">Il modulo **Opzioni tipi di dati** consente di ridefinire le impostazioni di configurazione del riferimento al servizio generato:</span><span class="sxs-lookup"><span data-stu-id="4df9e-135">The **Data Type Options** form enables you to refine the generated service reference configuration settings:</span></span>

    ![Scheda Opzioni tipi di dati di Visual Studio per .NET Core](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

    > [!NOTE]
    > <span data-ttu-id="4df9e-137">La casella di controllo **Riutilizza tipi in assembly di riferimento** è utile quando i tipi di dati necessari per la generazione del codice del riferimento al servizio sono definiti in uno degli assembly di riferimento del progetto.</span><span class="sxs-lookup"><span data-stu-id="4df9e-137">The **Reuse types in referenced assemblies** check box option is useful when data types needed for service reference code generation are defined in one of your project's referenced assemblies.</span></span>  <span data-ttu-id="4df9e-138">È importante riusare tali tipi di dati esistenti per evitare problemi di runtime o conflitto del tipo in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4df9e-138">It's important to reuse those existing data types to avoid compile-time type clash or runtime issues.</span></span>

    <span data-ttu-id="4df9e-139">È possibile che si verifichi un ritardo durante il caricamento delle informazioni, a seconda del numero di dipendenze del progetto e di altri fattori relativi alle prestazioni di sistema.</span><span class="sxs-lookup"><span data-stu-id="4df9e-139">There may be a delay while type information is loaded, depending on the number of project dependencies and other system performance factors.</span></span> <span data-ttu-id="4df9e-140">Il pulsante **Fine** è disabilitato durante il caricamento, a meno che la casella di controllo **Riutilizza tipi in assembly di riferimento** non sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="4df9e-140">The **Finish** button is disabled during loading unless the **Reuse types in referenced assemblies** check box is unchecked.</span></span>

5. <span data-ttu-id="4df9e-141">Fare clic su **Fine** al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="4df9e-141">Click **Finish** when you are done.</span></span>

<span data-ttu-id="4df9e-142">Durante la visualizzazione dello stato, lo strumento:</span><span class="sxs-lookup"><span data-stu-id="4df9e-142">While displaying progress, the tool:</span></span>

- <span data-ttu-id="4df9e-143">Scarica i metadati dal servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="4df9e-143">Downloads metadata from the WCF service.</span></span>
- <span data-ttu-id="4df9e-144">Genera il codice del riferimento al servizio in un file denominato *reference.cs*e lo aggiunge al progetto sotto il nodo **Servizi connessi**.</span><span class="sxs-lookup"><span data-stu-id="4df9e-144">Generates the service reference code in a file named *reference.cs*, and adds it to your project under the **Connected Services** node.</span></span>
- <span data-ttu-id="4df9e-145">Aggiorna il file di progetto con estensione csproj con i riferimenti al pacchetto NuGet necessari per la compilazione e l'esecuzione nella piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4df9e-145">Updates the project file (.csproj) with NuGet package references required to compile and run on the target platform.</span></span>

![Finestra di stato di Visual Studio](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

<span data-ttu-id="4df9e-147">Al termine di questi processi, è possibile creare un'istanza del tipo di client WCF generato e richiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="4df9e-147">When these processes complete, you can create an instance of the generated WCF client type and invoke the service operations.</span></span>

## <a name="see-also"></a><span data-ttu-id="4df9e-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4df9e-148">See also</span></span>

- [<span data-ttu-id="4df9e-149">Inizia a usare le applicazioni Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="4df9e-149">Get started with Windows Communication Foundation applications</span></span>](../../framework/wcf/getting-started-tutorial.md)
- [<span data-ttu-id="4df9e-150">Servizi di Windows Communication Foundation e WCF Data Services in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4df9e-150">Windows Communication Foundation services and WCF data services in Visual Studio</span></span>](/visualstudio/data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio)
- [<span data-ttu-id="4df9e-151">Funzionalità supportate di WCF in .NET Core</span><span class="sxs-lookup"><span data-stu-id="4df9e-151">WCF supported features on .NET Core</span></span>](https://github.com/dotnet/wcf/blob/master/release-notes/SupportedFeatures-v2.1.0.md)

## <a name="feedback--questions"></a><span data-ttu-id="4df9e-152">Commenti, suggerimenti e domande</span><span class="sxs-lookup"><span data-stu-id="4df9e-152">Feedback & questions</span></span>

<span data-ttu-id="4df9e-153">In caso di domande o commenti e suggerimenti, è possibile segnalarlo alla [community degli sviluppatori](https://developercommunity.visualstudio.com/) usando lo strumento [segnala un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio) .</span><span class="sxs-lookup"><span data-stu-id="4df9e-153">If you have any questions or feedback, report it at [Developer Community](https://developercommunity.visualstudio.com/) using the [Report a problem](/visualstudio/ide/how-to-report-a-problem-with-visual-studio) tool.</span></span>

## <a name="release-notes"></a><span data-ttu-id="4df9e-154">Note sulla versione</span><span class="sxs-lookup"><span data-stu-id="4df9e-154">Release notes</span></span>

- <span data-ttu-id="4df9e-155">Fare riferimento alle [note sulla versione](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) per informazioni aggiornate sulle versioni, compresi i problemi noti.</span><span class="sxs-lookup"><span data-stu-id="4df9e-155">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) for updated release information, including known issues.</span></span>
