---
title: 'Esercitazione: creare un client di Windows Communication Foundation'
description: Informazioni su come creare un client recuperando i metadati da un servizio WCF come parte di una serie di articoli che consentono di iniziare a creare un'applicazione WCF.
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: d5a2a2b5175c9e34eaf1dbaff20ac57f34117c4e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246324"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="9d9e0-103">Esercitazione: creare un client di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9d9e0-103">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="9d9e0-104">Questa esercitazione descrive il quarto di cinque attività necessarie per creare un'applicazione di base Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9d9e0-104">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="9d9e0-105">Per una panoramica delle esercitazioni, vedere [esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="9d9e0-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="9d9e0-106">L'attività successiva per la creazione di un'applicazione WCF consiste nel creare un client recuperando i metadati da un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-106">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="9d9e0-107">Si usa Visual Studio per aggiungere un riferimento al servizio, che ottiene i metadati dall'endpoint MEX del servizio.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-107">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="9d9e0-108">Visual Studio genera quindi un file di codice sorgente gestito per un proxy client nel linguaggio scelto.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-108">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="9d9e0-109">Viene inoltre creato un file di configurazione client (*App.config*).</span><span class="sxs-lookup"><span data-stu-id="9d9e0-109">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="9d9e0-110">Questo file consente all'applicazione client di connettersi al servizio in un endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-110">This file enables the client application to connect to the service at an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="9d9e0-111">Se si chiama un servizio WCF da un progetto libreria di classi in Visual Studio, utilizzare la funzionalità **Aggiungi riferimento al servizio** per generare automaticamente un proxy e un file di configurazione associato.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-111">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="9d9e0-112">Tuttavia, poiché i progetti della libreria di classi non utilizzano questo file di configurazione, è necessario aggiungere le impostazioni nel file di configurazione generato al file di *App.config* per il file eseguibile che chiama la libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-112">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="9d9e0-113">In alternativa, utilizzare lo [strumento ServiceModel Metadata Utility](#servicemodel-metadata-utility-tool) anziché Visual Studio per generare la classe proxy e il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-113">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="9d9e0-114">L'applicazione client utilizza la classe proxy generata per comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-114">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="9d9e0-115">Questa procedura è descritta in [esercitazione: usare un client](how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="9d9e0-115">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="9d9e0-116">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="9d9e0-116">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="9d9e0-117">Creare e configurare un progetto di app console per il client WCF.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-117">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="9d9e0-118">Aggiungere un riferimento al servizio WCF per generare la classe proxy e i file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-118">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="9d9e0-119">Creare un client di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9d9e0-119">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="9d9e0-120">Creare un progetto di app console in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="9d9e0-120">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="9d9e0-121">Dal menu **file** selezionare **Apri**  >  **progetto/soluzione** e passare alla soluzione **GettingStarted** creata in precedenza (*GettingStarted. sln*).</span><span class="sxs-lookup"><span data-stu-id="9d9e0-121">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="9d9e0-122">Scegliere **Open**(Apri).</span><span class="sxs-lookup"><span data-stu-id="9d9e0-122">Select **Open**.</span></span>

    2. <span data-ttu-id="9d9e0-123">Scegliere **Esplora soluzioni**dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="9d9e0-123">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="9d9e0-124">Nella finestra di **Esplora soluzioni** selezionare la soluzione **GettingStarted** (nodo principale), quindi scegliere **Aggiungi**  >  **nuovo progetto** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-124">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="9d9e0-125">Nella finestra **Aggiungi nuovo progetto** sul lato sinistro selezionare la categoria **desktop di Windows** in **Visual C#** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-125">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="9d9e0-126">Selezionare il modello **applicazione console (.NET Framework)** e immettere *GettingStartedClient* per **nome**.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-126">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="9d9e0-127">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-127">Select **OK**.</span></span>

2. <span data-ttu-id="9d9e0-128">Aggiungere un riferimento nel progetto **GettingStartedClient** all' <xref:System.ServiceModel> assembly:</span><span class="sxs-lookup"><span data-stu-id="9d9e0-128">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="9d9e0-129">Nella finestra di **Esplora soluzioni** selezionare la cartella **riferimenti** nel progetto **GettingStartedClient** e quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-129">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="9d9e0-130">Nella finestra **Aggiungi riferimento** , in **assembly** sul lato sinistro della finestra, selezionare **Framework**.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-130">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="9d9e0-131">Individuare e selezionare **System. ServiceModel**, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-131">Find and select **System.ServiceModel**, and then choose **OK**.</span></span>

    4. <span data-ttu-id="9d9e0-132">Salvare la soluzione selezionando **file**  >  **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-132">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="9d9e0-133">Aggiungere un riferimento al servizio del calcolatore:</span><span class="sxs-lookup"><span data-stu-id="9d9e0-133">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="9d9e0-134">Nella finestra di **Esplora soluzioni** selezionare la cartella **riferimenti** nel progetto **GettingStartedClient** e quindi selezionare **Aggiungi riferimento al servizio** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-134">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="9d9e0-135">Nella finestra di **Aggiungi riferimento al servizio** selezionare **individua**.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-135">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="9d9e0-136">Il servizio CalculatorService viene avviato e Visual Studio lo Visualizza nella casella **Servizi** .</span><span class="sxs-lookup"><span data-stu-id="9d9e0-136">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="9d9e0-137">Selezionare **CalculatorService** per espanderlo e visualizzare i contratti di servizio implementati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-137">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="9d9e0-138">Lasciare lo **spazio dei nomi** predefinito e scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-138">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="9d9e0-139">Visual Studio aggiunge un nuovo elemento sotto la cartella **servizi connessi** nel progetto **GettingStartedClient** .</span><span class="sxs-lookup"><span data-stu-id="9d9e0-139">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span>

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="9d9e0-140">ServiceModel Metadata Utility Tool</span><span class="sxs-lookup"><span data-stu-id="9d9e0-140">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="9d9e0-141">Negli esempi seguenti viene illustrato come utilizzare facoltativamente lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il file di classe proxy.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-141">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="9d9e0-142">Questo strumento genera il file di classe proxy e il file di *App.config* .</span><span class="sxs-lookup"><span data-stu-id="9d9e0-142">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="9d9e0-143">Gli esempi seguenti illustrano come generare il proxy in C# e Visual Basic, rispettivamente:</span><span class="sxs-lookup"><span data-stu-id="9d9e0-143">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="9d9e0-144">File di configurazione del client</span><span class="sxs-lookup"><span data-stu-id="9d9e0-144">Client configuration file</span></span>

<span data-ttu-id="9d9e0-145">Dopo aver creato il client, Visual Studio crea il file di configurazione **App.config** nel progetto **GettingStartedClient** , che dovrebbe essere simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9d9e0-145">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="9d9e0-146">Nella [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) sezione si noti l' [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-146">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="9d9e0-147">L'elemento \*\* &lt; endpoint &gt; \*\* definisce l'endpoint utilizzato dal client per accedere al servizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9d9e0-147">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="9d9e0-148">Indirizzo: `http://localhost:8000/GettingStarted/CalculatorService` .</span><span class="sxs-lookup"><span data-stu-id="9d9e0-148">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="9d9e0-149">L'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-149">The address of the endpoint.</span></span>
- <span data-ttu-id="9d9e0-150">Contratto di servizio: `ServiceReference1.ICalculator` .</span><span class="sxs-lookup"><span data-stu-id="9d9e0-150">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="9d9e0-151">Il contratto di servizio gestisce la comunicazione tra il client WCF e il servizio.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-151">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="9d9e0-152">Questo contratto è stato generato da Visual Studio quando è stata usata la relativa funzione **Aggiungi riferimento al servizio** .</span><span class="sxs-lookup"><span data-stu-id="9d9e0-152">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="9d9e0-153">Si tratta essenzialmente di una copia del contratto definito nel progetto GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-153">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span>
- <span data-ttu-id="9d9e0-154">Binding: <xref:System.ServiceModel.WSHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="9d9e0-154">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="9d9e0-155">L'associazione specifica HTTP come trasporto, sicurezza interoperativa e altri dettagli di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-155">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9d9e0-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="9d9e0-156">Next steps</span></span>

<span data-ttu-id="9d9e0-157">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="9d9e0-157">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="9d9e0-158">Creare e configurare un progetto di app console per il client WCF.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-158">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="9d9e0-159">Aggiungere un riferimento al servizio WCF per generare la classe proxy e i file di configurazione per l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-159">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="9d9e0-160">Passare all'esercitazione successiva per apprendere come usare il client generato.</span><span class="sxs-lookup"><span data-stu-id="9d9e0-160">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9d9e0-161">Esercitazione: usare un client WCF</span><span class="sxs-lookup"><span data-stu-id="9d9e0-161">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
