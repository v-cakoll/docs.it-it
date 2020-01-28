---
title: Introduzione al routing
ms.date: 03/30/2017
ms.assetid: bf6ceb38-6622-433b-9ee7-f79bc93497a1
ms.openlocfilehash: 8ce98aab2ed14401fa7c2cbf43eb92a633fa96b0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746475"
---
# <a name="routing-introduction"></a><span data-ttu-id="7f88b-102">Introduzione al routing</span><span class="sxs-lookup"><span data-stu-id="7f88b-102">Routing Introduction</span></span>

<span data-ttu-id="7f88b-103">Il servizio di routing fornisce un intermediario SOAP di collegamento generico in grado di indirizzare i messaggi in base al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="7f88b-103">The Routing Service provides a generic pluggable SOAP intermediary that is capable of routing messages based on message content.</span></span> <span data-ttu-id="7f88b-104">Il servizio di routing consente di creare logica di routing complessa per l'implementazione di scenari quali l'aggregazione dei servizi, il controllo delle versioni dei servizi, il routing prioritario e il routing multicast.</span><span class="sxs-lookup"><span data-stu-id="7f88b-104">With the Routing Service, you can create complex routing logic that allows you to implement scenarios such as service aggregation, service versioning, priority routing, and multicast routing.</span></span> <span data-ttu-id="7f88b-105">Il servizio di routing offre inoltre funzionalità di gestione degli errori che consentono di configurare elenchi di endpoint di backup ai quali vengono inviati i messaggi se si verifica un errore di invio all'endpoint di destinazione primario.</span><span class="sxs-lookup"><span data-stu-id="7f88b-105">The Routing Service also provides error handling that allows you to set up lists of backup endpoints, to which messages are sent if a failure occurs when sending to the primary destination endpoint.</span></span>

<span data-ttu-id="7f88b-106">Questo argomento è destinato a coloro i quali non hanno familiarità con il servizio di routing e ne illustra la configurazione di base e l'hosting.</span><span class="sxs-lookup"><span data-stu-id="7f88b-106">This topic is intended for those new to the Routing Service and covers basic configuration and hosting of the Routing Service.</span></span>

## <a name="configuration"></a><span data-ttu-id="7f88b-107">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="7f88b-107">Configuration</span></span>

<span data-ttu-id="7f88b-108">Il servizio di routing viene implementato come servizio WCF che espone uno o più endpoint servizio i quali ricevono i messaggi dalle applicazioni client e li indirizzano a uno o più endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-108">The Routing Service is implemented as a WCF service that exposes one or more service endpoints that receive messages from client applications and route the messages to one or more destination endpoints.</span></span> <span data-ttu-id="7f88b-109">Il servizio include un elemento <xref:System.ServiceModel.Routing.RoutingBehavior> che viene applicato agli endpoint servizio esposti.</span><span class="sxs-lookup"><span data-stu-id="7f88b-109">The service provides a <xref:System.ServiceModel.Routing.RoutingBehavior>, which is applied to the service endpoints exposed by the service.</span></span> <span data-ttu-id="7f88b-110">Questo comportamento viene usato per configurare diversi aspetti del funzionamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-110">This behavior is used to configure various aspects of how the service operates.</span></span> <span data-ttu-id="7f88b-111">Per semplificare la configurazione quando si usa un file di configurazione, i parametri vengono specificati in **RoutingBehavior**.</span><span class="sxs-lookup"><span data-stu-id="7f88b-111">For ease of configuration when using a configuration file, the parameters are specified on the **RoutingBehavior**.</span></span> <span data-ttu-id="7f88b-112">Negli scenari basati sul codice, questi parametri vengono specificati come parte di un oggetto <xref:System.ServiceModel.Routing.RoutingConfiguration>, che può quindi essere passato a un **RoutingBehavior**.</span><span class="sxs-lookup"><span data-stu-id="7f88b-112">In code-based scenarios, these parameters would be specified as part of a <xref:System.ServiceModel.Routing.RoutingConfiguration> object, which can then be passed to a **RoutingBehavior**.</span></span>

<span data-ttu-id="7f88b-113">Inizialmente, questo comportamento aggiunge agli endpoint client <xref:System.ServiceModel.Routing.SoapProcessingBehavior>, il quale è usato per eseguire l'elaborazione SOAP dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="7f88b-113">When starting, this behavior adds the <xref:System.ServiceModel.Routing.SoapProcessingBehavior>, which is used to perform SOAP processing of messages, to the client endpoints.</span></span> <span data-ttu-id="7f88b-114">Ciò consente al servizio di routing di trasmettere messaggi agli endpoint che richiedono un oggetto **MessageVersion** diverso rispetto all'endpoint su cui è stato ricevuto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-114">This allows the Routing Service to transmit messages to endpoints that require a different **MessageVersion** than the endpoint the message was received over.</span></span> <span data-ttu-id="7f88b-115">**RoutingBehavior** registra inoltre un'estensione del servizio, la <xref:System.ServiceModel.Routing.RoutingExtension>, che fornisce un punto di accessibilità per la modifica della configurazione del servizio di routing in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-115">The **RoutingBehavior** also registers a service extension, the <xref:System.ServiceModel.Routing.RoutingExtension>, which provides an accessibility point for modifying the Routing Service configuration at run time.</span></span>

<span data-ttu-id="7f88b-116">La classe **RoutingConfiguration** fornisce un mezzo coerente per la configurazione e l'aggiornamento della configurazione del servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="7f88b-116">The **RoutingConfiguration** class provides a consistent means of configuring and updating the configuration of the Routing Service.</span></span>  <span data-ttu-id="7f88b-117">Contiene i parametri che fungono da impostazioni per il servizio di routing e viene usato per configurare il **RoutingBehavior** all'avvio del servizio o viene passato a **RoutingExtension** per modificare la configurazione del routing in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-117">It contains parameters that act as the settings for the Routing Service and is used to configure the **RoutingBehavior** when the service starts, or is passed to the **RoutingExtension** to modify routing configuration at run time.</span></span>

<span data-ttu-id="7f88b-118">La logica di routing usata per indirizzare i messaggi in base al contenuto viene definita raggruppando più oggetti <xref:System.ServiceModel.Dispatcher.MessageFilter> in tabelle di filtri (oggetti <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>).</span><span class="sxs-lookup"><span data-stu-id="7f88b-118">The routing logic used to perform content-based routing of messages is defined by grouping multiple <xref:System.ServiceModel.Dispatcher.MessageFilter> objects together into filter tables (<xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> objects).</span></span> <span data-ttu-id="7f88b-119">I messaggi in arrivo vengono valutati in base ai filtri messaggi contenuti nella tabella dei filtri e per ogni **MessageFilter** che corrisponde al messaggio, che viene inviato a un endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-119">Incoming messages are evaluated against the message filters contained in the filter table, and for each **MessageFilter** that matches the message, forwarded to a destination endpoint.</span></span> <span data-ttu-id="7f88b-120">La tabella dei filtri da utilizzare per il routing dei messaggi viene specificata utilizzando **RoutingBehavior** nella configurazione o tramite codice tramite l'oggetto **RoutingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7f88b-120">The filter table that should be used to route messages is specified by using either the **RoutingBehavior** in configuration or through code by using the **RoutingConfiguration** object.</span></span>

### <a name="defining-endpoints"></a><span data-ttu-id="7f88b-121">Definizione di endpoint</span><span class="sxs-lookup"><span data-stu-id="7f88b-121">Defining Endpoints</span></span>

<span data-ttu-id="7f88b-122">Sebbene possa sembrare opportuno iniziare la configurazione definendo la logica di routing che verrà usata, è consigliabile che il primo passaggio consista nel determinare la forma degli endpoint a cui verranno indirizzati i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7f88b-122">While it may seem that you should start your configuration by defining the routing logic you will use, your first step should actually be to determine the shape of the endpoints you will be routing messages to.</span></span> <span data-ttu-id="7f88b-123">Il servizio di routing usa contratti che definiscono la forma dei canali usati per ricevere e inviare messaggi, pertanto la forma del canale di input deve corrispondere a quella del canale di output.</span><span class="sxs-lookup"><span data-stu-id="7f88b-123">The Routing Service uses contracts that define the shape of the channels used to receive and send messages, and therefore the shape of the input channel must match that of the output channel.</span></span>  <span data-ttu-id="7f88b-124">Se ad esempio si esegue il routing a endpoint che usano la forma del canale di tipo request/reply, è necessario usare un contratto compatibile negli endpoint in ingresso, ad esempio <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span><span class="sxs-lookup"><span data-stu-id="7f88b-124">For example, if you are routing to endpoints that use the request-reply channel shape, then you must use a compatible contract on the inbound endpoints, such as the <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span></span>

<span data-ttu-id="7f88b-125">Ciò significa che se gli endpoint di destinazione usano contratti con più modelli di comunicazione (ad esempio una combinazione di operazioni unidirezionali e bidirezionali), non è possibile creare un singolo endpoint servizio in grado di ricevere e indirizzare i messaggi a tutti.</span><span class="sxs-lookup"><span data-stu-id="7f88b-125">This means that if your destination endpoints use contracts with multiple communication patterns (such as mixing one-way and two-way operations,) you cannot create a single service endpoint that can receive and route messages to all of them.</span></span> <span data-ttu-id="7f88b-126">È necessario determinare quali endpoint dispongono di forme compatibili e definire uno o più endpoint servizio che verranno usati per ricevere i messaggi da indirizzare agli endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-126">You must determine which endpoints have compatible shapes and define one or more service endpoints that will be used to receive messages to be routed to the destination endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="7f88b-127">Quando si usano contratti che specificano più modelli di comunicazione (ad esempio una combinazione di operazioni unidirezionali e bidirezionali), una soluzione alternativa è rappresentata dall'uso di un contratto di tipo duplex nel servizio di routing, ad esempio <xref:System.ServiceModel.Routing.IDuplexSessionRouter>.</span><span class="sxs-lookup"><span data-stu-id="7f88b-127">When working with contracts that specify multiple communication patterns (such as a mix of one-way and two-way operations,) a workaround is to use a duplex contract at the Routing Service such as <xref:System.ServiceModel.Routing.IDuplexSessionRouter>.</span></span> <span data-ttu-id="7f88b-128">Ciò implica tuttavia che l'associazione deve supportare la comunicazione duplex, il che potrebbe non essere possibile per tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="7f88b-128">However this means that the binding must be capable of duplex communication, which may not be possible for all scenarios.</span></span> <span data-ttu-id="7f88b-129">Negli scenari in cui questa soluzione non è possibile, può risultare necessario eseguire il factoring della comunicazione in più endpoint oppure modificare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-129">In scenarios where this is not possible, factoring the communication into multiple endpoints or modifying the application may be necessary.</span></span>

<span data-ttu-id="7f88b-130">Per ulteriori informazioni sui contratti di routing, vedere [routing dei contratti](routing-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="7f88b-130">For more information about routing contracts, see [Routing Contracts](routing-contracts.md).</span></span>

<span data-ttu-id="7f88b-131">Dopo aver definito l'endpoint del servizio, è possibile usare **RoutingBehavior** per associare un **RoutingConfiguration** specifico all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="7f88b-131">After the service endpoint is defined, you can use the **RoutingBehavior** to associate a specific **RoutingConfiguration** with the endpoint.</span></span> <span data-ttu-id="7f88b-132">Quando si configura il servizio di routing utilizzando un file di configurazione, **RoutingBehavior** viene utilizzato per specificare la tabella dei filtri che contiene la logica di routing utilizzata per elaborare i messaggi ricevuti sull'endpoint.</span><span class="sxs-lookup"><span data-stu-id="7f88b-132">When configuring the Routing Service by using a configuration file, the **RoutingBehavior** is used to specify the filter table that contains the routing logic used to process messages received on this endpoint.</span></span> <span data-ttu-id="7f88b-133">Se si configura il servizio di routing a livello di codice, è possibile specificare la tabella dei filtri utilizzando **RoutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="7f88b-133">If you are configuring the Routing Service programmatically you can specify the filter table by using the **RoutingConfiguration**.</span></span>

<span data-ttu-id="7f88b-134">Nell'esempio seguente gli endpoint servizio e client usati dal servizio di routing sono definiti sia a livello di codice sia tramite un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-134">The following example defines the service and client endpoints that are used by the Routing Service both programmatically and by using a configuration file.</span></span>

```xml
<services>
  <!--ROUTING SERVICE -->
  <service behaviorConfiguration="routingData"
            name="System.ServiceModel.Routing.RoutingService">
    <host>
      <baseAddresses>
        <add baseAddress="http://localhost:8000/routingservice/router"/>
      </baseAddresses>
    </host>
    <!-- Define the service endpoints that are receive messages -->
    <endpoint address=""
              binding="wsHttpBinding"
              name="reqReplyEndpoint"
              contract="System.ServiceModel.Routing.IRequestReplyRouter" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="routingData">
      <serviceMetadata httpGetEnabled="True"/>
      <!-- Add the RoutingBehavior and specify the Routing Table to use -->
      <routing filterTableName="routingTable1" />
    </behavior>
  </serviceBehaviors>
</behaviors>
<client>
<!-- Define the client endpoint(s) to route messages to -->
  <endpoint name="CalculatorService"
            address="http://localhost:8000/servicemodelsamples/service"
            binding="wsHttpBinding" contract="*" />
</client>
```

```csharp
//set up some communication defaults
string clientAddress = "http://localhost:8000/servicemodelsamples/service";
string routerAddress = "http://localhost:8000/routingservice/router";
Binding routerBinding = new WSHttpBinding();
Binding clientBinding = new WSHttpBinding();
//add the endpoint the router uses to receive messages
serviceHost.AddServiceEndpoint(
     typeof(IRequestReplyRouter),
     routerBinding,
     routerAddress);
//create the client endpoint the router routes messages to
ContractDescription contract = ContractDescription.GetContract(
     typeof(IRequestReplyRouter));
ServiceEndpoint client = new ServiceEndpoint(
     contract,
     clientBinding,
     new EndpointAddress(clientAddress));
//create a new routing configuration object
RoutingConfiguration rc = new RoutingConfiguration();
….
rc.FilterTable.Add(new MatchAllMessageFilter(), endpointList);
//attach the behavior to the service host
serviceHost.Description.Behaviors.Add(
     new RoutingBehavior(rc));
```

<span data-ttu-id="7f88b-135">In questo esempio il servizio di routing viene configurato per esporre un singolo endpoint con un indirizzo di `http://localhost:8000/routingservice/router`, che viene utilizzato per ricevere i messaggi da indirizzare.</span><span class="sxs-lookup"><span data-stu-id="7f88b-135">This example configures the Routing Service to expose a single endpoint with an address of `http://localhost:8000/routingservice/router`, which is used to receive messages to be routed.</span></span> <span data-ttu-id="7f88b-136">Poiché i messaggi vengono indirizzati agli endpoint di tipo request/reply, l'endpoint servizio usa il contratto <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span><span class="sxs-lookup"><span data-stu-id="7f88b-136">Because the messages are routed to request-reply endpoints, the service endpoint uses the <xref:System.ServiceModel.Routing.IRequestReplyRouter> contract.</span></span> <span data-ttu-id="7f88b-137">Questa configurazione definisce anche un endpoint client singolo di `http://localhost:8000/servicemodelsample/service` a cui vengono indirizzati i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7f88b-137">This configuration also defines a single client endpoint of `http://localhost:8000/servicemodelsample/service` that messages are routed to.</span></span> <span data-ttu-id="7f88b-138">La tabella dei filtri (non mostrata) denominata "routingTable1" contiene la logica di routing usata per indirizzare i messaggi ed è associata all'endpoint del servizio usando **RoutingBehavior** (per un file di configurazione) o **RoutingConfiguration** (per la configurazione a livello di codice).</span><span class="sxs-lookup"><span data-stu-id="7f88b-138">The filter table (not shown) named "routingTable1" contains the routing logic used to route messages, and is associated with the service endpoint by using the **RoutingBehavior** (for a configuration file) or **RoutingConfiguration** (for programmatic configuration).</span></span>

### <a name="routing-logic"></a><span data-ttu-id="7f88b-139">Logica di routing</span><span class="sxs-lookup"><span data-stu-id="7f88b-139">Routing Logic</span></span>

<span data-ttu-id="7f88b-140">Per definire la logica di routing usata per indirizzare i messaggi, è necessario stabilire su quali dati contenuti nei messaggi in entrata è possibile intervenire in modo univoco.</span><span class="sxs-lookup"><span data-stu-id="7f88b-140">To define the routing logic used to route messages, you must determine what data contained within the incoming messages can be uniquely acted upon.</span></span> <span data-ttu-id="7f88b-141">Se ad esempio tutti gli endpoint di destinazione del routing condividono le stesse azioni SOAP, il valore dell'elemento Action all'interno del messaggio non rappresenta un indicatore utile dell'endpoint specifico a cui deve essere indirizzato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-141">For example, if all the destination endpoints you are routing to share the same SOAP Actions, the value of the Action contained within the message is not a good indicator of which specific endpoint the message should be routed to.</span></span> <span data-ttu-id="7f88b-142">Se è necessario indirizzare i messaggi in modo univoco a un endpoint specifico, è consigliabile applicare filtri in base a dati che identificano in modo univoco l'endpoint di destinazione a cui il messaggio viene indirizzato.</span><span class="sxs-lookup"><span data-stu-id="7f88b-142">If you must uniquely route messages to one specific endpoint, you should filter upon data that uniquely identifies the destination endpoint that the message is routed to.</span></span>

<span data-ttu-id="7f88b-143">Il servizio di routing fornisce diverse implementazioni di **MessageFilter** che controllano valori specifici all'interno del messaggio, ad esempio l'indirizzo, l'azione, il nome dell'endpoint o persino una query XPath.</span><span class="sxs-lookup"><span data-stu-id="7f88b-143">The Routing Service provides several **MessageFilter** implementations that inspect specific values within the message, such as the address, action, endpoint name, or even an XPath query.</span></span> <span data-ttu-id="7f88b-144">Se nessuna di queste implementazioni soddisfa le proprie esigenze, è possibile creare un'implementazione personalizzata di **MessageFilter** .</span><span class="sxs-lookup"><span data-stu-id="7f88b-144">If none of these implementations meet your needs you can create a custom **MessageFilter** implementation.</span></span> <span data-ttu-id="7f88b-145">Per ulteriori informazioni sui filtri messaggi e un confronto delle implementazioni utilizzate dal servizio di routing, vedere [filtri messaggi](message-filters.md) e [scelta di un filtro](choosing-a-filter.md).</span><span class="sxs-lookup"><span data-stu-id="7f88b-145">For more information about message filters and a comparison of the implementations used by the Routing Service, see [Message Filters](message-filters.md) and [Choosing a Filter](choosing-a-filter.md).</span></span>

<span data-ttu-id="7f88b-146">Più filtri messaggi sono organizzati insieme in tabelle dei filtri, che associano ogni **MessageFilter** a un endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-146">Multiple message filters are organized together into filter tables, which associate each **MessageFilter** with a destination endpoint.</span></span> <span data-ttu-id="7f88b-147">Facoltativamente, è inoltre possibile usare la tabella dei filtri per specificare un elenco di endpoint di backup a cui il servizio di routing tenterà di inviare il messaggio qualora si verifichi un errore di trasmissione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-147">Optionally, the filter table can also be used to specify a list of back-up endpoints that the Routing Service will attempt to send the message to in the event of a transmission failure.</span></span>

<span data-ttu-id="7f88b-148">Per impostazione predefinita, tutti i filtri messaggi all'interno di una tabella vengono valutati contemporaneamente. È tuttavia possibile specificare un oggetto <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A> che impone la valutazione dei filtri messaggi in un ordine specifico.</span><span class="sxs-lookup"><span data-stu-id="7f88b-148">By default all message filters within a filter table are evaluated simultaneously; however, you can specify a <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A> that causes the message filters to be evaluated in a specific order.</span></span> <span data-ttu-id="7f88b-149">Tutte le voci con priorità massima vengono valutati per primi, mentre i filtri dei messaggi di priorità inferiore non vengono valutati se viene individuata una corrispondenza a un livello di priorità superiore.</span><span class="sxs-lookup"><span data-stu-id="7f88b-149">All entries with the highest priority are evaluated first, and message filters of lower priorities are not evaluated if a match is found at a higher priority level.</span></span> <span data-ttu-id="7f88b-150">Per ulteriori informazioni sulle tabelle dei filtri, vedere [filtri messaggi](message-filters.md).</span><span class="sxs-lookup"><span data-stu-id="7f88b-150">For more information about filter tables, see [Message Filters](message-filters.md).</span></span>

<span data-ttu-id="7f88b-151">Negli esempi seguenti viene usato <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>, il quale restituisce `true` per tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7f88b-151">The following examples use the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>, which evaluates to `true` for all messages.</span></span> <span data-ttu-id="7f88b-152">Questo **MessageFilter** viene aggiunto alla tabella dei filtri "routingTable1", che associa **MessageFilter** all'endpoint client denominato "CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="7f88b-152">This **MessageFilter** is added to the "routingTable1" filter table, which associates the **MessageFilter** with the client endpoint named "CalculatorService".</span></span> <span data-ttu-id="7f88b-153">**RoutingBehavior** specifica quindi che questa tabella deve essere utilizzata per indirizzare i messaggi elaborati dall'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-153">The **RoutingBehavior** then specifies that this table should be used to route messages processed by the service endpoint.</span></span>

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name="routingData">
      <serviceMetadata httpGetEnabled="True"/>
      <!-- Add the RoutingBehavior and specify the Routing Table to use -->
      <routing filterTableName="routingTable1" />
    </behavior>
  </serviceBehaviors>
</behaviors>
<!--ROUTING SECTION -->
<routing>
  <filters>
    <filter name="MatchAllFilter1" filterType="MatchAll" />
  </filters>
  <filterTables>
    <table name="routingTable1">
      <filters>
        <add filterName="MatchAllFilter1" endpointName="CalculatorService" />
      </filters>
    </table>
  </filterTables>
</routing>
```

```csharp
//create a new routing configuration object
RoutingConfiguration rc = new RoutingConfiguration();
//create the endpoint list that contains the endpoints to route to
//in this case we have only one
List<ServiceEndpoint> endpointList = new List<ServiceEndpoint>();
endpointList.Add(client);
//add a MatchAll filter to the Router's filter table
//map it to the endpoint list defined earlier
//when a message matches this filter, it is sent to the endpoint contained in the list
rc.FilterTable.Add(new MatchAllMessageFilter(), endpointList);
```

> [!NOTE]
> <span data-ttu-id="7f88b-154">Per impostazione predefinita, il servizio di routing valuta solo le intestazioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-154">By default, the Routing Service only evaluates the headers of the message.</span></span> <span data-ttu-id="7f88b-155">Per consentire ai filtri di accedere al corpo del messaggio, è necessario impostare <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="7f88b-155">To allow the filters to access the message body, you must set <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> to `false`.</span></span>

<span data-ttu-id="7f88b-156">**Multicast**</span><span class="sxs-lookup"><span data-stu-id="7f88b-156">**Multicast**</span></span>

<span data-ttu-id="7f88b-157">Sebbene molte configurazioni del servizio di routing utilizzino logica di filtro esclusiva che indirizza i messaggi a un unico specifico endpoint, potrebbe essere necessario indirizzare il messaggio in questione a più endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-157">While many Routing Service configurations use exclusive filter logic that routes messages to only one specific endpoint, you may need to route a given message to multiple destination endpoints.</span></span> <span data-ttu-id="7f88b-158">Per il multicast di un messaggio a più destinazioni, è necessario che siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f88b-158">To multicast a message to multiple destinations, the following conditions must be true:</span></span>

- <span data-ttu-id="7f88b-159">La forma del canale non deve essere di tipo request/reply (tuttavia può essere unidirezionale o duplex), poiché l'applicazione client può ricevere una sola risposta alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="7f88b-159">The channel shape must not be request-reply (though may be one-way or duplex,) because only one reply can be received by the client application in response to the request.</span></span>

- <span data-ttu-id="7f88b-160">Più filtri devono restituire `true` in seguito alla valutazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-160">Multiple filters must return `true` when evaluating the message.</span></span>

<span data-ttu-id="7f88b-161">Se vengono soddisfatte queste condizioni, il messaggio viene indirizzato a tutti gli endpoint di tutti i filtri che restituiscono `true`.</span><span class="sxs-lookup"><span data-stu-id="7f88b-161">If these conditions are met, the message is routed to all endpoints of all filters that evaluate to `true`.</span></span> <span data-ttu-id="7f88b-162">Nell'esempio seguente viene definita una configurazione di routing che consente di indirizzare i messaggi a entrambi gli endpoint se l'indirizzo dell'endpoint nel messaggio è `http://localhost:8000/routingservice/router/rounding`.</span><span class="sxs-lookup"><span data-stu-id="7f88b-162">The following example defines a routing configuration that results in messages being routed to both endpoints if the endpoint address in the message is `http://localhost:8000/routingservice/router/rounding`.</span></span>

```xml
<!--ROUTING SECTION -->
<routing>
  <filters>
    <filter name="MatchAllFilter1" filterType="MatchAll" />
    <filter name="RoundingFilter1" filterType="EndpointAddress"
            filterData="http://localhost:8000/routingservice/router/rounding" />
  </filters>
  <filterTables>
    <table name="routingTable1">
      <filters>
        <add filterName="MatchAllFilter1" endpointName="CalculatorService" />
        <add filterName="RoundingFilter1" endpointName="RoundingCalcService" />
      </filters>
    </table>
  </filterTables>
</routing>
```

```csharp
rc.FilterTable.Add(new MatchAllMessageFilter(), calculatorEndpointList);
rc.FilterTable.Add(new EndpointAddressMessageFilter(new EndpointAddress(
    "http://localhost:8000/routingservice/router/rounding")),
    roundingCalcEndpointList);
```

### <a name="soap-processing"></a><span data-ttu-id="7f88b-163">Elaborazione SOAP</span><span class="sxs-lookup"><span data-stu-id="7f88b-163">SOAP Processing</span></span>

<span data-ttu-id="7f88b-164">Per supportare il routing dei messaggi tra protocolli diversi, per impostazione predefinita **RoutingBehavior** aggiunge il <xref:System.ServiceModel.Routing.SoapProcessingBehavior> a tutti gli endpoint client ai quali vengono indirizzati i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7f88b-164">To support the routing of messages between dissimilar protocols, the **RoutingBehavior** by default adds the <xref:System.ServiceModel.Routing.SoapProcessingBehavior> to all client endpoint(s) that messages are routed to.</span></span> <span data-ttu-id="7f88b-165">Questo comportamento crea automaticamente un nuovo oggetto **MessageVersion** prima di indirizzare il messaggio all'endpoint, nonché di creare un oggetto **MessageVersion** compatibile per qualsiasi documento di risposta prima di restituirlo all'applicazione client richiedente.</span><span class="sxs-lookup"><span data-stu-id="7f88b-165">This behavior automatically creates a new **MessageVersion** before routing the message to the endpoint, as well as creating a compatible **MessageVersion** for any response document before returning it to the requesting client application.</span></span>

<span data-ttu-id="7f88b-166">I passaggi necessari per creare un nuovo oggetto **MessageVersion** per il messaggio in uscita sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f88b-166">The steps taken to create a new **MessageVersion** for the outbound message are as follows:</span></span>

<span data-ttu-id="7f88b-167">**Elaborazione richieste**</span><span class="sxs-lookup"><span data-stu-id="7f88b-167">**Request processing**</span></span>

- <span data-ttu-id="7f88b-168">Ottenere l'oggetto **MessageVersion** del canale/binding in uscita.</span><span class="sxs-lookup"><span data-stu-id="7f88b-168">Get the **MessageVersion** of the outbound binding/channel.</span></span>

- <span data-ttu-id="7f88b-169">Ottenere il reader del corpo per il messaggio originale.</span><span class="sxs-lookup"><span data-stu-id="7f88b-169">Get the body reader for the original message.</span></span>

- <span data-ttu-id="7f88b-170">Creare un nuovo messaggio con la stessa azione, il lettore del corpo e un nuovo elemento **MessageVersion**.</span><span class="sxs-lookup"><span data-stu-id="7f88b-170">Create a new message with the same action, body reader, and a new **MessageVersion**.</span></span>

- <span data-ttu-id="7f88b-171">Se <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>! = **Addressing. None**, copiare le intestazioni into, from, FaultTo e laTesto nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-171">If <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> != **Addressing.None**, copy the To, From, FaultTo, and RelatesTo headers to the new message.</span></span>

- <span data-ttu-id="7f88b-172">Copiare tutte le proprietà del messaggio nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-172">Copy all message properties to the new message.</span></span>

- <span data-ttu-id="7f88b-173">Archiviare il messaggio di richiesta originale da usare per l'elaborazione della risposta.</span><span class="sxs-lookup"><span data-stu-id="7f88b-173">Store the original request message to use when processing the response.</span></span>

- <span data-ttu-id="7f88b-174">Restituire il nuovo messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="7f88b-174">Return the new request message.</span></span>

<span data-ttu-id="7f88b-175">**Elaborazione della risposta**</span><span class="sxs-lookup"><span data-stu-id="7f88b-175">**Response processing**</span></span>

- <span data-ttu-id="7f88b-176">Ottiene l'oggetto **MessageVersion** del messaggio di richiesta originale.</span><span class="sxs-lookup"><span data-stu-id="7f88b-176">Get the **MessageVersion** of the original request message.</span></span>

- <span data-ttu-id="7f88b-177">Ottenere il reader del corpo per il messaggio di risposta ricevuto.</span><span class="sxs-lookup"><span data-stu-id="7f88b-177">Get the body reader for the received response message.</span></span>

- <span data-ttu-id="7f88b-178">Creare un nuovo messaggio di risposta con la stessa azione, il lettore del corpo e l'oggetto **MessageVersion** del messaggio di richiesta originale.</span><span class="sxs-lookup"><span data-stu-id="7f88b-178">Create a new response message with the same action, body reader, and the **MessageVersion** of the original request message.</span></span>

- <span data-ttu-id="7f88b-179">Se <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>! = **Addressing. None**, copiare le intestazioni into, from, FaultTo e laTesto nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-179">If <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> != **Addressing.None**, copy the To, From, FaultTo, and RelatesTo headers to the new message.</span></span>

- <span data-ttu-id="7f88b-180">Copiare le proprietà del messaggio nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-180">Copy the message properties to the new message.</span></span>

- <span data-ttu-id="7f88b-181">Restituire il nuovo messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="7f88b-181">Return the new response message.</span></span>

<span data-ttu-id="7f88b-182">Per impostazione predefinita, **SoapProcessingBehavior** viene aggiunto automaticamente agli endpoint client dall'<xref:System.ServiceModel.Routing.RoutingBehavior> all'avvio del servizio. Tuttavia, è possibile controllare se l'elaborazione SOAP viene aggiunta a tutti gli endpoint client tramite la proprietà <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f88b-182">By default, the **SoapProcessingBehavior** is automatically added to the client endpoints by the <xref:System.ServiceModel.Routing.RoutingBehavior> when the service starts; however, you can control whether SOAP processing is added to all client endpoints by using the <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A> property.</span></span> <span data-ttu-id="7f88b-183">È inoltre possibile aggiungere il comportamento direttamente a un endpoint specifico e abilitare o disabilitare tale comportamento al livello dell'endpoint se è necessario un controllo più granulare dell'elaborazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="7f88b-183">You can also add the behavior directly to a specific endpoint and enable or disable this behavior at the endpoint level if a more granular control of SOAP processing is required.</span></span>

> [!NOTE]
> <span data-ttu-id="7f88b-184">Se l'elaborazione SOAP è disabilitata per un endpoint che richiede un elemento MessageVersion diverso rispetto a quello del messaggio di richiesta originale, è necessario fornire un meccanismo personalizzato per l'esecuzione di eventuali modifiche SOAP da apportare prima dell'invio del messaggio all'endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-184">If SOAP processing is disabled for an endpoint that requires a different MessageVersion than that of the original request message, you must provide a custom mechanism for performing any SOAP modifications that are required before sending the message to the destination endpoint.</span></span>

<span data-ttu-id="7f88b-185">Negli esempi seguenti, la proprietà **SoapProcessingEnabled** viene usata per impedire che **SoapProcessingBehavior** venga aggiunto automaticamente a tutti gli endpoint client.</span><span class="sxs-lookup"><span data-stu-id="7f88b-185">In the following examples, the **soapProcessingEnabled** property is used to prevent the **SoapProcessingBehavior** from being automatically added to all client endpoints.</span></span>

```xml
<behaviors>
  <!--default routing service behavior definition-->
  <serviceBehaviors>
    <behavior name="routingConfiguration">
      <routing filterTableName="filterTable1" soapProcessingEnabled="false"/>
    </behavior>
  </serviceBehaviors>
</behaviors>
```

```csharp
//create the default RoutingConfiguration
RoutingConfiguration rc = new RoutingConfiguration();
rc.SoapProcessingEnabled = false;
```

### <a name="dynamic-configuration"></a><span data-ttu-id="7f88b-186">configurazione dinamica</span><span class="sxs-lookup"><span data-stu-id="7f88b-186">Dynamic Configuration</span></span>

<span data-ttu-id="7f88b-187">Quando si aggiungono ulteriori endpoint client oppure occorre modificare i filtri usati per il routing dei messaggi, è necessario disporre di un modo per aggiornare dinamicamente la configurazione in fase di esecuzione allo scopo di evitare interruzioni del servizio per gli endpoint attualmente definiti per la ricezione dei messaggi tramite il servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="7f88b-187">When you add additional client endpoints, or need to modify the filters that are used to route messages, you must have a way to update the configuration dynamically at run time to prevent interrupting the service to the endpoints currently receiving messages through the Routing Service.</span></span> <span data-ttu-id="7f88b-188">La modifica di un file di configurazione o del codice dell'applicazione host non è sempre sufficiente poiché tali metodi richiedono il riciclo dell'applicazione, il che potrebbe causare la perdita di eventuali messaggi attualmente in transito nonché tempi di inattività durante l'attesa del riavvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-188">Modifying a configuration file or the code of the host application is not always sufficient, because either method requires recycling the application, which would lead to the potential loss of any messages currently in transit and the potential for downtime while waiting on the service to restart.</span></span>

<span data-ttu-id="7f88b-189">È possibile modificare solo il **RoutingConfiguration** a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="7f88b-189">You can only modify the **RoutingConfiguration** programmatically.</span></span> <span data-ttu-id="7f88b-190">Sebbene sia possibile configurare inizialmente il servizio usando un file di configurazione, è possibile modificare la configurazione solo in fase di esecuzione costruendo un nuovo **RoutingConfiguration** e passandolo come parametro al metodo <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> esposto dall'estensione del servizio <xref:System.ServiceModel.Routing.RoutingExtension>.</span><span class="sxs-lookup"><span data-stu-id="7f88b-190">While you can initially configure the service by using a configuration file, you can only modify the configuration at run time by constructing a new **RoutingConfiguration** and passing it as a parameter to the <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> method exposed by the <xref:System.ServiceModel.Routing.RoutingExtension> service extension.</span></span> <span data-ttu-id="7f88b-191">Tutti i messaggi attualmente in transito continuano a essere instradati utilizzando la configurazione precedente, mentre i messaggi ricevuti dopo la chiamata a **ApplyConfiguration** utilizzano la nuova configurazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-191">Any messages currently in transit continue to be routed using the previous configuration, while messages received after the call to **ApplyConfiguration** use the new configuration.</span></span> <span data-ttu-id="7f88b-192">Nell'esempio seguente viene illustrata la creazione di un'istanza del servizio di routing e successivamente la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-192">The following example demonstrates creating an instance of the Routing Service and then subsequently modifying the configuration.</span></span>

```csharp
RoutingConfiguration routingConfig = new RoutingConfiguration();
routingConfig.RouteOnHeadersOnly = true;
routingConfig.FilterTable.Add(new MatchAllMessageFilter(), endpointList);
RoutingBehavior routing = new RoutingBehavior(routingConfig);
routerHost.Description.Behaviors.Add(routing);
routerHost.Open();
// Construct a new RoutingConfiguration
RoutingConfiguration rc2 = new RoutingConfiguration();
ServiceEndpoint clientEndpoint = new ServiceEndpoint();
ServiceEndpoint clientEndpoint2 = new ServiceEndpoint();
// Add filters to the FilterTable in the new configuration
rc2.FilterTable.add(new MatchAllMessageFilter(),
       new List<ServiceEndpoint>() { clientEndpoint });
rc2.FilterTable.add(new MatchAllMessageFilter(),
       new List<ServiceEndpoint>() { clientEndpoint2 });
rc2.RouteOnHeadersOnly = false;
// Apply the new configuration to the Routing Service hosted in
routerHost.routerHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc2);
```

> [!NOTE]
> <span data-ttu-id="7f88b-193">Per aggiornare il servizio di routing in questo modo è possibile passare solo una nuova configurazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-193">When updating the Routing Service in this manner it is only possible to pass a new configuration.</span></span> <span data-ttu-id="7f88b-194">Non è possibile modificare solo elementi scelti della configurazione corrente o aggiungere nuove voci alla configurazione corrente. È necessario creare e passare una nuova configurazione che sostituisca quella esistente.</span><span class="sxs-lookup"><span data-stu-id="7f88b-194">It is not possible to modify only select elements of the current configuration or append new entries to the current configuration; you must create and pass a new configuration that replaces the existing one.</span></span>

> [!NOTE]
> <span data-ttu-id="7f88b-195">Le eventuali sessioni aperte usando la configurazione precedente continuano a usare quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="7f88b-195">Any sessions opened using the previous configuration continue using the previous configuration.</span></span> <span data-ttu-id="7f88b-196">La nuova configurazione viene usata solo dalle nuove sessioni.</span><span class="sxs-lookup"><span data-stu-id="7f88b-196">The new configuration is only used by new sessions.</span></span>

## <a name="error-handling"></a><span data-ttu-id="7f88b-197">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="7f88b-197">Error Handling</span></span>

<span data-ttu-id="7f88b-198">Se si verificano eccezioni <xref:System.ServiceModel.CommunicationException> durante il tentativo di inviare un messaggio, viene eseguita la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="7f88b-198">If any <xref:System.ServiceModel.CommunicationException> is encountered while attempting to send a message, error handling take place.</span></span> <span data-ttu-id="7f88b-199">Queste eccezioni indicano in genere che si è verificato un problema durante il tentativo di comunicare con l'endpoint client definito, ad esempio <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> o <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span><span class="sxs-lookup"><span data-stu-id="7f88b-199">These exceptions typically indicate that a problem was encountered while attempting to communicate with the defined client endpoint, such as an <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException>, or <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span></span> <span data-ttu-id="7f88b-200">Il codice di gestione degli errori intercetta inoltre e tenta di ritentare l'invio quando si verifica un <xref:System.TimeoutException>, ovvero un'altra eccezione comune non derivata da **CommunicationException**.</span><span class="sxs-lookup"><span data-stu-id="7f88b-200">The error handling-code will also catch and attempt to retry sending when a <xref:System.TimeoutException> occurs, which is another common exception that is not derived from **CommunicationException**.</span></span>

<span data-ttu-id="7f88b-201">Quando si verifica una delle eccezioni precedenti, il servizio di routing esegue il failover a un elenco di endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-201">When one of the preceding exceptions occurs, the Routing Service fails over to a list of backup endpoints.</span></span> <span data-ttu-id="7f88b-202">Se in tutti gli endpoint di backup si verifica un errore di comunicazione oppure un endpoint restituisce un'eccezione indicante un errore all'interno del servizio di destinazione, il servizio di routing restituisce un errore all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="7f88b-202">If all backup endpoints fail with a communications failure, or if an endpoint returns an exception that indicates a failure within the destination service, the Routing Service returns a fault to the client application.</span></span>

> [!NOTE]
> <span data-ttu-id="7f88b-203">La funzionalità di gestione degli errori acquisisce e gestisce le eccezioni che si verificano quando si tenta di inviare un messaggio e di chiudere un canale.</span><span class="sxs-lookup"><span data-stu-id="7f88b-203">The error-handling functionality captures and handles exceptions that occur when attempting to send a message and when attempting to close a channel.</span></span> <span data-ttu-id="7f88b-204">Il codice di gestione degli errori non è progettato per rilevare o gestire le eccezioni create dagli endpoint dell'applicazione con cui sta comunicando; una <xref:System.ServiceModel.FaultException> generata da un servizio viene visualizzata nel servizio di routing come **FaultMessage** e viene propagata al client.</span><span class="sxs-lookup"><span data-stu-id="7f88b-204">The error-handling code is not intended to detect or handle exceptions created by the application endpoints it is communicating with; a <xref:System.ServiceModel.FaultException> thrown by a service appears at the Routing Service as a **FaultMessage** and is flowed back to the client.</span></span>
>
> <span data-ttu-id="7f88b-205">Se si verifica un errore quando il servizio di routing tenta di inoltrare un messaggio, potrebbe essere generata un'eccezione <xref:System.ServiceModel.FaultException> sul lato client, anziché l'eccezione <xref:System.ServiceModel.EndpointNotFoundException> che verrebbe generata di norma in assenza del servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="7f88b-205">If an error occurs when the routing service tries to relay a message, you may  get a <xref:System.ServiceModel.FaultException> on the client side, rather than a <xref:System.ServiceModel.EndpointNotFoundException> you would normally get in the absence of the routing service.</span></span> <span data-ttu-id="7f88b-206">Un servizio di routing potrebbe quindi mascherare eventuali eccezioni e non fornire completa trasparenza a meno che non si esamino le eccezioni annidate.</span><span class="sxs-lookup"><span data-stu-id="7f88b-206">A routing service may thus mask exceptions and not provide full transparency unless you examine nested exceptions.</span></span>

### <a name="tracing-exceptions"></a><span data-ttu-id="7f88b-207">Traccia delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="7f88b-207">Tracing Exceptions</span></span>

<span data-ttu-id="7f88b-208">Quando si invia un messaggio a un endpoint in un elenco ha esito negativo, il servizio di routing traccia i dati dell'eccezione risultante e alleghi i dettagli dell'eccezione come proprietà del messaggio denominata **Exceptions**.</span><span class="sxs-lookup"><span data-stu-id="7f88b-208">When sending a message to an endpoint in a list fails, the Routing Service traces the resulting exception data and attaches the exception details as a message property named **Exceptions**.</span></span> <span data-ttu-id="7f88b-209">Ciò consente di mantenere i dati dell'eccezione e l'accesso utente a livello di codice tramite un controllo messaggi.</span><span class="sxs-lookup"><span data-stu-id="7f88b-209">This preserves the exception data and allows a user programmatic access through a message inspector.</span></span>  <span data-ttu-id="7f88b-210">I dati dell'eccezione vengono archiviati per ciascun messaggio in un dizionario che stabilisce il mapping del nome dell'endpoint ai dettagli dell'eccezione verificatasi durante il tentativo di inviare un messaggio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-210">The exception data is stored per message in a dictionary that maps the endpoint name to the exception details encountered when trying to send a message to it.</span></span>

### <a name="backup-endpoints"></a><span data-ttu-id="7f88b-211">Endpoint di backup</span><span class="sxs-lookup"><span data-stu-id="7f88b-211">Backup Endpoints</span></span>

<span data-ttu-id="7f88b-212">Ogni voce di filtro all'interno della tabella dei filtri può facoltativamente specificare un elenco di endpoint di backup da usare in caso di errore di trasmissione durante l'invio all'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="7f88b-212">Each filter entry within the filter table can optionally specify a list of backup endpoints, which are used in the event of a transmission failure when sending to the primary endpoint.</span></span> <span data-ttu-id="7f88b-213">Se si verifica un errore di questo tipo, il servizio di routing tenta di trasmettere il messaggio alla prima voce nell'elenco di endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-213">If such a failure occurs, the Routing Service attempts to transmit the message to the first entry in the backup endpoint list.</span></span> <span data-ttu-id="7f88b-214">Se durante il tentativo di invio si verifica un errore di trasmissione, viene eseguito un tentativo con l'endpoint successivo nell'elenco di quelli di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-214">If this send attempt also encounters a transmission failure, the next endpoint in the backup list is tried.</span></span> <span data-ttu-id="7f88b-215">Il servizio di routing continua a inviare il messaggio a ogni endpoint nell'elenco finché il messaggio non viene ricevuto correttamente, tutti gli endpoint restituiscono un errore di trasmissione oppure viene restituito un errore non di trasmissione da un endpoint.</span><span class="sxs-lookup"><span data-stu-id="7f88b-215">The Routing Service continues sending the message to each endpoint in the list until the message is successfully received, all endpoints return a transmission failure, or a non-transmission failure is returned by an endpoint.</span></span>

<span data-ttu-id="7f88b-216">Negli esempi seguenti il servizio di routing viene configurato per l'uso di un elenco di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-216">The following examples configure the Routing Service to use a backup list.</span></span>

```xml
<routing>
  <filters>
    <!-- Create a MatchAll filter that catches all messages -->
    <filter name="MatchAllFilter1" filterType="MatchAll" />
  </filters>
  <filterTables>
    <!-- Set up the Routing Service's Message Filter Table -->
    <filterTable name="filterTable1">
        <!-- Add an entry that maps the MatchAllMessageFilter to the dead destination -->
        <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->
        <!-- Listed in the backupEndpointList -->
        <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>
    </filterTable>
  </filterTables>
  <!-- Create the backup endpoint list -->
  <backupLists>
    <!-- Add an endpoint list that contains the backup destinations -->
    <backupList name="backupEndpointList">
      <add endpointName="realDestination" />
      <add endpointName="backupDestination" />
    </backupList>
  </backupLists>
</routing>
```

```csharp
//create the endpoint list that contains the service endpoints we want to route to
List<ServiceEndpoint> backupList = new List<ServiceEndpoint>();
//add the endpoints in the order that the Routing Service should contact them
//first add the endpoint that we know is down
//clearly, normally you wouldn't know that this endpoint was down by default
backupList.Add(fakeDestination);
//then add the real Destination endpoint
//the Routing Service attempts to send to this endpoint only if it
//encounters a TimeOutException or CommunicationException when sending
//to the previous endpoint in the list.
backupList.Add(realDestination);
//add the backupDestination endpoint
//the Routing Service attempts to send to this endpoint only if it
//encounters a TimeOutException or CommunicationsException when sending
//to the previous endpoints in the list
backupList.Add(backupDestination);
//create the default RoutingConfiguration option
RoutingConfiguration rc = new RoutingConfiguration();
//add a MatchAll filter to the Routing Configuration's filter table
//map it to the list of endpoints defined above
//when a message matches this filter, it is sent to the endpoints in the list in order
//if an endpoint is down or does not respond (which the first endpoint won't
//since the client does not exist), the Routing Service automatically moves the message
//to the next endpoint in the list and try again.
rc.FilterTable.Add(new MatchAllMessageFilter(), backupList);
```

### <a name="supported-error-patterns"></a><span data-ttu-id="7f88b-217">Modelli di errore supportati</span><span class="sxs-lookup"><span data-stu-id="7f88b-217">Supported Error Patterns</span></span>

<span data-ttu-id="7f88b-218">Nella tabella seguente vengono descritti i modelli compatibili con l'uso di elenchi di endpoint di backup, insieme a note che descrivono dettagli specifici di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="7f88b-218">The following table describes the patterns that are compatible with the use of backup endpoint lists, along with notes describing the details of error handling for specific patterns.</span></span>

|<span data-ttu-id="7f88b-219">Criterio</span><span class="sxs-lookup"><span data-stu-id="7f88b-219">Pattern</span></span>|<span data-ttu-id="7f88b-220">Sessione</span><span class="sxs-lookup"><span data-stu-id="7f88b-220">Session</span></span>|<span data-ttu-id="7f88b-221">Transazione</span><span class="sxs-lookup"><span data-stu-id="7f88b-221">Transaction</span></span>|<span data-ttu-id="7f88b-222">Contesto di ricezione</span><span class="sxs-lookup"><span data-stu-id="7f88b-222">Receive Context</span></span>|<span data-ttu-id="7f88b-223">Elenco di backup supportato</span><span class="sxs-lookup"><span data-stu-id="7f88b-223">Backup List Supported</span></span>|<span data-ttu-id="7f88b-224">Note</span><span class="sxs-lookup"><span data-stu-id="7f88b-224">Notes</span></span>|
|-------------|-------------|-----------------|---------------------|---------------------------|-----------|
|<span data-ttu-id="7f88b-225">Unidirezionale</span><span class="sxs-lookup"><span data-stu-id="7f88b-225">One-Way</span></span>||||<span data-ttu-id="7f88b-226">Sì</span><span class="sxs-lookup"><span data-stu-id="7f88b-226">Yes</span></span>|<span data-ttu-id="7f88b-227">Tenta di inviare di nuovo il messaggio a un endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-227">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="7f88b-228">Se per il messaggio viene usata la trasmissione multicast, solo il messaggio nel canale con errori viene spostato alla relativa destinazione di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-228">If this message is being multicast, only the message on the failed channel is moved to its backup destination.</span></span>|
|<span data-ttu-id="7f88b-229">Unidirezionale</span><span class="sxs-lookup"><span data-stu-id="7f88b-229">One-Way</span></span>||<span data-ttu-id="7f88b-230">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-230">✔️</span></span>||<span data-ttu-id="7f88b-231">No</span><span class="sxs-lookup"><span data-stu-id="7f88b-231">No</span></span>|<span data-ttu-id="7f88b-232">Viene generata un'eccezione e viene eseguito il rollback della transazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-232">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="7f88b-233">Unidirezionale</span><span class="sxs-lookup"><span data-stu-id="7f88b-233">One-Way</span></span>|||<span data-ttu-id="7f88b-234">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-234">✔️</span></span>|<span data-ttu-id="7f88b-235">Sì</span><span class="sxs-lookup"><span data-stu-id="7f88b-235">Yes</span></span>|<span data-ttu-id="7f88b-236">Tenta di inviare di nuovo il messaggio a un endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-236">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="7f88b-237">Dopo che il messaggio viene ricevuto correttamente, completare tutti i contesti di ricezione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-237">After the message is successfully received, complete all receive contexts.</span></span> <span data-ttu-id="7f88b-238">Se il messaggio non viene ricevuto correttamente da uno o più endpoint, non completare il contesto di ricezione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-238">If the message is not successfully received by any endpoint, do not complete the receive context.</span></span><br /><br /> <span data-ttu-id="7f88b-239">Se per il messaggio viene usata la trasmissione multicast, il contesto di ricezione viene completato solo se il messaggio viene ricevuto correttamente da almeno un endpoint (primario o di backup).</span><span class="sxs-lookup"><span data-stu-id="7f88b-239">When this message is being multicast, the receive context is only completed if the message is successfully received by at least one endpoint (primary or backup).</span></span> <span data-ttu-id="7f88b-240">Se nessuno degli endpoint in uno o più percorsi multicast riceve correttamente il messaggio, non completare il contesto di ricezione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-240">If none of the endpoints in any of the multicast paths successfully receive the message, do not complete the receive context.</span></span>|
|<span data-ttu-id="7f88b-241">Unidirezionale</span><span class="sxs-lookup"><span data-stu-id="7f88b-241">One-Way</span></span>||<span data-ttu-id="7f88b-242">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-242">✔️</span></span>|<span data-ttu-id="7f88b-243">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-243">✔️</span></span>|<span data-ttu-id="7f88b-244">Sì</span><span class="sxs-lookup"><span data-stu-id="7f88b-244">Yes</span></span>|<span data-ttu-id="7f88b-245">Interrompere la transazione precedente, creare una nuova transazione e inviare nuovamente tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7f88b-245">Abort the previous transaction, create a new transaction, and resend all messages.</span></span> <span data-ttu-id="7f88b-246">I messaggi per i quali si verifica un errore vengono trasmessi a una destinazione di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-246">Messages that encountered an error are transmitted to a backup destination.</span></span><br /><br /> <span data-ttu-id="7f88b-247">Dopo che è stata creata una transazione in cui tutte le trasmissioni hanno esito positivo, completare i contesti di ricezione ed eseguire il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-247">After a transaction has been created in which all transmissions succeed, complete the receive contexts and commit the transaction.</span></span>|
|<span data-ttu-id="7f88b-248">Unidirezionale</span><span class="sxs-lookup"><span data-stu-id="7f88b-248">One-Way</span></span>|<span data-ttu-id="7f88b-249">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-249">✔️</span></span>|||<span data-ttu-id="7f88b-250">Sì</span><span class="sxs-lookup"><span data-stu-id="7f88b-250">Yes</span></span>|<span data-ttu-id="7f88b-251">Tenta di inviare di nuovo il messaggio a un endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-251">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="7f88b-252">In un scenario multicast vengono inviati di nuovo a destinazioni di backup solo i messaggi in una sessione nella quale si è verificato un errore o in una sessione la cui chiusura ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="7f88b-252">In a multicast scenario only the messages in a session that encountered an error or in a session whose session close failed are resent to backup destinations.</span></span>|
|<span data-ttu-id="7f88b-253">Unidirezionale</span><span class="sxs-lookup"><span data-stu-id="7f88b-253">One-Way</span></span>|<span data-ttu-id="7f88b-254">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-254">✔️</span></span>|<span data-ttu-id="7f88b-255">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-255">✔️</span></span>||<span data-ttu-id="7f88b-256">No</span><span class="sxs-lookup"><span data-stu-id="7f88b-256">No</span></span>|<span data-ttu-id="7f88b-257">Viene generata un'eccezione e viene eseguito il rollback della transazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-257">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="7f88b-258">Unidirezionale</span><span class="sxs-lookup"><span data-stu-id="7f88b-258">One-Way</span></span>|<span data-ttu-id="7f88b-259">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-259">✔️</span></span>||<span data-ttu-id="7f88b-260">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-260">✔️</span></span>|<span data-ttu-id="7f88b-261">Sì</span><span class="sxs-lookup"><span data-stu-id="7f88b-261">Yes</span></span>|<span data-ttu-id="7f88b-262">Tenta di inviare di nuovo il messaggio a un endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-262">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="7f88b-263">Dopo che tutte le operazioni di invio dei messaggi vengono completate senza errori, la sessione indica che non sono presenti altri messaggi e il servizio di routing chiude correttamente tutti i canali di sessione in uscita, tutti i contesti di ricezione vengono completati e il canale di sessione in ingresso viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="7f88b-263">After all message sends complete without error, the session indicates no more messages and the Routing Service successfully closes all outbound session channel(s), all receive contexts are completed, and the inbound session channel is closed.</span></span>|
|<span data-ttu-id="7f88b-264">Unidirezionale</span><span class="sxs-lookup"><span data-stu-id="7f88b-264">One-Way</span></span>|<span data-ttu-id="7f88b-265">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-265">✔️</span></span>|<span data-ttu-id="7f88b-266">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-266">✔️</span></span>|<span data-ttu-id="7f88b-267">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-267">✔️</span></span>|<span data-ttu-id="7f88b-268">Sì</span><span class="sxs-lookup"><span data-stu-id="7f88b-268">Yes</span></span>|<span data-ttu-id="7f88b-269">Interrompere la transazione corrente e crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="7f88b-269">Abort the current transaction and create a new one.</span></span> <span data-ttu-id="7f88b-270">Inviare di nuovo tutti i messaggi precedenti nella sessione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-270">Resend all previous messages in the session.</span></span> <span data-ttu-id="7f88b-271">Dopo che è stata creata una transazione in cui tutti i messaggi vengono inviati correttamente e la sessione indica che non sono presenti altri messaggi, tutti i canali di sessione in uscita vengono chiusi, i contesti di ricezione vengono tutti completati con la transazione, il canale di sessione in ingresso viene chiuso e viene eseguito il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-271">After a transaction has been created in which all messages have been successfully sent and the session indicates no more messages, all the outbound session channels are closed, receive contexts are all completed with the transaction, the inbound session channel is closed, and the transaction is committed.</span></span><br /><br /> <span data-ttu-id="7f88b-272">Quando per le sessioni viene usata la trasmissione multicast, i messaggi senza errori vengono inviati di nuovo alla stessa destinazione, mentre quelli per i quali si è verificato un errore vengono inviati a destinazioni di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-272">When the sessions are being multicast the messages that had no error are resent to the same destination as before, and messages that encountered an error are sent to backup destinations.</span></span>|
|<span data-ttu-id="7f88b-273">Bidirezionale</span><span class="sxs-lookup"><span data-stu-id="7f88b-273">Two-Way</span></span>||||<span data-ttu-id="7f88b-274">Sì</span><span class="sxs-lookup"><span data-stu-id="7f88b-274">Yes</span></span>|<span data-ttu-id="7f88b-275">Inviare a una destinazione di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-275">Send to a backup destination.</span></span>  <span data-ttu-id="7f88b-276">Dopo che un canale restituisce un messaggio di risposta, viene restituita la risposta al client originale.</span><span class="sxs-lookup"><span data-stu-id="7f88b-276">After a channel returns a response message, return the response to the original client.</span></span>|
|<span data-ttu-id="7f88b-277">Bidirezionale</span><span class="sxs-lookup"><span data-stu-id="7f88b-277">Two-Way</span></span>|<span data-ttu-id="7f88b-278">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-278">✔️</span></span>|||<span data-ttu-id="7f88b-279">Sì</span><span class="sxs-lookup"><span data-stu-id="7f88b-279">Yes</span></span>|<span data-ttu-id="7f88b-280">Inviare tutti i messaggi nel canale a una destinazione di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-280">Send all messages on the channel to a backup destination.</span></span>  <span data-ttu-id="7f88b-281">Dopo che un canale restituisce un messaggio di risposta, viene restituita la risposta al client originale.</span><span class="sxs-lookup"><span data-stu-id="7f88b-281">After a channel returns a response message, return the response to the original client.</span></span>|
|<span data-ttu-id="7f88b-282">Bidirezionale</span><span class="sxs-lookup"><span data-stu-id="7f88b-282">Two-Way</span></span>||<span data-ttu-id="7f88b-283">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-283">✔️</span></span>||<span data-ttu-id="7f88b-284">No</span><span class="sxs-lookup"><span data-stu-id="7f88b-284">No</span></span>|<span data-ttu-id="7f88b-285">Viene generata un'eccezione e viene eseguito il rollback della transazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-285">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="7f88b-286">Bidirezionale</span><span class="sxs-lookup"><span data-stu-id="7f88b-286">Two-Way</span></span>|<span data-ttu-id="7f88b-287">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-287">✔️</span></span>|<span data-ttu-id="7f88b-288">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-288">✔️</span></span>||<span data-ttu-id="7f88b-289">No</span><span class="sxs-lookup"><span data-stu-id="7f88b-289">No</span></span>|<span data-ttu-id="7f88b-290">Viene generata un'eccezione e viene eseguito il rollback della transazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-290">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="7f88b-291">Duplex</span><span class="sxs-lookup"><span data-stu-id="7f88b-291">Duplex</span></span>||||<span data-ttu-id="7f88b-292">No</span><span class="sxs-lookup"><span data-stu-id="7f88b-292">No</span></span>|<span data-ttu-id="7f88b-293">La comunicazione duplex non di sessione non è attualmente supportata.</span><span class="sxs-lookup"><span data-stu-id="7f88b-293">Non-session duplex communication is not currently supported.</span></span>|
|<span data-ttu-id="7f88b-294">Duplex</span><span class="sxs-lookup"><span data-stu-id="7f88b-294">Duplex</span></span>|<span data-ttu-id="7f88b-295">✔️</span><span class="sxs-lookup"><span data-stu-id="7f88b-295">✔️</span></span>|||<span data-ttu-id="7f88b-296">Sì</span><span class="sxs-lookup"><span data-stu-id="7f88b-296">Yes</span></span>|<span data-ttu-id="7f88b-297">Inviare a una destinazione di backup.</span><span class="sxs-lookup"><span data-stu-id="7f88b-297">Send to a backup destination.</span></span>|

## <a name="hosting"></a><span data-ttu-id="7f88b-298">Hosting</span><span class="sxs-lookup"><span data-stu-id="7f88b-298">Hosting</span></span>

<span data-ttu-id="7f88b-299">Poiché il servizio di routing viene implementato come servizio WCF, deve essere indipendente all'interno di un'applicazione o ospitato da IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="7f88b-299">Because the Routing Service is implemented as a WCF service, it must be either self-hosted within an application or hosted by IIS or WAS.</span></span> <span data-ttu-id="7f88b-300">È consigliabile che il servizio di routing sia ospitato in IIS, WAS o un'applicazione di servizio Windows per sfruttare le funzionalità di avvio automatico e di gestione del ciclo di vita disponibili in tali ambienti di hosting.</span><span class="sxs-lookup"><span data-stu-id="7f88b-300">It is recommended that the Routing Service be hosted in either IIS, WAS, or a Windows Service application to take advantage of the automatic start and life-cycle management features available in these hosting environments.</span></span>

<span data-ttu-id="7f88b-301">Nell'esempio seguente viene illustrato l'hosting del servizio di routing in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-301">The following example demonstrates hosting the Routing Service in an application.</span></span>

```csharp
using (ServiceHost serviceHost =
                new ServiceHost(typeof(RoutingService)))
```

<span data-ttu-id="7f88b-302">Per ospitare il servizio di routing in IIS o WAS, è necessario creare un file del servizio (con estensione svc) oppure usare l'attivazione basata sulla configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-302">To host the Routing Service within IIS or WAS, you must either create a service file (.svc) or use configuration-based activation of the service.</span></span> <span data-ttu-id="7f88b-303">Se si usa un file del servizio, è necessario specificare <xref:System.ServiceModel.Routing.RoutingService> mediante il parametro Service.</span><span class="sxs-lookup"><span data-stu-id="7f88b-303">When using a service file, you must specify the <xref:System.ServiceModel.Routing.RoutingService> using the Service parameter.</span></span> <span data-ttu-id="7f88b-304">L'esempio seguente contiene un servizio di esempio che può essere usato per ospitare il servizio di routing con IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="7f88b-304">The following example contains a sample service file that can be used to host the Routing Service with IIS or WAS.</span></span>

```aspx-csharp
<%@ ServiceHost Language="C#" Debug="true" Service="System.ServiceModel.Routing.RoutingService,
     System.ServiceModel.Routing, version=4.0.0.0, Culture=neutral,
     PublicKeyToken=31bf3856ad364e35" %>
```

## <a name="routing-service-and-impersonation"></a><span data-ttu-id="7f88b-305">Servizio di routing e rappresentazione</span><span class="sxs-lookup"><span data-stu-id="7f88b-305">Routing Service and Impersonation</span></span>

<span data-ttu-id="7f88b-306">Il servizio di routing di WCF può essere usato con la rappresentazione sia per l'invio sia per la ricezione di messaggi.</span><span class="sxs-lookup"><span data-stu-id="7f88b-306">The WCF Routing Service can be used with impersonation for both sending and receiving messages.</span></span> <span data-ttu-id="7f88b-307">Si applicano tutti i consueti vincoli di rappresentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="7f88b-307">All of the usual Windows constraints of impersonation apply.</span></span> <span data-ttu-id="7f88b-308">Come per la configurazione delle autorizzazioni dell'account o del servizio per usare la rappresentazione durante la scrittura del servizio, questi stessi passaggi sono necessari per usare la rappresentazione con il servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="7f88b-308">If you would have needed to set up service or account permissions to use impersonation when writing your own service, then you’ll have to do those same steps to use impersonation with the routing service.</span></span> <span data-ttu-id="7f88b-309">Per ulteriori informazioni, vedere [delega e rappresentazione](delegation-and-impersonation-with-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="7f88b-309">For more information, see [Delegation and Impersonation](delegation-and-impersonation-with-wcf.md).</span></span>

<span data-ttu-id="7f88b-310">La rappresentazione con il servizio di routing richiede l'uso della rappresentazione ASP.NET in modalità di compatibilità ASP.NET o l'uso delle credenziali di Windows che sono state configurate per consentire la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-310">Impersonation with the routing service requires either the use of ASP.NET impersonation while in ASP.NET compatibility mode or the use of Windows credentials that have been configured to allow impersonation.</span></span> <span data-ttu-id="7f88b-311">Per ulteriori informazioni sulla modalità di compatibilità ASP.NET, vedere [servizi WCF e ASP.NET](wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="7f88b-311">For more information about ASP.NET compatibility mode, see [WCF Services and ASP.NET](wcf-services-and-aspnet.md).</span></span>

> [!WARNING]
> <span data-ttu-id="7f88b-312">Il servizio di routing di WCF non supporta la rappresentazione con l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="7f88b-312">The WCF Routing Service does not support impersonation with basic authentication.</span></span>

<span data-ttu-id="7f88b-313">Per usare la rappresentazione ASP.NET con il servizio di routing, abilitare la modalità di compatibilità ASP.NET nell'ambiente host del servizio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-313">To use ASP.NET impersonation with the routing service, enable ASP.NET compatibility mode on the service hosting environment.</span></span> <span data-ttu-id="7f88b-314">Il servizio di routing è già stato contrassegnato come servizio che consente la modalità di compatibilità ASP.NET e la rappresentazione verrà abilitata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f88b-314">The routing service has already been marked as allowing ASP.NET compatibility mode and impersonation will automatically be enabled.</span></span> <span data-ttu-id="7f88b-315">La rappresentazione è l'unico utilizzo supportato dell'integrazione ASP.NET con il servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="7f88b-315">Impersonation is the only supported use of ASP.NET integration with the routing service.</span></span>

<span data-ttu-id="7f88b-316">Per usare la rappresentazione di credenziali di Windows con il servizio di routing è necessario configurare sia le credenziali sia il servizio.</span><span class="sxs-lookup"><span data-stu-id="7f88b-316">To use Windows credential impersonation with the routing service you need to configure both the credentials and the service.</span></span> <span data-ttu-id="7f88b-317">L'oggetto delle credenziali client (<xref:System.ServiceModel.Security.WindowsClientCredential>, accessibile da <xref:System.ServiceModel.ChannelFactory>) definisce una proprietà <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> che deve essere impostata per consentire la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="7f88b-317">The client credentials object (<xref:System.ServiceModel.Security.WindowsClientCredential>, accessable from the <xref:System.ServiceModel.ChannelFactory>) defines an <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> property that must be set to permit impersonation.</span></span> <span data-ttu-id="7f88b-318">Infine, nel servizio è necessario configurare il comportamento di <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> per impostare `ImpersonateCallerForAllOperations` su `true`.</span><span class="sxs-lookup"><span data-stu-id="7f88b-318">Finally, on the service you need to configure the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> behavior to set `ImpersonateCallerForAllOperations` to `true`.</span></span> <span data-ttu-id="7f88b-319">Il servizio di routing usa questo flag per decidere se creare i client per inoltrare i messaggi con la rappresentazione abilitata.</span><span class="sxs-lookup"><span data-stu-id="7f88b-319">The routing service uses this flag to decide whether to create the clients for forwarding messages with impersonation enabled.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f88b-320">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f88b-320">See also</span></span>

- [<span data-ttu-id="7f88b-321">Filtri per messaggi</span><span class="sxs-lookup"><span data-stu-id="7f88b-321">Message Filters</span></span>](message-filters.md)
- [<span data-ttu-id="7f88b-322">Contratti di routing</span><span class="sxs-lookup"><span data-stu-id="7f88b-322">Routing Contracts</span></span>](routing-contracts.md)
- [<span data-ttu-id="7f88b-323">Scelta di un filtro</span><span class="sxs-lookup"><span data-stu-id="7f88b-323">Choosing a Filter</span></span>](choosing-a-filter.md)
