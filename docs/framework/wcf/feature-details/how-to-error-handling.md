---
title: 'Procedura: gestione degli errori'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de566e39-9358-44ff-8244-780f6b799966
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5b0fe57bb6a4604c86e63a154e3af5542672912
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-error-handling"></a><span data-ttu-id="63a6a-102">Procedura: gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="63a6a-102">How To: Error Handling</span></span>
<span data-ttu-id="63a6a-103">In questo argomento vengono descritti i passaggi di base necessari per creare una configurazione del routing che usa la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="63a6a-103">This topic outlines the basic steps required to create a routing configuration that uses error handling.</span></span> <span data-ttu-id="63a6a-104">In questo esempio i messaggi vengono indirizzati a un endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="63a6a-104">In this example, messages are routed to a destination endpoint.</span></span> <span data-ttu-id="63a6a-105">Se non è possibile recapitare un messaggio a causa di un errore di rete o relativo alle comunicazioni (<xref:System.ServiceModel.CommunicationException>), il messaggio viene nuovamente inviato a un endpoint alternativo.</span><span class="sxs-lookup"><span data-stu-id="63a6a-105">If a message cannot be delivered due to a network or communications-related failure (<xref:System.ServiceModel.CommunicationException>), the message is resent to an alternate endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63a6a-106">Per simulare un errore di rete, l'endpoint di destinazione usato in questo esempio contiene un indirizzo errato.</span><span class="sxs-lookup"><span data-stu-id="63a6a-106">To simulate a network failure, the destination endpoint used in this example contains an incorrect address.</span></span> <span data-ttu-id="63a6a-107">I messaggi indirizzati a questo endpoint hanno esito negativo, in quanto nessun servizio è in ascolto sull'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="63a6a-107">Messages routed to this endpoint fail as no service is listening on the specified address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63a6a-108">Mentre l'esempio contenuto in questo argomento non descrive in modo esplicito le impostazioni di timeout, è necessario considerarle in caso di utilizzo della gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="63a6a-108">While the example contained in this topic does not explicitly discuss time-out settings, you must take these into consideration when using error handling.</span></span> <span data-ttu-id="63a6a-109">Se vengono rilevati errori, si verificherà un ulteriore ritardo prima che il client riceverà una risposta.</span><span class="sxs-lookup"><span data-stu-id="63a6a-109">When errors are encountered, there will be an additional delay encountered before the client receives a response.</span></span> <span data-ttu-id="63a6a-110">Ciò è dovuto al fatto che l'errore viene ricevuto nel servizio di routing, che tenta quindi di inviare il messaggio a un endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="63a6a-110">This is because the error is received at the Routing Service, which then attempts to send the message to a backup endpoint.</span></span> <span data-ttu-id="63a6a-111">Se i valori di timeout associati agli endpoint di destinazione primari e di backup sono elevati, il client potrebbe subire un notevole ritardo, in quanto il messaggio ha esito negativo su più endpoint nell'elenco di backup prima di poter essere inviato.</span><span class="sxs-lookup"><span data-stu-id="63a6a-111">If the time-out values associated with the primary and backup destination endpoints are large, the client could experience a long delay as the message fails over multiple endpoints in the backup list before being successfully sent.</span></span>  
>   
>  <span data-ttu-id="63a6a-112">Poiché il servizio di routing potrebbe subire un ritardo massimo equivalente alla somma del valore di timeout per tutti gli endpoint associati a un filtro, è consigliabile aumentare di conseguenza il timeout previsto nel client.</span><span class="sxs-lookup"><span data-stu-id="63a6a-112">Since the Routing Service could encounter a maximum delay equal to the sum of the time-out value for all endpoints associated with a filter, we recommend that you increase the expected time-out at the client accordingly.</span></span>  
  
### <a name="implement-error-handling"></a><span data-ttu-id="63a6a-113">Implementare la gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="63a6a-113">Implement Error Handling</span></span>  
  
1.  <span data-ttu-id="63a6a-114">Creare la configurazione del servizio di routing di base specificando l'endpoint servizio esposto dal servizio.</span><span class="sxs-lookup"><span data-stu-id="63a6a-114">Create the basic Routing Service configuration by specifying the service endpoint exposed by the service.</span></span> <span data-ttu-id="63a6a-115">Nell'esempio seguente viene definito un solo endpoint servizio usato per ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="63a6a-115">The following example defines a single service endpoint, which is used to receive messages.</span></span> <span data-ttu-id="63a6a-116">Vengono inoltre definiti gli endpoint client usati per inviare messaggi: deadDestination e realDestination.</span><span class="sxs-lookup"><span data-stu-id="63a6a-116">It also defines the client endpoints that are used to send messages; deadDestination and realDestination.</span></span> <span data-ttu-id="63a6a-117">L'endpoint deadDestination contiene un indirizzo che non fa riferimento a un servizio in esecuzione e viene usato per simulare un errore di rete in caso di invio di messaggi a questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="63a6a-117">The deadDestination endpoint contains an address that does not reference a running service and is used to simulate a network failure when sending messages to this endpoint.</span></span>  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/" />  
          </baseAddresses>  
        </host>  
        <!-- Create the Routing Service endpoint -->  
        <endpoint address="router"  
                  binding="basicHttpBinding"  
                  name="RoutingServiceEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
  
    <!-- Create the destination endpoints that we want to send to -->  
    <client>  
      <!-- Create a dummy endpoint that we know will be down -->  
      <endpoint name="deadDestination"   
                address="net.tcp://localhost:9090/servicemodelsamples/fakeDestination"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <!-- Now create the real service endpoint -->  
      <endpoint name="realDestination"   
                address="net.tcp://localhost:8080/servicemodelsamples/service"  
                binding="netTcpBinding"   
                contract="*" />  
    </client>  
    ```  
  
2.  <span data-ttu-id="63a6a-118">Definire i filtri usati per indirizzare messaggi agli endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="63a6a-118">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="63a6a-119">Ai fini di questo esempio, viene usato un filtro MatchAll per individuare la corrispondenza con tutti i messaggi ricevuti dal servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="63a6a-119">For this example, a MatchAll filter is used to match all messages received by the Routing Service.</span></span>  
  
    ```xml  
    <filters>  
      <!-- Create a MatchAll filter which will catch all messages -->  
      <filter name="MatchAllFilter1" filterType="MatchAll" />  
    </filters>  
    ```  
  
3.  <span data-ttu-id="63a6a-120">Definire l'elenco di endpoint di backup che contiene gli endpoint a cui viene inviato un messaggio in caso di un errore di rete o relativo alle comunicazioni in fase di invio all'endpoint di destinazione primario.</span><span class="sxs-lookup"><span data-stu-id="63a6a-120">Define the backup endpoint list, which contains the endpoints that a message is sent to in the event of a network or communications failure when sending to the primary destination endpoint.</span></span> <span data-ttu-id="63a6a-121">Nell'esempio seguente viene definito un elenco di backup che contiene un endpoint. È tuttavia possibile specificare più endpoint in un elenco di backup.</span><span class="sxs-lookup"><span data-stu-id="63a6a-121">The following example defines a backup list that contains one endpoint; however, multiple endpoints can be specified in a backup list.</span></span>  
  
     <span data-ttu-id="63a6a-122">Se l'elenco di backup contiene più endpoint, in caso si verifichi un errore di rete o relativo alle comunicazioni, il servizio di routing tenta di inviare il messaggio al primo endpoint dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="63a6a-122">If the backup list contains multiple endpoints, when a network or communications failure occurs the Routing Service attempts to send the message to the first endpoint in the list.</span></span> <span data-ttu-id="63a6a-123">Se si verifica un errore di rete o relativo alle comunicazioni in fase di invio a questo endpoint, il servizio di routing tenta di inviare il messaggio all'endpoint successivo contenuto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="63a6a-123">If a network or communications failure occurs when sending to this endpoint, the Routing Service attempts to send the message to the next endpoint contained in the list.</span></span> <span data-ttu-id="63a6a-124">Il servizio continua a inviare il messaggio a ogni endpoint nell'elenco di endpoint di backup finché il messaggio non viene ricevuto correttamente, tutti gli endpoint di backup non restituiscono un errore di rete o relativo alle comunicazioni oppure il messaggio non viene inviato e l'endpoint restituisce un errore non di rete e non relativo alle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="63a6a-124">The service continues sending the message to each endpoint in the backup endpoint list until the message is successfully sent, all backup endpoints return a network or communications-related error, or the message is sent and the endpoint returns a non-network, non-communications-related error.</span></span>  
  
    ```xml  
    <backupLists>          
      <backupList name="backupEndpointList">  
          <add endpointName="realDestination" />  
      </backupList>  
    </backupLists>  
    ```  
  
4.  <span data-ttu-id="63a6a-125">Definire la tabella dei filtri, che associa il filtro all'endpoint deadDestination e all'elenco di endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="63a6a-125">Define the filter table, which associates the filter with the deadDestination endpoint and the backup endpoint list.</span></span>  <span data-ttu-id="63a6a-126">Il servizio di routing tenta in primo luogo di inviare il messaggio all'endpoint di destinazione associato al filtro.</span><span class="sxs-lookup"><span data-stu-id="63a6a-126">The Routing Service first attempts to send the message to the destination endpoint associated with the filter.</span></span> <span data-ttu-id="63a6a-127">Poiché deadDestination contiene un indirizzo che non fa riferimento a un servizio in esecuzione, viene generato un errore di rete.</span><span class="sxs-lookup"><span data-stu-id="63a6a-127">Since the deadDestination contains an address that does not refer to a running service, this results in a network error.</span></span> <span data-ttu-id="63a6a-128">Il servizio di routing tenta quindi di inviare il messaggio all'endpoint specificato in backupEndpointlist.</span><span class="sxs-lookup"><span data-stu-id="63a6a-128">The Routing Service then attempts to send the message to the endpoint specified in the backupEndpointlist.</span></span>  
  
    ```xml  
    <filterTables>  
            <!-- Set up the Routing Service's Message Filter Table -->  
            <filterTable name="filterTable1">  
                <!-- Add an entity that maps the MatchAllMessageFilter to the dead destination -->  
                <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->  
                <!-- Listed in the backupEndpointList -->  
                <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>  
            </filterTable>  
          </filterTables>  
    ```  
  
5.  <span data-ttu-id="63a6a-129">Per valutare i messaggi in ingresso rispetto al filtro contenuto nella rispettiva tabella, è necessario associare la tabella dei filtri agli endpoint servizio tramite il comportamento di routing.</span><span class="sxs-lookup"><span data-stu-id="63a6a-129">To evaluate incoming messages against the filter contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span>  <span data-ttu-id="63a6a-130">Nell'esempio seguente viene illustrata l'associazione di "filterTable1" agli endpoint servizio.</span><span class="sxs-lookup"><span data-stu-id="63a6a-130">The following example demonstrates associating "filterTable1" with the service endpoints.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <!-- Set up the Routing Behavior -->  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a><span data-ttu-id="63a6a-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="63a6a-131">Example</span></span>  
 <span data-ttu-id="63a6a-132">Il codice seguente costituisce un elenco completo del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="63a6a-132">Following is a complete listing of the configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright (c) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/" />  
          </baseAddresses>  
        </host>  
        <!-- Create the Routing Service endpoint -->  
        <endpoint address="router"  
                  binding="basicHttpBinding"  
                  name="RoutingServiceEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <!-- Set up the Routing Behavior -->  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <!-- Create the destination endpoints that we want to send to -->  
    <client>  
      <!-- Create a dummy endpoint that we know will be down -->  
      <endpoint name="deadDestination"   
                address="net.tcp://localhost:9090/servicemodelsamples/fakeDestination"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <!-- Now create the real service endpoint -->  
      <endpoint name="realDestination"   
                address="net.tcp://localhost:8080/servicemodelsamples/service"  
                binding="netTcpBinding"   
                contract="*" />  
    </client>  
    <routing>  
      <filters>  
        <!-- Create a MatchAll filter which will catch all messages -->  
        <filter name="MatchAllFilter1" filterType="MatchAll" />  
      </filters>  
      <filterTables>  
        <!-- Set up the Routing Service's Message Filter Table -->  
        <filterTable name="filterTable1">  
            <!-- Add an entrty that maps the MatchAllMessageFilter to the dead destination -->  
            <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->  
            <!-- Listed in the backupEndpointList -->  
            <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>  
        </filterTable>  
      </filterTables>  
      <!-- Create the backup endpoint list -->  
      <backupLists>          
        <backupList name="backupEndpointList">  
            <add endpointName="realDestination" />  
        </backupList>  
      </backupLists>  
      </routing>  
  </system.serviceModel>  
</configuration>  
```
