---
title: 'Procedura: ospitare un servizio WCF in un''applicazione gestita'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
caps.latest.revision: "42"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ca834c097f7e8cea14337fece651b2b3059d06b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-host-a-wcf-service-in-a-managed-application"></a><span data-ttu-id="7c42a-102">Procedura: ospitare un servizio WCF in un'applicazione gestita</span><span class="sxs-lookup"><span data-stu-id="7c42a-102">How to: Host a WCF Service in a Managed Application</span></span>
<span data-ttu-id="7c42a-103">Per ospitare un servizio all'interno di un'applicazione gestita, incorporare il codice per il servizio nel codice dell'applicazione, definire un endpoint per il servizio in modo imperativo nel codice, in modo dichiarativo tramite la configurazione o tramite endpoint predefiniti, quindi creare un'istanza di <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7c42a-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="7c42a-104">Per iniziare a ricevere messaggi, chiamare <xref:System.ServiceModel.ICommunicationObject.Open%2A> su <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7c42a-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="7c42a-105">In tal modo viene creato e aperto il listener per il servizio.</span><span class="sxs-lookup"><span data-stu-id="7c42a-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="7c42a-106">Questo tipo di hosting di un servizio viene spesso chiamato "self-hosting"" perché è la stessa applicazione gestita a svolgere il lavoro di hosting.</span><span class="sxs-lookup"><span data-stu-id="7c42a-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="7c42a-107">Per chiudere il servizio, chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7c42a-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="7c42a-108">Un servizio può essere ospitato anche in un servizio Windows gestito, in Internet Information Services (IIS) o nel servizio Attivazione processo Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="7c42a-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="7c42a-109">opzioni per un servizio di hosting, vedere [servizi di Hosting](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="7c42a-109"> hosting options for a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
 <span data-ttu-id="7c42a-110">L'hosting di un servizio in un'applicazione gestita è l'opzione più flessibile perché richiede la distribuzione di un'infrastruttura minima.</span><span class="sxs-lookup"><span data-stu-id="7c42a-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="7c42a-111">hosting dei servizi in applicazioni gestite, vedere [Hosting in un'applicazione gestita](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="7c42a-111"> hosting services in managed applications, see [Hosting in a Managed Application](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>  
  
 <span data-ttu-id="7c42a-112">Nella procedura seguente viene illustrato come implementare un servizio indipendente in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="7c42a-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>  
  
### <a name="to-create-a-self-hosted-service"></a><span data-ttu-id="7c42a-113">Per creare un servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="7c42a-113">To create a self-hosted service</span></span>  
  
1.  <span data-ttu-id="7c42a-114">Aprire [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] e selezionare **New**, **progetto...**  dal **File** menu.</span><span class="sxs-lookup"><span data-stu-id="7c42a-114">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and select **New**, **Project...** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="7c42a-115">Nel **modelli installati** elenco, selezionare **Visual c#**, **Windows** o **Visual Basic**, **Windows**.</span><span class="sxs-lookup"><span data-stu-id="7c42a-115">In the **Installed Templates** list, select **Visual C#**, **Windows** or **Visual Basic**, **Windows**.</span></span> <span data-ttu-id="7c42a-116">A seconda del [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] impostazioni, uno o entrambi questi potrebbe essere nel **altri linguaggi** nodo il **modelli installati** elenco.</span><span class="sxs-lookup"><span data-stu-id="7c42a-116">Depending on your [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] settings, one or both of these may be under the **Other Languages** node in the **Installed Templates** list.</span></span>  
  
3.  <span data-ttu-id="7c42a-117">Selezionare **applicazione Console** dal **Windows** elenco.</span><span class="sxs-lookup"><span data-stu-id="7c42a-117">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="7c42a-118">Tipo `SelfHost` nel **nome** casella e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c42a-118">Type `SelfHost` in the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="7c42a-119">Fare doppio clic su **SelfHost** in **Esplora** e selezionare **Aggiungi riferimento...** . Selezionare **System. ServiceModel** dal **.NET** scheda e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c42a-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference...**. Select **System.ServiceModel** from the **.NET** tab and click **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="7c42a-120">Se il **Esplora** finestra non è visibile, selezionare **Esplora** dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="7c42a-120">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="7c42a-121">Fare doppio clic su **Program.cs** o **Module1. vb** in **Esplora** per aprirlo nella finestra del codice, se non è già aperto.</span><span class="sxs-lookup"><span data-stu-id="7c42a-121">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window if it is not already open.</span></span> <span data-ttu-id="7c42a-122">Aggiungere le seguenti istruzioni all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="7c42a-122">Add the following statements at the top of the file.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]  
  
6.  <span data-ttu-id="7c42a-123">Definire e implementare un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="7c42a-123">Define and implement a service contract.</span></span> <span data-ttu-id="7c42a-124">In questo esempio viene definito un codice `HelloWorldService` che restituisce un messaggio in base all'input del servizio.</span><span class="sxs-lookup"><span data-stu-id="7c42a-124">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]  
  
    > [!NOTE]
    >  [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="7c42a-125">come definire e implementare un'interfaccia di servizio, vedere [procedura: definire un contratto di servizio](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) e [procedura: implementare un contratto di servizio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span><span class="sxs-lookup"><span data-stu-id="7c42a-125"> how to define and implement a service interface, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span></span>  
  
7.  <span data-ttu-id="7c42a-126">All'inizio del metodo `Main`, creare un'istanza della classe <xref:System.Uri> con l'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="7c42a-126">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]  
  
8.  <span data-ttu-id="7c42a-127">Creare un'istanza della classe <xref:System.ServiceModel.ServiceHost>, passando un <xref:System.Type> che rappresenta il tipo di servizio e l'URI (Uniform Resource Identifier) dell'indirizzo di base a <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="7c42a-127">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="7c42a-128">Abilitare la pubblicazione dei metadati, quindi chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> sull'oggetto <xref:System.ServiceModel.ServiceHost> per inizializzare il servizio e prepararlo a ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="7c42a-128">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]       
  
    > [!NOTE]
    >  <span data-ttu-id="7c42a-129">In questo esempio vengono utilizzati endpoint predefiniti e per il servizio non è necessario alcun file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7c42a-129">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="7c42a-130">Se non è specificato alcun endpoint, il runtime ne crea uno per ogni indirizzo di base per ciascun contratto di servizio implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="7c42a-130">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="7c42a-131">gli endpoint predefiniti, vedere [configurazione semplificata](../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7c42a-131"> default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
9. <span data-ttu-id="7c42a-132">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="7c42a-132">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
### <a name="to-test-the-service"></a><span data-ttu-id="7c42a-133">Per eseguire il test del servizio</span><span class="sxs-lookup"><span data-stu-id="7c42a-133">To test the service</span></span>  
  
1.  <span data-ttu-id="7c42a-134">Premere CTRL+F5 per eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="7c42a-134">Press Ctrl + F5 to run the service.</span></span>  
  
2.  <span data-ttu-id="7c42a-135">Aprire **Client di prova WCF**.</span><span class="sxs-lookup"><span data-stu-id="7c42a-135">Open **WCF Test Client**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="7c42a-136">Per aprire **Client di prova WCF**, aprire un [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] prompt dei comandi ed eseguire **WcfTestClient.exe**.</span><span class="sxs-lookup"><span data-stu-id="7c42a-136">To open **WCF Test Client**, open a [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] command prompt and execute **WcfTestClient.exe**.</span></span>  
  
3.  <span data-ttu-id="7c42a-137">Selezionare **aggiungere il servizio...**  dal **File** menu.</span><span class="sxs-lookup"><span data-stu-id="7c42a-137">Select **Add Service...** from the **File** menu.</span></span>  
  
4.  <span data-ttu-id="7c42a-138">Tipo `http://localhost:8080/hello` nella casella Indirizzo e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c42a-138">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="7c42a-139">Verificare che il servizio sia in esecuzione. In caso contrario, il passaggio non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="7c42a-139">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="7c42a-140">Se nel codice è stato modificato l'indirizzo di base, in questo passaggio utilizzare l'indirizzo di base modificato.</span><span class="sxs-lookup"><span data-stu-id="7c42a-140">If you have changed the base address in the code, then use the modified base address in this step.</span></span>  
  
5.  <span data-ttu-id="7c42a-141">Fare doppio clic su **SayHello** sotto il **progetti di servizi** nodo.</span><span class="sxs-lookup"><span data-stu-id="7c42a-141">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="7c42a-142">Digitare il nome nel **valore** colonna il **richiesta** elenco e fare clic su **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="7c42a-142">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span> <span data-ttu-id="7c42a-143">Viene visualizzato un messaggio di risposta di **risposta** elenco.</span><span class="sxs-lookup"><span data-stu-id="7c42a-143">A reply message appears in the **Response** list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c42a-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c42a-144">Example</span></span>  
 <span data-ttu-id="7c42a-145">Nell'esempio seguente viene creato un oggetto <xref:System.ServiceModel.ServiceHost> per ospitare un servizio di tipo `HelloWorldService`, quindi viene chiamato il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> su <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7c42a-145">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="7c42a-146">Nel codice viene fornito un indirizzo di base, viene abilitata la pubblicazione di metadati e vengono utilizzati endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="7c42a-146">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>  
  
 [!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
 [!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="7c42a-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c42a-147">See Also</span></span>  
 <xref:System.Uri>  
 <xref:System.Configuration.ConfigurationManager.AppSettings%2A>  
 <xref:System.Configuration.ConfigurationManager>  
 [<span data-ttu-id="7c42a-148">Procedura: ospitare un servizio WCF in IIS</span><span class="sxs-lookup"><span data-stu-id="7c42a-148">How to: Host a WCF Service in IIS</span></span>](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)  
 [<span data-ttu-id="7c42a-149">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="7c42a-149">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)  
 [<span data-ttu-id="7c42a-150">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="7c42a-150">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="7c42a-151">Procedura: Definire un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="7c42a-151">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 [<span data-ttu-id="7c42a-152">Procedura: Implementare un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="7c42a-152">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [<span data-ttu-id="7c42a-153">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="7c42a-153">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="7c42a-154">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="7c42a-154">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="7c42a-155">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="7c42a-155">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)
