---
title: Servizi duplex
ms.date: 05/09/2018
dev_langs:
- csharp
- vb
ms.assetid: 396b875a-d203-4ebe-a3a1-6a330d962e95
ms.openlocfilehash: 33cfcb765b93309d365a85e679107405a55a91f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61858039"
---
# <a name="duplex-services"></a><span data-ttu-id="15e88-102">Servizi duplex</span><span class="sxs-lookup"><span data-stu-id="15e88-102">Duplex Services</span></span>

<span data-ttu-id="15e88-103">Un contratto di servizio duplex è un modello di scambio di messaggi nel quale entrambi gli endpoint possono inviare messaggi l'uno all'altro in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="15e88-103">A duplex service contract is a message exchange pattern in which both endpoints can send messages to the other independently.</span></span> <span data-ttu-id="15e88-104">Un servizio duplex, pertanto, può inviare messaggi all'endpoint client, fornendo un comportamento simile a quello degli eventi.</span><span class="sxs-lookup"><span data-stu-id="15e88-104">A duplex service, therefore, can send messages back to the client endpoint, providing event-like behavior.</span></span> <span data-ttu-id="15e88-105">Una comunicazione duplex ha luogo quando un client si connette a un servizio e fornisce a quest'ultimo un canale utilizzabile per inviare messaggi al client.</span><span class="sxs-lookup"><span data-stu-id="15e88-105">Duplex communication occurs when a client connects to a service and provides the service with a channel on which the service can send messages back to the client.</span></span> <span data-ttu-id="15e88-106">Si noti che il comportamento simile a quello degli eventi di servizi duplex funziona solo all'interno di una sessione.</span><span class="sxs-lookup"><span data-stu-id="15e88-106">Note that the event-like behavior of duplex services only works within a session.</span></span>

<span data-ttu-id="15e88-107">Per creare un contratto duplex è necessario creare una coppia di interfacce.</span><span class="sxs-lookup"><span data-stu-id="15e88-107">To create a duplex contract you create a pair of interfaces.</span></span> <span data-ttu-id="15e88-108">La prima è l'interfaccia del contratto di servizio che descrive le operazioni che un client può richiamare.</span><span class="sxs-lookup"><span data-stu-id="15e88-108">The first is the service contract interface that describes the operations that a client can invoke.</span></span> <span data-ttu-id="15e88-109">Contratto di servizio è necessario specificare una *contratto di callback* nel <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="15e88-109">That service contract must specify a *callback contract* in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="15e88-110">Il contratto callback è l'interfaccia che definisce le operazioni che il servizio può chiamare sull'endpoint client.</span><span class="sxs-lookup"><span data-stu-id="15e88-110">The callback contract is the interface that defines the operations that the service can call on the client endpoint.</span></span> <span data-ttu-id="15e88-111">Un contratto duplex non richiede sessioni, sebbene le associazioni duplex fornite dal sistema le utilizzino.</span><span class="sxs-lookup"><span data-stu-id="15e88-111">A duplex contract does not require a session, although the system-provided duplex bindings make use of them.</span></span>

<span data-ttu-id="15e88-112">Di seguito è riportato un esempio di contratto duplex.</span><span class="sxs-lookup"><span data-stu-id="15e88-112">The following is an example of a duplex contract.</span></span>

[!code-csharp[c_DuplexServices#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#0)]
[!code-vb[c_DuplexServices#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#0)]

<span data-ttu-id="15e88-113">La classe `CalculatorService` implementa l'interfaccia `ICalculatorDuplex` primaria.</span><span class="sxs-lookup"><span data-stu-id="15e88-113">The `CalculatorService` class implements the primary `ICalculatorDuplex` interface.</span></span> <span data-ttu-id="15e88-114">Il servizio usa la modalità di istanza <xref:System.ServiceModel.InstanceContextMode.PerSession> per gestire il risultato per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="15e88-114">The service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the result for each session.</span></span> <span data-ttu-id="15e88-115">Una proprietà privata denominata `Callback` accede al canale callback al client.</span><span class="sxs-lookup"><span data-stu-id="15e88-115">A private property named `Callback` accesses the callback channel to the client.</span></span> <span data-ttu-id="15e88-116">Il servizio utilizza il callback per inviare i messaggi al client tramite l'interfaccia callback, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="15e88-116">The service uses the callback for sending messages back to the client through the callback interface, as shown in the following sample code.</span></span>

[!code-csharp[c_DuplexServices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#1)]
[!code-vb[c_DuplexServices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#1)]

<span data-ttu-id="15e88-117">Il client deve fornire una classe che implementi l'interfaccia callback del contratto duplex per ricevere messaggi dal servizio.</span><span class="sxs-lookup"><span data-stu-id="15e88-117">The client must provide a class that implements the callback interface of the duplex contract, for receiving messages from the service.</span></span> <span data-ttu-id="15e88-118">Nel codice di esempio seguente viene illustrata una classe `CallbackHandler` che implementa l'interfaccia `ICalculatorDuplexCallback`.</span><span class="sxs-lookup"><span data-stu-id="15e88-118">The following sample code shows a `CallbackHandler` class that implements the `ICalculatorDuplexCallback` interface.</span></span>

[!code-csharp[c_DuplexServices#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#2)]
[!code-vb[c_DuplexServices#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#2)]

<span data-ttu-id="15e88-119">Il client WCF che viene generato per un contratto duplex richiede una <xref:System.ServiceModel.InstanceContext> classe devono essere fornite dopo la costruzione.</span><span class="sxs-lookup"><span data-stu-id="15e88-119">The WCF client that is generated for a duplex contract requires a <xref:System.ServiceModel.InstanceContext> class to be provided upon construction.</span></span> <span data-ttu-id="15e88-120">Questa classe <xref:System.ServiceModel.InstanceContext> viene usata come sito per un oggetto che implementa l'interfaccia callback e gestisce i messaggi restituiti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="15e88-120">This <xref:System.ServiceModel.InstanceContext> class is used as the site for an object that implements the callback interface and handles messages that are sent back from the service.</span></span> <span data-ttu-id="15e88-121">Una classe <xref:System.ServiceModel.InstanceContext> viene costruita con un'istanza della classe `CallbackHandler`.</span><span class="sxs-lookup"><span data-stu-id="15e88-121">An <xref:System.ServiceModel.InstanceContext> class is constructed with an instance of the `CallbackHandler` class.</span></span> <span data-ttu-id="15e88-122">Questo oggetto gestisce i messaggi inviati dal servizio al client sull'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="15e88-122">This object handles messages sent from the service to the client on the callback interface.</span></span>

[!code-csharp[c_DuplexServices#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#3)]
[!code-vb[c_DuplexServices#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#3)]

<span data-ttu-id="15e88-123">La configurazione per il servizio deve essere impostata in modo da fornire un'associazione che supporta sia la comunicazione della sessione che la comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="15e88-123">The configuration for the service must be set up to provide a binding that supports both session communication and duplex communication.</span></span> <span data-ttu-id="15e88-124">L'elemento `wsDualHttpBinding` supporta la comunicazione della sessione e consente la comunicazione duplex fornendo connessioni HTTP doppie, una per ogni direzione.</span><span class="sxs-lookup"><span data-stu-id="15e88-124">The `wsDualHttpBinding` element supports session communication and allows duplex communication by providing dual HTTP connections, one for each direction.</span></span>

<span data-ttu-id="15e88-125">Sul client, è necessario configurare un indirizzo utilizzabile dal server per la connessione al client, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="15e88-125">On the client, you must configure an address that the server can use to connect to the client, as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="15e88-126">I client non duplex, la cui autenticazione mediante conversazione protetta non riesce, generano di norma un'eccezione <xref:System.ServiceModel.Security.MessageSecurityException>.</span><span class="sxs-lookup"><span data-stu-id="15e88-126">Non-duplex clients that fail to authenticate using a secure conversation typically throw a <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span> <span data-ttu-id="15e88-127">Se, tuttavia, un client duplex che usa una conversazione protetta non viene autenticato, riceve un'eccezione <xref:System.TimeoutException>.</span><span class="sxs-lookup"><span data-stu-id="15e88-127">However, if a duplex client that uses a secure conversation fails to authenticate, the client receives a <xref:System.TimeoutException> instead.</span></span>

<span data-ttu-id="15e88-128">Quando si crea un client/servizio utilizzando l'elemento `WSHttpBinding` e non si include l'endpoint di callback client, verrà restituito l'errore seguente.</span><span class="sxs-lookup"><span data-stu-id="15e88-128">If you create a client/service using the `WSHttpBinding` element and you do not include the client callback endpoint, you will receive the following error.</span></span>

```
HTTP could not register URL
htp://+:80/Temporary_Listen_Addresses/<guid> because TCP port 80 is being used by another application.
```

<span data-ttu-id="15e88-129">Esempio di codice seguente viene illustrato come specificare il client indirizzo dell'endpoint a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="15e88-129">The following sample code shows how to specify the client endpoint address programmatically.</span></span>

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

<span data-ttu-id="15e88-130">Nel codice di esempio seguente viene illustrato come specificare l'indirizzo endpoint client nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="15e88-130">The following sample code shows how to specify the client endpoint address in configuration.</span></span>

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
> <span data-ttu-id="15e88-131">Il modello duplex non consente di rilevare automaticamente il momento in cui un servizio o un client permette la chiusura del proprio canale.</span><span class="sxs-lookup"><span data-stu-id="15e88-131">The duplex model does not automatically detect when a service or client closes its channel.</span></span> <span data-ttu-id="15e88-132">Pertanto, se un client viene terminato in modo imprevisto, per impostazione predefinita, non sarà inviata alcuna notifica al servizio.</span><span class="sxs-lookup"><span data-stu-id="15e88-132">So if a client unexpectedly terminates, by default the service will not be notified, or if a client unexpectedly terminates, the service will not be notified.</span></span> <span data-ttu-id="15e88-133">Client e servizi sono in grado di implementare il proprio protocollo per inviarsi vicendevolmente una notifica, se necessario.</span><span class="sxs-lookup"><span data-stu-id="15e88-133">Clients and services can implement their own protocol to notify each other if they so choose.</span></span>

## <a name="see-also"></a><span data-ttu-id="15e88-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15e88-134">See also</span></span>

- [<span data-ttu-id="15e88-135">Duplex</span><span class="sxs-lookup"><span data-stu-id="15e88-135">Duplex</span></span>](../../../../docs/framework/wcf/samples/duplex.md)
- [<span data-ttu-id="15e88-136">Specifica del comportamento in fase di esecuzione dei client</span><span class="sxs-lookup"><span data-stu-id="15e88-136">Specifying Client Run-Time Behavior</span></span>](../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="15e88-137">Procedura: Creare una Channel Factory e usarlo per creare e gestire canali</span><span class="sxs-lookup"><span data-stu-id="15e88-137">How to: Create a Channel Factory and Use it to Create and Manage Channels</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels.md)
