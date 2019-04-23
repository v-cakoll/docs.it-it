---
title: 'Endpoint: indirizzi, associazioni e contratti'
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: 3e78e7cf0c5acde53d7ee23294fd52134414e860
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207526"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="72d79-102">Endpoint: indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="72d79-102">Endpoints: Addresses, Bindings, and Contracts</span></span>
<span data-ttu-id="72d79-103">Tutte le comunicazioni con un servizio Windows Communication Foundation (WCF) viene eseguita tramite il *endpoint* del servizio.</span><span class="sxs-lookup"><span data-stu-id="72d79-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="72d79-104">Gli endpoint forniscono ai client l'accesso alla funzionalità offerta da un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="72d79-104">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>  
  
 <span data-ttu-id="72d79-105">Ogni endpoint è costituito da quattro proprietà:</span><span class="sxs-lookup"><span data-stu-id="72d79-105">Each endpoint consists of four properties:</span></span>  
  
-   <span data-ttu-id="72d79-106">Un indirizzo che indica dove si trova l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="72d79-106">An address that indicates where the endpoint can be found.</span></span>  
  
-   <span data-ttu-id="72d79-107">Un'associazione che specifica in che modo un client può comunicare con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="72d79-107">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="72d79-108">Un contratto che identifica le operazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="72d79-108">A contract that identifies the operations available.</span></span>  
  
-   <span data-ttu-id="72d79-109">Un set di comportamenti che specificano dettagli di implementazione locali dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="72d79-109">A set of behaviors that specify local implementation details of the endpoint.</span></span>  
  
 <span data-ttu-id="72d79-110">In questo argomento viene illustrata questa struttura di endpoint e viene illustrato come viene rappresentato nel modello a oggetti WCF.</span><span class="sxs-lookup"><span data-stu-id="72d79-110">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="72d79-111">Struttura di un endpoint</span><span class="sxs-lookup"><span data-stu-id="72d79-111">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="72d79-112">Ogni endpoint è costituito dagli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="72d79-112">Each endpoint consists of the following:</span></span>  
  
-   <span data-ttu-id="72d79-113">Indirizzo: L'indirizzo identifica l'endpoint in modo univoco e indica a potenziali consumer del servizio in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="72d79-113">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="72d79-114">È rappresentato nel modello a oggetti WCF dal <xref:System.ServiceModel.EndpointAddress> classe.</span><span class="sxs-lookup"><span data-stu-id="72d79-114">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="72d79-115">Una classe <xref:System.ServiceModel.EndpointAddress> contiene:</span><span class="sxs-lookup"><span data-stu-id="72d79-115">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>  
  
    -   <span data-ttu-id="72d79-116">Una proprietà <xref:System.ServiceModel.EndpointAddress.Uri%2A>, che rappresenta l'indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="72d79-116">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>  
  
    -   <span data-ttu-id="72d79-117">Una proprietà <xref:System.ServiceModel.EndpointAddress.Identity%2A>, che rappresenta l'identità di sicurezza del servizio e una raccolta di intestazioni di messaggio facoltative.</span><span class="sxs-lookup"><span data-stu-id="72d79-117">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="72d79-118">Le intestazioni di messaggio facoltative vengono utilizzate per fornire ulteriori informazioni di indirizzamento più dettagliate, per identificare o interagire con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="72d79-118">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>  
  
     <span data-ttu-id="72d79-119">Per altre informazioni, vedere [che specifica un indirizzo Endpoint](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="72d79-119">For more information, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
-   <span data-ttu-id="72d79-120">Binding: L'associazione specifica la modalità di comunicazione con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="72d79-120">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="72d79-121">vale a dire:</span><span class="sxs-lookup"><span data-stu-id="72d79-121">This includes:</span></span>  
  
    -   <span data-ttu-id="72d79-122">Il protocollo di trasporto da utilizzare (ad esempio, TCP o HTTP).</span><span class="sxs-lookup"><span data-stu-id="72d79-122">The transport protocol to use (for example, TCP or HTTP).</span></span>  
  
    -   <span data-ttu-id="72d79-123">La codifica da utilizzare per i messaggi (ad esempio, testo o binaria).</span><span class="sxs-lookup"><span data-stu-id="72d79-123">The encoding to use for the messages (for example, text or binary).</span></span>  
  
    -   <span data-ttu-id="72d79-124">I necessari requisiti di sicurezza (ad esempio, la protezione dei messaggi SSL o SOAP).</span><span class="sxs-lookup"><span data-stu-id="72d79-124">The necessary security requirements (for example, SSL or SOAP message security).</span></span>  
  
     <span data-ttu-id="72d79-125">Per altre informazioni, vedere [panoramica delle associazioni WCF](../../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="72d79-125">For more information, see [WCF Bindings Overview](../../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="72d79-126">Un'associazione è rappresentata nel modello a oggetti WCF dalla classe di base astratta <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="72d79-126">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="72d79-127">Per la maggior parte degli scenari, gli utenti possono utilizzare una delle associazioni fornite dal sistema.</span><span class="sxs-lookup"><span data-stu-id="72d79-127">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="72d79-128">Per altre informazioni, vedere [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="72d79-128">For more information, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
-   <span data-ttu-id="72d79-129">Contratti: Il contratto delinea la funzionalità che l'endpoint espone al client.</span><span class="sxs-lookup"><span data-stu-id="72d79-129">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="72d79-130">Un contratto specifica:</span><span class="sxs-lookup"><span data-stu-id="72d79-130">A contract specifies:</span></span>  
  
    -   <span data-ttu-id="72d79-131">Quali operazioni possono essere chiamate da un client.</span><span class="sxs-lookup"><span data-stu-id="72d79-131">What operations can be called by a client.</span></span>  
  
    -   <span data-ttu-id="72d79-132">La forma del messaggio.</span><span class="sxs-lookup"><span data-stu-id="72d79-132">The form of the message.</span></span>  
  
    -   <span data-ttu-id="72d79-133">Il tipo di parametri di input o di dati necessario per chiamare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="72d79-133">The type of input parameters or data required to call the operation.</span></span>  
  
    -   <span data-ttu-id="72d79-134">Il tipo di elaborazione o di messaggio di risposta che il client può aspettarsi.</span><span class="sxs-lookup"><span data-stu-id="72d79-134">What type of processing or response message the client can expect.</span></span>  
  
     <span data-ttu-id="72d79-135">Per altre informazioni sulla definizione di un contratto, vedere [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="72d79-135">For more information about defining a contract, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
-   <span data-ttu-id="72d79-136">Comportamenti: È possibile usare i comportamenti dell'endpoint per personalizzare il comportamento dell'endpoint del servizio locale.</span><span class="sxs-lookup"><span data-stu-id="72d79-136">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="72d79-137">I comportamenti dell'endpoint realizzano questo obiettivo partecipando nel processo di compilazione un WCFruntime.</span><span class="sxs-lookup"><span data-stu-id="72d79-137">Endpoint behaviors achieve this by participating in the process of building a WCFruntime.</span></span> <span data-ttu-id="72d79-138">Un esempio di comportamento dell'endpoint è rappresentato dalla proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, che consente di specificare un indirizzo di ascolto diverso dall'indirizzo SOAP o WSDL (Web Services Description Language).</span><span class="sxs-lookup"><span data-stu-id="72d79-138">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="72d79-139">Per altre informazioni, vedere [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span><span class="sxs-lookup"><span data-stu-id="72d79-139">For more information, see [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span></span>  
  
## <a name="defining-endpoints"></a><span data-ttu-id="72d79-140">Definizione di endpoint</span><span class="sxs-lookup"><span data-stu-id="72d79-140">Defining Endpoints</span></span>  
 <span data-ttu-id="72d79-141">È possibile specificare l'endpoint di un servizio in modo imperativo, tramite codice, o in modo dichiarativo, tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="72d79-141">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="72d79-142">Per altre informazioni, vedere [Procedura: Creare un Endpoint del servizio nella configurazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) e [come: Creare un Endpoint del servizio nel codice](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="72d79-142">For more information, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="72d79-143">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="72d79-143">In This Section</span></span>  
 <span data-ttu-id="72d79-144">Contenuto della sezione viene illustrato lo scopo di associazioni, endpoint e indirizzi; viene descritto come configurare un'associazione e un endpoint e viene dimostrato come utilizzare il comportamento `ClientVia` e la proprietà `ListenUri`.</span><span class="sxs-lookup"><span data-stu-id="72d79-144">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>  
  
 [<span data-ttu-id="72d79-145">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="72d79-145">Addresses</span></span>](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 <span data-ttu-id="72d79-146">Viene descritto come vengono indirizzati gli endpoint in WCF.</span><span class="sxs-lookup"><span data-stu-id="72d79-146">Describes how endpoints are addressed in WCF.</span></span>  
  
 [<span data-ttu-id="72d79-147">Associazioni</span><span class="sxs-lookup"><span data-stu-id="72d79-147">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 <span data-ttu-id="72d79-148">Viene descritto come vengono utilizzate le associazioni per specificare i dettagli sul trasporto, la codifica e il protocollo necessari per consentire la comunicazione tra client e servizi.</span><span class="sxs-lookup"><span data-stu-id="72d79-148">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>  
  
 [<span data-ttu-id="72d79-149">Contratti</span><span class="sxs-lookup"><span data-stu-id="72d79-149">Contracts</span></span>](../../../../docs/framework/wcf/feature-details/contracts.md)  
 <span data-ttu-id="72d79-150">Viene descritto in che modo i contratti definiscono i metodi di un servizio.</span><span class="sxs-lookup"><span data-stu-id="72d79-150">Describes how contracts define the methods of a service.</span></span>  
  
 [<span data-ttu-id="72d79-151">Procedura: Creare un Endpoint del servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="72d79-151">How to: Create a Service Endpoint in Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="72d79-152">Viene descritto come creare un endpoint del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="72d79-152">Describes how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="72d79-153">Procedura: Creare un Endpoint del servizio nel codice</span><span class="sxs-lookup"><span data-stu-id="72d79-153">How to: Create a Service Endpoint in Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="72d79-154">Viene descritto come creare un endpoint del servizio nel codice.</span><span class="sxs-lookup"><span data-stu-id="72d79-154">Describes how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="72d79-155">Procedura: Usare Svcutil.exe per convalidare il codice del servizio compilato</span><span class="sxs-lookup"><span data-stu-id="72d79-155">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 <span data-ttu-id="72d79-156">Viene descritto come rilevare errori in implementazioni del servizio e le configurazioni senza ospitare il servizio utilizzando il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="72d79-156">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72d79-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72d79-157">See also</span></span>

- [<span data-ttu-id="72d79-158">Configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="72d79-158">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)
- [<span data-ttu-id="72d79-159">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="72d79-159">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
