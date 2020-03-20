---
title: 'Esercitazione: Creare un client Windows Communication FoundationTutorial: Create a Windows Communication Foundation client'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184105"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="b7104-102">Esercitazione: Creare un client Windows Communication FoundationTutorial: Create a Windows Communication Foundation client</span><span class="sxs-lookup"><span data-stu-id="b7104-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="b7104-103">Questa esercitazione descrive la quarta di cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF) di base.</span><span class="sxs-lookup"><span data-stu-id="b7104-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="b7104-104">Per una panoramica delle esercitazioni, vedere [Esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="b7104-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="b7104-105">L'attività successiva per la creazione di un'applicazione WCF consiste nel creare un client recuperando i metadati da un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="b7104-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="b7104-106">Utilizzare Visual Studio per aggiungere un riferimento al servizio, che ottiene i metadati dall'endpoint MEX del servizio.</span><span class="sxs-lookup"><span data-stu-id="b7104-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="b7104-107">Visual Studio genera quindi un file di codice sorgente gestito per un proxy client nel linguaggio scelto.</span><span class="sxs-lookup"><span data-stu-id="b7104-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="b7104-108">Viene inoltre creato un file di configurazione client (*App.config*).</span><span class="sxs-lookup"><span data-stu-id="b7104-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="b7104-109">Questo file consente all'applicazione client di connettersi al servizio in un endpoint.</span><span class="sxs-lookup"><span data-stu-id="b7104-109">This file enables the client application to connect to the service at an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="b7104-110">Se si chiama un servizio WCF da un progetto di libreria di classi in Visual Studio, usare la funzionalità **Aggiungi riferimento** al servizio per generare automaticamente un proxy e un file di configurazione associato.</span><span class="sxs-lookup"><span data-stu-id="b7104-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="b7104-111">Tuttavia, poiché i progetti di libreria di classi non utilizzano questo file di configurazione, è necessario aggiungere le impostazioni nel file di configurazione generato al file *App.config* per l'eseguibile che chiama la libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="b7104-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="b7104-112">In alternativa, utilizzare [lo strumento ServiceModel Metadata Utility](#servicemodel-metadata-utility-tool) anziché Visual Studio per generare la classe proxy e il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b7104-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="b7104-113">L'applicazione client utilizza la classe proxy generata per comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="b7104-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="b7104-114">Questa procedura è descritta in [Esercitazione: Utilizzare un client](how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="b7104-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="b7104-115">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="b7104-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="b7104-116">Creare e configurare un progetto di app console per il client WCF.</span><span class="sxs-lookup"><span data-stu-id="b7104-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="b7104-117">Aggiungere un riferimento al servizio WCF per generare la classe proxy e i file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b7104-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="b7104-118">Creare un client Windows Communication FoundationCreate a Windows Communication Foundation client</span><span class="sxs-lookup"><span data-stu-id="b7104-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="b7104-119">Creare un progetto di app console in Visual Studio:Create a console app project in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="b7104-119">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="b7104-120">Scegliere **Apri** > **progetto/soluzione** dal menu **File** e individuare la soluzione **GettingStarted** creata in precedenza (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="b7104-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="b7104-121">Selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="b7104-121">Select **Open**.</span></span>

    2. <span data-ttu-id="b7104-122">Scegliere **Esplora soluzioni**dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="b7104-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="b7104-123">Nella finestra **Esplora soluzioni** selezionare la soluzione **GettingStarted** (nodo superiore), quindi scegliere **Aggiungi** > **nuovo progetto** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="b7104-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="b7104-124">Nella finestra **Aggiungi nuovo progetto,** sul lato sinistro, selezionare la categoria **Desktop di Windows** in Visual **Cè** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="b7104-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="b7104-125">Selezionare il modello **App console (.NET Framework)** e immettere *GettingStartedClient* come **Nome**.</span><span class="sxs-lookup"><span data-stu-id="b7104-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="b7104-126">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7104-126">Select **OK**.</span></span>

2. <span data-ttu-id="b7104-127">Aggiungere un riferimento nel progetto GettingStartedClient all'assembly:Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span><span class="sxs-lookup"><span data-stu-id="b7104-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="b7104-128">Nella finestra **Esplora soluzioni** selezionare la cartella **Riferimenti** nel progetto **GettingStartedClient,** quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="b7104-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="b7104-129">Nella finestra **Aggiungi riferimento,** in **Assembly** sul lato sinistro della finestra, selezionare **Framework**.</span><span class="sxs-lookup"><span data-stu-id="b7104-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="b7104-130">Individuare e selezionare **System.ServiceModel**, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7104-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span>

    4. <span data-ttu-id="b7104-131">Salvare la soluzione selezionando Salva**tutto** **al file** > .</span><span class="sxs-lookup"><span data-stu-id="b7104-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="b7104-132">Aggiungere un riferimento al servizio di calcolo:Add a service reference to the calculator service:</span><span class="sxs-lookup"><span data-stu-id="b7104-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="b7104-133">Nella finestra **Esplora soluzioni** selezionare la cartella **Riferimenti** nel progetto **GettingStartedClient,** quindi scegliere **Aggiungi riferimento al servizio** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="b7104-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="b7104-134">Nella finestra **Aggiungi riferimento** al servizio selezionare **Individua**.</span><span class="sxs-lookup"><span data-stu-id="b7104-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="b7104-135">Il servizio CalculatorService viene avviato e Visual Studio lo visualizza nella casella **Servizi.**</span><span class="sxs-lookup"><span data-stu-id="b7104-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="b7104-136">Selezionare **CalculatorService** per espanderlo e visualizzare i contratti di servizio implementati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="b7104-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="b7104-137">Lasciare il valore predefinito **Spazio dei nomi** e scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7104-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="b7104-138">Visual Studio aggiunge un nuovo elemento nella cartella **Servizi connessi** nel progetto **GettingStartedClient.**</span><span class="sxs-lookup"><span data-stu-id="b7104-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span>

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="b7104-139">Strumento Utilità metadati ServiceModelServiceModel Metadata Utility tool</span><span class="sxs-lookup"><span data-stu-id="b7104-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="b7104-140">Negli esempi seguenti viene illustrato come utilizzare facoltativamente [lo strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il file di classe proxy.</span><span class="sxs-lookup"><span data-stu-id="b7104-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="b7104-141">Questo strumento genera il file della classe proxy e il file *App.config.*</span><span class="sxs-lookup"><span data-stu-id="b7104-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="b7104-142">Negli esempi seguenti viene illustrato come generare il proxy rispettivamente in C .</span><span class="sxs-lookup"><span data-stu-id="b7104-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="b7104-143">File di configurazione del client</span><span class="sxs-lookup"><span data-stu-id="b7104-143">Client configuration file</span></span>

<span data-ttu-id="b7104-144">Dopo aver creato il client, Visual Studio crea il file di configurazione App.config nel progetto **GettingStartedClient,** che dovrebbe essere simile all'esempio seguente:After you've created the client, Visual Studio creates the **App.config** configuration file in the GettingStartedClient project, which should be similar to the following example:</span><span class="sxs-lookup"><span data-stu-id="b7104-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="b7104-145">Nella sezione [ \<>system.serviceModel](../configure-apps/file-schema/wcf/system-servicemodel.md) notare l'elemento [ \<endpoint>.](../configure-apps/file-schema/wcf/endpoint-element.md)</span><span class="sxs-lookup"><span data-stu-id="b7104-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="b7104-146">L'elemento \*\* &lt;endpoint&gt; \*\* definisce l'endpoint utilizzato dal client per accedere al servizio nel modo seguente:The endpoint element defines the endpoint that the client uses to access the service as follows:</span><span class="sxs-lookup"><span data-stu-id="b7104-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="b7104-147">Indirizzo: `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="b7104-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="b7104-148">L'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b7104-148">The address of the endpoint.</span></span>
- <span data-ttu-id="b7104-149">Contratto `ServiceReference1.ICalculator`di servizio: .</span><span class="sxs-lookup"><span data-stu-id="b7104-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="b7104-150">Il contratto di servizio gestisce la comunicazione tra il client WCF e il servizio.</span><span class="sxs-lookup"><span data-stu-id="b7104-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="b7104-151">Visual Studio ha generato questo contratto quando è stata utilizzata la funzione **Aggiungi riferimento al servizio.**</span><span class="sxs-lookup"><span data-stu-id="b7104-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="b7104-152">Si tratta essenzialmente di una copia del contratto definito nel progetto GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="b7104-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span>
- <span data-ttu-id="b7104-153">Rilegatura: <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="b7104-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="b7104-154">L'associazione specifica HTTP come trasporto, sicurezza interoperabile e altri dettagli di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b7104-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b7104-155">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b7104-155">Next steps</span></span>

<span data-ttu-id="b7104-156">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="b7104-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="b7104-157">Creare e configurare un progetto di app console per il client WCF.</span><span class="sxs-lookup"><span data-stu-id="b7104-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="b7104-158">Aggiungere un riferimento al servizio WCF per generare la classe proxy e i file di configurazione per l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="b7104-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="b7104-159">Passare all'esercitazione successiva per informazioni su come usare il client generato.</span><span class="sxs-lookup"><span data-stu-id="b7104-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b7104-160">Esercitazione: Usare un client WCFTutorial: Use a WCF client</span><span class="sxs-lookup"><span data-stu-id="b7104-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
