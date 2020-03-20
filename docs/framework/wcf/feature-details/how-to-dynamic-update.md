---
title: 'Procedura: aggiornamento dinamico'
ms.date: 03/30/2017
ms.assetid: 9b8f6e0d-edab-4a7e-86e3-8c66bebc64bb
ms.openlocfilehash: aaeb4d9d42c289cf34a6aee9212fc2d74b8f8c01
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184961"
---
# <a name="how-to-dynamic-update"></a><span data-ttu-id="e6bb0-102">Procedura: aggiornamento dinamico</span><span class="sxs-lookup"><span data-stu-id="e6bb0-102">How To: Dynamic Update</span></span>
<span data-ttu-id="e6bb0-103">In questo argomento vengono descritti i passaggi di base necessari per creare e aggiornare in modo dinamico la configurazione del routing.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-103">This topic outlines the basic steps required to create and dynamically update the routing configuration.</span></span> <span data-ttu-id="e6bb0-104">In questo esempio, la configurazione iniziale del routing viene ottenuta dal file di configurazione e indirizza tutti i messaggi al servizio di calcolo regularCalc. Viene tuttavia aggiornata in un secondo momento a livello di codice per modificare l'endpoint di destinazione del servizio roundingCalc.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-104">In this example, the initial routing configuration is obtained from the configuration file and routes all messages to the regularCalc calculator service; however, it is subsequently updated programmatically in order to change the destination endpoint the roundingCalc service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6bb0-105">In molte implementazioni la configurazione sarà completamente dinamica e non si baserà su una configurazione predefinita. Tuttavia, in alcuni scenari, come quello citato in questo argomento, è preferibile disporre di uno stato di configurazione predefinito all'avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-105">In many implementations, configuration will be fully dynamic and will not rely on a default configuration; however, there are some scenarios, such as the one in this topic, where it is desirable to have a default configuration state when the service starts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6bb0-106">Gli aggiornamenti dinamici si verificano solo nella memoria e non comportano la modifica dei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-106">Dynamic updates occur only in memory, and do not result in the modification of configuration files.</span></span>  
  
 <span data-ttu-id="e6bb0-107">Sia regularCalc sia roundingCalc supportano le stesse operazioni di aggiunta, sottrazione, moltiplicazione e divisione. roundingCalc esegue tuttavia l'arrotondamento di tutti i calcoli all'integer più vicino prima della restituzione.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-107">Both regularCalc and roundingCalc support the same operations of add, subtract, multiply and divide; however, roundingCalc rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="e6bb0-108">Viene utilizzato un file di configurazione per configurare il servizio al fine di indirizzare tutti i messaggi al servizio regularCalc.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-108">A configuration file is used to configure the service to route all messages to the regularCalc service.</span></span> <span data-ttu-id="e6bb0-109">Una volta avviato il servizio di routing, viene utilizzato <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> per riconfigurare il servizio al fine di indirizzare messaggi al servizio roundingCalc.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-109">After the Routing Service has been started, <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> is used to reconfigure the service to route messages to the roundingCalc service.</span></span>  
  
### <a name="implement-initial-configuration"></a><span data-ttu-id="e6bb0-110">Implementare la configurazione iniziale</span><span class="sxs-lookup"><span data-stu-id="e6bb0-110">Implement Initial Configuration</span></span>  
  
1. <span data-ttu-id="e6bb0-111">Creare la configurazione del servizio di routing di base specificando gli endpoint servizio esposti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-111">Create the basic Routing Service Configuration by specifying the service endpoints exposed by the service.</span></span> <span data-ttu-id="e6bb0-112">Nell'esempio seguente viene definito un solo endpoint servizio che verrà utilizzato per ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-112">The following example defines a single service endpoint, which will be used to receive messages.</span></span> <span data-ttu-id="e6bb0-113">Viene inoltre definito un endpoint client che verrà utilizzato per inviare messaggi al servizio regularCalc.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-113">It also defines a client endpoint that will be used to send messages to the regularCalc.</span></span>  
  
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
    <!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    ```  
  
2. <span data-ttu-id="e6bb0-114">Definire il filtro utilizzato per indirizzare messaggi agli endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-114">Define the filter used to route messages to the destination endpoints.</span></span> <span data-ttu-id="e6bb0-115">Ai fini di questo esempio, viene utilizzato il filtro MatchAll per indirizzare tutti i messaggi al servizio regularCalcEndpoint definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-115">For this example, the MatchAll filter is used to route all messages to the regularCalcEndpoint defined previously.</span></span> <span data-ttu-id="e6bb0-116">Nell'esempio indicato di seguito vengono definiti il filtro e la tabella dei filtri.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-116">The following example defines the filter and filter table.</span></span>  
  
    ```xml  
    <filters>  
      <!--define the message filter-->  
      <filter name="MatchAllFilter" filterType="MatchAll"/>  
    </filters>  
    <filterTables>  
      <filterTable name="filterTable1">  
          <!--add the filter to the message filter table-->  
          <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
      </filterTable>  
    </filterTables>  
    ```  
  
3. <span data-ttu-id="e6bb0-117">Per valutare i messaggi in ingresso rispetto ai filtri contenuti nella rispettiva tabella, è necessario associare la tabella dei filtri agli endpoint servizio tramite il comportamento di routing.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-117">To evaluate incoming messages against the filters contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="e6bb0-118">Nell'esempio seguente viene illustrata l'associazione di "filterTable1" all'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-118">The following example demonstrates associating "filterTable1" with the service endpoint.</span></span>  
  
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
  
## <a name="implement-dynamic-configuration"></a><span data-ttu-id="e6bb0-119">Implementare la configurazione dinamica</span><span class="sxs-lookup"><span data-stu-id="e6bb0-119">Implement Dynamic Configuration</span></span>  
 <span data-ttu-id="e6bb0-120">La configurazione dinamica del servizio di routing può essere eseguita esclusivamente nel codice creando un nuovo elemento <xref:System.ServiceModel.Routing.RoutingConfiguration> e utilizzando <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> per sostituire la configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-120">Dynamic configuration of the Routing Service can only be performed in code by creating a new <xref:System.ServiceModel.Routing.RoutingConfiguration> and using <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> to replace the current configuration.</span></span>  <span data-ttu-id="e6bb0-121">Ai fini di questo esempio, il servizio di routing è indipendente all'interno di un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-121">For this example, the Routing Service is self-hosted within a console application.</span></span> <span data-ttu-id="e6bb0-122">In seguito all'avvio dell'applicazione, è possibile modificare la configurazione del routing immettendo 'normal' o 'rounding' nella finestra della console per configurare l'endpoint di destinazione a cui vengono indirizzati i messaggi (regularCalc se viene immesso 'regular', altrimenti roundingCalc).</span><span class="sxs-lookup"><span data-stu-id="e6bb0-122">After the application has started, you can modify the routing configuration by entering ‘regular’ or ‘rounding’ at the console window to configure the destination endpoint that messages are routed to; regularCalc when ‘regular’ is entered, otherwise roundingCalc when ‘rounding’ is entered.</span></span>  
  
1. <span data-ttu-id="e6bb0-123">È necessario aggiungere le istruzioni using seguenti per supportare il servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-123">The following using statements must be added in order to support the Routing Service.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ServiceModel;  
    using System.ServiceModel.Channels;  
    using System.ServiceModel.Description;  
    using System.ServiceModel.Dispatcher;  
    using System.ServiceModel.Routing;  
    ```  
  
2. <span data-ttu-id="e6bb0-124">Il codice seguente viene utilizzato per ospitare in modo automatico il servizio di routing come applicazione console.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-124">The following code is used to self-host the Routing Service as a console application.</span></span> <span data-ttu-id="e6bb0-125">In questo modo viene inizializzato il servizio di routing utilizzando la configurazione descritta nel passaggio precedente, contenuta all'interno del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-125">This initializes the Routing Service using the configuration described in the previous step, which is contained within the application configuration file.</span></span> <span data-ttu-id="e6bb0-126">Il ciclo while contiene il codice utilizzato per modificare la configurazione del routing.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-126">The while loop contains the code used to change the routing configuration.</span></span>  
  
    ```csharp  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost =  
            new ServiceHost(typeof(RoutingService)))  
        {  
            // Open the ServiceHost to create listeners
            // and start listening for messages.  
            Console.WriteLine("The Routing Service configured, opening....");  
            serviceHost.Open();  
            Console.WriteLine("The Routing Service is now running.");  
             Console.WriteLine("Type 'quit' to terminate router.");  
             Console.WriteLine("<ENTER> to change routing configuration.");  
             while (Console.ReadLine() != "quit")  
             {  
            ....  
            }  
        }  
    }  
    ```  
  
3. <span data-ttu-id="e6bb0-127">Per aggiornare in modo dinamico la configurazione del routing, è necessario crearne una nuova,</span><span class="sxs-lookup"><span data-stu-id="e6bb0-127">To dynamically update the routing configuration, a new routing configuration must be created.</span></span> <span data-ttu-id="e6bb0-128">che contenga tutti gli endpoint, i filtri e le tabelle dei filtri necessari per la nuova configurazione del routing, in quanto sostituirà completamente la configurazione del routing esistente.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-128">This must contain all endpoints, filters and filter tables that are required for the new routing configuration, as it will completely replace the existing routing configuration.</span></span> <span data-ttu-id="e6bb0-129">Per utilizzare la nuova configurazione del routing, è necessario richiamare <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> e passare la nuova configurazione.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-129">In order to use the new routing configuration, you must invoke <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> and pass the new configuration.</span></span>  
  
     <span data-ttu-id="e6bb0-130">Aggiungere il codice seguente al ciclo while precedentemente definito per consentire la riconfigurazione del servizio in base all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e6bb0-130">Add the following code to the while loop defined previously to allow the service to be reconfigured based on user input.</span></span>  
  
    ```csharp  
    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
    string destEndpoint = Console.ReadLine();  
    // Create a new RoutingConfiguration  
    RoutingConfiguration rc = new RoutingConfiguration();  
    // Determine the endpoint to configure for  
    switch (destEndpoint)  
    {  
        case "regular":  
            // Define the destination endpoint  
            ServiceEndpoint regularCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        case "rounding":  
            // Define the destination endpoint  
            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        default:  
            Console.WriteLine("Incorrect value entered, no change.");  
            break;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="e6bb0-131">Poiché il metodo per fornire un nuovo elemento RoutingConfiguration è contenuto nell'estensione RoutingExtension del servizio, possono essere forniti nuovi oggetti RoutingConfiguration in qualunque punto del modello di estensibilità WCF che dispone o può ottenere un riferimento a ServiceHost o ServiceExtensions (ad esempio in un altro ServiceExtension).</span><span class="sxs-lookup"><span data-stu-id="e6bb0-131">Since the method for providing a new RoutingConfiguration is contained in the RoutingExtension service extension, new RoutingConfiguration objects can be provided anywhere in the WCF extensibility model that has or can obtain a reference to the ServiceHost or ServiceExtensions (such as in another ServiceExtension).</span></span>
  
## <a name="example"></a><span data-ttu-id="e6bb0-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6bb0-132">Example</span></span>  

<span data-ttu-id="e6bb0-133">Di seguito è riportato un elenco completo dell'applicazione console utilizzata in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="e6bb0-133">The following is a complete listing of the console application used in this example:</span></span>
  
```csharp
//-----------------------------------------------------------------  
//  Copyright (c) Microsoft Corporation.  All Rights Reserved.  
//-----------------------------------------------------------------  
  
using System;  
using System.Collections.Generic;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.ServiceModel.Description;  
using System.ServiceModel.Dispatcher;  
using System.ServiceModel.Routing;  
  
namespace Microsoft.Samples.AdvancedFilters  
{  
    public class Router  
    {  
        // Host the service within this EXE console application.  
        public static void Main()  
        {
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost =  
                new ServiceHost(typeof(RoutingService)))  
            {  
                // Open the ServiceHost to create listeners
                // and start listening for messages.  
                Console.WriteLine("The Routing Service configured, opening....");  
                serviceHost.Open();  
                Console.WriteLine("The Routing Service is now running.");  
                Console.WriteLine("Type 'quit' to terminate router.");  
                Console.WriteLine("<ENTER> to change routing configuration.");  
                while (Console.ReadLine() != "quit")  
                {  
                    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
                    string destEndpoint = Console.ReadLine();  
                    // Create a new RoutingConfiguration  
                    RoutingConfiguration rc = new RoutingConfiguration();  
                    // Determine the endpoint to configure for  
                    switch (destEndpoint)  
                    {  
                        case "regular":  
                            // Define the destination endpoint  
                            ServiceEndpoint regularCalc = new ServiceEndpoint(  
                            ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                            new NetTcpBinding(),  
                            new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        case "rounding":  
                            // Define the destination endpoint  
                            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
                                ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                                new NetTcpBinding(),  
                                new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        default:  
                            Console.WriteLine("Incorrect value entered, no change.");  
                            break;  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="e6bb0-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6bb0-134">Example</span></span>  

<span data-ttu-id="e6bb0-135">Di seguito è riportato un elenco completo del file di configurazione utilizzato in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="e6bb0-135">The following is a complete listing of the configuration file used in this example:</span></span>
  
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
<!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
  
      <filters>  
        <!--define the message filter-->  
        <filter name="MatchAllFilter" filterType="MatchAll"/>  
      </filters>  
      <filterTables>  
        <filterTable name="filterTable1">  
            <!--add the filter to the message filter table-->  
            <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
        </filterTable>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6bb0-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6bb0-136">See also</span></span>

- [<span data-ttu-id="e6bb0-137">Servizi di routing</span><span class="sxs-lookup"><span data-stu-id="e6bb0-137">Routing Services</span></span>](../samples/routing-services.md)
