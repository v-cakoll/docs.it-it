---
title: "Procedura: ospitare un servizio WCF in un'applicazione gestita"
description: Informazioni su come ospitare un servizio WCF all'interno di un'applicazione gestita creando un servizio indipendente ed eseguendone il test.
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 7d1d61b683f60a6c643d2a2f03d367a6ae6c6c15
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246168"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="f8f01-103">Procedura: ospitare un servizio WCF in un'app gestita</span><span class="sxs-lookup"><span data-stu-id="f8f01-103">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="f8f01-104">Per ospitare un servizio all'interno di un'applicazione gestita, incorporare il codice per il servizio nel codice dell'applicazione, definire un endpoint per il servizio in modo imperativo nel codice, in modo dichiarativo tramite la configurazione o tramite endpoint predefiniti, quindi creare un'istanza di <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="f8f01-104">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="f8f01-105">Per iniziare a ricevere messaggi, chiamare <xref:System.ServiceModel.ICommunicationObject.Open%2A> su <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="f8f01-105">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="f8f01-106">In tal modo viene creato e aperto il listener per il servizio.</span><span class="sxs-lookup"><span data-stu-id="f8f01-106">This creates and opens the listener for the service.</span></span> <span data-ttu-id="f8f01-107">Questo tipo di hosting di un servizio viene spesso chiamato "self-hosting"" perché è la stessa applicazione gestita a svolgere il lavoro di hosting.</span><span class="sxs-lookup"><span data-stu-id="f8f01-107">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="f8f01-108">Per chiudere il servizio, chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="f8f01-108">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="f8f01-109">Un servizio può essere ospitato anche in un servizio Windows gestito, in Internet Information Services (IIS) o nel servizio Attivazione processo Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="f8f01-109">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="f8f01-110">Per ulteriori informazioni sulle opzioni di hosting per un servizio, vedere [Hosting Services](hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="f8f01-110">For more information about hosting options for a service, see [Hosting Services](hosting-services.md).</span></span>

<span data-ttu-id="f8f01-111">L'hosting di un servizio in un'applicazione gestita è l'opzione più flessibile perché richiede la distribuzione di un'infrastruttura minima.</span><span class="sxs-lookup"><span data-stu-id="f8f01-111">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="f8f01-112">Per ulteriori informazioni sui servizi di hosting nelle applicazioni gestite, vedere [hosting in un'applicazione gestita](./feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="f8f01-112">For more information about hosting services in managed applications, see [Hosting in a Managed Application](./feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="f8f01-113">Nella procedura seguente viene illustrato come implementare un servizio indipendente in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="f8f01-113">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="f8f01-114">Creazione di un servizio self-hosted</span><span class="sxs-lookup"><span data-stu-id="f8f01-114">Create a self-hosted service</span></span>

1. <span data-ttu-id="f8f01-115">Creare una nuova applicazione console:</span><span class="sxs-lookup"><span data-stu-id="f8f01-115">Create a new console application:</span></span>

   1. <span data-ttu-id="f8f01-116">Aprire Visual Studio e scegliere **nuovo**  >  **progetto** dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="f8f01-116">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="f8f01-117">Nell'elenco **modelli installati** selezionare **Visual C#** o **Visual Basic**, quindi selezionare **desktop di Windows**.</span><span class="sxs-lookup"><span data-stu-id="f8f01-117">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="f8f01-118">Selezionare il modello **applicazione console** .</span><span class="sxs-lookup"><span data-stu-id="f8f01-118">Select the **Console App** template.</span></span> <span data-ttu-id="f8f01-119">Digitare `SelfHost` nella casella **nome** , quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8f01-119">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="f8f01-120">Fare clic con il pulsante destro del mouse su **SelfHost** in **Esplora soluzioni** e scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="f8f01-120">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="f8f01-121">Selezionare **System. ServiceModel** dalla scheda **.NET** , quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8f01-121">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f8f01-122">Se la finestra **Esplora soluzioni** non è visibile, selezionare **Esplora soluzioni** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="f8f01-122">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="f8f01-123">Fare doppio clic su **Program.cs** o **Module1. vb** in **Esplora soluzioni** per aprirlo nella finestra del codice, se non è già aperto.</span><span class="sxs-lookup"><span data-stu-id="f8f01-123">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="f8f01-124">Aggiungere le seguenti istruzioni all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="f8f01-124">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="f8f01-125">Definire e implementare un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="f8f01-125">Define and implement a service contract.</span></span> <span data-ttu-id="f8f01-126">In questo esempio viene definito un codice `HelloWorldService` che restituisce un messaggio in base all'input del servizio.</span><span class="sxs-lookup"><span data-stu-id="f8f01-126">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="f8f01-127">Per altre informazioni su come definire e implementare un'interfaccia del servizio, vedere [procedura: definire un contratto di servizio](how-to-define-a-wcf-service-contract.md) e [procedura: implementare un contratto di servizio](how-to-implement-a-wcf-contract.md).</span><span class="sxs-lookup"><span data-stu-id="f8f01-127">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="f8f01-128">All'inizio del metodo `Main`, creare un'istanza della classe <xref:System.Uri> con l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="f8f01-128">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="f8f01-129">Creare un'istanza della classe <xref:System.ServiceModel.ServiceHost>, passando un <xref:System.Type> che rappresenta il tipo di servizio e l'URI (Uniform Resource Identifier) dell'indirizzo di base a <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="f8f01-129">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="f8f01-130">Abilitare la pubblicazione dei metadati, quindi chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> sull'oggetto <xref:System.ServiceModel.ServiceHost> per inizializzare il servizio e prepararlo a ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="f8f01-130">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="f8f01-131">In questo esempio vengono utilizzati endpoint predefiniti e per il servizio non è necessario alcun file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f8f01-131">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="f8f01-132">Se non è specificato alcun endpoint, il runtime ne crea uno per ogni indirizzo di base per ciascun contratto di servizio implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="f8f01-132">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="f8f01-133">Per ulteriori informazioni sugli endpoint predefiniti, vedere [Configurazione semplificata](simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](./samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f8f01-133">For more information about default endpoints, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="f8f01-134">Premere **CTRL** + **MAIUSC** + **B** per compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="f8f01-134">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="f8f01-135">Testare il servizio</span><span class="sxs-lookup"><span data-stu-id="f8f01-135">Test the service</span></span>

1. <span data-ttu-id="f8f01-136">Premere **CTRL** + **F5** per eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="f8f01-136">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="f8f01-137">Aprire il **client di prova WCF**.</span><span class="sxs-lookup"><span data-stu-id="f8f01-137">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f8f01-138">Per aprire il **client di prova WCF**, aprire prompt dei comandi per gli sviluppatori per Visual Studio ed eseguire **WcfTestClient.exe**.</span><span class="sxs-lookup"><span data-stu-id="f8f01-138">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="f8f01-139">Scegliere **Aggiungi servizio** dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="f8f01-139">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="f8f01-140">Digitare `http://localhost:8080/hello` nella casella Address, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8f01-140">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f8f01-141">Verificare che il servizio sia in esecuzione. In caso contrario, il passaggio non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="f8f01-141">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="f8f01-142">Se nel codice è stato modificato l'indirizzo di base, in questo passaggio utilizzare l'indirizzo di base modificato.</span><span class="sxs-lookup"><span data-stu-id="f8f01-142">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="f8f01-143">Fare doppio clic su **sayHello** nel nodo **progetti di servizio** .</span><span class="sxs-lookup"><span data-stu-id="f8f01-143">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="f8f01-144">Digitare il nome nella colonna **valore** nell'elenco **richiesta** e fare clic su **richiama**.</span><span class="sxs-lookup"><span data-stu-id="f8f01-144">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="f8f01-145">Un messaggio di risposta viene visualizzato nell'elenco **risposta** .</span><span class="sxs-lookup"><span data-stu-id="f8f01-145">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="f8f01-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8f01-146">Example</span></span>

<span data-ttu-id="f8f01-147">Nell'esempio seguente viene creato un oggetto <xref:System.ServiceModel.ServiceHost> per ospitare un servizio di tipo `HelloWorldService`, quindi viene chiamato il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> su <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="f8f01-147">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="f8f01-148">Nel codice viene fornito un indirizzo di base, viene abilitata la pubblicazione di metadati e vengono utilizzati endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f8f01-148">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="f8f01-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8f01-149">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="f8f01-150">Procedura: ospitare un servizio WCF in IIS</span><span class="sxs-lookup"><span data-stu-id="f8f01-150">How to: Host a WCF Service in IIS</span></span>](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="f8f01-151">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="f8f01-151">Self-Host</span></span>](./samples/self-host.md)
- [<span data-ttu-id="f8f01-152">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="f8f01-152">Hosting Services</span></span>](hosting-services.md)
- [<span data-ttu-id="f8f01-153">Procedura: Definire un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="f8f01-153">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="f8f01-154">Procedura: Implementare un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="f8f01-154">How to: Implement a Service Contract</span></span>](how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="f8f01-155">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="f8f01-155">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="f8f01-156">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="f8f01-156">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f8f01-157">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="f8f01-157">System-Provided Bindings</span></span>](system-provided-bindings.md)
