---
title: 'Procedura: controllo delle versioni dei servizi'
ms.date: 03/30/2017
ms.assetid: 4287b6b3-b207-41cf-aebe-3b1d4363b098
ms.openlocfilehash: 3cd52e1f52a93e408ebed846894cc5686652cc91
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184852"
---
# <a name="how-to-service-versioning"></a><span data-ttu-id="9d867-102">Procedura: controllo delle versioni dei servizi</span><span class="sxs-lookup"><span data-stu-id="9d867-102">How To: Service Versioning</span></span>
<span data-ttu-id="9d867-103">In questo argomento vengono descritti i passaggi di base necessari per creare una configurazione del routing che indirizza messaggi a versioni diverse dello stesso servizio.</span><span class="sxs-lookup"><span data-stu-id="9d867-103">This topic outlines the basic steps required to create a routing configuration that routes messages to different versions of the same service.</span></span> <span data-ttu-id="9d867-104">In questo esempio i messaggi vengono indirizzati a due versioni diverse di un servizio di calcolo, `roundingCalc` (v1) e `regularCalc` (v2).</span><span class="sxs-lookup"><span data-stu-id="9d867-104">In this example, messages are routed to two different versions of a calculator service, `roundingCalc` (v1) and `regularCalc` (v2).</span></span> <span data-ttu-id="9d867-105">Entrambe le implementazioni supportano le stesse operazioni; tuttavia il primo servizio, `roundingCalc`, arrotonda tutti i calcoli al valore intero più vicino prima della restituzione.</span><span class="sxs-lookup"><span data-stu-id="9d867-105">Both implementations support the same operations; however the older service, `roundingCalc`, rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="9d867-106">Un'applicazione client deve essere in grado di indicare se utilizzare il secondo servizio, `regularCalc`.</span><span class="sxs-lookup"><span data-stu-id="9d867-106">A client application must be able to indicate whether to use the newer `regularCalc` service.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="9d867-107">Per indirizzare un messaggio a una specifica versione del servizio, il servizio di routing deve essere in grado di determinare la destinazione del messaggio in base al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="9d867-107">In order to route a message to a specific service version, the Routing Service must be able to determine the message destination based on the message content.</span></span> <span data-ttu-id="9d867-108">Nel metodo illustrato di seguito il client specifica la versione inserendo informazioni in un'intestazione di messaggio.</span><span class="sxs-lookup"><span data-stu-id="9d867-108">In the method demonstrated below, the client will specify the version by inserting information into a message header.</span></span> <span data-ttu-id="9d867-109">Esistono metodi di controllo delle versioni del servizio che non richiedono il passaggio di dati aggiuntivi da parte dei client.</span><span class="sxs-lookup"><span data-stu-id="9d867-109">There are methods of service versioning that do not require clients to pass additional data.</span></span> <span data-ttu-id="9d867-110">Un messaggio potrebbe essere ad esempio indirizzato alla versione più recente o più compatibile di un servizio oppure una parte del relativo elemento SOAP Envelope standard potrebbe essere utilizzato dal router.</span><span class="sxs-lookup"><span data-stu-id="9d867-110">For example, a message could be routed to the most recent or most compatible version of a service or the router could use a part of the standard SOAP envelope.</span></span>  
  
 <span data-ttu-id="9d867-111">Le operazioni esposte da entrambi servizi sono:</span><span class="sxs-lookup"><span data-stu-id="9d867-111">The operations exposed by both services are:</span></span>  
  
- <span data-ttu-id="9d867-112">Add</span><span class="sxs-lookup"><span data-stu-id="9d867-112">Add</span></span>  
  
- <span data-ttu-id="9d867-113">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="9d867-113">Subtract</span></span>  
  
- <span data-ttu-id="9d867-114">Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="9d867-114">Multiply</span></span>  
  
- <span data-ttu-id="9d867-115">Divisione</span><span class="sxs-lookup"><span data-stu-id="9d867-115">Divide</span></span>  
  
 <span data-ttu-id="9d867-116">Poiché entrambe le implementazioni del servizio gestiscono le stesse operazioni e sono essenzialmente identiche tranne che per i dati che restituiscono, i dati di base contenuti nei messaggi inviati dalle applicazioni client non sono sufficientemente univoci per consentire di determinare la modalità di routing della richiesta.</span><span class="sxs-lookup"><span data-stu-id="9d867-116">Because both service implementations handle the same operations, and are essentially identical other than the data that they return, the base data contained in messages sent from client applications is not unique enough to allow you to determine how to route the request.</span></span> <span data-ttu-id="9d867-117">Non è ad esempio possibile utilizzare i filtri Action, poiché le azioni predefinite per entrambi i servizi sono identiche.</span><span class="sxs-lookup"><span data-stu-id="9d867-117">For example, Action filters cannot be used because the default actions for both services are the same.</span></span>  
  
 <span data-ttu-id="9d867-118">È possibile risolvere questo problema in diversi modi, ad esempio esponendo un endpoint specifico sul router per ogni versione del servizio o aggiungendo un elemento di intestazione personalizzato al messaggio per indicare la versione del servizio.</span><span class="sxs-lookup"><span data-stu-id="9d867-118">This can be resolved in several ways, such as exposing a specific endpoint on the router for each version of the service or adding a custom header element to the message to indicate service version.</span></span>  <span data-ttu-id="9d867-119">Ognuno di questi approcci consente di indirizzare in modo univoco messaggi in ingresso a una versione specifica del servizio, ma l'utilizzo di contenuti univoci nei messaggi è il metodo preferibile per distinguere le richieste indirizzate a versioni diverse del servizio.</span><span class="sxs-lookup"><span data-stu-id="9d867-119">Each of these approaches allows you to uniquely route incoming messages to a specific version of the service, but utilizing unique message content is the preferred method of differentiating between requests for different service versions.</span></span>  
  
 <span data-ttu-id="9d867-120">In questo esempio l'applicazione client aggiunge l'intestazione personalizzata 'CalcVer' al messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="9d867-120">In this example, the client application adds the ‘CalcVer’ custom header to the request message.</span></span> <span data-ttu-id="9d867-121">Questa intestazione contiene un valore che indica la versione del servizio a cui deve essere indirizzato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="9d867-121">This header will contain a value that indicates the version of the service that the message should be routed to.</span></span> <span data-ttu-id="9d867-122">Il valore '1' indica che il messaggio deve essere elaborato dal servizio roundingCalc, mentre il valore '2' indica il servizio regularCalc.</span><span class="sxs-lookup"><span data-stu-id="9d867-122">A value of ‘1’ indicates that the message must be processed by the roundingCalc service, while a value of ‘2’ indicates the regularCalc service.</span></span> <span data-ttu-id="9d867-123">In questo modo l'applicazione client può controllare direttamente quale versione del servizio elaborerà il messaggio.</span><span class="sxs-lookup"><span data-stu-id="9d867-123">This allows the client application to directly control which version of the service will process the message.</span></span>  <span data-ttu-id="9d867-124">Poiché l'intestazione personalizzata è un valore contenuto all'interno del messaggio, è possibile utilizzare un endpoint per ricevere messaggi destinati a entrambe le versioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="9d867-124">Since the custom header is a value contained within the message, you can use one endpoint to receive messages destined for both versions of the service.</span></span> <span data-ttu-id="9d867-125">Il codice seguente può essere utilizzato nell'applicazione client per aggiungere l'intestazione personalizzata al messaggio:</span><span class="sxs-lookup"><span data-stu-id="9d867-125">The following code can be used in the client application to add this custom header to the message:</span></span>  
  
```csharp  
messageHeadersElement.Add(MessageHeader.CreateHeader("CalcVer", "http://my.custom.namespace/", "2"));  
```  
  
### <a name="implement-service-versioning"></a><span data-ttu-id="9d867-126">Implementare il controllo delle versioni del servizio</span><span class="sxs-lookup"><span data-stu-id="9d867-126">Implement Service Versioning</span></span>  
  
1. <span data-ttu-id="9d867-127">Creare la configurazione del servizio di routing di base specificando l'endpoint servizio esposto dal servizio.</span><span class="sxs-lookup"><span data-stu-id="9d867-127">Create the basic Routing Service configuration by specifying the service endpoint exposed by the service.</span></span> <span data-ttu-id="9d867-128">Nell'esempio seguente viene definito un solo endpoint servizio che verrà utilizzato per ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="9d867-128">The following example defines a single service endpoint, which will be used to receive messages.</span></span> <span data-ttu-id="9d867-129">Vengono inoltre definiti gli endpoint client che verranno utilizzati per inviare messaggi ai servizi `roundingCalc` (v1) `regularCalc` (v2).</span><span class="sxs-lookup"><span data-stu-id="9d867-129">It also defines the client endpoints which will be used to send messages to the `roundingCalc` (v1) and the `regularCalc` (v2) services.</span></span>  
  
    ```xml  
    <services>  
        <service behaviorConfiguration="routingConfiguration"  
                 name="System.ServiceModel.Routing.RoutingService">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost/routingservice/router" />  
            </baseAddresses>  
          </host>  
          <!--Set up the inbound endpoint for the Routing Service-->  
          <endpoint address="calculator"  
                    binding="wsHttpBinding"  
                    name="routerEndpoint"  
                    contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        </service>  
    </services>  
    <client>  
    <!--set up the destination endpoints-->  
          <endpoint name="regularCalcEndpoint"  
                    address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
  
          <endpoint name="roundingCalcEndpoint"  
                    address="http://localhost:8080/servicemodelsamples/service/"  
                    binding="wsHttpBinding"  
                    contract="*" />  
        </client>  
    ```  
  
2. <span data-ttu-id="9d867-130">Definire i filtri usati per indirizzare messaggi agli endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9d867-130">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="9d867-131">Per questo esempio, il filtro XPath viene utilizzato per rilevare il valore dell'intestazione personalizzata "CalcVer" per determinare a quale versione deve essere instradato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="9d867-131">For this example, the XPath filter is used to detect the value of the "CalcVer" custom header to determine which version the message should be routed to.</span></span> <span data-ttu-id="9d867-132">Un filtro XPath viene utilizzato anche per rilevare i messaggi che non contengono l'intestazione "CalcVer".</span><span class="sxs-lookup"><span data-stu-id="9d867-132">An XPath filter is also used to detect messages that do not contain the "CalcVer" header.</span></span> <span data-ttu-id="9d867-133">Nell'esempio seguente vengono definiti la tabella dello spazio dei nomi e dei filtri necessari.</span><span class="sxs-lookup"><span data-stu-id="9d867-133">The following example defines the required filters and namespace table.</span></span>  
  
    ```xml  
    <!-- use the namespace table element to define a prefix for our custom namespace-->  
    <namespaceTable>  
      <add prefix="custom" namespace="http://my.custom.namespace/"/>  
    </namespaceTable>  
    <filters>  
      <!--define the different message filters-->  
      <!--define an xpath message filter to look for the  
          custom header containing a value of 2-->  
      <filter name="XPathFilterRegular" filterType="XPath"  
              filterData="sm:header()/custom:CalcVer = '2'"/>  
      <!--define an xpath message filter to look for the  
          custom header containing a value of 1-->  
      <filter name="XPathFilterRounding" filterType="XPath"  
              filterData="sm:header()/custom:CalcVer = '1'"/>  
       <!--define an xpath message filter to look for  
           messages that do not contain the custom header-->  
       <filter name="XPathFilterNoHeader" filterType="XPath"  
               filterData="count(sm:header()/custom:CalcVer)=0"/>  
    </filters  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="9d867-134">Il prefisso dello spazio dei nomi s12 è `http://www.w3.org/2003/05/soap-envelope`definito per impostazione predefinita nella tabella dello spazio dei nomi e rappresenta lo spazio dei nomi .</span><span class="sxs-lookup"><span data-stu-id="9d867-134">The s12 namespace prefix is defined by default in the namespace table, and represents the namespace `http://www.w3.org/2003/05/soap-envelope`.</span></span>
  
3. <span data-ttu-id="9d867-135">Definire la tabella dei filtri, che associa ogni filtro a un endpoint client.</span><span class="sxs-lookup"><span data-stu-id="9d867-135">Define the filter table, which associates each filter with a client endpoint.</span></span> <span data-ttu-id="9d867-136">Se il messaggio contiene l'intestazione "CalcVer" con un valore pari a 1, verrà inviato al servizio regularCalc.</span><span class="sxs-lookup"><span data-stu-id="9d867-136">If the message contains the "CalcVer" header with a value of 1, it will be sent to the regularCalc service.</span></span> <span data-ttu-id="9d867-137">Se l'intestazione contiene il valore 2, verrà inviato al servizio roundingCalc.</span><span class="sxs-lookup"><span data-stu-id="9d867-137">If the header contains a value of 2, it will be sent to the roundingCalc service.</span></span> <span data-ttu-id="9d867-138">Se non è presente alcuna intestazione, il messaggio verrà indirizzato a regularCalc.</span><span class="sxs-lookup"><span data-stu-id="9d867-138">If no header is present, the message will be routed to the regularCalc.</span></span>  
  
     <span data-ttu-id="9d867-139">Di seguito viene definita la tabella dei filtri e vengono aggiunti i filtri definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9d867-139">The following defines the filter table and adds the filters defined earlier.</span></span>  
  
    ```xml  
    <filterTables>  
      <filterTable name="filterTable1">  
          <!--add the filters to the message filter table-->  
          <!--look for the custom header = 1, and if we find it,  
              send the message to the rounding calc endpoint-->  
          <add filterName="XPathFilterRounding" endpointName="roundingCalcEndpoint"/>  
          <!--look for the custom header = 2, and if we find it,  
              send the message to the rounding calc endpoint-->  
          <add filterName="XPathFilterRegular" endpointName="regularCalcEndpoint"/>  
          <!--look for the absence of the custom header, and if  
              it is not present, assume the v1 endpoint-->  
          <add filterName="XPathFilterNoHeader" endpointName="roundingCalcEndpoint"/>  
      </filterTable>  
    </filterTables>  
    ```  
  
4. <span data-ttu-id="9d867-140">Per valutare i messaggi in ingresso rispetto ai filtri contenuti nella rispettiva tabella, è necessario associare la tabella dei filtri agli endpoint servizio tramite il comportamento di routing.</span><span class="sxs-lookup"><span data-stu-id="9d867-140">To evaluate incoming messages against the filters contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="9d867-141">Nell'esempio seguente `filterTable1` viene illustrata l'associazione agli endpoint del servizio:The following example demonstrates associating with the service endpoints:</span><span class="sxs-lookup"><span data-stu-id="9d867-141">The following example demonstrates associating `filterTable1` with the service endpoints:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="9d867-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d867-142">Example</span></span>  
 <span data-ttu-id="9d867-143">Il codice seguente costituisce un elenco completo del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9d867-143">The following is a complete listing of the configuration file.</span></span>  
  
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
        <!--Set up the inbound endpoint for the Routing Service-->  
        <endpoint address="calculator"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
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
                address="http://localhost:8080/servicemodelsamples/service/"  
                binding="wsHttpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
      <namespaceTable>  
        <add prefix="custom" namespace="http://my.custom.namespace/"/>  
      </namespaceTable>  
      <filters>  
        <!--define the different message filters-->  
        <!--define an xpath message filter to look for the  
            custom header containing a value of 2-->  
        <filter name="XPathFilterRegular" filterType="XPath"  
                filterData="sm:header()/custom:CalcVer = '2'"/>  
        <!--define an xpath message filter to look for the  
            custom header containing a value of 1-->  
        <filter name="XPathFilterRounding" filterType="XPath"  
                filterData="sm:header()/custom:CalcVer = '1'"/>  
        <!--define an xpath message filter to look for  
            messages that do not contain the custom header-->  
        <filter name="XPathFilterNoHeader" filterType="XPath"  
                filterData="count(sm:header()/custom:CalcVer)=0"/>  
      </filters>  
      <filterTables>  
        <filterTable name="filterTable1">  
            <!--add the filters to the message filter table-->  
            <!--look for the custom header = 1, and if we find it,  
                send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilterRounding" endpointName="roundingCalcEndpoint"/>  
            <!--look for the custom header = 2, and if we find it,  
                send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilterRegular" endpointName="regularCalcEndpoint"/>  
            <!--look for the absence of the custom header, and if  
                it is not present, assume the v1 endpoint-->  
            <add filterName="XPathFilterNoHeader" endpointName="roundingCalcEndpoint"/>  
        </filterTable>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="9d867-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d867-144">Example</span></span>  
 <span data-ttu-id="9d867-145">Il codice seguente costituisce un elenco completo dell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="9d867-145">The following is a complete listing of the client application.</span></span>  
  
```csharp  
using System;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
  
namespace Microsoft.Samples.AdvancedFilters  
{  
    //The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.  
  
    //Client implementation code.  
    class Client  
    {  
        static void Main()  
        {  
            //Print out the welcome text  
            Console.WriteLine("This sample routes the Calculator Sample through the new WCF RoutingService");  
            Console.WriteLine("Wait for all the services to indicate that they've started, then press");  
            Console.WriteLine("<ENTER> to start the client.");  
  
            while (Console.ReadLine() != "quit")  
            {  
                //Offer the Address configuration for the client  
                Console.WriteLine("");  
                Console.WriteLine("Welcome to the Calculator Client!");  
  
                EndpointAddress epa;  
                //set the default address as the general router endpoint  
                epa = new EndpointAddress("http://localhost/routingservice/router/calculator");  
  
                //set up the CalculatorClient with the EndpointAddress, the WSHttpBinding, and the ICalculator contract  
                //We use the WSHttpBinding so that the outgoing has a message envelope, which we'll manipulate in a minute  
                CalculatorClient client = new CalculatorClient(new WSHttpBinding(), epa);  
                //client.Endpoint.Contract = ContractDescription.GetContract(typeof(ICalculator));  
  
                //Ask the customer if they want to add a custom header to the outgoing message.  
                //The Router will look for this header, and if so ignore the endpoint the message was  
                //received on, and instead direct the message to the RoundingCalcService.  
                Console.WriteLine("");  
                Console.WriteLine("Which calculator service should be used?");  
                Console.WriteLine("Enter 1 for the rounding calculator, 2 for the regular calculator.");  
                Console.WriteLine("[1] or [2]?");  
  
                string header = Console.ReadLine();  
  
                //get the current operationContextScope from the client's inner channel  
                using (OperationContextScope ocs = new OperationContextScope((client.InnerChannel)))  
                {  
                    //get the outgoing message headers element (collection) from the context  
                    MessageHeaders messageHeadersElement = OperationContext.Current.OutgoingMessageHeaders;  
  
                    //if they wanted to create the header, go ahead and add it to the outgoing message  
                    if (header != null && (header=="1" || header=="2"))  
                    {  
                        //create a new header "RoundingCalculator", no specific namespace, and set the value to
                        //the value of header.  
                        //the Routing Service will look for this header in order to determine if the message  
                        //should be routed to the RoundingCalculator  
                        messageHeadersElement.Add(MessageHeader.CreateHeader("CalcVer", "http://my.custom.namespace/", header));  
                    }  
                    else //incorrect choice, no header added  
                    {  
                        Console.WriteLine("Incorrect value entered, not adding a header");  
                    }  
  
                        //call the client operations  
                        CallClient(client);  
                }  
  
                //close the client to clean it up  
                client.Close();  
                Console.WriteLine();  
                Console.WriteLine("Press <ENTER> to run the client again or type 'quit' to quit.");  
            }  
        }  
  
        private static void CallClient(CalculatorClient client)  
        {  
            Console.WriteLine("");  
            Console.WriteLine("Sending!");  
            // Call the Add service operation.  
            double value1 = 100.00D;  
            double value2 = 15.99D;  
            double result = client.Add(value1, value2);  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Subtract service operation.  
            value1 = 145.00D;  
            value2 = 76.54D;  
            result = client.Subtract(value1, value2);  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Multiply service operation.  
            value1 = 9.00D;  
            value2 = 81.25D;  
            result = client.Multiply(value1, value2);  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Divide service operation.  
            value1 = 22.00D;  
            value2 = 7.00D;  
            result = client.Divide(value1, value2);  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d867-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d867-146">See also</span></span>

- [<span data-ttu-id="9d867-147">Servizi di routing</span><span class="sxs-lookup"><span data-stu-id="9d867-147">Routing Services</span></span>](../../../../docs/framework/wcf/samples/routing-services.md)
