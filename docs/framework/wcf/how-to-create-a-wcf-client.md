---
title: 'Esercitazione: Creare un client Windows Communication Foundation'
ms.dat8: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 051275e56a8e63c6ab8136dbb9e24bdcf4c387df
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411857"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="dedaa-102">Esercitazione: Creare un client Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="dedaa-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="dedaa-103">Questa esercitazione illustra il quarto di cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="dedaa-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="dedaa-104">Per una panoramica delle esercitazioni, vedere [esercitazione: Iniziare con le applicazioni di Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="dedaa-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="dedaa-105">L'attività successiva per la creazione di un'applicazione WCF consiste nel creare un client tramite il recupero dei metadati da un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="dedaa-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="dedaa-106">Si usa Visual Studio per aggiungere un riferimento al servizio, che ottiene i metadati dall'endpoint MEX del servizio.</span><span class="sxs-lookup"><span data-stu-id="dedaa-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="dedaa-107">Visual Studio genera quindi un file di codice sorgente gestito per un proxy client nel linguaggio scelto.</span><span class="sxs-lookup"><span data-stu-id="dedaa-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="dedaa-108">Viene anche creato un file di configurazione client (*app. config*).</span><span class="sxs-lookup"><span data-stu-id="dedaa-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="dedaa-109">Questo file consente all'applicazione client di connettersi al servizio in un endpoint.</span><span class="sxs-lookup"><span data-stu-id="dedaa-109">This file enables the client application to connect to the service at an endpoint.</span></span> 

> [!NOTE]
> <span data-ttu-id="dedaa-110">Se si chiama un servizio WCF da un progetto libreria di classi in Visual Studio, usare il **Aggiungi riferimento al servizio** funzionalità per generare automaticamente un proxy e un file di configurazione associata.</span><span class="sxs-lookup"><span data-stu-id="dedaa-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="dedaa-111">Tuttavia, poiché i progetti libreria di classi non utilizzano questo file di configurazione, è necessario aggiungere le impostazioni nel file di configurazione generato per il *app. config* file per il file eseguibile che chiama la libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="dedaa-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="dedaa-112">In alternativa, usare il [strumento ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) invece di Visual Studio per generare il file di classe e la configurazione proxy.</span><span class="sxs-lookup"><span data-stu-id="dedaa-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="dedaa-113">L'applicazione client utilizza la classe proxy generata per comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="dedaa-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="dedaa-114">Questa procedura è descritta nella [esercitazione: Usare un client](how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="dedaa-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="dedaa-115">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="dedaa-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="dedaa-116">Creare e configurare un progetto app console per il client WCF.</span><span class="sxs-lookup"><span data-stu-id="dedaa-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="dedaa-117">Aggiungere un riferimento al servizio per il servizio WCF per generare i file di classe e la configurazione proxy.</span><span class="sxs-lookup"><span data-stu-id="dedaa-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>


## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="dedaa-118">Creare un client Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="dedaa-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="dedaa-119">Creare un progetto app console in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="dedaa-119">Create a console app project in Visual Studio:</span></span> 

    1. <span data-ttu-id="dedaa-120">Dal **File** dal menu **Open** > **progetto/soluzione** e passare alla **GettingStarted** soluzione si creato in precedenza (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="dedaa-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="dedaa-121">Selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="dedaa-121">Select **Open**.</span></span>

    2. <span data-ttu-id="dedaa-122">Dal **View** dal menu **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="dedaa-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="dedaa-123">Nel **Esplora soluzioni** finestra, seleziona la **GettingStarted** soluzione (nodo in alto) e quindi selezionare **Add** > **nuovo progetto** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="dedaa-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 
    
    4. <span data-ttu-id="dedaa-124">Nel **Aggiungi nuovo progetto** finestra a sinistra, seleziona il **Desktop di Windows** categoria sotto **Visual C#**  oppure **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="dedaa-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="dedaa-125">Selezionare il **App Console (.NET Framework)** modello, quindi immettere *GettingStartedClient* per il **nome**.</span><span class="sxs-lookup"><span data-stu-id="dedaa-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="dedaa-126">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="dedaa-126">Select **OK**.</span></span>

2. <span data-ttu-id="dedaa-127">Aggiungere un riferimento nel **GettingStartedClient** del progetto per il <xref:System.ServiceModel> assembly:</span><span class="sxs-lookup"><span data-stu-id="dedaa-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1.  <span data-ttu-id="dedaa-128">Nel **Esplora soluzioni** finestra, seleziona la **riferimenti** cartella sotto la **GettingStartedClient** del progetto e quindi selezionare **Aggiungi riferimento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="dedaa-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="dedaa-129">Nel **Aggiungi riferimento** finestra, sotto **assembly** sul lato sinistro della finestra, selezionare **Framework**.</span><span class="sxs-lookup"><span data-stu-id="dedaa-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>
    
    3. <span data-ttu-id="dedaa-130">Individuare e selezionare **System. ServiceModel**, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="dedaa-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> 

    4. <span data-ttu-id="dedaa-131">Salvare la soluzione selezionando **File** > **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="dedaa-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="dedaa-132">Aggiungere un riferimento al servizio di calcolatrice:</span><span class="sxs-lookup"><span data-stu-id="dedaa-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="dedaa-133">Nel **Esplora soluzioni** finestra, seleziona la **riferimenti** cartella sotto la **GettingStartedClient** del progetto e quindi selezionare **Aggiungi riferimento al servizio**  dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="dedaa-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="dedaa-134">Nel **Aggiungi riferimento al servizio** finestra, seleziona **Discover**.</span><span class="sxs-lookup"><span data-stu-id="dedaa-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="dedaa-135">L'avvio del servizio CalculatorService e Visual Studio li visualizza nel **Services** casella.</span><span class="sxs-lookup"><span data-stu-id="dedaa-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="dedaa-136">Selezionare **CalculatorService** per espanderlo e visualizzare i contratti di servizio implementati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="dedaa-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="dedaa-137">Lasciare l'impostazione predefinita **Namespace** e scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="dedaa-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="dedaa-138">Visual Studio aggiunge un nuovo elemento con il **servizi connessi** cartella nel **GettingStartedClient** progetto.</span><span class="sxs-lookup"><span data-stu-id="dedaa-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span> 


### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="dedaa-139">Strumento ServiceModel Metadata Utility tool</span><span class="sxs-lookup"><span data-stu-id="dedaa-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="dedaa-140">Gli esempi seguenti illustrano come usare facoltativamente la [strumento ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il file di classe proxy.</span><span class="sxs-lookup"><span data-stu-id="dedaa-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="dedaa-141">Questo strumento genera il file di classe proxy e il *app. config* file.</span><span class="sxs-lookup"><span data-stu-id="dedaa-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="dedaa-142">Gli esempi seguenti illustrano come generare il proxy in C# e Visual Basic, rispettivamente:</span><span class="sxs-lookup"><span data-stu-id="dedaa-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="dedaa-143">File di configurazione client</span><span class="sxs-lookup"><span data-stu-id="dedaa-143">Client configuration file</span></span>

<span data-ttu-id="dedaa-144">Dopo aver creato il client, Visual Studio crea il **app. config** file di configurazione le **GettingStartedClient** progetto, che dovrebbe essere simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dedaa-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

<span data-ttu-id="dedaa-145">Sotto il [ \<System. ServiceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) sezione, si noti il [ \<endpoint >](../configure-apps/file-schema/wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="dedaa-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="dedaa-146">Il **&lt;endpoint&gt;** elemento definisce l'endpoint utilizzato dal client per accedere al servizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dedaa-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>
- <span data-ttu-id="dedaa-147">Indirizzo: `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="dedaa-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="dedaa-148">L'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dedaa-148">The address of the endpoint.</span></span>
- <span data-ttu-id="dedaa-149">Contratto di servizio: `ServiceReference1.ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="dedaa-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="dedaa-150">Il contratto di servizio gestisce la comunicazione tra il client WCF e il servizio.</span><span class="sxs-lookup"><span data-stu-id="dedaa-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="dedaa-151">Visual Studio generato questo contratto quando è stato usato il **Aggiungi riferimento al servizio** (funzione).</span><span class="sxs-lookup"><span data-stu-id="dedaa-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="dedaa-152">È essenzialmente una copia del contratto definito nel progetto GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="dedaa-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span> 
- <span data-ttu-id="dedaa-153">Associazione: <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="dedaa-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="dedaa-154">L'associazione specifica HTTP come trasporto, sicurezza interoperativa e altri dettagli di configurazione.</span><span class="sxs-lookup"><span data-stu-id="dedaa-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dedaa-155">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="dedaa-155">Next steps</span></span>

<span data-ttu-id="dedaa-156">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="dedaa-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="dedaa-157">Creare e configurare un progetto app console per il client WCF.</span><span class="sxs-lookup"><span data-stu-id="dedaa-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="dedaa-158">Aggiungere un riferimento al servizio per il servizio WCF per generare i file di classe e la configurazione proxy per l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="dedaa-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="dedaa-159">Passare all'esercitazione successiva per informazioni su come usare il client generato.</span><span class="sxs-lookup"><span data-stu-id="dedaa-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="dedaa-160">Esercitazione: Usare un client WCF</span><span class="sxs-lookup"><span data-stu-id="dedaa-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)


