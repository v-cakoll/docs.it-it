---
title: 'Endpoint: indirizzi, associazioni e contratti'
description: Informazioni sull'utilizzo di tutte le comunicazioni con un servizio WCF tramite gli endpoint del servizio, che forniscono ai client l'accesso alla funzionalità offerta dal servizio.
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: ce0874bfed716716b6fd1801b35a4266095cd752
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247312"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="c077e-103">Endpoint: indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="c077e-103">Endpoints: Addresses, Bindings, and Contracts</span></span>

<span data-ttu-id="c077e-104">Tutte le comunicazioni con un servizio Windows Communication Foundation (WCF) avvengono tramite gli *endpoint* del servizio.</span><span class="sxs-lookup"><span data-stu-id="c077e-104">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="c077e-105">Gli endpoint forniscono ai client l'accesso alla funzionalità offerta da un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="c077e-105">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>

<span data-ttu-id="c077e-106">Ogni endpoint è costituito da quattro proprietà:</span><span class="sxs-lookup"><span data-stu-id="c077e-106">Each endpoint consists of four properties:</span></span>

- <span data-ttu-id="c077e-107">Un indirizzo che indica dove si trova l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="c077e-107">An address that indicates where the endpoint can be found.</span></span>

- <span data-ttu-id="c077e-108">Un'associazione che specifica in che modo un client può comunicare con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="c077e-108">A binding that specifies how a client can communicate with the endpoint.</span></span>

- <span data-ttu-id="c077e-109">Un contratto che identifica le operazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="c077e-109">A contract that identifies the operations available.</span></span>

- <span data-ttu-id="c077e-110">Un set di comportamenti che specificano dettagli di implementazione locali dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="c077e-110">A set of behaviors that specify local implementation details of the endpoint.</span></span>

<span data-ttu-id="c077e-111">In questo argomento viene illustrata la struttura dell'endpoint e viene illustrato come viene rappresentata nel modello a oggetti WCF.</span><span class="sxs-lookup"><span data-stu-id="c077e-111">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>

## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="c077e-112">Struttura di un endpoint</span><span class="sxs-lookup"><span data-stu-id="c077e-112">The Structure of an Endpoint</span></span>

<span data-ttu-id="c077e-113">Ogni endpoint è costituito dagli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c077e-113">Each endpoint consists of the following:</span></span>

- <span data-ttu-id="c077e-114">Indirizzo: l'indirizzo identifica in modo univoco l'endpoint e comunica ai potenziali utenti l'ubicazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="c077e-114">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="c077e-115">Viene rappresentata nel modello a oggetti WCF dalla <xref:System.ServiceModel.EndpointAddress> classe.</span><span class="sxs-lookup"><span data-stu-id="c077e-115">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="c077e-116">Una classe <xref:System.ServiceModel.EndpointAddress> contiene:</span><span class="sxs-lookup"><span data-stu-id="c077e-116">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>

  - <span data-ttu-id="c077e-117">Una proprietà <xref:System.ServiceModel.EndpointAddress.Uri%2A>, che rappresenta l'indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="c077e-117">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>

  - <span data-ttu-id="c077e-118">Una proprietà <xref:System.ServiceModel.EndpointAddress.Identity%2A>, che rappresenta l'identità di sicurezza del servizio e una raccolta di intestazioni di messaggio facoltative.</span><span class="sxs-lookup"><span data-stu-id="c077e-118">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="c077e-119">Le intestazioni di messaggio facoltative vengono utilizzate per fornire ulteriori informazioni di indirizzamento più dettagliate, per identificare o interagire con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="c077e-119">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>

  <span data-ttu-id="c077e-120">Per ulteriori informazioni, vedere [specifica di un indirizzo endpoint](../specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="c077e-120">For more information, see [Specifying an Endpoint Address](../specifying-an-endpoint-address.md).</span></span>

- <span data-ttu-id="c077e-121">Associazione: l'associazione specifica la modalità di comunicazione con l'endpoint,</span><span class="sxs-lookup"><span data-stu-id="c077e-121">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="c077e-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c077e-122">This includes:</span></span>

  - <span data-ttu-id="c077e-123">Il protocollo di trasporto da utilizzare (ad esempio, TCP o HTTP).</span><span class="sxs-lookup"><span data-stu-id="c077e-123">The transport protocol to use (for example, TCP or HTTP).</span></span>

  - <span data-ttu-id="c077e-124">La codifica da utilizzare per i messaggi (ad esempio, testo o binaria).</span><span class="sxs-lookup"><span data-stu-id="c077e-124">The encoding to use for the messages (for example, text or binary).</span></span>

  - <span data-ttu-id="c077e-125">I necessari requisiti di sicurezza (ad esempio, la protezione dei messaggi SSL o SOAP).</span><span class="sxs-lookup"><span data-stu-id="c077e-125">The necessary security requirements (for example, SSL or SOAP message security).</span></span>

  <span data-ttu-id="c077e-126">Per ulteriori informazioni, vedere [Cenni preliminari sulle associazioni WCF](../bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c077e-126">For more information, see [WCF Bindings Overview](../bindings-overview.md).</span></span> <span data-ttu-id="c077e-127">Un'associazione viene rappresentata nel modello a oggetti WCF dalla classe di base astratta <xref:System.ServiceModel.Channels.Binding> .</span><span class="sxs-lookup"><span data-stu-id="c077e-127">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="c077e-128">Per la maggior parte degli scenari, gli utenti possono utilizzare una delle associazioni fornite dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c077e-128">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="c077e-129">Per ulteriori informazioni, vedere [binding forniti dal sistema](../system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="c077e-129">For more information, see [System-Provided Bindings](../system-provided-bindings.md).</span></span>

- <span data-ttu-id="c077e-130">Contratti: il contratto delinea la funzionalità che l'endpoint espone al client.</span><span class="sxs-lookup"><span data-stu-id="c077e-130">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="c077e-131">Un contratto specifica:</span><span class="sxs-lookup"><span data-stu-id="c077e-131">A contract specifies:</span></span>

  - <span data-ttu-id="c077e-132">Quali operazioni possono essere chiamate da un client.</span><span class="sxs-lookup"><span data-stu-id="c077e-132">What operations can be called by a client.</span></span>

  - <span data-ttu-id="c077e-133">La forma del messaggio.</span><span class="sxs-lookup"><span data-stu-id="c077e-133">The form of the message.</span></span>

  - <span data-ttu-id="c077e-134">Il tipo di parametri di input o di dati necessario per chiamare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="c077e-134">The type of input parameters or data required to call the operation.</span></span>

  - <span data-ttu-id="c077e-135">Il tipo di elaborazione o di messaggio di risposta che il client può aspettarsi.</span><span class="sxs-lookup"><span data-stu-id="c077e-135">What type of processing or response message the client can expect.</span></span>

  <span data-ttu-id="c077e-136">Per ulteriori informazioni sulla definizione di un contratto, vedere [progettazione di contratti di servizio](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="c077e-136">For more information about defining a contract, see [Designing Service Contracts](../designing-service-contracts.md).</span></span>

- <span data-ttu-id="c077e-137">Comportamenti: è possibile utilizzare i comportamenti dell'endpoint per personalizzare il comportamento locale dell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="c077e-137">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="c077e-138">A questo scopo, i comportamenti degli endpoint partecipano al processo di compilazione di un runtime WCF.</span><span class="sxs-lookup"><span data-stu-id="c077e-138">Endpoint behaviors achieve this by participating in the process of building a WCF runtime.</span></span> <span data-ttu-id="c077e-139">Un esempio di comportamento dell'endpoint è rappresentato dalla proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, che consente di specificare un indirizzo di ascolto diverso dall'indirizzo SOAP o WSDL (Web Services Description Language).</span><span class="sxs-lookup"><span data-stu-id="c077e-139">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="c077e-140">Per ulteriori informazioni, vedere [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md).</span><span class="sxs-lookup"><span data-stu-id="c077e-140">For more information, see [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md).</span></span>

## <a name="defining-endpoints"></a><span data-ttu-id="c077e-141">Definizione di endpoint</span><span class="sxs-lookup"><span data-stu-id="c077e-141">Defining Endpoints</span></span>

<span data-ttu-id="c077e-142">È possibile specificare l'endpoint di un servizio in modo imperativo, tramite codice, o in modo dichiarativo, tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="c077e-142">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="c077e-143">Per altre informazioni, vedere [procedura: creare un endpoint del servizio nella configurazione](how-to-create-a-service-endpoint-in-configuration.md) e [procedura: creare un endpoint di servizio nel codice](how-to-create-a-service-endpoint-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="c077e-143">For more information, see [How to: Create a Service Endpoint in Configuration](how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](how-to-create-a-service-endpoint-in-code.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c077e-144">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c077e-144">In This Section</span></span>

<span data-ttu-id="c077e-145">Contenuto della sezione viene illustrato lo scopo di associazioni, endpoint e indirizzi; viene descritto come configurare un'associazione e un endpoint e viene dimostrato come utilizzare il comportamento `ClientVia` e la proprietà `ListenUri`.</span><span class="sxs-lookup"><span data-stu-id="c077e-145">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>

<span data-ttu-id="c077e-146">[Indirizzi](endpoint-addresses.md)</span><span class="sxs-lookup"><span data-stu-id="c077e-146">[Addresses](endpoint-addresses.md)</span></span>\
<span data-ttu-id="c077e-147">Viene descritto come vengono risolti gli endpoint in WCF.</span><span class="sxs-lookup"><span data-stu-id="c077e-147">Describes how endpoints are addressed in WCF.</span></span>

<span data-ttu-id="c077e-148">[Associazioni](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c077e-148">[Bindings](bindings.md)</span></span>\
<span data-ttu-id="c077e-149">Viene descritto come vengono utilizzate le associazioni per specificare i dettagli sul trasporto, la codifica e il protocollo necessari per consentire la comunicazione tra client e servizi.</span><span class="sxs-lookup"><span data-stu-id="c077e-149">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>

<span data-ttu-id="c077e-150">[Contratti](contracts.md)</span><span class="sxs-lookup"><span data-stu-id="c077e-150">[Contracts](contracts.md)</span></span>\
<span data-ttu-id="c077e-151">Viene descritto in che modo i contratti definiscono i metodi di un servizio.</span><span class="sxs-lookup"><span data-stu-id="c077e-151">Describes how contracts define the methods of a service.</span></span>

<span data-ttu-id="c077e-152">[Procedura: creare un endpoint del servizio nella configurazione](how-to-create-a-service-endpoint-in-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="c077e-152">[How to: Create a Service Endpoint in Configuration](how-to-create-a-service-endpoint-in-configuration.md)</span></span>\
<span data-ttu-id="c077e-153">Viene descritto come creare un endpoint del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="c077e-153">Describes how to create a service endpoint in configuration.</span></span>

<span data-ttu-id="c077e-154">[Procedura: creare un endpoint di servizio nel codice](how-to-create-a-service-endpoint-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="c077e-154">[How to: Create a Service Endpoint in Code](how-to-create-a-service-endpoint-in-code.md)</span></span>\
<span data-ttu-id="c077e-155">Viene descritto come creare un endpoint del servizio nel codice.</span><span class="sxs-lookup"><span data-stu-id="c077e-155">Describes how to create a service endpoint in code.</span></span>

<span data-ttu-id="c077e-156">[Procedura: usare Svcutil.exe per convalidare il codice del servizio compilato](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)</span><span class="sxs-lookup"><span data-stu-id="c077e-156">[How to: Use Svcutil.exe to Validate Compiled Service Code](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)</span></span>\
<span data-ttu-id="c077e-157">Viene descritto come rilevare errori in implementazioni e configurazioni del servizio senza ospitare il servizio utilizzando lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c077e-157">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c077e-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c077e-158">See also</span></span>

- [<span data-ttu-id="c077e-159">Configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="c077e-159">Configuring Services</span></span>](../configuring-services.md)
- [<span data-ttu-id="c077e-160">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="c077e-160">Extending Bindings</span></span>](../extending/extending-bindings.md)
