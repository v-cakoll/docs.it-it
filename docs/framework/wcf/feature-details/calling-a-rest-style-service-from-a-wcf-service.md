---
title: Chiamata di un servizio in stile REST da un servizio WCF
ms.date: 03/30/2017
ms.assetid: 77df81d8-7f53-4daf-8d2d-bf7996e94d5a
ms.openlocfilehash: c2a3467fb5fe28194dcb8ee7715353f4cb6a1bff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62048218"
---
# <a name="calling-a-rest-style-service-from-a-wcf-service"></a><span data-ttu-id="eed0d-102">Chiamata di un servizio in stile REST da un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="eed0d-102">Calling a REST-style service from a WCF service</span></span>

<span data-ttu-id="eed0d-103">Quando si chiama un servizio in stile REST da un normale un servizio WCF (basato su SOAP), il contesto dell'operazione sul metodo del servizio (contenente le informazioni sulla richiesta in entrata) sostituisce il contesto che deve essere utilizzato dalla richiesta in uscita.</span><span class="sxs-lookup"><span data-stu-id="eed0d-103">When calling a REST-style service from a regular (SOAP-based) WCF service, the operation context on the service method (which contains information about the incoming request) overrides the context which should be used by the outgoing request.</span></span> <span data-ttu-id="eed0d-104">Ciò determina la modifica delle richieste HTTP GET in richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="eed0d-104">This causes HTTP GET requests to change to HTTP POST requests.</span></span> <span data-ttu-id="eed0d-105">Per forzare il servizio WCF a utilizzare il giusto contesto per chiamare il servizio in stile REST, creare un nuovo oggetto <xref:System.ServiceModel.OperationContextScope> e chiamare il servizio in stile REST dall'ambito del contesto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="eed0d-105">To force the WCF service to use the right context for calling the REST-style service, create a new <xref:System.ServiceModel.OperationContextScope> and call the REST-style service from inside the operation context scope.</span></span> <span data-ttu-id="eed0d-106">In questo argomento viene descritto come creare un semplice esempio che illustra questa tecnica.</span><span class="sxs-lookup"><span data-stu-id="eed0d-106">This topic will describe how to create a simple sample that illustrates this technique.</span></span>

## <a name="define-the-rest-style-service-contract"></a><span data-ttu-id="eed0d-107">Definire il contratto del servizio in stile REST</span><span class="sxs-lookup"><span data-stu-id="eed0d-107">Define the REST-style service contract</span></span>

<span data-ttu-id="eed0d-108">Definire un semplice contratto del servizio in stile REST:</span><span class="sxs-lookup"><span data-stu-id="eed0d-108">Define a simple  REST-style service contract:</span></span>

```csharp
[ServiceContract]
public interface IRestInterface
{
    [OperationContract, WebGet]
    int Add(int x, int y);

    [OperationContract, WebGet]
    string Echo(string input);
}
```

## <a name="implement-the-rest-style-service-contract"></a><span data-ttu-id="eed0d-109">Implementare il contratto del servizio in stile REST</span><span class="sxs-lookup"><span data-stu-id="eed0d-109">Implement the REST-style service contract</span></span>

<span data-ttu-id="eed0d-110">Implementare il contratto del servizio in stile REST:</span><span class="sxs-lookup"><span data-stu-id="eed0d-110">Implement the REST-style service contract:</span></span>

```csharp
public class RestService : IRestInterface
{
    public int Add(int x, int y)
    {
        return x + y;
    }

    public string Echo(string input)
    {
        return input;
    }
}
```

## <a name="define-the-wcf-service-contract"></a><span data-ttu-id="eed0d-111">Definire il contratto di servizio WCF</span><span class="sxs-lookup"><span data-stu-id="eed0d-111">Define the WCF service contract</span></span>

<span data-ttu-id="eed0d-112">Definire un contratto di servizio WCF che verrà utilizzato per chiamare il servizio in stile REST:</span><span class="sxs-lookup"><span data-stu-id="eed0d-112">Define a WCF service contract  that will be used to call the REST-style service:</span></span>

```csharp
[ServiceContract]
public interface INormalInterface
{
    [OperationContract]
    int CallAdd(int x, int y);

    [OperationContract]
    string CallEcho(string input);
}
```

## <a name="implement-the-wcf-service-contract"></a><span data-ttu-id="eed0d-113">Implementare il contratto di servizio WCF</span><span class="sxs-lookup"><span data-stu-id="eed0d-113">Implement the WCF service contract</span></span>

<span data-ttu-id="eed0d-114">Implementare il contratto di servizio WCF:</span><span class="sxs-lookup"><span data-stu-id="eed0d-114">Implement the WCF service contract:</span></span>

```csharp
public class NormalService : INormalInterface
{
    static MyRestClient client = new MyRestClient(RestServiceBaseAddress);
    public int CallAdd(int x, int y)
    {
        return client.Add(x, y);
    }

    public string CallEcho(string input)
    {
        return client.Echo(input);
    }
}
```

## <a name="create-the-client-proxy-for-the-rest-style-service"></a><span data-ttu-id="eed0d-115">Creare il proxy client per il servizio in stile REST</span><span class="sxs-lookup"><span data-stu-id="eed0d-115">Create the client proxy for the REST-style service</span></span>

<span data-ttu-id="eed0d-116">Usando <xref:System.ServiceModel.ClientBase%601> per implementare il proxy client.</span><span class="sxs-lookup"><span data-stu-id="eed0d-116">Using <xref:System.ServiceModel.ClientBase%601> to implement the client proxy.</span></span> <span data-ttu-id="eed0d-117">Per ogni metodo chiamato, un nuovo oggetto <xref:System.ServiceModel.OperationContextScope> viene creato e utilizzato per chiamare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="eed0d-117">For each method called, a new <xref:System.ServiceModel.OperationContextScope> is created and used to call the operation.</span></span>

```csharp
public class MyRestClient : ClientBase<IRestInterface>, IRestInterface
{
    public MyRestClient(string address)
        : base(new WebHttpBinding(), new EndpointAddress(address))
    {
        this.Endpoint.Behaviors.Add(new WebHttpBehavior());
    }

    public int Add(int x, int y)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Add(x, y);
        }
    }

    public string Echo(string input)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Echo(input);
        }
    }
}
```

## <a name="host-and-call-the-services"></a><span data-ttu-id="eed0d-118">Ospitare e chiamare i servizi</span><span class="sxs-lookup"><span data-stu-id="eed0d-118">Host and call the services</span></span>

<span data-ttu-id="eed0d-119">Ospitare entrambi i servizi in un'applicazione console, aggiungendo gli endpoint e i comportamenti necessari.</span><span class="sxs-lookup"><span data-stu-id="eed0d-119">Host both services in a console app, adding the needed endpoints and behaviors.</span></span> <span data-ttu-id="eed0d-120">Quindi, chiamare il servizio WCF normale:</span><span class="sxs-lookup"><span data-stu-id="eed0d-120">And then call the regular WCF service:</span></span>

```csharp
public static void Main()
{
    ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));
    restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());
    restHost.Open();

    ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));
    normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");
    normalHost.Open();

    Console.WriteLine("Hosts opened");

    ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));
    INormalInterface proxy = factory.CreateChannel();

    Console.WriteLine(proxy.CallAdd(123, 456));
    Console.WriteLine(proxy.CallEcho("Hello world"));
}
```

## <a name="complete-code-listing"></a><span data-ttu-id="eed0d-121">Elenco codice completo</span><span class="sxs-lookup"><span data-stu-id="eed0d-121">Complete code listing</span></span>

<span data-ttu-id="eed0d-122">Di seguito è riportato un elenco completo dell'esempio implementato in questo argomento:</span><span class="sxs-lookup"><span data-stu-id="eed0d-122">The following is a complete listing of the sample implemented in this topic:</span></span>

```csharp
public class CallingRESTSample
{
    static readonly string RestServiceBaseAddress = "http://" + Environment.MachineName + ":8008/Service";
    static readonly string NormalServiceBaseAddress = "http://" + Environment.MachineName + ":8000/Service";

    [ServiceContract]
    public interface IRestInterface
    {
        [OperationContract, WebGet]
        int Add(int x, int y);
        [OperationContract, WebGet]
        string Echo(string input);
    }

    [ServiceContract]
    public interface INormalInterface
    {
        [OperationContract]
        int CallAdd(int x, int y);
        [OperationContract]
        string CallEcho(string input);
    }

    public class RestService : IRestInterface
    {
        public int Add(int x, int y)
        {
            return x + y;
        }

        public string Echo(string input)
        {
            return input;
        }
    }

    public class MyRestClient : ClientBase<IRestInterface>, IRestInterface
    {
        public MyRestClient(string address)
            : base(new WebHttpBinding(), new EndpointAddress(address))
        {
            this.Endpoint.Behaviors.Add(new WebHttpBehavior());
        }

        public int Add(int x, int y)
        {
            using (new OperationContextScope(this.InnerChannel))
            {
                return base.Channel.Add(x, y);
            }
        }

        public string Echo(string input)
        {
            using (new OperationContextScope(this.InnerChannel))
            {
                return base.Channel.Echo(input);
            }
        }
    }

    public class NormalService : INormalInterface
    {
        static MyRestClient client = new MyRestClient(RestServiceBaseAddress);
        public int CallAdd(int x, int y)
        {
            return client.Add(x, y);
        }

        public string CallEcho(string input)
        {
            return client.Echo(input);
        }
    }

    public static void Main()
    {
        ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));
        restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());
        restHost.Open();

        ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));
        normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");
        normalHost.Open();

        Console.WriteLine("Hosts opened");

        ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));
        INormalInterface proxy = factory.CreateChannel();

        Console.WriteLine(proxy.CallAdd(123, 456));
        Console.WriteLine(proxy.CallEcho("Hello world"));
    }
}
```

## <a name="see-also"></a><span data-ttu-id="eed0d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eed0d-123">See also</span></span>

- [<span data-ttu-id="eed0d-124">Procedura: Creare un servizio HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="eed0d-124">How to: Create a Basic WCF Web HTTP Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)
- [<span data-ttu-id="eed0d-125">Modello a oggetti per la programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="eed0d-125">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)
