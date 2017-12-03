---
title: 'Endpoint: indirizzi, associazioni e contratti'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6c0b13ee48ed729d89f4b4b506e3608abe7e82b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="fb1d7-102">Endpoint: indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="fb1d7-102">Endpoints: Addresses, Bindings, and Contracts</span></span>
<span data-ttu-id="fb1d7-103">Tutte le comunicazioni con un [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] servizio avviene tramite il *endpoint* del servizio.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-103">All communication with a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="fb1d7-104">Gli endpoint forniscono ai client l'accesso alla funzionalità offerta da un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb1d7-104">Endpoints provide clients access to the functionality offered by a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="fb1d7-105">Ogni endpoint è costituito da quattro proprietà:</span><span class="sxs-lookup"><span data-stu-id="fb1d7-105">Each endpoint consists of four properties:</span></span>  
  
-   <span data-ttu-id="fb1d7-106">Un indirizzo che indica dove si trova l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-106">An address that indicates where the endpoint can be found.</span></span>  
  
-   <span data-ttu-id="fb1d7-107">Un'associazione che specifica in che modo un client può comunicare con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-107">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="fb1d7-108">Un contratto che identifica le operazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-108">A contract that identifies the operations available.</span></span>  
  
-   <span data-ttu-id="fb1d7-109">Un set di comportamenti che specificano dettagli di implementazione locali dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-109">A set of behaviors that specify local implementation details of the endpoint.</span></span>  
  
 <span data-ttu-id="fb1d7-110">In questo argomento viene illustrata la struttura di un endpoint e viene spiegato come tale struttura viene rappresentata nel modello a oggetti [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb1d7-110">This topic discusses this endpoint structure and explains how it is represented in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] object model.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="fb1d7-111">Struttura di un endpoint</span><span class="sxs-lookup"><span data-stu-id="fb1d7-111">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="fb1d7-112">Ogni endpoint è costituito dagli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb1d7-112">Each endpoint consists of the following:</span></span>  
  
-   <span data-ttu-id="fb1d7-113">Indirizzo: l'indirizzo identifica in modo univoco l'endpoint e comunica ai potenziali utenti l'ubicazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-113">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="fb1d7-114">Nel modello a oggetti [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], l'indirizzo è rappresentato dalla classe <xref:System.ServiceModel.EndpointAddress>.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-114">It is represented in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="fb1d7-115">Una classe <xref:System.ServiceModel.EndpointAddress> contiene:</span><span class="sxs-lookup"><span data-stu-id="fb1d7-115">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>  
  
    -   <span data-ttu-id="fb1d7-116">Una proprietà <xref:System.ServiceModel.EndpointAddress.Uri%2A>, che rappresenta l'indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-116">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>  
  
    -   <span data-ttu-id="fb1d7-117">Una proprietà <xref:System.ServiceModel.EndpointAddress.Identity%2A>, che rappresenta l'identità di sicurezza del servizio e una raccolta di intestazioni di messaggio facoltative.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-117">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="fb1d7-118">Le intestazioni di messaggio facoltative vengono utilizzate per fornire ulteriori informazioni di indirizzamento più dettagliate, per identificare o interagire con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-118">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>  
  
     [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fb1d7-119">[Specificando un indirizzo Endpoint](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="fb1d7-119"> [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
-   <span data-ttu-id="fb1d7-120">Associazione: l'associazione specifica la modalità di comunicazione con l'endpoint,</span><span class="sxs-lookup"><span data-stu-id="fb1d7-120">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="fb1d7-121">vale a dire:</span><span class="sxs-lookup"><span data-stu-id="fb1d7-121">This includes:</span></span>  
  
    -   <span data-ttu-id="fb1d7-122">Il protocollo di trasporto da utilizzare (ad esempio, TCP o HTTP).</span><span class="sxs-lookup"><span data-stu-id="fb1d7-122">The transport protocol to use (for example, TCP or HTTP).</span></span>  
  
    -   <span data-ttu-id="fb1d7-123">La codifica da utilizzare per i messaggi (ad esempio, testo o binaria).</span><span class="sxs-lookup"><span data-stu-id="fb1d7-123">The encoding to use for the messages (for example, text or binary).</span></span>  
  
    -   <span data-ttu-id="fb1d7-124">I necessari requisiti di sicurezza (ad esempio, la protezione dei messaggi SSL o SOAP).</span><span class="sxs-lookup"><span data-stu-id="fb1d7-124">The necessary security requirements (for example, SSL or SOAP message security).</span></span>  
  
     [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fb1d7-125">[Panoramica delle associazioni WCF](../../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fb1d7-125"> [WCF Bindings Overview](../../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="fb1d7-126">Nel modello a oggetti [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], un'associazione è rappresentata dalla classe astratta di base <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-126">A binding is represented in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="fb1d7-127">Per la maggior parte degli scenari, gli utenti possono utilizzare una delle associazioni fornite dal sistema.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-127">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="fb1d7-128">Per ulteriori informazioni, vedere [associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="fb1d7-128">For more information, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
-   <span data-ttu-id="fb1d7-129">Contratti: il contratto delinea la funzionalità che l'endpoint espone al client.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-129">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="fb1d7-130">Un contratto specifica:</span><span class="sxs-lookup"><span data-stu-id="fb1d7-130">A contract specifies:</span></span>  
  
    -   <span data-ttu-id="fb1d7-131">Quali operazioni possono essere chiamate da un client.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-131">What operations can be called by a client.</span></span>  
  
    -   <span data-ttu-id="fb1d7-132">La forma del messaggio.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-132">The form of the message.</span></span>  
  
    -   <span data-ttu-id="fb1d7-133">Il tipo di parametri di input o di dati necessario per chiamare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-133">The type of input parameters or data required to call the operation.</span></span>  
  
    -   <span data-ttu-id="fb1d7-134">Il tipo di elaborazione o di messaggio di risposta che il client può aspettarsi.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-134">What type of processing or response message the client can expect.</span></span>  
  
     <span data-ttu-id="fb1d7-135">Per ulteriori informazioni sulla definizione di un contratto, vedere [progettazione contratti di servizio](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="fb1d7-135">For more information about defining a contract, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
-   <span data-ttu-id="fb1d7-136">Comportamenti: è possibile utilizzare i comportamenti dell'endpoint per personalizzare il comportamento locale dell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-136">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="fb1d7-137">I comportamenti dell'endpoint realizzano questo obiettivo partecipando nel processo di compilazione un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]runtime.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-137">Endpoint behaviors achieve this by participating in the process of building a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]runtime.</span></span> <span data-ttu-id="fb1d7-138">Un esempio di comportamento dell'endpoint è rappresentato dalla proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, che consente di specificare un indirizzo di ascolto diverso dall'indirizzo SOAP o WSDL (Web Services Description Language).</span><span class="sxs-lookup"><span data-stu-id="fb1d7-138">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fb1d7-139">[ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span><span class="sxs-lookup"><span data-stu-id="fb1d7-139"> [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span></span>  
  
## <a name="defining-endpoints"></a><span data-ttu-id="fb1d7-140">Definizione di endpoint</span><span class="sxs-lookup"><span data-stu-id="fb1d7-140">Defining Endpoints</span></span>  
 <span data-ttu-id="fb1d7-141">È possibile specificare l'endpoint di un servizio in modo imperativo, tramite codice, o in modo dichiarativo, tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-141">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fb1d7-142">[Procedura: creare un Endpoint del servizio nella configurazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) e [procedura: creare un Endpoint del servizio nel codice](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="fb1d7-142"> [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fb1d7-143">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="fb1d7-143">In This Section</span></span>  
 <span data-ttu-id="fb1d7-144">Contenuto della sezione viene illustrato lo scopo di associazioni, endpoint e indirizzi; viene descritto come configurare un'associazione e un endpoint e viene dimostrato come utilizzare il comportamento `ClientVia` e la proprietà `ListenUri`.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-144">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>  
  
 [<span data-ttu-id="fb1d7-145">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="fb1d7-145">Addresses</span></span>](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 <span data-ttu-id="fb1d7-146">Viene descritto come vengono indirizzati gli endpoint in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb1d7-146">Describes how endpoints are addressed in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="fb1d7-147">Associazioni</span><span class="sxs-lookup"><span data-stu-id="fb1d7-147">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 <span data-ttu-id="fb1d7-148">Viene descritto come vengono utilizzate le associazioni per specificare i dettagli sul trasporto, la codifica e il protocollo necessari per consentire la comunicazione tra client e servizi.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-148">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>  
  
 [<span data-ttu-id="fb1d7-149">Contratti</span><span class="sxs-lookup"><span data-stu-id="fb1d7-149">Contracts</span></span>](../../../../docs/framework/wcf/feature-details/contracts.md)  
 <span data-ttu-id="fb1d7-150">Viene descritto in che modo i contratti definiscono i metodi di un servizio.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-150">Describes how contracts define the methods of a service.</span></span>  
  
 [<span data-ttu-id="fb1d7-151">Procedura: creare un Endpoint del servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="fb1d7-151">How to: Create a Service Endpoint in Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="fb1d7-152">Viene descritto come creare un endpoint del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-152">Describes how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="fb1d7-153">Procedura: creare un Endpoint del servizio nel codice</span><span class="sxs-lookup"><span data-stu-id="fb1d7-153">How to: Create a Service Endpoint in Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="fb1d7-154">Viene descritto come creare un endpoint del servizio nel codice.</span><span class="sxs-lookup"><span data-stu-id="fb1d7-154">Describes how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="fb1d7-155">Procedura: usare Svcutil.exe per convalidare il codice del servizio compilato</span><span class="sxs-lookup"><span data-stu-id="fb1d7-155">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 <span data-ttu-id="fb1d7-156">Viene descritto come individuare gli errori nelle configurazioni e le implementazioni del servizio senza ospitare il servizio utilizzando il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fb1d7-156">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb1d7-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb1d7-157">See Also</span></span>  
 [<span data-ttu-id="fb1d7-158">Configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="fb1d7-158">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
 [<span data-ttu-id="fb1d7-159">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="fb1d7-159">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
