---
title: DiscoveryClient e DynamicEndpoint
ms.date: 03/30/2017
ms.assetid: 7cd418f0-0eab-48d1-a493-7eb907867ec3
ms.openlocfilehash: 6144a3fb528e64fd55fa125b6254d415ec3e8b26
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599165"
---
# <a name="discoveryclient-and-dynamicendpoint"></a><span data-ttu-id="8a999-102">DiscoveryClient e DynamicEndpoint</span><span class="sxs-lookup"><span data-stu-id="8a999-102">DiscoveryClient and DynamicEndpoint</span></span>
<span data-ttu-id="8a999-103"><xref:System.ServiceModel.Discovery.DiscoveryClient> e <xref:System.ServiceModel.Discovery.DynamicEndpoint> sono due classi utilizzate sul lato client per cercare servizi.</span><span class="sxs-lookup"><span data-stu-id="8a999-103"><xref:System.ServiceModel.Discovery.DiscoveryClient> and <xref:System.ServiceModel.Discovery.DynamicEndpoint> are two classes used on the client side to search for services.</span></span> <span data-ttu-id="8a999-104"><xref:System.ServiceModel.Discovery.DiscoveryClient> fornisce un elenco di servizi che corrispondono a un set di criteri specifico e consente di connettersi ai servizi.</span><span class="sxs-lookup"><span data-stu-id="8a999-104"><xref:System.ServiceModel.Discovery.DiscoveryClient> provides you with a list of services that match a specific set of criteria and allows you to connect to the services.</span></span> <span data-ttu-id="8a999-105"><xref:System.ServiceModel.Discovery.DynamicEndpoint> esegue la stessa operazione e si connette inoltre a uno dei servizi trovati in modo automatico.</span><span class="sxs-lookup"><span data-stu-id="8a999-105"><xref:System.ServiceModel.Discovery.DynamicEndpoint> performs the same operation and in addition, automatically connects to one of the services that was found.</span></span> <span data-ttu-id="8a999-106">È possibile trasformare qualsiasi endpoint in un oggetto <xref:System.ServiceModel.Discovery.DynamicEndpoint>. È inoltre possibile aggiungere i criteri di ricerca alla configurazione, pertanto un oggetto <xref:System.ServiceModel.Discovery.DynamicEndpoint> è utile se l'individuazione è necessaria nella soluzione, ma non si desidera modificare la logica client: a tale scopo è sufficiente modificare gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="8a999-106">Any endpoint can be made into a <xref:System.ServiceModel.Discovery.DynamicEndpoint>, the search criteria can also be added in configuration, thus <xref:System.ServiceModel.Discovery.DynamicEndpoint> is useful when you need discovery in your solution but do not want to modify the client logic – you only need to modify the endpoints.</span></span> <span data-ttu-id="8a999-107">D'altro canto, è possibile utilizzare <xref:System.ServiceModel.Discovery.DiscoveryClient> per ottenere un livello di controllo più preciso sull'operazione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="8a999-107"><xref:System.ServiceModel.Discovery.DiscoveryClient> on the other hand can be used to gain finer control over your search operation.</span></span> <span data-ttu-id="8a999-108">Gli utilizzi e i vantaggi di ogni classe vengono indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="8a999-108">The uses and benefits of each are elaborated below.</span></span>  
  
## <a name="discoveryclient"></a><span data-ttu-id="8a999-109">DiscoveryClient</span><span class="sxs-lookup"><span data-stu-id="8a999-109">DiscoveryClient</span></span>  
 <span data-ttu-id="8a999-110"><xref:System.ServiceModel.Discovery.DiscoveryClient> definisce metodi Find sincroni e asincroni, eventi <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> e <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>.</span><span class="sxs-lookup"><span data-stu-id="8a999-110">The <xref:System.ServiceModel.Discovery.DiscoveryClient> defines synchronous and asynchronous Find methods, <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> and <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> events.</span></span>  <span data-ttu-id="8a999-111">Definisce inoltre metodi Resolve sincroni e asincroni, nonché un evento <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted>.</span><span class="sxs-lookup"><span data-stu-id="8a999-111">It also defines synchronous and asynchronous Resolve methods and a <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted> event.</span></span> <span data-ttu-id="8a999-112">Utilizzare i metodi <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> o <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> per cercare servizi.</span><span class="sxs-lookup"><span data-stu-id="8a999-112">Use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> or <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> methods to search for services.</span></span> <span data-ttu-id="8a999-113">Entrambi i metodi utilizzano un'istanza <xref:System.ServiceModel.Discovery.FindCriteria> che consente di specificare nomi di tipi di contratto, ambiti, numero massimo di risultati richiesti e regole di corrispondenza dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="8a999-113">Both of these methods take a <xref:System.ServiceModel.Discovery.FindCriteria> instance that allows you to specify contract type names, scopes, maximum number of results requested, and scope matching rules.</span></span> <span data-ttu-id="8a999-114">Gli eventi <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> e <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> possono essere utilizzati in caso di chiamata del metodo <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="8a999-114">The <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> and <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> events can be used when calling the <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> method.</span></span> <span data-ttu-id="8a999-115"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> viene generato ogni qualvolta <xref:System.ServiceModel.Discovery.DiscoveryClient> riceve una risposta da un servizio.</span><span class="sxs-lookup"><span data-stu-id="8a999-115"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> is fired whenever the <xref:System.ServiceModel.Discovery.DiscoveryClient> receives a response from a service.</span></span> <span data-ttu-id="8a999-116">Può essere utilizzato per visualizzare un indicatore di stato relativo all'operazione di ricerca,</span><span class="sxs-lookup"><span data-stu-id="8a999-116">It can be used to display a progress bar showing the progress of the find operation.</span></span> <span data-ttu-id="8a999-117">nonché per agire sulle risposte di ricerca nel momento in cui vengono ricevute.</span><span class="sxs-lookup"><span data-stu-id="8a999-117">It can also be used to act on find responses as they are received.</span></span> <span data-ttu-id="8a999-118">L'evento <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> si verifica nel momento in cui l'operazione di ricerca viene completato.</span><span class="sxs-lookup"><span data-stu-id="8a999-118">The <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is fired when the find operation completes.</span></span> <span data-ttu-id="8a999-119">Ciò potrebbe verificarsi poiché è stato ricevuto il numero massimo di risposte o se è trascorso il valore relativo a <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>.</span><span class="sxs-lookup"><span data-stu-id="8a999-119">This may happen because the maximum number of responses has been received or if the <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> has elapsed.</span></span> <span data-ttu-id="8a999-120">Se l'operazione di ricerca viene completata, i risultati vengono restituiti in un'istanza <xref:System.ServiceModel.Discovery.FindResponse>.</span><span class="sxs-lookup"><span data-stu-id="8a999-120">When the find operation completes the results are returned in a <xref:System.ServiceModel.Discovery.FindResponse> instance.</span></span> <span data-ttu-id="8a999-121"><xref:System.ServiceModel.Discovery.FindResponse> contiene una raccolta di <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> che contiene gli indirizzi, i nomi dei tipi di contratto, le estensioni, gli URI di ascolto e gli ambiti dei servizi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="8a999-121">The <xref:System.ServiceModel.Discovery.FindResponse> contains a collection of <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> which contains the addresses, contract type names, extensions, listen URIs, and scopes of the matching services.</span></span> <span data-ttu-id="8a999-122">È quindi possibile utilizzare queste informazioni per connettersi e chiamare uno dei servizi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="8a999-122">You can then use this information to connect to and call one of the matching services.</span></span> <span data-ttu-id="8a999-123">Nell'esempio seguente viene illustrato come chiamare il metodo System. ServiceModel. Discovery. DiscoveryClient. Find (System. ServiceModel. Discovery. FindCriteria) e come utilizzare i metadati restituiti per chiamare il servizio trovato.</span><span class="sxs-lookup"><span data-stu-id="8a999-123">The following example shows how to call the System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria) method and use the returned metadata to call the found service.</span></span> <span data-ttu-id="8a999-124">Un vantaggio dell'uso di <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> è la possibilità di memorizzare nella cache l'elenco degli endpoint trovati e di usarli in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="8a999-124">A benefit of using <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> is that you can cache the list of endpoints you’ve found and use them at a later time.</span></span> <span data-ttu-id="8a999-125">Con questa cache è possibile compilare una logica personalizzata per gestire le varie condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="8a999-125">With this cache, you can build custom logic to handle various failure conditions.</span></span>  
  
```csharp
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
FindCriteria criteria = new FindCriteria(typeof(ICalculatorService));  
FindResponse fr = dc.Find(criteria);  
  
if (fr.Endpoints.Count > 0)  
{  
   EndpointAddress ep = fr.Endpoints[0].Address;  
   CalculatorServiceClient client = new CalculatorServiceClient();  
  
    // Connect to the discovered service endpoint  
   client.Endpoint.Address = endpointAddress;  
   Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
   double value1 = 100.00D;  
   double value2 = 15.99D;  
  
   // Call the Add service operation.  
   double result = client.Add(value1, value2);  
   Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
}  
else  
   Console.WriteLine("No matching endpoints found");  
```  
  
 <span data-ttu-id="8a999-126">Nell'esempio seguente viene mostrato come eseguire in modo asincrono un'operazione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="8a999-126">The following example shows how to perform a find operation asynchronously.</span></span>  
  
```csharp
static void FindServiceAsync()  
{  
   DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());
   dc.FindCompleted += new EventHandler<FindCompletedEventArgs>( discoveryClient_FindCompleted);  
   dc.FindProgressChanged += new EventHandler<FindProgressChangedEventArgs>(discoveryClient_FindProgressChanged);  
   dc.FindAsync(new FindCriteria(typeof(ICalculatorService)));
}
static void discoveryClient_FindProgressChanged(object sender, FindProgressChangedEventArgs e)  
{  
   Console.WriteLine("Found service at: " + e.EndpointDiscoveryMetadata.Address  
}
  
static void discoveryClient_FindCompleted(object sender, FindCompletedEventArgs e)  
{
      if (e.Result.Endpoints.Count > 0)  
            {  
                EndpointAddress ep = e.Result.Endpoints[0].Address;  
                CalculatorServiceClient client = new CalculatorServiceClient();  
  
                // Connect to the discovered service endpoint  
                client.Endpoint.Address = ep;  
                Console.WriteLine("Invoking CalculatorService at {0}", ep);  
  
                double value1 = 100.00D;  
                double value2 = 15.99D;  
  
                double result = client.Add(value1, value2);  
                Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
            }  
            else  
                Console.WriteLine("No matching endpoints found");  
  
        }  
```
  
 <span data-ttu-id="8a999-127">Utilizzare i metodi <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> e <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29> per individuare un servizio in base al relativo indirizzo endpoint.</span><span class="sxs-lookup"><span data-stu-id="8a999-127">Use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> and <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29> methods to locate a service based on its endpoint address.</span></span> <span data-ttu-id="8a999-128">Ciò risulta utile nel caso in cui l'indirizzo endpoint non è indirizzabile alla rete.</span><span class="sxs-lookup"><span data-stu-id="8a999-128">This is useful when the endpoint address is not network addressable.</span></span> <span data-ttu-id="8a999-129">I metodi Resolve utilizzano un'istanza di <xref:System.ServiceModel.Discovery.ResolveCriteria> che consente di specificare l'indirizzo endpoint del servizio in fase di risoluzione, la durata massima dell'operazione di risoluzione e un set di estensioni.</span><span class="sxs-lookup"><span data-stu-id="8a999-129">The Resolve methods take an instance of <xref:System.ServiceModel.Discovery.ResolveCriteria> which allows you to specify the endpoint address of the service you are resolving, the maximum duration of the resolve operation, and a set of extensions.</span></span> <span data-ttu-id="8a999-130">Nell'esempio riportato di seguito viene mostrato come utilizzare il metodo <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> per risolvere un servizio.</span><span class="sxs-lookup"><span data-stu-id="8a999-130">The following example shows how to use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> method to resolve a service.</span></span>  
  
```csharp  
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
ResolveCriteria criteria = new ResolveCriteria(endpointAddress);  
ResolveResponse response = dc.Resolve(criteria);  
EndpointAddress newEp = response.EndpointDiscoveryMetadata.Address;  
```  
  
## <a name="dynamicendpoint"></a><span data-ttu-id="8a999-131">DynamicEndpoint</span><span class="sxs-lookup"><span data-stu-id="8a999-131">DynamicEndpoint</span></span>  
 <span data-ttu-id="8a999-132"><xref:System.ServiceModel.Discovery.DynamicEndpoint>è un endpoint standard (per altre informazioni, vedere [endpoint standard](standard-endpoints.md)) che esegue l'individuazione e seleziona automaticamente un servizio corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8a999-132"><xref:System.ServiceModel.Discovery.DynamicEndpoint> is a standard endpoint (For more information, see [Standard Endpoints](standard-endpoints.md)) which performs discovery and automatically selects a matching service.</span></span> <span data-ttu-id="8a999-133">È sufficiente creare un <xref:System.ServiceModel.Discovery.DynamicEndpoint> che passa il contratto da cercare e l'associazione da utilizzare e passare l'istanza <xref:System.ServiceModel.Discovery.DynamicEndpoint> al client WCF.</span><span class="sxs-lookup"><span data-stu-id="8a999-133">Just create a <xref:System.ServiceModel.Discovery.DynamicEndpoint> passing in the contract to search for and the binding to use and pass the <xref:System.ServiceModel.Discovery.DynamicEndpoint> instance to the WCF client.</span></span> <span data-ttu-id="8a999-134">Nell'esempio seguente viene illustrato come creare e utilizzare un <xref:System.ServiceModel.Discovery.DynamicEndpoint> per chiamare il servizio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="8a999-134">The following example shows how to create and use a <xref:System.ServiceModel.Discovery.DynamicEndpoint> to call the calculator service.</span></span> <span data-ttu-id="8a999-135">L'individuazione viene eseguita a ogni apertura del client.</span><span class="sxs-lookup"><span data-stu-id="8a999-135">The discovery is performed every time the client is opened.</span></span> <span data-ttu-id="8a999-136">Qualsiasi endpoint definito nella configurazione può anche essere trasformato in un oggetto <xref:System.ServiceModel.Discovery.DynamicEndpoint> aggiungendo l' `kind ="dynamicEndpoint"` attributo all'elemento di configurazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="8a999-136">Any endpoint defined in configuration can also be turned into a <xref:System.ServiceModel.Discovery.DynamicEndpoint> by adding the `kind ="dynamicEndpoint"` attribute to the endpoint configuration element.</span></span>  
  
```csharp  
DynamicEndpoint dynamicEndpoint = new DynamicEndpoint(ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());  
CalculatorServiceClient client = new CalculatorServiceClient(dynamicEndpoint);  
  
Console.WriteLine("Invoking CalculatorService");  
Console.WriteLine();  
  
double value1 = 100.00D;  
double value2 = 15.99D;  
  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a999-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a999-137">See also</span></span>

- [<span data-ttu-id="8a999-138">Individuazione con ambiti</span><span class="sxs-lookup"><span data-stu-id="8a999-138">Discovery with Scopes</span></span>](../samples/discovery-with-scopes-sample.md)
- [<span data-ttu-id="8a999-139">Basic</span><span class="sxs-lookup"><span data-stu-id="8a999-139">Basic</span></span>](../samples/basic-sample.md)
