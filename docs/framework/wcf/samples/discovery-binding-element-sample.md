---
title: Esempio di elemento di associazione di individuazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af513015-85bf-417b-8729-1bdff77ff6d6
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dbbaefbd32048924434342dc3f902c99a3c2448c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="discovery-binding-element-sample"></a><span data-ttu-id="a5f08-102">Esempio di elemento di associazione di individuazione</span><span class="sxs-lookup"><span data-stu-id="a5f08-102">Discovery Binding Element Sample</span></span>
<span data-ttu-id="a5f08-103">In questo esempio viene illustrato come utilizzare l'elemento di associazione del client di individuazione per individuare un servizio.</span><span class="sxs-lookup"><span data-stu-id="a5f08-103">This sample demonstrates how to use the discovery client binding element to discover a service.</span></span> <span data-ttu-id="a5f08-104">Questa funzionalità consente agli sviluppatori di aggiungere un canale client di individuazione allo stack dei canali del client esistente, rendendo il modello di programmazione estremamente intuitivo.</span><span class="sxs-lookup"><span data-stu-id="a5f08-104">This feature enables developers to add a discovery client channel to their existing client channel stack, making the programming model very intuitive.</span></span> <span data-ttu-id="a5f08-105">Quando il canale associato viene aperto, l'indirizzo del servizio viene risolto utilizzando la funzionalità di individuazione.</span><span class="sxs-lookup"><span data-stu-id="a5f08-105">When the associated channel is opened, the address of the service is resolved using discovery.</span></span> <span data-ttu-id="a5f08-106">L'esempio è costituito dai progetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5f08-106">This sample consists of the following projects:</span></span>  
  
-   <span data-ttu-id="a5f08-107">**CalculatorService**: individuabile [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizio.</span><span class="sxs-lookup"><span data-stu-id="a5f08-107">**CalculatorService**: A discoverable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
-   <span data-ttu-id="a5f08-108">**CalculatorClient**: A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applicazione client che utilizza il canale client di individuazione per cercare e chiamare CalculatorService.</span><span class="sxs-lookup"><span data-stu-id="a5f08-108">**CalculatorClient**: A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application that uses the discovery client channel to search for and call the CalculatorService.</span></span>  
  
-   <span data-ttu-id="a5f08-109">**DynamicCalculatorClient**: A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applicazione client che utilizza un endpoint dinamico per cercare e chiamare CalculatorService.</span><span class="sxs-lookup"><span data-stu-id="a5f08-109">**DynamicCalculatorClient**: A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application that uses a dynamic endpoint to search for and call the CalculatorService.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a5f08-110">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a5f08-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a5f08-111">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a5f08-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a5f08-112">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5f08-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a5f08-113">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a5f08-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryBindingElement`  
  
## <a name="calculatorservice"></a><span data-ttu-id="a5f08-114">CalculatorService</span><span class="sxs-lookup"><span data-stu-id="a5f08-114">CalculatorService</span></span>  
 <span data-ttu-id="a5f08-115">Questo progetto contiene un servizio calcolatrice semplice che implementa il contratto `ICalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="a5f08-115">This project contains a simple calculator service that implements the `ICalculatorService` contract.</span></span>  
  
 <span data-ttu-id="a5f08-116">Il file App.config seguente viene utilizzato per aggiungere un comportamento `<serviceDiscovery>` nei comportamenti del servizio, nonché l'endpoint di individuazione.</span><span class="sxs-lookup"><span data-stu-id="a5f08-116">The following App.config file is used to add a `<serviceDiscovery>` behavior in the service behaviors as well as the discovery endpoint.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">  
        <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <!--Enable discovery through configuration.-->  
      <serviceBehaviors>  
        <behavior name="CalculatorBehavior">  
          <serviceDiscovery>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="a5f08-117">Il servizio e gli endpoint corrispondenti vengono in tal modo resi individuabili.</span><span class="sxs-lookup"><span data-stu-id="a5f08-117">This makes the service and its endpoints discoverable.</span></span> <span data-ttu-id="a5f08-118">CalculatorService è un servizio indipendente che aggiunge un endpoint utilizzando l'associazione NetTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="a5f08-118">The CalculatorService is a self-hosted service that adds one endpoint using the NetTcpBinding binding.</span></span> <span data-ttu-id="a5f08-119">Aggiunge inoltre `EndpointDiscoveryBehavior` all'endpoint e specifica un ambito, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a5f08-119">It also adds an `EndpointDiscoveryBehavior` to the endpoint and specifies a scope as shown in the following code.</span></span>  
  
```  
// Add a NET.TCP endpoint and add a scope to that endpoint.  
ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new NetTcpBinding(), netTcpAddress);  
EndpointDiscoveryBehavior netTctEndpointBehavior = new EndpointDiscoveryBehavior();  
netTctEndpointBehavior.Scopes.Add(new Uri("ldap:///ou=engineering,o=exampleorg,c=us"));  
netTcpEndpoint.Behaviors.Add(netTctEndpointBehavior);  
serviceHost.Open();  
```  
  
## <a name="calculatorclient"></a><span data-ttu-id="a5f08-120">CalculatorClient</span><span class="sxs-lookup"><span data-stu-id="a5f08-120">CalculatorClient</span></span>  
 <span data-ttu-id="a5f08-121">Questo progetto contiene un'implementazione client che invia messaggi a CalculatorService.</span><span class="sxs-lookup"><span data-stu-id="a5f08-121">This project contains a client implementation that sends messages to the CalculatorService.</span></span> <span data-ttu-id="a5f08-122">Questo programma utilizza il metodo `CreateCustomBindingWithDiscoveryElement()` per creare un'associazione personalizzata che utilizza il canale client di individuazione.</span><span class="sxs-lookup"><span data-stu-id="a5f08-122">This program uses the `CreateCustomBindingWithDiscoveryElement()` method to create a custom binding that uses the Discovery Client Channel.</span></span>  
  
```  
static CustomBinding CreateCustomBindingWithDiscoveryElement()  
 {  
      DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
            // Provide the search criteria and the endpoint over which the probe is sent  
            discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
            discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
            CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
            // Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
            // An exception is thrown if this binding element is not at the top  
            customBinding.Elements.Insert(0, discoveryBindingElement);  
  
            return customBinding; }  
```  
  
 <span data-ttu-id="a5f08-123">Dopo aver creato un'istanza di <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, lo sviluppatore specifica i criteri da utilizzare durante la ricerca di un servizio.</span><span class="sxs-lookup"><span data-stu-id="a5f08-123">After the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> is instantiated, the developer specifies the criteria to use when searching for a service.</span></span> <span data-ttu-id="a5f08-124">In questo caso, il criterio di ricerca dell'individuazione è il tipo `ICalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="a5f08-124">In this case, the discovery find criterion is the `ICalculatorService` type.</span></span> <span data-ttu-id="a5f08-125">Lo sviluppatore specifica inoltre un oggetto <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> che restituisce un oggetto <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> che specifica la posizione in cui eseguire la ricerca dei servizi.</span><span class="sxs-lookup"><span data-stu-id="a5f08-125">Additionally, the developer specifies a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> which returns a <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> that specifies where to look for the services.</span></span> <span data-ttu-id="a5f08-126"><xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> restituisce una nuova istanza di <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="a5f08-126">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> returns a new <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instance.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="a5f08-127">[Utilizzando un'associazione personalizzata con il canale Client di individuazione](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md).</span><span class="sxs-lookup"><span data-stu-id="a5f08-127"> [Using a Custom Binding with the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md).</span></span>  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
    // to the DiscoveryClientBindingElement. The Discovery ClientChannel   
    // uses this endpoint to send Probe message.  
    public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
    {  
        public override DiscoveryEndpoint GetDiscoveryEndpoint()  
        {  
            return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
        }  
    }  
```  
  
 <span data-ttu-id="a5f08-128">In questo caso, il client utilizza il meccanismo UDP multicast definito dal protocollo di individuazione per la ricerca dei servizi nella subnet locale.</span><span class="sxs-lookup"><span data-stu-id="a5f08-128">In this case, the client uses the UDP multicast mechanism defined by the Discovery protocol to search for services on the local subnet.</span></span> <span data-ttu-id="a5f08-129">La restante parte del metodo crea un'associazione personalizzata e inserisce l'elemento di associazione dell'individuazione in cima allo stack.</span><span class="sxs-lookup"><span data-stu-id="a5f08-129">The remainder of the method creates a custom binding and inserts the Discovery binding element at the top of the stack.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5f08-130">È necessario posizionare <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> in cima allo stack dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="a5f08-130">The <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must be placed on the top of the binding stack.</span></span> <span data-ttu-id="a5f08-131">È necessario che qualsiasi <xref:System.ServiceModel.Channels.BindingElement> posto in cima a <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> verifichi che la channel factory o il canale creato non utilizzi la proprietà `EndpointAddress` o `Via`, poiché l'indirizzo effettivo viene trovato solo in corrispondenza del canale client di individuazione.</span><span class="sxs-lookup"><span data-stu-id="a5f08-131">Any <xref:System.ServiceModel.Channels.BindingElement> on top of <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must make sure that the channel factory or channel it creates does not use the `EndpointAddress` or `Via` properties, because the actual address is found only at the Discovery client channel.</span></span>  
  
 <span data-ttu-id="a5f08-132">È quindi possibile creare un'istanza di `CalculatorClient` attraverso il passaggio di questa associazione personalizzata e di un indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="a5f08-132">Next, the `CalculatorClient` can be instantiated by passing in this custom binding as well as an endpoint address.</span></span>  
  
```  
CalculatorServiceClient client = new CalculatorServiceClient(CreateCustomBindingWithDiscoveryElement(), DiscoveryClientBindingElement.DiscoveryEndpointAddress);  
```  
  
 <span data-ttu-id="a5f08-133">Quando si utilizza il canale client di individuazione, viene passato l'indirizzo dell'endpoint costante specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a5f08-133">When using the Discovery Client Channel, the constant endpoint address specified previously is passed in.</span></span> <span data-ttu-id="a5f08-134">Quindi, in fase di esecuzione, il canale client di individuazione trova il servizio specificato dai criteri di ricerca e vi si connette.</span><span class="sxs-lookup"><span data-stu-id="a5f08-134">Now at runtime, the Discovery Client Channel finds the service specified by the find criteria and connects to it.</span></span> <span data-ttu-id="a5f08-135">Affinché il servizio e il client stabiliscano una connessione, è inoltre necessario che dispongano dello stesso stack dell'associazione sottostante.</span><span class="sxs-lookup"><span data-stu-id="a5f08-135">For the service and the client to establish a connection, they must also have the same underlying binding stack.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a5f08-136">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="a5f08-136">To use this sample</span></span>  
  
1.  <span data-ttu-id="a5f08-137">Aprire la soluzione in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5f08-137">Open the solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="a5f08-138">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="a5f08-138">Build the solution.</span></span>  
  
3.  <span data-ttu-id="a5f08-139">Eseguire l'applicazione di servizio e ognuna delle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="a5f08-139">Run the service application and each of the client applications.</span></span>  
  
4.  <span data-ttu-id="a5f08-140">Si osservi che il client è stato in grado di trovare il servizio senza conoscerne l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="a5f08-140">Observe that the client was able to find the service without knowing its address.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f08-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5f08-141">See Also</span></span>
