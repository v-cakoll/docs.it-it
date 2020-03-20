---
title: Correlazione duplex durevole
ms.date: 03/30/2017
ms.assetid: 8eb0e49a-6d3b-4f7e-a054-0d4febee2ffb
ms.openlocfilehash: bb73cef5190a0b146e713ef1adae24219dc2eed8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185165"
---
# <a name="durable-duplex-correlation"></a><span data-ttu-id="3a0a7-102">Correlazione duplex durevole</span><span class="sxs-lookup"><span data-stu-id="3a0a7-102">Durable Duplex Correlation</span></span>
<span data-ttu-id="3a0a7-103">La correlazione duplex durevole, nota anche come correlazione di callback, risulta utile se un servizio flusso di lavoro dispone del requisito adatto a inviare un callback al chiamante iniziale.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-103">Durable duplex correlation, also known as callback correlation, is useful when a workflow service has a requirement to send a callback to the initial caller.</span></span> <span data-ttu-id="3a0a7-104">A differenza del duplex WCF, il callback si può verificare in qualsiasi momento nel futuro e non è legato allo stesso canale o al canale di durata. L'unico requisito è costituito dal fatto che il chiamante dispone di un endpoint attivo in ascolto del messaggio di callback.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-104">Unlike WCF duplex, the callback can happen at any time in the future and is not tied to the same channel or the channel lifetime; the only requirement is that the caller have an active endpoint listening for the callback message.</span></span> <span data-ttu-id="3a0a7-105">In questo modo due servizi flusso di lavoro possono comunicare in una conversazione prolungata.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-105">This allows two workflow services to communicate in a long-running conversation.</span></span> <span data-ttu-id="3a0a7-106">In questo argomento vengono forniti cenni preliminari sulla correlazione duplex durevole.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-106">This topic provides an overview of durable duplex correlation.</span></span>  
  
## <a name="using-durable-duplex-correlation"></a><span data-ttu-id="3a0a7-107">Utilizzo della correlazione duplex durevole</span><span class="sxs-lookup"><span data-stu-id="3a0a7-107">Using Durable Duplex Correlation</span></span>  
 <span data-ttu-id="3a0a7-108">Per utilizzare la correlazione duplex durevole, i due servizi devono utilizzare un'associazione abilitata per il contesto che supporta operazioni bidirezionali, ad esempio <xref:System.ServiceModel.NetTcpContextBinding> o <xref:System.ServiceModel.WSHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-108">To use durable duplex correlation, the two services must use a context-enabled binding that supports two-way operations, such as <xref:System.ServiceModel.NetTcpContextBinding> or <xref:System.ServiceModel.WSHttpContextBinding>.</span></span> <span data-ttu-id="3a0a7-109">Il servizio chiamante registra un <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> con l'associazione desiderata sul client <xref:System.ServiceModel.Endpoint>.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-109">The calling service registers a <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> with the desired binding on their client <xref:System.ServiceModel.Endpoint>.</span></span> <span data-ttu-id="3a0a7-110">Il servizio ricevente riceve questi dati nella chiamata iniziale, quindi li utilizza sul proprio <xref:System.ServiceModel.Endpoint> nell'attività <xref:System.ServiceModel.Activities.Send> che effettua nuovamente la chiamata al servizio chiamante.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-110">The receiving service receives this data in the initial call and then uses it on its own <xref:System.ServiceModel.Endpoint> in the <xref:System.ServiceModel.Activities.Send> activity that makes the call back to the calling service.</span></span> <span data-ttu-id="3a0a7-111">In questo esempio, due servizi comunicano l'uno con l'altro.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-111">In this example, two services communicate with each other.</span></span> <span data-ttu-id="3a0a7-112">Il primo servizio richiama un metodo nel secondo servizio, quindi attende una risposta.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-112">The first service invokes a method on the second service and then waits for a reply.</span></span> <span data-ttu-id="3a0a7-113">Il secondo servizio conosce il nome del metodo di callback, ma l'endpoint del servizio che implementa questo metodo non è noto in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-113">The second service knows the name of the callback method, but the endpoint of the service that implements this method is not known at design time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a0a7-114">La correlazione duplex durevole può essere utilizzata soltanto quando <xref:System.ServiceModel.Channels.AddressingVersion> dell'endpoint è configurato con <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A>.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-114">Durable duplex can only be used when the <xref:System.ServiceModel.Channels.AddressingVersion> of the endpoint is configured with <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A>.</span></span> <span data-ttu-id="3a0a7-115">In caso contrario, <xref:System.InvalidOperationException> viene generata un'eccezione con il messaggio seguente: "Il messaggio contiene un'intestazione del contesto di callback con un riferimento all'endpoint per [AddressingVersion](http://schemas.xmlsoap.org/ws/2004/08/addressing).</span><span class="sxs-lookup"><span data-stu-id="3a0a7-115">If it is not, then an <xref:System.InvalidOperationException> exception is thrown with the following message: "The message contains a callback context header with an endpoint reference for [AddressingVersion](http://schemas.xmlsoap.org/ws/2004/08/addressing).</span></span> <span data-ttu-id="3a0a7-116">Il contesto di callback può essere trasmesso solo quando AddressingVersion è configurato con 'WSAddressing10'.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-116">Callback context can only be transmitted when the AddressingVersion is configured with 'WSAddressing10'.</span></span>
  
 <span data-ttu-id="3a0a7-117">Nell'esempio seguente viene ospitato un servizio flusso di lavoro che crea un <xref:System.ServiceModel.Endpoint> del callback mediante <xref:System.ServiceModel.WSHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-117">In the following example, a workflow service is hosted that creates a callback <xref:System.ServiceModel.Endpoint> using <xref:System.ServiceModel.WSHttpContextBinding>.</span></span>  
  
```csharp  
// Host WF Service 1.  
string baseAddress1 = "http://localhost:8080/Service1";  
WorkflowServiceHost host1 = new WorkflowServiceHost(GetWF1(), new Uri(baseAddress1));  
  
// Add the callback endpoint.  
WSHttpContextBinding Binding1 = new WSHttpContextBinding();  
host1.AddServiceEndpoint("ICallbackItemsReady", Binding1, "ItemsReady");  
  
// Add the service endpoint.  
host1.AddServiceEndpoint("IService1", Binding1, baseAddress1);  
  
// Open the first workflow service.  
host1.Open();  
Console.WriteLine("Service1 waiting at: {0}", baseAddress1);  
```  
  
 <span data-ttu-id="3a0a7-118">Il flusso di lavoro che implementa questo servizio flusso di lavoro inizializza la correlazione di callback con l'attività <xref:System.ServiceModel.Activities.Send> e fa riferimento a questo endpoint di callback dall'attività <xref:System.ServiceModel.Activities.Receive> correlata all'elemento <xref:System.ServiceModel.Activities.Send>.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-118">The workflow that implements this workflow service initializes the callback correlation with its <xref:System.ServiceModel.Activities.Send> activity, and references this callback endpoint from the <xref:System.ServiceModel.Activities.Receive> activity that correlates with the <xref:System.ServiceModel.Activities.Send>.</span></span> <span data-ttu-id="3a0a7-119">Nell'esempio seguente viene rappresentato il flusso di lavoro restituito dal metodo `GetWF1`.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-119">The following example represents the workflow that is returned from the `GetWF1` method.</span></span>  
  
```csharp  
Variable<CorrelationHandle> CallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IService1",  
    OperationName = "StartOrder"  
};  
  
Send GetItems = new Send  
{  
    CorrelationInitializers =
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = CallbackHandle  
        }  
    },  
    ServiceContractName = "IService2",  
    OperationName = "StartItems",  
    Endpoint = new Endpoint  
    {  
        AddressUri = new Uri("http://localhost:8081/Service2"),  
        Binding = new WSHttpContextBinding  
        {  
            ClientCallbackAddress = new Uri("http://localhost:8080/Service1/ItemsReady")
        }  
    }  
};  
  
Receive ItemsReady = new Receive  
{  
    ServiceContractName = "ICallbackItemsReady",  
    OperationName = "ItemsReady",  
    CorrelatesWith = CallbackHandle,  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        CallbackHandle  
    },  
    Activities =  
    {  
        StartOrder,  
        new WriteLine  
        {  
            Text = "WF1 - Started"  
        },  
        GetItems,  
        new WriteLine  
        {  
            Text = "WF1 - Request Submitted"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF1 - Items Received"  
        }  
     }  
};  
```  
  
 <span data-ttu-id="3a0a7-120">Il secondo servizio flusso di lavoro viene ospitato utilizzando un'associazione fornita dal sistema e basata sul contesto.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-120">The second workflow service is hosted using a system-provided, context-based binding.</span></span>  
  
```csharp  
// Host WF Service 2.  
string baseAddress2 = "http://localhost:8081/Service2";  
WorkflowServiceHost host2 = new WorkflowServiceHost(GetWF2(), new Uri(baseAddress2));  
  
// Add the service endpoint.  
WSHttpContextBinding Binding2 = new WSHttpContextBinding();  
host2.AddServiceEndpoint("IService2", Binding2, baseAddress2);  
  
// Open the second workflow service.  
host2.Open();  
Console.WriteLine("Service2 waiting at: {0}", baseAddress2);  
```  
  
 <span data-ttu-id="3a0a7-121">Il flusso di lavoro che implementa questo servizio flusso di lavoro inizia con un'attività <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-121">The workflow that implements this workflow service begins with a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="3a0a7-122">Questa attività di ricezione inizializza la correlazione di callback per questo servizio, ritarda per un periodo di tempo al fine di simulare un lavoro dall'esecuzione prolungata, quindi esegue una nuova chiamata nel primo servizio utilizzando il contesto di callback passato nella prima chiamata nel servizio.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-122">This receive activity initializes the callback correlation for this service, delays for a period of time to simulate long-running work, and then calls back into the first service using the callback context that was passed in the first call into the service.</span></span> <span data-ttu-id="3a0a7-123">Nell'esempio seguente viene rappresentato il flusso di lavoro restituito da una chiamata a `GetWF2`.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-123">The following example represents the workflow that is returned from a call to `GetWF2`.</span></span> <span data-ttu-id="3a0a7-124">L'attività <xref:System.ServiceModel.Activities.Send> dispone di un indirizzo del segnaposto `http://www.contoso.com`. L'indirizzo effettivo utilizzato al runtime coincide con l'indirizzo di callback fornito.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-124">Note that the <xref:System.ServiceModel.Activities.Send> activity has a placeholder address of `http://www.contoso.com`; the actual address used at runtime is the supplied callback address.</span></span>  
  
```csharp  
Variable<CorrelationHandle> ItemsCallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartItems = new Receive  
{  
    CorrelationInitializers =
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = ItemsCallbackHandle  
        }  
    },  
    CanCreateInstance = true,  
    ServiceContractName = "IService2",  
    OperationName = "StartItems"  
};  
  
Send ItemsReady = new Send  
{  
    CorrelatesWith = ItemsCallbackHandle,  
    Endpoint = new Endpoint  
    {  
        // The callback address on the binding is used  
        // instead of this placeholder address.  
        AddressUri = new Uri("http://www.contoso.com"),  
  
        Binding = new WSHttpContextBinding()  
    },  
    OperationName = "ItemsReady",  
    ServiceContractName = "ICallbackItemsReady"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        ItemsCallbackHandle  
    },  
    Activities =  
    {  
        StartItems,  
        new WriteLine  
        {  
            Text = "WF2 - Request Received"  
        },  
        new Delay  
        {  
            Duration = TimeSpan.FromMinutes(90)  
        },  
        new WriteLine  
        {  
            Text = "WF2 - Sending items"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF2 - Items sent"  
        }  
     }  
};  
```  
  
 <span data-ttu-id="3a0a7-125">Quando il metodo `StartOrder` viene richiamato nel primo flusso di lavoro, viene visualizzato l'output seguente che indica il flusso di esecuzione tramite i due flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-125">When the `StartOrder` method is invoked on the first workflow, the following output is displayed, which shows the flow of execution through the two workflows.</span></span>  
  
```output  
Service1 waiting at: http://localhost:8080/Service1  
Service2 waiting at: http://localhost:8081/Service2  
Press enter to exit.
WF1 - Started  
WF2 - Request Received  
WF1 - Request Submitted  
WF2 - Sending items  
WF2 - Items sent  
WF1 - Items Received  
```  
  
 <span data-ttu-id="3a0a7-126">In questo esempio, entrambi i flussi di lavoro gestiscono in modo esplicito la correlazione mediante un <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-126">In this example, both workflows explicitly manage correlation using a <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.</span></span> <span data-ttu-id="3a0a7-127">Poiché in questi flussi di lavoro di esempio era presente una sola correlazione, sarebbe stata sufficiente la gestione di <xref:System.ServiceModel.Activities.CorrelationHandle> predefinita.</span><span class="sxs-lookup"><span data-stu-id="3a0a7-127">Because there was only a single correlation in these sample workflows, the default <xref:System.ServiceModel.Activities.CorrelationHandle> management would have been sufficient.</span></span>
