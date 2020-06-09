---
title: 'Procedura: partizionamento dei dati del servizio'
ms.date: 03/30/2017
ms.assetid: 1ccff72e-d76b-4e36-93a2-e51f7b32dc83
ms.openlocfilehash: 3b2f86ee6a4dea25fb5c972d4cecb1b9ed411b29
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601192"
---
# <a name="how-to-service-data-partitioning"></a><span data-ttu-id="7135a-102">Procedura: partizionamento dei dati del servizio</span><span class="sxs-lookup"><span data-stu-id="7135a-102">How To: Service Data Partitioning</span></span>
<span data-ttu-id="7135a-103">In questo argomento vengono descritti i passaggi di base necessari per partizionare messaggi tra più istanze dello stesso servizio di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7135a-103">This topic outlines the basic steps required to partition messages across multiple instances of the same destination service.</span></span> <span data-ttu-id="7135a-104">Il partizionamento dei dati del servizio viene in genere utilizzato quando è necessario ridimensionare un servizio per fornire un livello migliore di qualità del servizio o gestire richieste da diversi clienti in modo specifico.</span><span class="sxs-lookup"><span data-stu-id="7135a-104">Service data partitioning is typically used when you need to scale a service in order to provide better quality of service, or when you need to handle requests from different customers in a specific way.</span></span> <span data-ttu-id="7135a-105">Ad esempio, potrebbe essere necessario elaborare i messaggi di clienti di valore elevato o "Gold" con una priorità più alta rispetto ai messaggi di un cliente standard.</span><span class="sxs-lookup"><span data-stu-id="7135a-105">For example, messages from high value or "Gold" customers may need to be processed at a higher priority than messages from a standard customer.</span></span>  
  
 <span data-ttu-id="7135a-106">In questo esempio i messaggi vengono indirizzati a una o due istanze del servizio regularCalc.</span><span class="sxs-lookup"><span data-stu-id="7135a-106">In this example, messages are routed to one of two instances of the regularCalc service.</span></span> <span data-ttu-id="7135a-107">Entrambe le istanze del servizio sono identiche. Il servizio rappresentato dall'endpoint di calculator1 elabora tuttavia i messaggi ricevuti dai clienti di valore elevato, mentre l'endpoint di calculator2 elabora i messaggi ricevuti dagli altri clienti</span><span class="sxs-lookup"><span data-stu-id="7135a-107">Both instances of the service are identical; however the service represented by the calculator1 endpoint processes messages received from high value customers, the calculator 2 endpoint processes messages from other customers</span></span>  
  
 <span data-ttu-id="7135a-108">Il messaggio inviato dal client non dispone di dati univoci che possono essere utilizzati per identificare l'istanza del servizio a cui indirizzare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7135a-108">The message sent from the client does not have any unique data that can be used to identify which service instance the message should be routed to.</span></span> <span data-ttu-id="7135a-109">Per consentire a ogni client di indirizzare dati a un servizio di destinazione specifico, verranno implementati due endpoint servizio che verranno utilizzati per ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="7135a-109">To allow each client to route data to a specific destination service we will implement two service endpoints that will be used to receive messages.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7135a-110">Mentre in questo esempio vengono utilizzati endpoint specifici per partizionare dati, è possibile portare a termine questa operazione anche utilizzando le informazioni contenute all'interno del messaggio stesso, ad esempio l'intestazione o i dati del corpo.</span><span class="sxs-lookup"><span data-stu-id="7135a-110">While this example uses specific endpoints to partition data, this could also be accomplished using information contained within the message itself such as header or body data.</span></span>  
  
### <a name="implement-service-data-partitioning"></a><span data-ttu-id="7135a-111">Implementare il partizionamento dei dati del servizio</span><span class="sxs-lookup"><span data-stu-id="7135a-111">Implement Service Data Partitioning</span></span>  
  
1. <span data-ttu-id="7135a-112">Creare la configurazione del servizio di routing di base specificando gli endpoint servizio esposti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="7135a-112">Create the basic Routing Service configuration by specifying the service endpoints exposed by the service.</span></span> <span data-ttu-id="7135a-113">Nell'esempio seguente vengono definiti due endpoint che verranno utilizzati per ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="7135a-113">The following example defines two endpoints, which will be used to receive messages.</span></span> <span data-ttu-id="7135a-114">Vengono inoltre definiti gli endpoint client, utilizzati per inviare messaggi alle istanze del servizio regularCalc.</span><span class="sxs-lookup"><span data-stu-id="7135a-114">It also defines the client endpoints, which are used to send messages to the regularCalc service instances.</span></span>  
  
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
        <!--create the endpoints for the calculator service-->  
        <endpoint address="calculator1"  
                  binding="wsHttpBinding"  
                  name="calculator1Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <endpoint address="calculator2"  
                  binding="wsHttpBinding"  
                  name="calculator2Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
       </service>  
    </services>  
    <client>  
    <!--set up the destination endpoints-->  
        <endpoint name="CalcEndpoint1"  
                  address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                  binding="netTcpBinding"  
                  contract="*" />  
  
        <endpoint name="CalcEndpoint2"  
                  address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                  binding="netTcpBinding"  
                  contract="*" />  
     </client>  
    ```  
  
2. <span data-ttu-id="7135a-115">Definire i filtri usati per indirizzare messaggi agli endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7135a-115">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="7135a-116">Ai fini di questo esempio viene utilizzato il filtro EndpointName per determinare quale endpoint servizio ha ricevuto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7135a-116">For this example, the EndpointName filter is used to determine which service endpoint received the message.</span></span> <span data-ttu-id="7135a-117">Nell'esempio seguente vengono definiti i filtri e la sezione di routing necessari.</span><span class="sxs-lookup"><span data-stu-id="7135a-117">The following example defines the necessary routing section and filters.</span></span>  
  
    ```xml  
    <filters>  
      <!--define the different message filters-->  
      <!--define endpoint name filters looking for messages that show up on the virtual endpoints-->  
      <filter name="HighPriority" filterType="EndpointName"  
              filterData="calculator1Endpoint"/>  
      <filter name="NormalPriority" filterType="EndpointName"  
              filterData="calculator2Endpoint"/>  
    </filters>  
    ```  
  
3. <span data-ttu-id="7135a-118">Definire la tabella dei filtri, che associa ogni filtro a un endpoint client.</span><span class="sxs-lookup"><span data-stu-id="7135a-118">Define the filter table, which associates each filter with a client endpoint.</span></span> <span data-ttu-id="7135a-119">In questo esempio il messaggio verrà indirizzato in base all'endpoint specifico su cui è stato ricevuto.</span><span class="sxs-lookup"><span data-stu-id="7135a-119">In this example, the message will be routed based on the specific endpoint it was received over.</span></span> <span data-ttu-id="7135a-120">Poiché il messaggio può corrispondere solo a uno dei due possibili filtri, non è necessario utilizzare la priorità del filtro per controllare l'ordine di valutazione dei filtri.</span><span class="sxs-lookup"><span data-stu-id="7135a-120">Since the message can only match one of the two possible filters, there is no need for using filter priority to control to the order in which filters are evaluated.</span></span>  
  
     <span data-ttu-id="7135a-121">Di seguito viene definita la tabella dei filtri e vengono aggiunti i filtri definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7135a-121">The following defines the filter table and adds the filters defined earlier.</span></span>  
  
    ```xml  
    <filterTables>  
       <filterTable name="filterTable1">  
         <!--add the filters to the message filter table-->  
         <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
         <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
       </filterTable>  
    </filterTables>  
    ```  
  
4. <span data-ttu-id="7135a-122">Per valutare i messaggi in ingresso rispetto ai filtri contenuti nella tabella, è necessario associare la tabella dei filtri agli endpoint servizio tramite il comportamento di routing.</span><span class="sxs-lookup"><span data-stu-id="7135a-122">To evaluate incoming messages against the filters contained in the table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="7135a-123">Nell'esempio seguente viene illustrata l'associazione di "filterTable1" con gli endpoint del servizio:</span><span class="sxs-lookup"><span data-stu-id="7135a-123">The following example demonstrates associating "filterTable1" with the service endpoints:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="7135a-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="7135a-124">Example</span></span>  
 <span data-ttu-id="7135a-125">Il codice seguente costituisce un elenco completo del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7135a-125">The following is a complete listing of the configuration file.</span></span>  
  
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
        <!--create the endpoints for the calculator service-->  
        <endpoint address="calculator1"  
                  binding="wsHttpBinding"  
                  name="calculator1Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <endpoint address="calculator2"  
                  binding="wsHttpBinding"  
                  name="calculator2Endpoint"  
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
      <endpoint name="CalcEndpoint1"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <endpoint name="CalcEndpoint2"  
                address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
  
      <filters>  
        <!--define the different message filters-->  
        <!--define endpoint name filters looking for messages that show up on the virtual endpoints-->  
        <filter name="HighPriority" filterType="EndpointName"  
                filterData="calculator1Endpoint"/>  
        <filter name="NormalPriority" filterType="EndpointName"  
                filterData="calculator2Endpoint"/>  
      </filters>  
  
      <filterTables>  
        <filterTable name="filterTable1">  
          <!--add the filters to the message filter table-->  
          <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
          <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
        </filterTable>  
      </filterTables>  
  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7135a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7135a-126">See also</span></span>

- [<span data-ttu-id="7135a-127">Servizi di routing</span><span class="sxs-lookup"><span data-stu-id="7135a-127">Routing Services</span></span>](../samples/routing-services.md)
