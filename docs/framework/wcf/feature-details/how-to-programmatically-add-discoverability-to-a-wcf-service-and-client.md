---
title: "Procedura: aggiungere capacità di individuazione a un client e un servizio WCF a livello di codice"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f94d99542a07711f618bc02316e6f61f6df647d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a>Procedura: aggiungere capacità di individuazione a un client e un servizio WCF a livello di codice
In questo argomento viene illustrato come rendere individuabile un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. È basato sul [indipendente](http://go.microsoft.com/fwlink/?LinkId=145523) esempio.  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a>Per configurare l'esempio di servizio indipendente esistente per l'individuazione  
  
1.  Aprire la soluzione Self-Host in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]. L'esempio si trova nella directory TechnologySamples\Basic\Service\Hosting\SelfHost.  
  
2.  Aggiungere al progetto di servizio un riferimento a `System.ServiceModel.Discovery.dll`. Si potrebbe visualizzare un messaggio di errore indicante che "System. ServiceModel.Discovery.dll o una delle relative dipendenze richiede una versione successiva del [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] rispetto a quello specificato nel progetto... " Se viene visualizzato questo messaggio, fare clic sul progetto in Esplora soluzioni e scegliere **proprietà**. Nel **le proprietà del progetto** finestra, assicurarsi che il **Framework di destinazione** è [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].  
  
3.  Aprire il file Service.cs e aggiungere l'istruzione `using` seguente.  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4.  Nel metodo `Main()`, all'interno dell'istruzione `using`, aggiungere un'istanza <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> all'host del servizio.  
  
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
  
     <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> specifica che il servizio a cui è applicato è individuabile.  
  
5.  Aggiungere <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> all'host del servizio subito dopo il codice che aggiunge <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     Questo codice specifica che i messaggi di individuazione devono essere inviati all'endpoint di individuazione UDP standard.  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a>Per creare un'applicazione client che utilizza l'individuazione per chiamare il servizio  
  
1.  Aggiungere alla soluzione una nuova applicazione console denominata `DiscoveryClientApp`.  
  
2.  Aggiungere un riferimento a `System.ServiceModel.dll` e `System.ServiceModel.Discovery.dll`  
  
3.  Copiare i file GeneratedClient.cs e App.config dal progetto client esistente al nuovo progetto DiscoveryClientApp. A tale scopo, fare clic sui file nel **Esplora**selezionare **copia**e quindi selezionare il **DiscoveryClientApp** del progetto, fare doppio clic e selezionare **Incolla**.  
  
4.  Aprire Program.cs.  
  
5.  Aggiungere le istruzioni `using` riportate di seguito.  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6.  Aggiungere un metodo statico denominato `FindCalculatorServiceAddress()` alla classe `Program`.  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     Questo metodo utilizza l'individuazione per cercare il servizio `CalculatorService`.  
  
7.  Creare nel metodo `FindCalculatorServiceAddress` una nuova istanza <xref:System.ServiceModel.Discovery.DiscoveryClient>, passando un elemento <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> al costruttore.  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     In questo modo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene informato del fatto che la classe <xref:System.ServiceModel.Discovery.DiscoveryClient> deve utilizzare l'endpoint di individuazione UDP standard per inviare e ricevere messaggi di individuazione.  
  
8.  Alla riga successiva, chiamare il metodo <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> e specificare un'istanza <xref:System.ServiceModel.Discovery.FindCriteria> che contiene il contratto di servizio che si desiderare cercare. In questo caso specificare `ICalculator`.  
  
    ```csharp  
    // Find ICalculatorService endpoints              
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. Successivamente alla chiamata a <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, verificare se sia disponibile almeno un servizio corrispondente e restituire l'elemento <xref:System.ServiceModel.EndpointAddress> del primo servizio corrispondente. In caso contrario, restituire `null`.  
  
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
  
10. Aggiungere un metodo statico denominato `InvokeCalculatorService` alla classe `Program`.  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     Questo metodo utilizza l'indirizzo endpoint restituito da `FindCalculatorServiceAddress` per chiamare il servizio di calcolo.  
  
11. Creare all'interno del metodo `InvokeCalculatorService` un'istanza della classe `CalculatorServiceClient`. Questa classe viene definita la [indipendente](http://go.microsoft.com/fwlink/?LinkId=145523) esempio. È stata generata utilizzando Svcutil.exe.  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. Alla riga successiva impostare l'indirizzo endpoint del client sull'indirizzo endpoint restituito da `FindCalculatorServiceAddress()`.  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. Immediatamente dopo il codice per il passaggio precedente, chiamare i metodi esposti dal servizio di calcolo.  
  
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
  
14. Aggiungere codice al metodo `Main()` nella classe `Program` per chiamare `FindCalculatorServiceAddress`.  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. Alla riga successiva chiamare `InvokeCalculatorService()` e passare l'indirizzo endpoint restituito da `FindCalculatorServiceAddress()`.  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a>Per eseguire il test dell'applicazione  
  
1.  Aprire un prompt dei comandi con privilegi elevati ed eseguire Service.exe.  
  
2.  Aprire un prompt dei comandi ed eseguire Discoveryclientapp.exe.  
  
3.  L'output di service.exe deve essere analogo all'output indicato di seguito.  
  
    ```Output  
    Received Add(100,15.99)  
    Return: 115.99  
    Received Subtract(100,15.99)  
    Return: 84.01  
    Received Multiply(100,15.99)  
    Return: 1599  
    Received Divide(100,15.99)  
    Return: 6.25390869293308  
    ```  
  
4.  L'output di Discoveryclientapp.exe deve essere analogo all'output indicato di seguito.  
  
    ```Output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato un elenco del codice per questo esempio. Poiché questo codice si basa sul [indipendente](http://go.microsoft.com/fwlink/?LinkId=145523) esempio, sono elencati solo i file che vengono modificati. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Nell'esempio di Host indipendente, vedere [le istruzioni di installazione](http://go.microsoft.com/fwlink/?LinkId=145522).  
  
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

## <a name="see-also"></a>Vedere anche  
 [Panoramica di WCF Discovery](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [Modello a oggetti WCF Discovery](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)
