---
title: 'Procedura: implementare un servizio individuabile che esegue la registrazione al proxy di individuazione'
ms.date: 03/30/2017
ms.assetid: eb275bc1-535b-44c8-b9f3-0b75e9aa473b
ms.openlocfilehash: bf878dff59a9a258567ff99098b0b3f8761194e2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599230"
---
# <a name="how-to-implement-a-discoverable-service-that-registers-with-the-discovery-proxy"></a><span data-ttu-id="7fbe7-102">Procedura: implementare un servizio individuabile che esegue la registrazione al proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="7fbe7-102">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>
<span data-ttu-id="7fbe7-103">Quello che segue è il secondo di quattro argomenti incentrato sull'implementazione di un proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="7fbe7-103">This topic is the second of four topics that discusses how to implement a discovery proxy.</span></span> <span data-ttu-id="7fbe7-104">Nell'argomento precedente, [procedura: implementare un proxy di individuazione](how-to-implement-a-discovery-proxy.md), è stato implementato un proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="7fbe7-104">In the previous topic, [How to: Implement a Discovery Proxy](how-to-implement-a-discovery-proxy.md), you implemented a discovery proxy.</span></span> <span data-ttu-id="7fbe7-105">In questo argomento viene creato un servizio WCF che invia messaggi di annuncio ( `Hello` e `Bye` ) al proxy di individuazione, causando la registrazione e l'annullamento della registrazione con il proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="7fbe7-105">In this topic, you create a WCF service that sends announcement messages (`Hello` and `Bye`) to the discovery proxy, causing it to register and unregister itself with the discovery proxy.</span></span>

### <a name="to-define-the-service-contract"></a><span data-ttu-id="7fbe7-106">Per definire il contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="7fbe7-106">To define the service contract</span></span>

1. <span data-ttu-id="7fbe7-107">Aggiungere un nuovo progetto applicazione console denominato `DiscoveryProxyExample` alla soluzione `Service`.</span><span class="sxs-lookup"><span data-stu-id="7fbe7-107">Add a new console application project to the `DiscoveryProxyExample` solution called `Service`.</span></span>

2. <span data-ttu-id="7fbe7-108">Aggiungere riferimenti agli assembly riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="7fbe7-108">Add references to the following assemblies:</span></span>

    1. <span data-ttu-id="7fbe7-109">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7fbe7-109">System.ServiceModel</span></span>

    2. <span data-ttu-id="7fbe7-110">System.ServiceModel.Discovery</span><span class="sxs-lookup"><span data-stu-id="7fbe7-110">System.ServiceModel.Discovery</span></span>

3. <span data-ttu-id="7fbe7-111">Aggiungere al progetto una nuova classe denominata `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="7fbe7-111">Add a new class to the project called `CalculatorService`.</span></span>

4. <span data-ttu-id="7fbe7-112">Aggiungere le istruzioni using seguenti.</span><span class="sxs-lookup"><span data-stu-id="7fbe7-112">Add the following using statements.</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    ```

5. <span data-ttu-id="7fbe7-113">Definire il contratto di servizio all'interno di CalculatorService.cs.</span><span class="sxs-lookup"><span data-stu-id="7fbe7-113">Within CalculatorService.cs, define the service contract.</span></span>

    ```csharp
    // Define a service contract.
    [ServiceContract(Namespace = "http://Microsoft.Samples.Discovery")]
    public interface ICalculatorService
    {
        [OperationContract]
        double Add(double n1, double n2);
        [OperationContract]
        double Subtract(double n1, double n2);
        [OperationContract]
        double Multiply(double n1, double n2);
        [OperationContract]
        double Divide(double n1, double n2);
    }
    ```

6. <span data-ttu-id="7fbe7-114">Implementare inoltre il contratto di servizio all'interno di CalculatorService.cs.</span><span class="sxs-lookup"><span data-stu-id="7fbe7-114">Also within CalculatorService.cs, implement the service contract.</span></span>

    ```csharp
    // Service class which implements the service contract.
    public class CalculatorService : ICalculatorService
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
    ```

### <a name="to-host-the-service"></a><span data-ttu-id="7fbe7-115">Per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="7fbe7-115">To host the service</span></span>

1. <span data-ttu-id="7fbe7-116">Aprire il file Program.cs generato in fase di creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="7fbe7-116">Open the Program.cs file that was generated when you created the project.</span></span>

2. <span data-ttu-id="7fbe7-117">Aggiungere le istruzioni using seguenti.</span><span class="sxs-lookup"><span data-stu-id="7fbe7-117">Add the following using statements.</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using System.ServiceModel.Discovery;
    ```

3. <span data-ttu-id="7fbe7-118">Nel metodo `Main()` aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="7fbe7-118">Within the `Main()` method, add the following code:</span></span>

    ```csharp
    // Define the base address of the service
    Uri baseAddress = new Uri("net.tcp://localhost:9002/CalculatorService/" + Guid.NewGuid().ToString());
    // Define the endpoint address where announcement messages will be sent
    Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");

    // Create the service host
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);
    try
    {
        // Add a service endpoint
        ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService),
            new NetTcpBinding(), string.Empty);

        // Create an announcement endpoint, which points to the Announcement Endpoint hosted by the proxy service.
        AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(),
            new EndpointAddress(announcementEndpointAddress));

        // Create a ServiceDiscoveryBehavior and add the announcement endpoint
        ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
        serviceDiscoveryBehavior.AnnouncementEndpoints.Add(announcementEndpoint);

        // Add the ServiceDiscoveryBehavior to the service host to make the service discoverable
        serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);

        // Start listening for messages
        serviceHost.Open();

        Console.WriteLine("Calculator Service started at {0}", baseAddress);
        Console.WriteLine();
        Console.WriteLine("Press <ENTER> to terminate the service.");
        Console.WriteLine();
        Console.ReadLine();

        serviceHost.Close();
    }
    catch (CommunicationException e)
    {
        Console.WriteLine(e.Message);
    }
    catch (TimeoutException e)
    {
        Console.WriteLine(e.Message);
    }

    if (serviceHost.State != CommunicationState.Closed)
    {
        Console.WriteLine("Aborting the service...");
        serviceHost.Abort();
    }
    ```

<span data-ttu-id="7fbe7-119">L'implementazione di un servizio individuabile è quindi completata.</span><span class="sxs-lookup"><span data-stu-id="7fbe7-119">You have completed implementing a discoverable service.</span></span> <span data-ttu-id="7fbe7-120">Continuare con [la procedura: implementare un'applicazione client che usa il proxy di individuazione per trovare un servizio](client-app-discovery-proxy-to-find-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="7fbe7-120">Continue on to [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](client-app-discovery-proxy-to-find-a-service.md).</span></span>

## <a name="example"></a><span data-ttu-id="7fbe7-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fbe7-121">Example</span></span>
 <span data-ttu-id="7fbe7-122">Quello che segue è l'elenco completo del codice usato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7fbe7-122">This is the full listing of the code used in this topic.</span></span>

```csharp
// CalculatorService.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.ServiceModel;

namespace Microsoft.Samples.Discovery
{
    // Define a service contract.
    [ServiceContract(Namespace = "http://Microsoft.Samples.Discovery")]
    public interface ICalculatorService
    {
        [OperationContract]
        double Add(double n1, double n2);
        [OperationContract]
        double Subtract(double n1, double n2);
        [OperationContract]
        double Multiply(double n1, double n2);
        [OperationContract]
        double Divide(double n1, double n2);
    }

    // Service class which implements the service contract.
    public class CalculatorService : ICalculatorService
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
  
        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```csharp
// Program.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.ServiceModel;
using System.ServiceModel.Description;
using System.ServiceModel.Discovery;

namespace Microsoft.Samples.Discovery
{
    class Program
    {
        public static void Main()
        {
            Uri baseAddress = new Uri("net.tcp://localhost:9002/CalculatorService/" + Guid.NewGuid().ToString());
            Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");

            ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);
            try
            {
                ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService),
                    new NetTcpBinding(), string.Empty);

                // Create an announcement endpoint, which points to the Announcement Endpoint hosted by the proxy service.
                AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(),
                    new EndpointAddress(announcementEndpointAddress));

                ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
                serviceDiscoveryBehavior.AnnouncementEndpoints.Add(announcementEndpoint);

                // Make the service discoverable
                serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);

                serviceHost.Open();

                Console.WriteLine("Calculator Service started at {0}", baseAddress);
                Console.WriteLine();
                Console.WriteLine("Press <ENTER> to terminate the service.");
                Console.WriteLine();
                Console.ReadLine();

                serviceHost.Close();
            }
            catch (CommunicationException e)
            {
                Console.WriteLine(e.Message);
            }
            catch (TimeoutException e)
            {
                Console.WriteLine(e.Message);
            }

            if (serviceHost.State != CommunicationState.Closed)
            {
                Console.WriteLine("Aborting the service...");
                serviceHost.Abort();
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="7fbe7-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fbe7-123">See also</span></span>

- [<span data-ttu-id="7fbe7-124">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="7fbe7-124">WCF Discovery</span></span>](wcf-discovery.md)
- [<span data-ttu-id="7fbe7-125">Procedura: implementare un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="7fbe7-125">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)
- [<span data-ttu-id="7fbe7-126">Procedura: implementare un'applicazione client che usa il proxy di individuazione per cercare un servizio</span><span class="sxs-lookup"><span data-stu-id="7fbe7-126">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)
