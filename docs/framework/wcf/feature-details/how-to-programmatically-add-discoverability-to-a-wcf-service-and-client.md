---
title: 'Procedura: aggiungere capacità di individuazione a un client e un servizio WCF a livello di codice'
ms.date: 03/30/2017
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
ms.openlocfilehash: c28815d1d208d3e91785a13d95e03c09c0f02ed9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596994"
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a><span data-ttu-id="f8314-102">Procedura: aggiungere capacità di individuazione a un client e un servizio WCF a livello di codice</span><span class="sxs-lookup"><span data-stu-id="f8314-102">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>
<span data-ttu-id="f8314-103">In questo argomento viene illustrato come rendere individuabile un servizio di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f8314-103">This topic explains how to make a Windows Communication Foundation (WCF) service discoverable.</span></span> <span data-ttu-id="f8314-104">Si basa sull'esempio [self-host](https://docs.microsoft.com/dotnet/framework/wcf/samples/self-host) .</span><span class="sxs-lookup"><span data-stu-id="f8314-104">It is based on the [Self-Host](https://docs.microsoft.com/dotnet/framework/wcf/samples/self-host) sample.</span></span>  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a><span data-ttu-id="f8314-105">Per configurare l'esempio di servizio indipendente esistente per l'individuazione</span><span class="sxs-lookup"><span data-stu-id="f8314-105">To configure the existing Self-Host service sample for Discovery</span></span>  
  
1. <span data-ttu-id="f8314-106">Aprire la soluzione self-host in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="f8314-106">Open the Self-Host solution in Visual Studio 2012.</span></span> <span data-ttu-id="f8314-107">L'esempio si trova nella directory TechnologySamples\Basic\Service\Hosting\SelfHost.</span><span class="sxs-lookup"><span data-stu-id="f8314-107">The sample is located in the TechnologySamples\Basic\Service\Hosting\SelfHost directory.</span></span>  
  
2. <span data-ttu-id="f8314-108">Aggiungere al progetto di servizio un riferimento a `System.ServiceModel.Discovery.dll`.</span><span class="sxs-lookup"><span data-stu-id="f8314-108">Add a reference to `System.ServiceModel.Discovery.dll` to the service project.</span></span> <span data-ttu-id="f8314-109">Potrebbe essere visualizzato un messaggio di errore che informa che "System.</span><span class="sxs-lookup"><span data-stu-id="f8314-109">You may see an error message saying "System.</span></span> <span data-ttu-id="f8314-110">ServiceModel. Discovery. dll o una delle relative dipendenze richiede una versione successiva del .NET Framework rispetto a quella specificata nel progetto... " Se viene visualizzato questo messaggio, fare clic con il pulsante destro del mouse sul progetto nella Esplora soluzioni e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f8314-110">ServiceModel.Discovery.dll or one of its dependencies requires a later version of the .NET Framework than the one specified in the project …" If you see this message, right-click the project in the Solution Explorer and choose **Properties**.</span></span> <span data-ttu-id="f8314-111">Nella finestra delle **proprietà del progetto** verificare che il Framework di **destinazione** sia [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8314-111">In the **Project Properties** window, make sure that the **Target Framework** is [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
3. <span data-ttu-id="f8314-112">Aprire il file Service.cs e aggiungere l'istruzione `using` seguente.</span><span class="sxs-lookup"><span data-stu-id="f8314-112">Open the Service.cs file and add the following `using` statement.</span></span>  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4. <span data-ttu-id="f8314-113">Nel metodo `Main()`, all'interno dell'istruzione `using`, aggiungere un'istanza <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> all'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f8314-113">In the `Main()` method, inside the `using` statement, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instance to the service host.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
        {  
            // Add a ServiceDiscoveryBehavior  
            serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());
  
            // ...  
        }  
    }  
    ```  
  
     <span data-ttu-id="f8314-114"><xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> specifica che il servizio a cui è applicato è individuabile.</span><span class="sxs-lookup"><span data-stu-id="f8314-114">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> specifies that the service it is applied to is discoverable.</span></span>  
  
5. <span data-ttu-id="f8314-115">Aggiungere <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> all'host del servizio subito dopo il codice che aggiunge <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="f8314-115">Add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the service host right after the code that adds the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span>  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     <span data-ttu-id="f8314-116">Questo codice specifica che i messaggi di individuazione devono essere inviati all'endpoint di individuazione UDP standard.</span><span class="sxs-lookup"><span data-stu-id="f8314-116">This code specifies that discovery messages should be sent to the standard UDP discovery endpoint.</span></span>  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a><span data-ttu-id="f8314-117">Per creare un'applicazione client che utilizza l'individuazione per chiamare il servizio</span><span class="sxs-lookup"><span data-stu-id="f8314-117">To create a client application that uses discovery to call the service</span></span>  
  
1. <span data-ttu-id="f8314-118">Aggiungere alla soluzione una nuova applicazione console denominata `DiscoveryClientApp`.</span><span class="sxs-lookup"><span data-stu-id="f8314-118">Add a new console application to the solution called `DiscoveryClientApp`.</span></span>  
  
2. <span data-ttu-id="f8314-119">Aggiungere un riferimento a `System.ServiceModel.dll` e `System.ServiceModel.Discovery.dll`</span><span class="sxs-lookup"><span data-stu-id="f8314-119">Add a reference to `System.ServiceModel.dll` and `System.ServiceModel.Discovery.dll`</span></span>  
  
3. <span data-ttu-id="f8314-120">Copiare i file GeneratedClient.cs e App.config dal progetto client esistente al nuovo progetto DiscoveryClientApp.</span><span class="sxs-lookup"><span data-stu-id="f8314-120">Copy the GeneratedClient.cs and App.config files from the existing client project to the new DiscoveryClientApp project.</span></span> <span data-ttu-id="f8314-121">A tale scopo, fare clic con il pulsante destro del mouse sui file nel **Esplora soluzioni**, selezionare **copia**, quindi selezionare il progetto **DiscoveryClientApp** , fare clic con il pulsante destro del mouse e scegliere **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="f8314-121">To do this, right-click the files in the **Solution Explorer**, select **Copy**, and then select the **DiscoveryClientApp** project, right-click and select **Paste**.</span></span>  
  
4. <span data-ttu-id="f8314-122">Aprire Program.cs.</span><span class="sxs-lookup"><span data-stu-id="f8314-122">Open Program.cs.</span></span>  
  
5. <span data-ttu-id="f8314-123">Aggiungere le istruzioni `using` seguenti.</span><span class="sxs-lookup"><span data-stu-id="f8314-123">Add the following `using` statements.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6. <span data-ttu-id="f8314-124">Aggiungere un metodo statico denominato `FindCalculatorServiceAddress()` alla classe `Program`.</span><span class="sxs-lookup"><span data-stu-id="f8314-124">Add a static method called `FindCalculatorServiceAddress()` to the `Program` class.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     <span data-ttu-id="f8314-125">Questo metodo utilizza l'individuazione per cercare il servizio `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="f8314-125">This method uses discovery to search for the `CalculatorService` service.</span></span>  
  
7. <span data-ttu-id="f8314-126">Creare nel metodo `FindCalculatorServiceAddress` una nuova istanza <xref:System.ServiceModel.Discovery.DiscoveryClient>, passando un elemento <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> al costruttore.</span><span class="sxs-lookup"><span data-stu-id="f8314-126">Inside the `FindCalculatorServiceAddress` method, create a new <xref:System.ServiceModel.Discovery.DiscoveryClient> instance, passing in a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the constructor.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     <span data-ttu-id="f8314-127">Indica a WCF che la <xref:System.ServiceModel.Discovery.DiscoveryClient> classe deve utilizzare l'endpoint di individuazione UDP standard per inviare e ricevere messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="f8314-127">This tells WCF that the <xref:System.ServiceModel.Discovery.DiscoveryClient> class should use the standard UDP discovery endpoint to send and receive discovery messages.</span></span>  
  
8. <span data-ttu-id="f8314-128">Alla riga successiva, chiamare il metodo <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> e specificare un'istanza <xref:System.ServiceModel.Discovery.FindCriteria> che contiene il contratto di servizio che si desiderare cercare.</span><span class="sxs-lookup"><span data-stu-id="f8314-128">On the next line, call the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method and specify a <xref:System.ServiceModel.Discovery.FindCriteria> instance that contains the service contract you want to search for.</span></span> <span data-ttu-id="f8314-129">In questo caso specificare `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="f8314-129">In this case, specify `ICalculator`.</span></span>  
  
    ```csharp  
    // Find ICalculatorService endpoints
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. <span data-ttu-id="f8314-130">Successivamente alla chiamata a <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, verificare se sia disponibile almeno un servizio corrispondente e restituire l'elemento <xref:System.ServiceModel.EndpointAddress> del primo servizio corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f8314-130">After the call to <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, check to see if there is at least one matching service and return the <xref:System.ServiceModel.EndpointAddress> of the first matching service.</span></span> <span data-ttu-id="f8314-131">In caso contrario, restituire `null`.</span><span class="sxs-lookup"><span data-stu-id="f8314-131">Otherwise return `null`.</span></span>  
  
    ```csharp  
    if (findResponse.Endpoints.Count > 0)  
    {  
        return findResponse.Endpoints[0].Address;  
    }  
    else  
    {  
        return null;  
    }  
    ```  
  
10. <span data-ttu-id="f8314-132">Aggiungere un metodo statico denominato `InvokeCalculatorService` alla classe `Program`.</span><span class="sxs-lookup"><span data-stu-id="f8314-132">Add a static method named `InvokeCalculatorService` to the `Program` class.</span></span>  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     <span data-ttu-id="f8314-133">Questo metodo utilizza l'indirizzo endpoint restituito da `FindCalculatorServiceAddress` per chiamare il servizio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="f8314-133">This method uses the endpoint address returned from `FindCalculatorServiceAddress` to call the calculator service.</span></span>  
  
11. <span data-ttu-id="f8314-134">Creare all'interno del metodo `InvokeCalculatorService` un'istanza della classe `CalculatorServiceClient`.</span><span class="sxs-lookup"><span data-stu-id="f8314-134">Inside the `InvokeCalculatorService` method, create an instance of the `CalculatorServiceClient` class.</span></span> <span data-ttu-id="f8314-135">Questa classe è definita dall'esempio [self-host](https://docs.microsoft.com/dotnet/framework/wcf/samples/self-host) .</span><span class="sxs-lookup"><span data-stu-id="f8314-135">This class is defined by the [Self-Host](https://docs.microsoft.com/dotnet/framework/wcf/samples/self-host) sample.</span></span> <span data-ttu-id="f8314-136">È stata generata utilizzando Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="f8314-136">It was generated using Svcutil.exe.</span></span>  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. <span data-ttu-id="f8314-137">Alla riga successiva impostare l'indirizzo endpoint del client sull'indirizzo endpoint restituito da `FindCalculatorServiceAddress()`.</span><span class="sxs-lookup"><span data-stu-id="f8314-137">On the next line, set the endpoint address of the client to the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. <span data-ttu-id="f8314-138">Immediatamente dopo il codice per il passaggio precedente, chiamare i metodi esposti dal servizio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="f8314-138">Immediately after the code for the previous step, call the methods exposed by the calculator service.</span></span>  
  
    ```csharp  
    Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
  
    // Call the Add service operation.  
    double result = client.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation.  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Multiply service operation.  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
    Console.WriteLine();  
  
    //Closing the client gracefully closes the connection and cleans up resources  
    client.Close();  
    ```  
  
14. <span data-ttu-id="f8314-139">Aggiungere codice al metodo `Main()` nella classe `Program` per chiamare `FindCalculatorServiceAddress`.</span><span class="sxs-lookup"><span data-stu-id="f8314-139">Add code to the `Main()` method in the `Program` class to call `FindCalculatorServiceAddress`.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. <span data-ttu-id="f8314-140">Alla riga successiva chiamare `InvokeCalculatorService()` e passare l'indirizzo endpoint restituito da `FindCalculatorServiceAddress()`.</span><span class="sxs-lookup"><span data-stu-id="f8314-140">On the next line, call the `InvokeCalculatorService()` and pass in the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="f8314-141">Per testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="f8314-141">To test the application</span></span>  
  
1. <span data-ttu-id="f8314-142">Aprire un prompt dei comandi con privilegi elevati ed eseguire Service.exe.</span><span class="sxs-lookup"><span data-stu-id="f8314-142">Open an elevated command prompt and run Service.exe.</span></span>  
  
2. <span data-ttu-id="f8314-143">Aprire un prompt dei comandi ed eseguire Discoveryclientapp.exe.</span><span class="sxs-lookup"><span data-stu-id="f8314-143">Open a command prompt and run Discoveryclientapp.exe.</span></span>  
  
3. <span data-ttu-id="f8314-144">L'output di service.exe deve essere analogo all'output indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f8314-144">The output from service.exe should look like the following output.</span></span>  
  
    ```output  
    Received Add(100,15.99)  
    Return: 115.99  
    Received Subtract(100,15.99)  
    Return: 84.01  
    Received Multiply(100,15.99)  
    Return: 1599  
    Received Divide(100,15.99)  
    Return: 6.25390869293308  
    ```  
  
4. <span data-ttu-id="f8314-145">L'output di Discoveryclientapp.exe deve essere analogo all'output indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f8314-145">The output from Discoveryclientapp.exe should look like the following output.</span></span>  
  
    ```output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a><span data-ttu-id="f8314-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8314-146">Example</span></span>  
 <span data-ttu-id="f8314-147">Di seguito è riportato un elenco del codice per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="f8314-147">The following is a listing of the code for this sample.</span></span> <span data-ttu-id="f8314-148">Poiché questo codice è basato sull'esempio [self-host](https://docs.microsoft.com/dotnet/framework/wcf/samples/self-host) , vengono elencati solo i file modificati.</span><span class="sxs-lookup"><span data-stu-id="f8314-148">Because this code is based on the [Self-Host](https://docs.microsoft.com/dotnet/framework/wcf/samples/self-host) sample, only those files that are changed are listed.</span></span> <span data-ttu-id="f8314-149">Per ulteriori informazioni sull'esempio Self-host, vedere [istruzioni di installazione](https://docs.microsoft.com/dotnet/framework/wcf/samples/set-up-instructions).</span><span class="sxs-lookup"><span data-stu-id="f8314-149">For more information about the Self-Host sample, see [Setup Instructions](https://docs.microsoft.com/dotnet/framework/wcf/samples/set-up-instructions).</span></span>  
  
```csharp  
// Service.cs  
using System;  
using System.Configuration;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
  
namespace Microsoft.ServiceModel.Samples  
{  
    // See SelfHost sample for service contract and implementation  
    // ...  
  
        // Host the service within this EXE console application.  
        public static void Main()  
        {  
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
            {  
                // Add the ServiceDiscoveryBehavior to make the service discoverable  
                serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
                serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
  
                // Open the ServiceHost to create listeners and start listening for messages.  
                serviceHost.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
            }  
        }  
    }  
}  
```  
  
```csharp  
// Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
using Microsoft.ServiceModel.Samples;  
using System.Text;  
  
namespace DiscoveryClientApp  
{  
    class Program  
    {  
        static EndpointAddress FindCalculatorServiceAddress()  
        {  
            // Create DiscoveryClient  
            DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
            // Find ICalculatorService endpoints
            FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
  
            if (findResponse.Endpoints.Count > 0)  
            {  
                return findResponse.Endpoints[0].Address;  
            }  
            else  
            {  
                return null;  
            }  
        }  
  
        static void InvokeCalculatorService(EndpointAddress endpointAddress)  
        {  
            // Create a client  
            CalculatorClient client = new CalculatorClient();  
  
            // Connect to the discovered service endpoint  
            client.Endpoint.Address = endpointAddress;  
  
            Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
            double value1 = 100.00D;  
            double value2 = 15.99D;  
  
            // Call the Add service operation.  
            double result = client.Add(value1, value2);  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Subtract service operation.  
            result = client.Subtract(value1, value2);  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Multiply service operation.  
            result = client.Multiply(value1, value2);  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Divide service operation.  
            result = client.Divide(value1, value2);  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
            Console.WriteLine();  
  
            //Closing the client gracefully closes the connection and cleans up resources  
            client.Close();  
        }  
        static void Main(string[] args)  
        {  
            EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
  
            if (endpointAddress != null)  
            {  
                InvokeCalculatorService(endpointAddress);  
            }  
  
            Console.WriteLine("Press <ENTER> to exit.");  
            Console.ReadLine();  
  
        }  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="f8314-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8314-150">See also</span></span>

- [<span data-ttu-id="f8314-151">Panoramica di WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="f8314-151">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="f8314-152">Modello a oggetti WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="f8314-152">WCF Discovery Object Model</span></span>](wcf-discovery-object-model.md)
