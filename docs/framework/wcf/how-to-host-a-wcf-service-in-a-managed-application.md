---
title: "Procedura: Ospitare un servizio WCF in un'applicazione gestita"
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: b6d1c9c38e2cc5f1b1b7b5538af0339987563de6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637586"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="d7a4d-102">Procedura: Ospitare un servizio WCF in un'app gestita</span><span class="sxs-lookup"><span data-stu-id="d7a4d-102">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="d7a4d-103">Per ospitare un servizio all'interno di un'applicazione gestita, incorporare il codice per il servizio nel codice dell'applicazione, definire un endpoint per il servizio in modo imperativo nel codice, in modo dichiarativo tramite la configurazione o tramite endpoint predefiniti, quindi creare un'istanza di <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="d7a4d-104">Per iniziare a ricevere messaggi, chiamare <xref:System.ServiceModel.ICommunicationObject.Open%2A> su <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="d7a4d-105">In tal modo viene creato e aperto il listener per il servizio.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="d7a4d-106">Questo tipo di hosting di un servizio viene spesso chiamato "self-hosting"" perché è la stessa applicazione gestita a svolgere il lavoro di hosting.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="d7a4d-107">Per chiudere il servizio, chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="d7a4d-108">Un servizio può essere ospitato anche in un servizio Windows gestito, in Internet Information Services (IIS) o nel servizio Attivazione processo Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="d7a4d-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="d7a4d-109">Per altre informazioni sulle opzioni per un servizio di hosting, vedere [servizi di Hosting](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="d7a4d-109">For more information about hosting options for a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>

<span data-ttu-id="d7a4d-110">L'hosting di un servizio in un'applicazione gestita è l'opzione più flessibile perché richiede la distribuzione di un'infrastruttura minima.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="d7a4d-111">Per altre informazioni sui servizi di hosting nelle applicazioni gestite, vedere [Hosting in un'applicazione gestita](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="d7a4d-111">For more information about hosting services in managed applications, see [Hosting in a Managed Application](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="d7a4d-112">Nella procedura seguente viene illustrato come implementare un servizio indipendente in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="d7a4d-113">Creare un servizio self-hosted</span><span class="sxs-lookup"><span data-stu-id="d7a4d-113">Create a self-hosted service</span></span>

1. <span data-ttu-id="d7a4d-114">Creare una nuova applicazione console:</span><span class="sxs-lookup"><span data-stu-id="d7a4d-114">Create a new console application:</span></span>

   1. <span data-ttu-id="d7a4d-115">Aprire Visual Studio e selezionare **New** > **Project** dal **File** menu.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-115">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="d7a4d-116">Nel **modelli installati** elenco, selezionare **Visual c#** oppure **Visual Basic**e quindi selezionare **Windows Desktop**.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-116">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="d7a4d-117">Selezionare il **App Console** modello.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-117">Select the **Console App** template.</span></span> <span data-ttu-id="d7a4d-118">Tipo di `SelfHost` nella **Name** casella e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-118">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="d7a4d-119">Fare doppio clic su **SelfHost** nelle **Esplora soluzioni** e selezionare **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="d7a4d-120">Selezionare **System. ServiceModel** dalle **.NET** scheda e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-120">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="d7a4d-121">Se il **Esplora soluzioni** finestra non è visibile, selezionarla **Esplora soluzioni** dal **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-121">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="d7a4d-122">Fare doppio clic su **Program.cs** oppure **Module1.vb** nelle **Esplora** per aprirlo nella finestra del codice, se non è già aperto.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-122">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="d7a4d-123">Aggiungere le istruzioni seguenti all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="d7a4d-123">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="d7a4d-124">Definire e implementare un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-124">Define and implement a service contract.</span></span> <span data-ttu-id="d7a4d-125">In questo esempio viene definito un codice `HelloWorldService` che restituisce un messaggio in base all'input del servizio.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-125">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="d7a4d-126">Per altre informazioni su come definire e implementare un'interfaccia del servizio, vedere [come: Definire un contratto di servizio](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) e [come: Implementare un contratto di servizio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span><span class="sxs-lookup"><span data-stu-id="d7a4d-126">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="d7a4d-127">All'inizio del metodo `Main`, creare un'istanza della classe <xref:System.Uri> con l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-127">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="d7a4d-128">Creare un'istanza della classe <xref:System.ServiceModel.ServiceHost>, passando un <xref:System.Type> che rappresenta il tipo di servizio e l'URI (Uniform Resource Identifier) dell'indirizzo di base a <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-128">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="d7a4d-129">Abilitare la pubblicazione dei metadati, quindi chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> sull'oggetto <xref:System.ServiceModel.ServiceHost> per inizializzare il servizio e prepararlo a ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-129">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="d7a4d-130">In questo esempio vengono utilizzati endpoint predefiniti e per il servizio non è necessario alcun file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-130">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="d7a4d-131">Se non è specificato alcun endpoint, il runtime ne crea uno per ogni indirizzo di base per ciascun contratto di servizio implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-131">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="d7a4d-132">Per altre informazioni sugli endpoint predefiniti, vedere [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d7a4d-132">For more information about default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="d7a4d-133">Premere **Ctrl**+**MAIUSC**+**B** per compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-133">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="d7a4d-134">Eseguire il test del servizio</span><span class="sxs-lookup"><span data-stu-id="d7a4d-134">Test the service</span></span>

1. <span data-ttu-id="d7a4d-135">Premere **Ctrl**+**F5** per eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-135">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="d7a4d-136">Aprire **Client di prova WCF**.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-136">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="d7a4d-137">Per aprire **Client di prova WCF**, aprire il prompt dei comandi per gli sviluppatori per Visual Studio ed eseguire **WcfTestClient.exe**.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-137">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="d7a4d-138">Selezionare **aggiunta di un servizio** dalle **File** menu.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-138">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="d7a4d-139">Tipo di `http://localhost:8080/hello` nella casella Indirizzo e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-139">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="d7a4d-140">Verificare che il servizio sia in esecuzione. In caso contrario, il passaggio non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-140">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="d7a4d-141">Se nel codice è stato modificato l'indirizzo di base, in questo passaggio utilizzare l'indirizzo di base modificato.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-141">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="d7a4d-142">Fare doppio clic su **SayHello** sotto il **progetti di servizi** nodo.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-142">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="d7a4d-143">Digitare il nome nel **valore** colonna il **richiedere** elenco e fare clic su **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-143">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="d7a4d-144">Viene visualizzato un messaggio di risposta nel **risposta** elenco.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-144">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="d7a4d-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7a4d-145">Example</span></span>

<span data-ttu-id="d7a4d-146">Nell'esempio seguente viene creato un oggetto <xref:System.ServiceModel.ServiceHost> per ospitare un servizio di tipo `HelloWorldService`, quindi viene chiamato il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> su <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-146">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="d7a4d-147">Nel codice viene fornito un indirizzo di base, viene abilitata la pubblicazione di metadati e vengono utilizzati endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d7a4d-147">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="d7a4d-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7a4d-148">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="d7a4d-149">Procedura: Ospitare un servizio WCF in IIS</span><span class="sxs-lookup"><span data-stu-id="d7a4d-149">How to: Host a WCF Service in IIS</span></span>](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="d7a4d-150">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="d7a4d-150">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="d7a4d-151">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="d7a4d-151">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="d7a4d-152">Procedura: Definire un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="d7a4d-152">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="d7a4d-153">Procedura: Implementare un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="d7a4d-153">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="d7a4d-154">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="d7a4d-154">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="d7a4d-155">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="d7a4d-155">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d7a4d-156">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="d7a4d-156">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)
