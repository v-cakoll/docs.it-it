---
title: Servizi duplex
description: Informazioni su come creare un contratto di servizio duplex in WCF, che consente a entrambi gli endpoint di inviare messaggi tra loro tramite un canale creato dal client.
ms.date: 05/09/2018
dev_langs:
- csharp
- vb
ms.assetid: 396b875a-d203-4ebe-a3a1-6a330d962e95
ms.openlocfilehash: a43bb63a0ccf1a34b79dce755c19f7ed4cb6c16c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247351"
---
# <a name="duplex-services"></a><span data-ttu-id="57c9a-103">Servizi duplex</span><span class="sxs-lookup"><span data-stu-id="57c9a-103">Duplex Services</span></span>

<span data-ttu-id="57c9a-104">Un contratto di servizio duplex è un modello di scambio di messaggi nel quale entrambi gli endpoint possono inviare messaggi l'uno all'altro in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="57c9a-104">A duplex service contract is a message exchange pattern in which both endpoints can send messages to the other independently.</span></span> <span data-ttu-id="57c9a-105">Un servizio duplex, pertanto, può inviare messaggi all'endpoint client, fornendo un comportamento simile a quello degli eventi.</span><span class="sxs-lookup"><span data-stu-id="57c9a-105">A duplex service, therefore, can send messages back to the client endpoint, providing event-like behavior.</span></span> <span data-ttu-id="57c9a-106">Una comunicazione duplex ha luogo quando un client si connette a un servizio e fornisce a quest'ultimo un canale utilizzabile per inviare messaggi al client.</span><span class="sxs-lookup"><span data-stu-id="57c9a-106">Duplex communication occurs when a client connects to a service and provides the service with a channel on which the service can send messages back to the client.</span></span> <span data-ttu-id="57c9a-107">Si noti che il comportamento simile a quello degli eventi di servizi duplex funziona solo all'interno di una sessione.</span><span class="sxs-lookup"><span data-stu-id="57c9a-107">Note that the event-like behavior of duplex services only works within a session.</span></span>

<span data-ttu-id="57c9a-108">Per creare un contratto duplex è necessario creare una coppia di interfacce.</span><span class="sxs-lookup"><span data-stu-id="57c9a-108">To create a duplex contract you create a pair of interfaces.</span></span> <span data-ttu-id="57c9a-109">La prima è l'interfaccia del contratto di servizio che descrive le operazioni che un client può richiamare.</span><span class="sxs-lookup"><span data-stu-id="57c9a-109">The first is the service contract interface that describes the operations that a client can invoke.</span></span> <span data-ttu-id="57c9a-110">Il contratto di servizio deve specificare un *contratto di callback* nella <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="57c9a-110">That service contract must specify a *callback contract* in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="57c9a-111">Il contratto callback è l'interfaccia che definisce le operazioni che il servizio può chiamare sull'endpoint client.</span><span class="sxs-lookup"><span data-stu-id="57c9a-111">The callback contract is the interface that defines the operations that the service can call on the client endpoint.</span></span> <span data-ttu-id="57c9a-112">Un contratto duplex non richiede sessioni, sebbene le associazioni duplex fornite dal sistema le utilizzino.</span><span class="sxs-lookup"><span data-stu-id="57c9a-112">A duplex contract does not require a session, although the system-provided duplex bindings make use of them.</span></span>

<span data-ttu-id="57c9a-113">Di seguito è riportato un esempio di contratto duplex.</span><span class="sxs-lookup"><span data-stu-id="57c9a-113">The following is an example of a duplex contract.</span></span>

[!code-csharp[c_DuplexServices#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#0)]
[!code-vb[c_DuplexServices#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#0)]

<span data-ttu-id="57c9a-114">La classe `CalculatorService` implementa l'interfaccia `ICalculatorDuplex` primaria.</span><span class="sxs-lookup"><span data-stu-id="57c9a-114">The `CalculatorService` class implements the primary `ICalculatorDuplex` interface.</span></span> <span data-ttu-id="57c9a-115">Il servizio usa la modalità di istanza <xref:System.ServiceModel.InstanceContextMode.PerSession> per gestire il risultato per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="57c9a-115">The service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the result for each session.</span></span> <span data-ttu-id="57c9a-116">Una proprietà privata denominata `Callback` accede al canale callback al client.</span><span class="sxs-lookup"><span data-stu-id="57c9a-116">A private property named `Callback` accesses the callback channel to the client.</span></span> <span data-ttu-id="57c9a-117">Il servizio utilizza il callback per inviare i messaggi al client tramite l'interfaccia callback, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="57c9a-117">The service uses the callback for sending messages back to the client through the callback interface, as shown in the following sample code.</span></span>

[!code-csharp[c_DuplexServices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#1)]
[!code-vb[c_DuplexServices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#1)]

<span data-ttu-id="57c9a-118">Il client deve fornire una classe che implementi l'interfaccia callback del contratto duplex per ricevere messaggi dal servizio.</span><span class="sxs-lookup"><span data-stu-id="57c9a-118">The client must provide a class that implements the callback interface of the duplex contract, for receiving messages from the service.</span></span> <span data-ttu-id="57c9a-119">Nel codice di esempio seguente viene illustrata una classe `CallbackHandler` che implementa l'interfaccia `ICalculatorDuplexCallback`.</span><span class="sxs-lookup"><span data-stu-id="57c9a-119">The following sample code shows a `CallbackHandler` class that implements the `ICalculatorDuplexCallback` interface.</span></span>

[!code-csharp[c_DuplexServices#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#2)]
[!code-vb[c_DuplexServices#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#2)]

<span data-ttu-id="57c9a-120">Il client WCF generato per un contratto duplex richiede la <xref:System.ServiceModel.InstanceContext> fornitura di una classe durante la costruzione.</span><span class="sxs-lookup"><span data-stu-id="57c9a-120">The WCF client that is generated for a duplex contract requires a <xref:System.ServiceModel.InstanceContext> class to be provided upon construction.</span></span> <span data-ttu-id="57c9a-121">Questa classe <xref:System.ServiceModel.InstanceContext> viene usata come sito per un oggetto che implementa l'interfaccia callback e gestisce i messaggi restituiti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="57c9a-121">This <xref:System.ServiceModel.InstanceContext> class is used as the site for an object that implements the callback interface and handles messages that are sent back from the service.</span></span> <span data-ttu-id="57c9a-122">Una classe <xref:System.ServiceModel.InstanceContext> viene costruita con un'istanza della classe `CallbackHandler`.</span><span class="sxs-lookup"><span data-stu-id="57c9a-122">An <xref:System.ServiceModel.InstanceContext> class is constructed with an instance of the `CallbackHandler` class.</span></span> <span data-ttu-id="57c9a-123">Questo oggetto gestisce i messaggi inviati dal servizio al client sull'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="57c9a-123">This object handles messages sent from the service to the client on the callback interface.</span></span>

[!code-csharp[c_DuplexServices#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#3)]
[!code-vb[c_DuplexServices#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#3)]

<span data-ttu-id="57c9a-124">La configurazione per il servizio deve essere impostata in modo da fornire un'associazione che supporta sia la comunicazione della sessione che la comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="57c9a-124">The configuration for the service must be set up to provide a binding that supports both session communication and duplex communication.</span></span> <span data-ttu-id="57c9a-125">L'elemento `wsDualHttpBinding` supporta la comunicazione della sessione e consente la comunicazione duplex fornendo connessioni HTTP doppie, una per ogni direzione.</span><span class="sxs-lookup"><span data-stu-id="57c9a-125">The `wsDualHttpBinding` element supports session communication and allows duplex communication by providing dual HTTP connections, one for each direction.</span></span>

<span data-ttu-id="57c9a-126">Sul client, è necessario configurare un indirizzo utilizzabile dal server per la connessione al client, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="57c9a-126">On the client, you must configure an address that the server can use to connect to the client, as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="57c9a-127">I client non duplex, la cui autenticazione mediante conversazione protetta non riesce, generano di norma un'eccezione <xref:System.ServiceModel.Security.MessageSecurityException>.</span><span class="sxs-lookup"><span data-stu-id="57c9a-127">Non-duplex clients that fail to authenticate using a secure conversation typically throw a <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span> <span data-ttu-id="57c9a-128">Se, tuttavia, un client duplex che usa una conversazione protetta non viene autenticato, riceve un'eccezione <xref:System.TimeoutException>.</span><span class="sxs-lookup"><span data-stu-id="57c9a-128">However, if a duplex client that uses a secure conversation fails to authenticate, the client receives a <xref:System.TimeoutException> instead.</span></span>

<span data-ttu-id="57c9a-129">Quando si crea un client/servizio utilizzando l'elemento `WSHttpBinding` e non si include l'endpoint di callback client, verrà restituito l'errore seguente.</span><span class="sxs-lookup"><span data-stu-id="57c9a-129">If you create a client/service using the `WSHttpBinding` element and you do not include the client callback endpoint, you will receive the following error.</span></span>

```console
HTTP could not register URL
htp://+:80/Temporary_Listen_Addresses/<guid> because TCP port 80 is being used by another application.
```

<span data-ttu-id="57c9a-130">Nell'esempio di codice seguente viene illustrato come specificare l'indirizzo dell'endpoint client a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="57c9a-130">The following sample code shows how to specify the client endpoint address programmatically.</span></span>

```csharp
WSDualHttpBinding binding = new WSDualHttpBinding();
EndpointAddress endptadr = new EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server");
binding.ClientBaseAddress = new Uri("http://localhost:8000/DuplexTestUsingCode/Client/");
```

```vb
Dim binding As New WSDualHttpBinding()
Dim endptadr As New EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server")
binding.ClientBaseAddress = New Uri("http://localhost:8000/DuplexTestUsingCode/Client/")
```

<span data-ttu-id="57c9a-131">Nel codice di esempio seguente viene illustrato come specificare l'indirizzo endpoint client nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="57c9a-131">The following sample code shows how to specify the client endpoint address in configuration.</span></span>

```xml
<client>
    <endpoint name ="ServerEndpoint"
          address="http://localhost:12000/DuplexTestUsingConfig/Server"
          bindingConfiguration="WSDualHttpBinding_IDuplexTest"
            binding="wsDualHttpBinding"
           contract="IDuplexTest" />
</client>
<bindings>
    <wsDualHttpBinding>
        <binding name="WSDualHttpBinding_IDuplexTest"
          clientBaseAddress="http://localhost:8000/myClient/" >
            <security mode="None"/>
         </binding>
    </wsDualHttpBinding>
</bindings>
```

> [!WARNING]
> <span data-ttu-id="57c9a-132">Il modello duplex non rileva automaticamente quando un servizio o un client chiude il canale.</span><span class="sxs-lookup"><span data-stu-id="57c9a-132">The duplex model doesn't automatically detect when a service or client closes its channel.</span></span> <span data-ttu-id="57c9a-133">Quindi, se un client termina in modo imprevisto, per impostazione predefinita il servizio non riceve una notifica o se un servizio termina in modo imprevisto, il client non riceverà alcuna notifica.</span><span class="sxs-lookup"><span data-stu-id="57c9a-133">So if a client unexpectedly terminates, by default the service will not be notified, or if a service unexpectedly terminates, the client will not be notified.</span></span> <span data-ttu-id="57c9a-134">Se si utilizza un servizio disconnesso, <xref:System.ServiceModel.CommunicationException> viene generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="57c9a-134">If you use a service that is disconnected, the <xref:System.ServiceModel.CommunicationException> exception is raised.</span></span> <span data-ttu-id="57c9a-135">Client e servizi sono in grado di implementare il proprio protocollo per inviarsi vicendevolmente una notifica, se necessario.</span><span class="sxs-lookup"><span data-stu-id="57c9a-135">Clients and services can implement their own protocol to notify each other if they so choose.</span></span> <span data-ttu-id="57c9a-136">Per ulteriori informazioni sulla gestione degli errori, vedere la pagina relativa alla [gestione degli errori WCF](../wcf-error-handling.md).</span><span class="sxs-lookup"><span data-stu-id="57c9a-136">For more information on error handling, see [WCF Error Handling](../wcf-error-handling.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="57c9a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57c9a-137">See also</span></span>

- [<span data-ttu-id="57c9a-138">Duplex</span><span class="sxs-lookup"><span data-stu-id="57c9a-138">Duplex</span></span>](../samples/duplex.md)
- [<span data-ttu-id="57c9a-139">Specifica del comportamento in fase di esecuzione dei client</span><span class="sxs-lookup"><span data-stu-id="57c9a-139">Specifying Client Run-Time Behavior</span></span>](../specifying-client-run-time-behavior.md)
- [<span data-ttu-id="57c9a-140">Procedura: creare una channel factory e usarla per la creazione e la gestione di canali</span><span class="sxs-lookup"><span data-stu-id="57c9a-140">How to: Create a Channel Factory and Use it to Create and Manage Channels</span></span>](how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels.md)
