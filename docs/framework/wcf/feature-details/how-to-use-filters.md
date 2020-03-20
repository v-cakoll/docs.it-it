---
title: 'Procedura: usare i filtri'
ms.date: 03/30/2017
ms.assetid: f2c7255f-c376-460e-aa20-14071f1666e5
ms.openlocfilehash: f99c2af623dacac3ebe46422815a7f42e2a4df2c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184820"
---
# <a name="how-to-use-filters"></a><span data-ttu-id="52539-102">Procedura: usare i filtri</span><span class="sxs-lookup"><span data-stu-id="52539-102">How To: Use Filters</span></span>
<span data-ttu-id="52539-103">In questo argomento vengono descritti i passaggi di base necessari per creare una configurazione di routing che usa più filtri.</span><span class="sxs-lookup"><span data-stu-id="52539-103">This topic outlines the basic steps required to create a routing configuration that uses multiple filters.</span></span> <span data-ttu-id="52539-104">In questo esempio, i messaggi vengono indirizzati a due implementazioni di un servizio di calcolo, regularCalc e roundingCalc.</span><span class="sxs-lookup"><span data-stu-id="52539-104">In this example, messages are routed to two implementations of a calculator service, regularCalc and roundingCalc.</span></span> <span data-ttu-id="52539-105">Entrambe le implementazioni supportano le stesse operazioni; tuttavia uno dei servizi arrotonda tutti i calcoli all'integer più vicino prima della restituzione.</span><span class="sxs-lookup"><span data-stu-id="52539-105">Both implementations support the same operations; however one service rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="52539-106">Un'applicazione client deve essere in grado di indicare se usare la versione del servizio che esegue l'arrotondamento. Se non viene espressa alcuna preferenza in merito al servizio da usare, il carico viene bilanciato tra i due servizi.</span><span class="sxs-lookup"><span data-stu-id="52539-106">A client application must be able to indicate whether to  use the rounding version of the service; if no service preference is expressed then the message is load balanced between the two services.</span></span> <span data-ttu-id="52539-107">Le operazioni esposte da entrambi servizi sono:</span><span class="sxs-lookup"><span data-stu-id="52539-107">The operations exposed by both services are:</span></span>  
  
- <span data-ttu-id="52539-108">Add</span><span class="sxs-lookup"><span data-stu-id="52539-108">Add</span></span>  
  
- <span data-ttu-id="52539-109">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="52539-109">Subtract</span></span>  
  
- <span data-ttu-id="52539-110">Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="52539-110">Multiply</span></span>  
  
- <span data-ttu-id="52539-111">Divisione</span><span class="sxs-lookup"><span data-stu-id="52539-111">Divide</span></span>  
  
 <span data-ttu-id="52539-112">Poiché entrambi i servizi implementano le stesse operazioni, non è possibile usare il filtro Action, perché l'azione specificata nel messaggio non risulterebbe univoca.</span><span class="sxs-lookup"><span data-stu-id="52539-112">Because both services implement the same operations, you cannot use the Action filter, because the action specified in the message will not be unique.</span></span> <span data-ttu-id="52539-113">È invece necessario eseguire ulteriori attività per accertarsi che i messaggi vengano indirizzati agli endpoint appropriati.</span><span class="sxs-lookup"><span data-stu-id="52539-113">Instead you must do additional work to ensure that the messages are routed to the appropriate endpoints.</span></span>  
  
### <a name="determine-unique-data"></a><span data-ttu-id="52539-114">Determinare dati univoci</span><span class="sxs-lookup"><span data-stu-id="52539-114">Determine Unique Data</span></span>  
  
1. <span data-ttu-id="52539-115">Poiché entrambe le implementazioni del servizio gestiscono le stesse operazioni e sono essenzialmente identiche tranne che per i dati che restituiscono, i dati di base contenuti nei messaggi inviati dalle applicazioni client non sono sufficientemente univoci per consentire di determinare la modalità di routing della richiesta.</span><span class="sxs-lookup"><span data-stu-id="52539-115">Because both service implementations handle the same operations, and are essentially identical other than the data that they return, the base data contained in messages sent from client applications is not unique enough to allow you to determine how to route the request.</span></span> <span data-ttu-id="52539-116">Se tuttavia l'applicazione client aggiunge un valore di intestazione univoco al messaggio, sarà possibile usare tale valore per determinare la modalità di routing del messaggio.</span><span class="sxs-lookup"><span data-stu-id="52539-116">But if the client application adds a unique header value to the message, then you can use this value to determine how the message should be routed.</span></span>  
  
     <span data-ttu-id="52539-117">Ai fini di questo esempio, se per l'applicazione client è necessario che il messaggio sia elaborato con l'arrotondamento, viene aggiunta un'intestazione personalizzata con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="52539-117">For this example, if the client application needs the message to be processed by the rounding calculator, it adds a custom header by using the following code:</span></span>  
  
    ```csharp  
    messageHeadersElement.Add(MessageHeader.CreateHeader("RoundingCalculator",
                                   "http://my.custom.namespace/", "rounding"));  
    ```  
  
     <span data-ttu-id="52539-118">È quindi possibile usare il filtro XPath per verificare che i messaggi contengano l'intestazione e indirizzare quelli in cui essa è presente al servizio roundCalc.</span><span class="sxs-lookup"><span data-stu-id="52539-118">You can now use the XPath filter to inspect messages for this header, and route messages containing the header to the roundCalc service.</span></span>  
  
2. <span data-ttu-id="52539-119">Il servizio di routing espone inoltre due endpoint servizio virtuali che possono essere usati con i filtri EndpointName, EndpointAddress o PrefixEndpointAddress per indirizzare in modo univoco i messaggi in ingresso a un'implementazione specifica del servizio di calcolo in base all'endpoint a cui l'applicazione client invia la richiesta.</span><span class="sxs-lookup"><span data-stu-id="52539-119">Additionally the Routing Service exposes two virtual service endpoints that can be used with the EndpointName, EndpointAddress, or PrefixEndpointAddress filters to uniquely route incoming messages to a specific calculator implementation based on the endpoint to which the client application submits the request.</span></span>  
  
### <a name="define-endpoints"></a><span data-ttu-id="52539-120">Definire gli endpoint</span><span class="sxs-lookup"><span data-stu-id="52539-120">Define Endpoints</span></span>  
  
1. <span data-ttu-id="52539-121">Quando si definiscono gli endpoint usati dal servizio di routing, è innanzitutto necessario determinare la forma del canale usato dai client e dai servizi.</span><span class="sxs-lookup"><span data-stu-id="52539-121">When defining the endpoints used by the Routing Service, you should first determine the shape of the channel used by your clients and services.</span></span> <span data-ttu-id="52539-122">In questo scenario entrambi i servizi di destinazione usano un modello di tipo request/reply, pertanto viene usato <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span><span class="sxs-lookup"><span data-stu-id="52539-122">In this scenario both the destination services use a request-reply pattern, so the <xref:System.ServiceModel.Routing.IRequestReplyRouter> is used.</span></span> <span data-ttu-id="52539-123">Nell'esempio seguente vengono definiti gli endpoint servizio esposti dal servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="52539-123">The following example defines the service endpoints exposed by the Routing Service.</span></span>  
  
    ```xml  
    <services>  
          <service behaviorConfiguration="routingConfiguration"  
                   name="System.ServiceModel.Routing.RoutingService">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost/routingservice/router" />  
              </baseAddresses>  
            </host>  
            <!--Set up the inbound endpoints for the Routing Service-->  
            <!--first create the general router endpoint-->  
            <endpoint address="general"  
                      binding="wsHttpBinding"  
                      name="routerEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
            <!--create a virtual endpoint for the regular calculator service-->  
            <endpoint address="regular/calculator"  
                      binding="wsHttpBinding"  
                      name="calculatorEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
            <!--now create a virtual endpoint for the rounding calculator-->  
            <endpoint address="rounding/calculator"  
                      binding="wsHttpBinding"  
                      name="roundingEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
  
          </service>  
    </services>  
    ```  
  
     <span data-ttu-id="52539-124">Con questa configurazione, il servizio di routing espone tre endpoint separati.</span><span class="sxs-lookup"><span data-stu-id="52539-124">With this configuration, the Routing Service exposes three separate endpoints.</span></span> <span data-ttu-id="52539-125">A seconda delle scelte di runtime, l'applicazione client invia messaggi a uno di questi indirizzi.</span><span class="sxs-lookup"><span data-stu-id="52539-125">Depending on run-time choices, the client application sends messages to one of these addresses.</span></span> <span data-ttu-id="52539-126">I messaggi che arrivano a uno degli endpoint del servizio "virtuali" ("arrotondamento/calcolo" o "normale/calcolatore") vengono inoltrati all'implementazione della calcolatrice corrispondente.</span><span class="sxs-lookup"><span data-stu-id="52539-126">Messages arriving at one of the "virtual" service endpoints ("rounding/calculator" or "regular/calculator") are forwarded to the corresponding calculator implementation.</span></span> <span data-ttu-id="52539-127">Se l'applicazione client non invia la richiesta a un determinato endpoint, il messaggio viene indirizzato all'endpoint generale.</span><span class="sxs-lookup"><span data-stu-id="52539-127">If the client application doesn’t send the request to a particular endpoint, the message is addressed to the general endpoint.</span></span> <span data-ttu-id="52539-128">Indipendentemente dall'endpoint scelto, è inoltre possibile che l'applicazione client scelga di includere l'intestazione personalizzata per indicare che il messaggio deve essere inoltrato all'implementazione del servizio di calcolo che esegue l'arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="52539-128">Regardless of the endpoint chosen, the client application may also choose to include the custom header to indicate that the message should be forwarded to the rounding calculator implementation.</span></span>  
  
2. <span data-ttu-id="52539-129">Nell'esempio di codice vengono definiti gli endpoint client (destinazione) a cui il servizio di routing indirizza i messaggi.</span><span class="sxs-lookup"><span data-stu-id="52539-129">The following example defines the client (destination) endpoints that the Routing Service routes messages to.</span></span>  
  
    ```xml  
    <client>  
          <endpoint name="regularCalcEndpoint"  
                    address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
  
          <endpoint name="roundingCalcEndpoint"  
                    address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
    </client>  
    ```  
  
     <span data-ttu-id="52539-130">Questi endpoint vengono usati nella tabella dei filtri per indicare l'endpoint di destinazione a cui viene inviato il messaggio quando quest'ultimo corrisponde a uno specifico filtro.</span><span class="sxs-lookup"><span data-stu-id="52539-130">These endpoints are used in the filter table to indicate the destination endpoint the message is sent to when it matches a specific filter.</span></span>  
  
### <a name="define-filters"></a><span data-ttu-id="52539-131">Definisci filtri</span><span class="sxs-lookup"><span data-stu-id="52539-131">Define Filters</span></span>  
  
1. <span data-ttu-id="52539-132">Per instradare i messaggi in base all'intestazione personalizzata "RoundingCalculator" che l'applicazione client aggiunge al messaggio, definire un filtro che utilizza una query XPath per verificare la presenza di questa intestazione.</span><span class="sxs-lookup"><span data-stu-id="52539-132">To route messages based on the "RoundingCalculator" custom header that the client application adds to the message, define a filter that uses an XPath query to check for the presence of this header.</span></span> <span data-ttu-id="52539-133">Poiché questa intestazione viene definita utilizzando uno spazio dei nomi personalizzato, aggiungere anche una voce dello spazio dei nomi che definisce un prefisso dello spazio dei nomi personalizzato "custom" utilizzato nella query XPath.</span><span class="sxs-lookup"><span data-stu-id="52539-133">Because this header is defined by using a custom namespace, also add a namespace entry that defines a custom namespace prefix of "custom" that is used in the XPath query.</span></span> <span data-ttu-id="52539-134">Nell'esempio seguente vengono definiti la sezione di routing, la tabella dello spazio dei nomi e il filtro XPath necessari.</span><span class="sxs-lookup"><span data-stu-id="52539-134">The following example defines the necessary routing section, namespace table, and XPath filter.</span></span>  
  
    ```xml  
    <routing>  
          <!-- use the namespace table element to define a prefix for our custom namespace-->  
          <namespaceTable>  
            <add prefix="custom" namespace="http://my.custom.namespace/"/>  
          </namespaceTable>  
          <filters>  
            <!--define the different message filters-->  
            <!--define an xpath message filter to look for the custom header coming from the client-->  
            <filter name="XPathFilter" filterType="XPath"
                    filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 'rounding'"/>  
          </filters>  
    </routing>  
    ```  
  
     <span data-ttu-id="52539-135">Questo **MessageFilter** cerca un'intestazione RoundingCalculator nel messaggio che contiene il valore "rounding".</span><span class="sxs-lookup"><span data-stu-id="52539-135">This **MessageFilter** looks for a RoundingCalculator header in the message that contains a value of "rounding".</span></span> <span data-ttu-id="52539-136">Questa intestazione viene impostata dal client per indicare che il messaggio deve essere indirizzato al servizio roundingCalc.</span><span class="sxs-lookup"><span data-stu-id="52539-136">This header is set by the client to indicate that the message should be routed to the roundingCalc service.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="52539-137">Il prefisso dello spazio dei nomi s12 è `http://www.w3.org/2003/05/soap-envelope`definito per impostazione predefinita nella tabella dello spazio dei nomi e rappresenta lo spazio dei nomi .</span><span class="sxs-lookup"><span data-stu-id="52539-137">The s12 namespace prefix is defined by default in the namespace table, and represents the namespace `http://www.w3.org/2003/05/soap-envelope`.</span></span>
  
2. <span data-ttu-id="52539-138">È inoltre necessario definire filtri che cercano i messaggi ricevuti nei due endpoint virtuali.</span><span class="sxs-lookup"><span data-stu-id="52539-138">You must also define filters that look for messages received on the two virtual endpoints.</span></span> <span data-ttu-id="52539-139">Il primo endpoint virtuale è l'endpoint "regolare/calcolatore".</span><span class="sxs-lookup"><span data-stu-id="52539-139">The first virtual endpoint is the "regular/calculator" endpoint.</span></span> <span data-ttu-id="52539-140">Il client può inviare richieste all'endpoint per indicare che il messaggio deve essere indirizzato al servizio regularCalc.</span><span class="sxs-lookup"><span data-stu-id="52539-140">The client can send requests to this endpoint to indicate that the message should be routed to the regularCalc service.</span></span> <span data-ttu-id="52539-141">Nella configurazione seguente viene definito un filtro che usa <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter> per determinare se il messaggio è arrivato tramite un endpoint con il nome specificato in filterData.</span><span class="sxs-lookup"><span data-stu-id="52539-141">The following configuration defines a filter that uses the <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter> to determine if the message arrived through an endpoint with the name specified in filterData.</span></span>  
  
    ```xml  
    <!--define an endpoint name filter looking for messages that show up on the virtual regular calculator endpoint-->  
    <filter name="EndpointNameFilter" filterType="EndpointName" filterData="calculatorEndpoint"/>  
    ```  
  
     <span data-ttu-id="52539-142">Se un messaggio viene ricevuto dall'endpoint del servizio denominato `true`"calculatorEndpoint", questo filtro restituisce .</span><span class="sxs-lookup"><span data-stu-id="52539-142">If a message is received by the service endpoint named "calculatorEndpoint", this filter evaluates to `true`.</span></span>  
  
3. <span data-ttu-id="52539-143">A questo punto, definire un filtro che cerchi i messaggi inviati all'indirizzo di roundingEndpoint.</span><span class="sxs-lookup"><span data-stu-id="52539-143">Next, define a filter that looks for messages sent to the address of the roundingEndpoint.</span></span> <span data-ttu-id="52539-144">Il client può inviare richieste all'endpoint per indicare che il messaggio deve essere indirizzato al servizio roundingCalc.</span><span class="sxs-lookup"><span data-stu-id="52539-144">The client can send requests to this endpoint to indicate that the message should be routed to the roundingCalc service.</span></span> <span data-ttu-id="52539-145">La configurazione seguente definisce un <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> filtro che utilizza per determinare se il messaggio è arrivato all'endpoint "rounding/calculator".</span><span class="sxs-lookup"><span data-stu-id="52539-145">The following configuration defines a filter that uses the <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> to determine if the message arrived at the "rounding/calculator" endpoint.</span></span>  
  
    ```xml  
    <!--define a filter looking for messages that show up with the address prefix.  The corresponds to the rounding calc virtual endpoint-->  
    <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress"  
            filterData="http://localhost/routingservice/router/rounding/"/>  
    ```  
  
     <span data-ttu-id="52539-146">Se un messaggio viene ricevuto a `http://localhost/routingservice/router/rounding/` un indirizzo che inizia con, il filtro restituisce **true**.</span><span class="sxs-lookup"><span data-stu-id="52539-146">If a message is received at an address that begins with `http://localhost/routingservice/router/rounding/` then this filter evaluates to **true**.</span></span> <span data-ttu-id="52539-147">Poiché l'indirizzo di `http://localhost/routingservice/router` base utilizzato da questa configurazione è e l'indirizzo specificato per roundingEndpoint è `http://localhost/routingservice/router/rounding/calculator`"rounding/calculator", l'indirizzo completo utilizzato per comunicare con questo endpoint è , che corrisponde a questo filtro.</span><span class="sxs-lookup"><span data-stu-id="52539-147">Because the base address used by this configuration is `http://localhost/routingservice/router` and the address specified for the roundingEndpoint is "rounding/calculator", the full address used to communicate with this endpoint is `http://localhost/routingservice/router/rounding/calculator`, which matches this filter.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="52539-148">Il filtro PrefixEndpointAddress non valuta il nome host in caso di corrispondenza poiché è possibile fare riferimento a un singolo host usando diversi nomi host che potrebbero essere tutti riferimenti validi all'host da parte dell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="52539-148">The PrefixEndpointAddress filter does not evaluate the host name when performing a match, because a single host can be referred to by using a variety of host names that may all be valid ways of referring to the host from the client application.</span></span> <span data-ttu-id="52539-149">Ad esempio, tutti i valori seguenti possono fare riferimento allo stesso host:</span><span class="sxs-lookup"><span data-stu-id="52539-149">For example, all of the following may refer to the same host:</span></span>  
    >
    > - <span data-ttu-id="52539-150">localhost</span><span class="sxs-lookup"><span data-stu-id="52539-150">localhost</span></span>  
    > - <span data-ttu-id="52539-151">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="52539-151">127.0.0.1</span></span>  
    > - `www.contoso.com`  
    > - <span data-ttu-id="52539-152">ContosoWeb01</span><span class="sxs-lookup"><span data-stu-id="52539-152">ContosoWeb01</span></span>  
  
4. <span data-ttu-id="52539-153">Il filtro finale deve supportare il routing di messaggi che arrivano all'endpoint generale senza l'intestazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="52539-153">The final filter must support the routing of messages that arrive at the general endpoint without the custom header.</span></span> <span data-ttu-id="52539-154">Per questo scenario, i messaggi devono alternarsi tra i servizi regularCalc e roundingCalc.</span><span class="sxs-lookup"><span data-stu-id="52539-154">For this scenario, the messages should alternate between the regularCalc and roundingCalc services.</span></span> <span data-ttu-id="52539-155">Per supportare il routing "round robin" di questi messaggi, utilizzare un filtro personalizzato che consenta la corrispondenza di un'istanza di filtro per ogni messaggio elaborato.</span><span class="sxs-lookup"><span data-stu-id="52539-155">To support the "round robin" routing of these messages,  use a custom filter that allows one filter instance to match for each message processed.</span></span>  <span data-ttu-id="52539-156">Il codice seguente definisce due istanze di un filtro RoundRobinMessageFilter, le quali vengono raggruppate per indicare che devono alternarsi tra loro.</span><span class="sxs-lookup"><span data-stu-id="52539-156">The following defines two instances of a RoundRobinMessageFilter, which are grouped together to indicate that they should alternate between each other.</span></span>  
  
    ```xml  
    <!-- Set up the custom message filters.  In this example,   
         we'll use the example round robin message filter,   
         which alternates between the references-->  
    <filter name="RoundRobinFilter1" filterType="Custom"  
                    customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly"  
                    filterData="group1"/>  
    <filter name="RoundRobinFilter2" filterType="Custom"  
                    customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly"  
                    filterData="group1"/>  
    ```  
  
     <span data-ttu-id="52539-157">Al runtime, questo tipo di filtro alterna tutte le istanze di filtro definite di questo tipo configurate come medesimo gruppo in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="52539-157">During run time, this filter type alternates between all defined filter instances of this type that are configured as the same group into one collection.</span></span> <span data-ttu-id="52539-158">In questo modo i messaggi elaborati da `true` `RoundRobinFilter1` questo `RoundRobinFilter2`filtro personalizzato alternano la restituzione di for e .</span><span class="sxs-lookup"><span data-stu-id="52539-158">This causes messages processed by this custom filter to alternate between returning `true` for `RoundRobinFilter1` and `RoundRobinFilter2`.</span></span>  
  
### <a name="define-filter-tables"></a><span data-ttu-id="52539-159">Definire tabelle dei filtri</span><span class="sxs-lookup"><span data-stu-id="52539-159">Define Filter Tables</span></span>  
  
1. <span data-ttu-id="52539-160">Per associare i filtri agli endpoint client specifici, è necessario inserirli in una tabella di filtri.</span><span class="sxs-lookup"><span data-stu-id="52539-160">To associate the filters with specific client endpoints, you must place them within a filter table.</span></span> <span data-ttu-id="52539-161">Questo scenario di esempio usa inoltre impostazioni di priorità dei filtri, ovvero impostazioni facoltative che consentono di indicare l'ordine in cui i filtri vengono elaborati.</span><span class="sxs-lookup"><span data-stu-id="52539-161">This example scenario also uses filter priority settings, which is an optional setting that allows you to indicate the order in which filters are processed.</span></span> <span data-ttu-id="52539-162">Se non viene specificata alcuna priorità per i filtri, questi ultimi vengono tutti elaborati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="52539-162">If no filter priority is specified, all filters are evaluated simultaneously.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="52539-163">Sebbene l'impostazione di una priorità dei filtri consenta di controllare l'ordine in cui essi vengono elaborati, questa soluzione può influire negativamente sulle prestazioni del servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="52539-163">While specifying a filter priority allows you to control the order in which filters are processed, it can adversely affect the performance of the Routing Service.</span></span> <span data-ttu-id="52539-164">Se possibile, costruire la logica di filtro in modo che non sia necessario assegnare priorità ai filtri.</span><span class="sxs-lookup"><span data-stu-id="52539-164">When possible, construct filter logic so that the use of filter priorities is not required.</span></span>  
  
     <span data-ttu-id="52539-165">Di seguito viene definita la tabella dei filtri e il "XPathFilter" definito in precedenza alla tabella con priorità 2.</span><span class="sxs-lookup"><span data-stu-id="52539-165">The following defines the filter table and adds the "XPathFilter" defined earlier to the table with a priority of 2.</span></span> <span data-ttu-id="52539-166">Questa voce specifica inoltre `XPathFilter` che se corrisponde al messaggio, il `roundingCalcEndpoint`messaggio verrà instradato al file .</span><span class="sxs-lookup"><span data-stu-id="52539-166">This entry also specifies that if the `XPathFilter` matches the message, the message will be routed to the `roundingCalcEndpoint`.</span></span>  
  
    ```xml  
    <routing>  
    ...      <filters>  
    ...      </filters>  
          <filterTables>  
            <table name="filterTable1">  
              <entries>  
                <!--add the filters to the message filter table-->  
                <!--first look for the custom header, and if we find it,  
                    send the message to the rounding calc endpoint-->  
                <add filterName="XPathFilter" endpointName="roundingCalcEndpoint" priority="2"/>  
              </entries>  
            </table>  
          <filterTables>  
    </routing>  
    ```  
  
     <span data-ttu-id="52539-167">Quando si imposta una priorità dei filtri, i filtri con priorità massima vengono valutati per primi.</span><span class="sxs-lookup"><span data-stu-id="52539-167">When specifying a filter priority, the highest priority filters are evaluated first.</span></span> <span data-ttu-id="52539-168">Se uno o più filtri a un livello di priorità specifico consentono di rilevare una corrispondenza, i filtri con priorità inferiore non verranno valutati.</span><span class="sxs-lookup"><span data-stu-id="52539-168">If one or more filters at a specific priority level match, no filters at lower priority levels will be evaluated.</span></span> <span data-ttu-id="52539-169">Per questo scenario, 2 è la priorità più elevata specificata e questa è l'unica voce di filtro su questo livello.</span><span class="sxs-lookup"><span data-stu-id="52539-169">For this scenario, 2 is the highest priority specified and this is the only filter entry at this level.</span></span>  
  
2. <span data-ttu-id="52539-170">Le voci di filtro vengono definite per verificare se un messaggio viene ricevuto su un endpoint specifico controllando il nome dell'endpoint o il prefisso dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="52539-170">Filter entries were defined to check to see if a message is received on a specific endpoint by inspecting the endpoint name or the address prefix.</span></span> <span data-ttu-id="52539-171">Le voci seguenti aggiungono entrambe le voci di filtro alla tabella e le associano agli endpoint di destinazione a cui verrà indirizzato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="52539-171">The following entries add both of these filter entries to the filter table and associate them with the destination endpoints that the message will be routed to.</span></span> <span data-ttu-id="52539-172">A questi filtri viene assegnata la priorità 1 per indicare che devono essere eseguiti solo se il filtro XPath precedente non corrisponde al messaggio.</span><span class="sxs-lookup"><span data-stu-id="52539-172">These filters are set to a priority of 1 to indicate that they should only run if the previous XPath filter did not match the message.</span></span>  
  
    ```xml  
    <!--if the header wasn't there, send the message based on which virtual endpoint it arrived at-->  
    <!--we determine this through the endpoint name, or through the address prefix-->  
    <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint" priority="1"/>  
    <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint" priority="1"/>  
    ```  
  
     <span data-ttu-id="52539-173">Poiché a questi filtri è assegnata la priorità 1, verranno valutati solo se il filtro con livello di priorità 2 non corrisponde al messaggio.</span><span class="sxs-lookup"><span data-stu-id="52539-173">Because these filters have a filter priority of 1, they will only be evaluated if the filter at priority level 2 does not match the message.</span></span> <span data-ttu-id="52539-174">Inoltre, poiché a entrambi i filtri è assegnato lo stesso livello di priorità, essi verranno valutati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="52539-174">Also, because both filters have the same priority level they will be evaluated simultaneously.</span></span> <span data-ttu-id="52539-175">Poiché entrambi i filtri sono mutuamente esclusivi, solo uno di essi può corrispondere al messaggio.</span><span class="sxs-lookup"><span data-stu-id="52539-175">Because both filters are mutually exclusive, it is possible for only one or the other to match a message.</span></span>  
  
3. <span data-ttu-id="52539-176">Se un messaggio non corrisponde ad alcuno dei filtri precedenti, è stato ricevuto tramite l'endpoint servizio generico e non contiene informazioni di intestazione indicanti l'endpoint a cui indirizzarlo.</span><span class="sxs-lookup"><span data-stu-id="52539-176">If a message does not match any of the previous filters, then the message was received through the generic service endpoint and contained no header information that indicates where to route it.</span></span> <span data-ttu-id="52539-177">Questi messaggi devono essere gestiti dal filtro personalizzato che bilancia il carico tra i due servizi di calcolo.</span><span class="sxs-lookup"><span data-stu-id="52539-177">These messages are to be handled by the custom filter, which load balances them between the two calculator services.</span></span> <span data-ttu-id="52539-178">Nell'esempio seguente viene illustrato come aggiungere le voci di filtro alla tabella dei filtri. Ogni filtro è associato a uno dei due endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="52539-178">The following example demonstrates how to add the filter entries to the filter table; each filter is associated with one of the two destination endpoints.</span></span>  
  
    ```xml  
    <!--if none of the other filters have matched,   
        this message showed up on the default router endpoint,   
        with no custom header-->  
    <!--round robin these requests between the two services-->  
    <add filterName="RoundRobinFilter1" endpointName="regularCalcEndpoint" priority="0"/>  
    <add filterName="RoundRobinFilter2" endpointName="roundingCalcEndpoint" priority="0"/>  
    ```  
  
     <span data-ttu-id="52539-179">Poiché per queste voci è specificata una priorità pari a 0, verranno valutate solo se nessun filtro di priorità più elevata corrisponde al messaggio.</span><span class="sxs-lookup"><span data-stu-id="52539-179">Because these entries specify a priority of 0, they will only be evaluated if no filter of a higher priority matches the message.</span></span> <span data-ttu-id="52539-180">Inoltre, poiché a entrambe è assegnata la stessa priorità, verranno valutate contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="52539-180">Also, since both are of the same priority, they are evaluated simultaneously.</span></span>  
  
     <span data-ttu-id="52539-181">Come indicato in precedenza, il filtro personalizzato usato dalle definizioni di filtro restituisce `true` per uno o l'altro per ciascun messaggio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="52539-181">As mentioned previously, the custom filter used by these filter definitions only evaluates one or the other as `true` for each message received.</span></span> <span data-ttu-id="52539-182">Poiché sono definiti solo due filtri con questo filtro, con la stessa impostazione di gruppo, ne consegue che il servizio di routing alterna l'invio a regularCalcEndpoint e RoundingCalcEndpoint.</span><span class="sxs-lookup"><span data-stu-id="52539-182">Because only two filters are defined using this filter, with the same specified group setting, the effect is that the Routing Service alternates between sending to the regularCalcEndpoint and the RoundingCalcEndpoint.</span></span>  
  
4. <span data-ttu-id="52539-183">Per valutare i messaggi rispetto ai filtri, è prima necessario associare la tabella dei filtri agli endpoint del servizio che verranno usati per ricevere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="52539-183">To evaluate messages against the filters, the filter table must first be associated with the service endpoints that will be used to receive messages.</span></span>  <span data-ttu-id="52539-184">Nell'esempio seguente viene illustrato come associare la tabella di routing agli endpoint del servizio mediante il comportamento di routing:</span><span class="sxs-lookup"><span data-stu-id="52539-184">The following example demonstrates how to associate the routing table with the service endpoints by using the routing behavior:</span></span>  
  
    ```xml  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a><span data-ttu-id="52539-185">Esempio</span><span class="sxs-lookup"><span data-stu-id="52539-185">Example</span></span>  
 <span data-ttu-id="52539-186">Il codice seguente costituisce un elenco completo del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="52539-186">The following is a complete listing of the configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright (c) Microsoft Corporation. All rights reserved -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoints for the Routing Service-->  
        <!--first create the general router endpoint-->  
        <endpoint address="general"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <!--create a virtual endpoint for the regular calculator service-->  
        <endpoint address="regular/calculator"  
                  binding="wsHttpBinding"  
                  name="calculatorEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <!--now create a virtual endpoint for the rounding calculator-->  
        <endpoint address="rounding/calculator"  
                  binding="wsHttpBinding"  
                  name="roundingEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
  
      </service>  
    </services>  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
    <client>  
<!--set up the destination endpoints-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <endpoint name="roundingCalcEndpoint"  
                address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
      <namespaceTable>  
        <add prefix="custom" namespace="http://my.custom.namespace/"/>  
      </namespaceTable>  
      <filters>  
        <!--define the different message filters-->  
        <!--define an xpath message filter to look for the custom header coming from the client-->  
        <filter name="XPathFilter" filterType="XPath" filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 'rounding'"/>  
  
        <!--define an endpoint name filter looking for messages that show up on the virtual regular calculator endpoint-->  
        <filter name="EndpointNameFilter" filterType="EndpointName" filterData="calculatorEndpoint"/>  
  
        <!--define a filter looking for messages that show up with the address prefix.  The corresponds to the rounding calc virtual endpoint-->  
        <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress" filterData="http://localhost/routingservice/router/rounding/"/>  
  
        <!--Set up the custom message filters.  In this example, we'll use the example round robin message filter, which alternates between the references-->  
        <filter name="RoundRobinFilter1" filterType="Custom" customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly" filterData="group1"/>  
        <filter name="RoundRobinFilter2" filterType="Custom" customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly" filterData="group1"/>  
      </filters>  
      <filterTables>  
        <table name="filterTable1">  
          <entries>  
            <!--add the filters to the message filter table-->  
            <!--first look for the custom header, and if we find it, send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilter" endpointName="roundingCalcEndpoint" priority="2"/>  
  
            <!--if the header wasn't there, send the message based on which virtual endpoint it arrived at-->  
            <!--we determine this through the endpoint name, or through the address prefix-->  
            <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint" priority="1"/>  
            <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint" priority="1"/>  
  
            <!--if none of the other filters have matched, this message showed up on the default router endpoint, with no custom header-->  
            <!--round robin these requests between the two services-->  
            <add filterName="RoundRobinFilter1" endpointName="regularCalcEndpoint" priority="0"/>  
            <add filterName="RoundRobinFilter2" endpointName="roundingCalcEndpoint" priority="0"/>  
          </entries>  
        </table>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="52539-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52539-187">See also</span></span>

- [<span data-ttu-id="52539-188">Servizi di routing</span><span class="sxs-lookup"><span data-stu-id="52539-188">Routing Services</span></span>](../../../../docs/framework/wcf/samples/routing-services.md)
