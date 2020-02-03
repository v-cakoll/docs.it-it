---
title: Esempio di base
ms.date: 03/30/2017
ms.assetid: c1910bc1-3d0a-4fa6-b12a-4ed6fe759620
ms.openlocfilehash: 2ea5af0a1c05b5632632b2619c0ee4813696d2fc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738178"
---
# <a name="basic-sample"></a><span data-ttu-id="0254f-102">Esempio di base</span><span class="sxs-lookup"><span data-stu-id="0254f-102">Basic Sample</span></span>

<span data-ttu-id="0254f-103">In questo esempio viene illustrato come rendere individuabile un servizio e come cercare e chiamare un servizio individuabile.</span><span class="sxs-lookup"><span data-stu-id="0254f-103">This sample shows how to make a service discoverable and how to search for and call a discoverable service.</span></span> <span data-ttu-id="0254f-104">Questo esempio è costituito da due progetti, ovvero il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="0254f-104">This sample is composed of two projects: service and client.</span></span>

> [!NOTE]
> <span data-ttu-id="0254f-105">In questo esempio l'individuazione viene implementata nel codice.</span><span class="sxs-lookup"><span data-stu-id="0254f-105">This sample implements discovery in code.</span></span>  <span data-ttu-id="0254f-106">Per un esempio di implementazione dell'individuazione nella configurazione, vedere [configurazione](../../../../docs/framework/wcf/samples/configuration-sample.md).</span><span class="sxs-lookup"><span data-stu-id="0254f-106">For a sample that implements discovery in configuration, see [Configuration](../../../../docs/framework/wcf/samples/configuration-sample.md).</span></span>

## <a name="service"></a><span data-ttu-id="0254f-107">Service</span><span class="sxs-lookup"><span data-stu-id="0254f-107">Service</span></span>

<span data-ttu-id="0254f-108">Si tratta di una semplice implementazione del servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="0254f-108">This is a simple calculator service implementation.</span></span> <span data-ttu-id="0254f-109">Il codice correlato all'individuazione è disponibile in `Main` dove un oggetto <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> viene aggiunto all'host del servizio e un oggetto <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> viene aggiunto come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0254f-109">The discovery related code can be found in `Main` where a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> is added to the service host and a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> is added as shown in the following code.</span></span>

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new
      WSHttpBinding(), String.Empty);

    // Make the service discoverable over UDP multicast
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());

    serviceHost.Open();
    // ...
}
```

## <a name="client"></a><span data-ttu-id="0254f-110">Client</span><span class="sxs-lookup"><span data-stu-id="0254f-110">Client</span></span>

<span data-ttu-id="0254f-111">Il client usa un oggetto <xref:System.ServiceModel.Discovery.DynamicEndpoint> per individuare il servizio.</span><span class="sxs-lookup"><span data-stu-id="0254f-111">The client uses a <xref:System.ServiceModel.Discovery.DynamicEndpoint> to locate the service.</span></span> <span data-ttu-id="0254f-112"><xref:System.ServiceModel.Discovery.DynamicEndpoint> è un endpoint standard che risolve l'endpoint del servizio all'apertura del client.</span><span class="sxs-lookup"><span data-stu-id="0254f-112">The <xref:System.ServiceModel.Discovery.DynamicEndpoint>, a standard endpoint, resolves the endpoint of the service when the client is opened.</span></span> <span data-ttu-id="0254f-113">In questo caso, <xref:System.ServiceModel.Discovery.DynamicEndpoint> cerca il servizio basato sul contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="0254f-113">In this case, the <xref:System.ServiceModel.Discovery.DynamicEndpoint> looks for the service based on the service contract.</span></span> <span data-ttu-id="0254f-114">Per impostazione predefinita, <xref:System.ServiceModel.Discovery.DynamicEndpoint> esegue la ricerca su <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="0254f-114">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> conducts the search over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> by default.</span></span> <span data-ttu-id="0254f-115">Dopo aver individuato un endpoint del servizio, il client si connette al servizio sull'associazione specificata.</span><span class="sxs-lookup"><span data-stu-id="0254f-115">Once it locates a service endpoint, the client connects to that service over the specified binding.</span></span>

```csharp
public static void Main()
{
   DynamicEndpoint dynamicEndpoint = new DynamicEndpoint( ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());
   // ...
}
```

<span data-ttu-id="0254f-116">Il client definisce un metodo denominato `InvokeCalculatorService` che usa la classe <xref:System.ServiceModel.Discovery.DiscoveryClient> per la ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="0254f-116">The client defines a method called `InvokeCalculatorService` that uses the <xref:System.ServiceModel.Discovery.DiscoveryClient> class to search for services.</span></span> <span data-ttu-id="0254f-117"><xref:System.ServiceModel.Discovery.DynamicEndpoint> eredita da <xref:System.ServiceModel.Description.ServiceEndpoint>, pertanto può essere passato al metodo `InvokeCalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="0254f-117">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> inherits from <xref:System.ServiceModel.Description.ServiceEndpoint>, so it can be passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="0254f-118">Nell'esempio viene quindi usato <xref:System.ServiceModel.Discovery.DynamicEndpoint> per creare un'istanza di `CalculatorServiceClient` e chiamare le varie operazioni del servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="0254f-118">The example then uses the <xref:System.ServiceModel.Discovery.DynamicEndpoint> to create an instance of `CalculatorServiceClient` and calls the various operations of the calculator service.</span></span>

```csharp
static void InvokeCalculatorService(ServiceEndpoint serviceEndpoint)
{
   // Create a client
   CalculatorServiceClient client = new CalculatorServiceClient(serviceEndpoint);

   Console.WriteLine("Invoking CalculatorService");
   Console.WriteLine();

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
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="0254f-119">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="0254f-119">To use this sample</span></span>

1. <span data-ttu-id="0254f-120">Questo esempio usa endpoint HTTP e per eseguirlo è necessario aggiungere elenchi di controllo di accesso (ACL) agli URL appropriati.</span><span class="sxs-lookup"><span data-stu-id="0254f-120">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="0254f-121">Per ulteriori informazioni, vedere [configurazione di http e HTTPS](../feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="0254f-121">For more information, see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="0254f-122">L'esecuzione del comando seguente con privilegi elevati consente di aggiungere gli elenchi di controllo di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="0254f-122">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="0254f-123">È possibile che si desideri sostituire il dominio e il nome utente per gli argomenti seguenti quando il comando non funziona nella forma originale.</span><span class="sxs-lookup"><span data-stu-id="0254f-123">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. <span data-ttu-id="0254f-124">Utilizzando Visual Studio 2012, aprire il. sln di base e compilare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="0254f-124">Using Visual Studio 2012, open the Basic.sln and build the sample.</span></span>

3. <span data-ttu-id="0254f-125">Eseguire l'applicazione service.exe.</span><span class="sxs-lookup"><span data-stu-id="0254f-125">Run the service.exe application.</span></span>

4. <span data-ttu-id="0254f-126">Dopo aver avviato il servizio, eseguire client.exe.</span><span class="sxs-lookup"><span data-stu-id="0254f-126">After the service has started, run the client.exe.</span></span>

5. <span data-ttu-id="0254f-127">Si osservi che il client è stato in grado di trovare il servizio senza conoscerne l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="0254f-127">Observe that the client was able to find the service without knowing its address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0254f-128">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="0254f-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0254f-129">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0254f-129">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="0254f-130">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="0254f-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0254f-131">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="0254f-131">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Basic`
